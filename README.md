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
5. Bulunulan dizindeki dosya ve klasörleri görüntülemek(gizli olanlar da olsun diye -a konur):
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

11. Klasör ve Dosya işlemleri:

* Klasör ve Dosyaları listelemek(Gizli dosyaların da gelmesi için -a ekliyoruz):
    ```
    ls -a
    ```

* Ayrıntılı listelemek:
    ```
    ls -al
    ```

* Klasörün içine girmek(cd -> change directory):
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

* Dosya ve klasörleri kopyalamak:
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

* Klasörlerin ismini değiştirmek:
    ```
    mv testFolder1/ testFolder2/
    ```

* Dosya ve klaörleri arşivlemek:
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

## linux-course 201

## linux-course 301

## linux-course 401