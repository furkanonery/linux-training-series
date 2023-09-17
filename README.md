# linux-course

## linux-course 101

1. Mevcut oturum açan kullanıyı görüntülemek:
    ```
    whoami
    ```
2. Sistem özelliklerini görüntülemek:
    ```
    uname -a
    ```
3. Bir web sayfasına ping atmak:
    ```
    ping -c4 ubuntu.com
    ```
4. Şu anki tarih ve zamanı görüntülemek:
    ```
    date
    ```
5. Bulunulan dizindeki dosya ve dizinleri görüntülemek(gizli olanlar da olsun diye -a konur):
    ```
    ls -a
    ```
6. Bulunulan dizinin adresini almak:
    ```
    pwd
    ```
7. Bir dizinin içine girmek:
    ```
    cd Desktop
    ```
8. Bir dizinin içine girmek:
    ```
    cd Desktop
    ```
9. Kullanıcı kılavuzunu görüntülemek:
    ```
    man ls
    ```
10. Komut geçmişini görüntülemek:
    ```
    history
    ```
<hr>

* Linux'ta her şey bir dosyadır.
* Dosyalar(-) Dizinler(d) Bağlantılar(l)

![Dizin açıklamaları](<Screenshot from 2023-09-09 14-59-51.png>)

#### Dizin ve Dosya işlemleri:

* Dizin ve Dosyaları listelemek(Gizli dosyaların da gelmesi için -a ekliyoruz):
    ```
    ls -a
    ```

* Ayrıntılı listelemek:
    ```
    ls -al
    ```

* Dizinin içine girmek(cd -> change directory):
    ```
    cd Desktop
    ```

* Dizin oluşturmak ve silmek:
    ```
    mkdir SampleDirectory
    ```
    ```
    rmdir SampleDirectory
    ```

* İçindeki dosyalarla beraber silmek:
    ```
    rm -r SampleDirectory
    ```

* Dosya ve dizinleri kopyalamak:
    ```
    cp file.txt new_file.txt
    ```

* Bir üst dizine dosya kopyalamak:
    ```
    cp file.txt ../
    ```

* Dosyaları taşımak:
    ```
    mv test.txt ../dir2/
    ```

* Dosyaların ismini değiştirmek:
    ```
    mv test.txt ../dir2/test2.txt
    ```

* Dizinlerin ismini değiştirmek:
    ```
    mv testFolder1/ testFolder2/
    ```

* Dosya ve dizinleri arşivlemek:
    ```
    tar -zcvf archive.tar file1.txt file2.pdf
    ```

    ```
    tar -zcvf archive.tar folder1/ folder2/
    ```
* Arşivi listelemnek:
    ```
    tar -zxvf archive.tar
    ```
* Dosyaları canlı izlemek:
    ```
    tail -f -n10 /var/log/postgresql/postgresql-15-main.log
    ```

* Dosyanın sonuna satır eklemek:
    ```
    echo "test line" >> test.txt
    ```

* Terminal ekranına sığmayan dosyaların görünümü:
    ```
    more test.txt
    ```

* Boş olmayan satırların başına satır numarası eklemek:
    ```
    nl test.txt
    ```

* Dosyalar hakkında bilgi almak:
    ```
    file test.txt
    ```

* Dosyanın satır sayısı, kelime sayısı ve byte cinsinden büyüklüğünü almak:
    ```
    wc test.txt
    ```
* Dosyayı sıralı şekilde açmak
    ```
    sort -k test.txt
    ```
* Dosya içinde kelime araması yapmak:
    ```
    grep "Google" test.txt
    ```
<hr>

## linux-course 201

1. Herhangi bir dosya uzantısına sahip dosyaları listelemek:
    ```
    ls *.html
    ```
2. İçinde herhangi bir kelime geçen dosyaları listelemek:
    ```
    ls *test*
    ```
3. Herhangi tek bir harfi gözardı edip(?) geriye kalan karakterlerle uyuşan dosyaları listelemek:
    ```
    ls qwerty?asdfg
    ```
4. Herhangi bir karaktere gelebilecek değerleri belirtmek:
    ```
    ls asdf[tyug]*.txt
    ```

5. Bir komutun çıktısını bir dosyaya yazdırmak:
    ```
    pip3 freeze > requirements.txt
    ```

6. Bir komutun çıktısını bir dosyanın sonuna yazdırmak:
    ```
    cat test1.txt >> test2.txt
    ```

7. Pipe kullanımı:
    * pipe'tan önceki çıktı üzerinden kelime araması yapıyor ve bulduğu satırları çıktı olarak veriyor.
    ```
    ls -l | grep search_word
    ```
    * Görüntülemek istediğimiz dosyanın ilk 10 satırını alfabetik olarak getirmek:
    ```
    cat test.txt | sort | head -n10
    ```
8. Alias komutu:
    * Çok sık kullandığımız uzun komutlar varsa bunları her seferinde yazmak yerine o uzun komuta bir takma ad verebiliriz.
    ```
    alias pipinstall='pip3 install -r requirements.txt'
    ```
    * Eşittir işaretinin yanlarında boşluk olmamalı

#### Kullanıcı ve Grup Kavramları

1. Kullanıcı listesi görüntüleme:
    ```
    cat /etc/passwd
    ```
2. Kullanıcı parolalarını görüntülemek(hash kodu):
    ```
    sudo cat /etc/shadow
    ```
3. Kullanıcı eklemek:
    ```
    sudo useradd <username>
    ```
3. Kullanıcı parolası değiştirmek:
    ```
    sudo passwd <username>
    ```
4. Ayrıntılı bilgilerle kullanıcı eklemek:
    ```
    sudo adduser <username>
    ```
5. Kullanıcı silmek:
    * Bilgilendirme mesajı verir:
    ```
    sudo deluser <username>
    ```
    * Bilgilendirme mesajı vermez:
    ```
    sudo userdel <username>
    ```
6. Grupları listelemek:
    ```
    cat /etc/group
    ```
7. Grup eklemek:
    ```
    sudo addgroup <group_name>
    ```
8. Grup silmek:
    ```
    sudo delgroup <group_name>
    ```
9. Kullanıcları herhangi bir gruba dahil etmek:
    ```
    sudo usermod -a -G <group_name> <username>
    ```
![İzin Açıklamaları](<Screenshot from 2023-09-11 12-54-43.png>)

![Dosya İzin Açıklamaları](<Screenshot from 2023-09-11 12-56-52.png>)

* Dosya ve dizinlerde sahiplik görüntüleme:
    * input
        ```
        ll
        ```

    * output
        ```
        drwxr-xr-x  2 fk   fk    4096 Eyl  8 04:26  Desktop/
        ```
    * Yukarıdaki ilk sütundaki ilk karakter bize "dosya mı ya da dizin mi" bilgisini veriyor, sonraki üç karakter da dizine sahip kullanıcıya verilen izinleri gösteriyor. Ortadaki üç karakter ise dizin grup izinlerini, son üç karakter ise herkese açık izin bilgisini gösteriyor.

* Dosya ve dizinlerin sahibini değiştirme:
    ```
    sudo chown <new_owner_username> <file_or_dir_name>
    ```

* Dosya ve dizinlerin grubunu değiştirme:
    ```
    sudo chgrp <new_group_name> <file_or_dir_name>
    ```

* Dosya ve dizinlerin sahibini toplu halde değiştirme:
    ```
    sudo chown <new_owner_username> <file_or_dir_name> <file_or_dir_name> <file_or_dir_name>
    ```
* Dosya ve dizinlerin grubunu Toplu şekilde değiştirme:
    ```
    sudo chgrp <new_group_name> <file_or_dir_name> <file_or_dir_name> <file_or_dir_name>
    ```

* Bir dizinin sahipliğini ya da grubunu değiştirdiğimiz zaman dizin içinde sahiplik ve gruplar değişmiyor, bunun için ek bir işlev var:

    * Kullanıcı
        ```
        sudo chown -R <new_owner_username> <dir_name>
        ```

    * Grup
        ```
        sudo chgrp -R <new_group_name> <dir_name>
        ```

* Bir dizindeki belirli bir sahipliği başkasına aktarmak:
    ```
    sudo chown -R old_group_name:new_group_name *
    ```
#### Dosya ve Dizin İzin Hesaplamaları:

|     Read     |     Write     |   Executable  |
| ------------ | ------------- | ------------- |
| 2<sup>2</sup>| 2<sup>1</sup> | 2<sup>0</sup> |

Örneğin bir kullanıcı için bir dosyaya hem okuma hem yazma hem de çalıştırma izni verilmişse:
* 2<sup>2</sup> + 2<sup>1</sup> + 2<sup>0</sup> = 7 olur.

Yani 7'nin anlamı tüm izinlere sahiptir anlamına geliyor.

* Örnek: İzin bilgileri bu şekilde verilmişse: `drwxrwxr-x` ilk karakter `d` olduğu için bunun bir dizin olduğunu anlıyoruz. sonraki üçerli karakterler tek tek hesaplandığında `775` gibi bir sonuç çıkıyor, yani bağlı bulunulan kullanıcı ve gruplar tüm izinlere sahip ama geriye kalan kullanıcılar ise sadece okuma ve çalıştırma yetkisine sahiptir anlamı çıkıyor.

#### Dosya ve Dizinlerin İzinlerini Değiştirmek

* Bir dosya ya da dizinin izinlerini değiştirmek için `chmod` komutunu kullanıyoruz.

    * Tüm kullanıcılara okuma, yazma ve çalıştırma izni vermek.
        ```
        chmod 777 test.txt
        ```

    * Sadece dosya sahibine ve bulunduğu gruplara okuma, yazma ve çalıştırma izni, diğer kullanıcılara sadece okuma izni vermek:
        ```
        chmod 774 test.txt
        ```

## linux-course 301

* Linux'ta çalışan her program bir süreçtir

![Linux Süreçleri](<Screenshot from 2023-09-15 16-54-36.png>)

#### Çalışan Süreçlerle İlgili İşlemler

1. Çalışan süreçleri listelemek:
    ```
    ps -ef
    ```

2. Çalışan süreçleri program adına göre arama yaparak listelemek:
    ```
    ps -ef | grep <process_name>
    ```

3. Tek bir kullanıcıya ait çalışan süreçleri listelemek:
    ```
    ps -au<user>
    ```

4. Çalışan süreçleri ayrıntılı olarak canlı izlemek:

    * İlk olarak htop'u yüklememiz gerekir:
        ```
        sudo apt install htop
        ```

    * Ardından aşağıdaki komutu yazarak htop'u çalıştırabiliriz:
        ```
        htop
        ```

5. Süreçleri sonlandırmak:

    * kill komutuyla:
        ```
        kill <PID>
        ```
    * SIGKILL(9) komutuyla(programı aniden sonlandırır, istenmeyen veri kaybı olabilir):
        ```
        kill -9 <PID>
        ```
    * SIGTERM(15) komutuyla(arkaplanda çalışan işlem varsa, onu toparlayıp öyle kapatır):
        ```
        kill -15 <PID>
        ```
    * Bir programa ait tüm süreçleri sonlandırmak:
        ```
        pkill <program_name>
        ```
#### Servis Yönetimi

6. Servisleri görüntülemek:

    * Sistem üzerindeki servis ünitelerini görüntülemek:
        ```
        systemctl list-units --type service
        ```
    * Servislerin durumunu görüntülemek:
        ```
        systemct status <service_name>
        ```
    * Çalışan bir servisi durdurmak:
        ```
        sudo systemcl stop <service_name>
        ```
    * Durdurulmuş bir servisi başlatmak:
        ```
        sudo systemcl start <service_name>
        ```
    * Çalışan bir servisi yeniden başlatmak:
        ```
        sudo systemcl restart <service_name>
        ```

#### Ağ Bağlantılarıyla İlgili İşlemnler

7. Ağ işlemleri:

    * Bağlantı bilgilerini öğrenmek:
        ```
        ip addr show
        ```
    * IP Adresini öğrenmek:
        ```
        hostname -I
        ```
    * Bağlantı testi için ping atmak:
        ```
        ping github.com
        ```
    * Ping sayısını belirtmek:
        ```
        ping -c 5 github.com
        ```

8. Ağ trafiğini izlemek:
    ```
    sudo tcpdump -v 
    ```

    * Ağ trafiğini özet bir şekilde izlemek:
        ```
        sudo iftop
        ```
    * Ağ bağlantısı üzerinde oluşan trafiğin, paketler bazında Wireshark kullanılarak izlenmesi:
        ```
        sudo wireshark
        ```
9. Dosya indirmek:
    
    * Web sayfalarının `index.html`'ini indirmek:
        ```
        wget https://github.com/
        ```
    * Url üzerinden dosya indirmek:
        ```
        wget https://avatars.githubusercontent.com/u/79539547
        ```

10. SSH kullanılarak uzaktan terminal erişimi:

    ```
    ssh <user>@<ip_address>
    ```

11. SSH sunucusunu kapatmak:

    * Kapatmak:
        ```
        sudo systemctl stop ssh
        ```
    * Otomatik açılmasını önlemek:
        ```
        sudo systemctl disable ssh
        ```

12. DNS sorguları yapmak:

    * Web adresinin dns adresini öğrenmek:
        ```
        nslookup github.com
        ```
    * Web adresinin mail sunucularını öğrenmek:
        ```
        nslookup -query=mx github.com
        ```

    * Web adresinin isim sunucularını öğrenmek:
        ```
        nslookup -query=ns github.com
        ```

## linux-course 401