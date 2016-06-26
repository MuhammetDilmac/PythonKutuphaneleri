# Hashlib

#### Kısa Açıklama
Çeşitli popüler şifreleme algoritmalarını barındıran bir kütüphanedir.

#### Detaylı Açıklama
Öncelikle biraz özet fonksiyonlardan bahsedelim. Özet fonksiyonu bir anahtarsız şifreleme yöntemidir. Yani özet fonksiyonu algoritmaları veriyi tek yönlü olarak işler ve algoritmanın tipine göre özet çıkartır. Çıkarılan özet veriye özeldir. Yani veride meydana gelecek 1 bit değişiklikte bile bu özet değişmektedir. Bu kriptografik özet fonksiyonları dijital imzalar, mesaj doğrulama kodları, manipülasyon tespiti, parmak izi, ileti bütünlük kontrollerinde(checksum) kullanılmaktadır.

Modülümüzü çağıralım.

    import hashlib

Bakalım yukarıda bahsettiğimiz hangi algoritmaları kullanabiliyoruz.

*Çıktı OpenSSL aracılığıyla kullanabileceğiniz algoritmalarla beraber sistemde bulunan algoritmaları vermektedir.*

    print(hashlib.algorithms_available)

    {'md5', 'SHA256', 'sha512', 'MD4', 'md4', 'DSA-SHA', 'dsaEncryption', 'sha1', 'ecdsa-with-SHA1', 'dsaWithSHA', 'SHA384', 'MD5', 'RIPEMD160', 'whirlpool', 'sha', 'SHA224', 'sha256', 'sha384', 'sha224', 'DSA', 'SHA', 'SHA1', 'SHA512', 'ripemd160'}

Çıktıda tekrarlanan algoritmalar bulunmaktadır. Modülde bulunan sabit algoritmaları görmek için ise;
    
    print(hashlib.algorithms_guaranteed)    

    {'sha224', 'sha512', 'sha256', 'md5', 'sha384', 'sha1'}

Şimdi birkaç kullanım ile pekiştirelim.


Öncelikle değişkene istediğimiz bir algoritmayı atayalım.

	example = hashlib.sha512()

Daha sonra stringi içeri alalım.

Bu işlemi **update fonksiyonu** ile gerçekleştiriyoruz. 

	example.update("ornekstring")


Fonksiyon özetimizi almamız için kullanmamız gereken iki özelliğimiz var. Bunlar **digest()** ve **hexdigest()**.

Digest, özetimizi non-ascii olarak döndürürken hexdigest, özetimizi string olarak döndürüyor.

<--*non-ascii*-->

    example = hashlib.md5()
    example.update("icerialinacakstring".encode('utf-8'))
    print(example.digest())

	b'\x9b\xb5z\x03\x9d\x9a\xcf\x1b\xec\x9a \xbd\x87\x92\xdb4\rO\xd9\xbbv\xda\x89\x9a\xd3W\xf3\x07\x1a\x9d\x04g\xe8\xedqE\xff\xc0rx\xb9t}\tt\xad\xd6\xed\xbd#~\xa5\x1f\xd4\x04$\x91\x99\x01kH\xd2\xeb\x0f'

    
<--*string*-->

    print(example.hexdigest())
    
    9bb57a039d9acf1bec9a20bd8792db340d4fd9bb76da899ad357f3071a9d0467e8ed7145ffc07278b9747d0974add6edbd237ea51fd404249199016b48d2eb0f

digest() ve hexdigest() dışında kullanımlarımız da var; bunlardan **copy** özetimizi kopyalamamızı sağlarken **digest_size** ise özetimizin byte boyunu döndürür.

    print(example.digest_size)

	64

#### Konuyla İlgili Faydalı Dökümanlar

- [Merkle–Damgård Yapısı Hakkında Sunu](http://csrc.nist.gov/groups/ST/hash/documents/Puniya_hashDesign.pdf)


- [Güvenli Özet Fonksiyonları  Hakkında Sunu](http://csrc.nist.gov/publications/fips/fips180-2/fips180-2.pdf) 

- [Kriptografik Özet Rehberi](http://www.unixwiz.net/techtips/iguide-crypto-hashes.html) 

#### Kaynakça
- [Hashlib Dökümantasyonu](https://docs.python.org/3.2/library/hashlib.html) 


