# Pillow

#### Kısa Açıklama
Pillow, PIL olarak da geçen, Python Image Library kütüphanesidir. Güncel Python sürümlerinde stabil olarak çalışmaktadır.

#### Detaylı Açıklama
Pillow kütüphanesi ile yeni resim dosyaları yaratabilir, varolanları düzenleyebilir, birden fazla resim dosyasını birbiriyle birleştirebilir, resimleri RGB olarak 3 katmana ayırabilir ve daha pek çok işlem yapabilirsiniz. Pillow günümüzdeki popüler jpg, png gibi pek çok resim formatını destekler.
Aşağıda birkaç örnek işlem görebilirsiniz.

```python
	from PIL import Image
    resim = Image.open("dosya/yolu/resim.jpg") # dosyayı belleğe alıyoruz
    resim = resim.rotate(90) # resimi 90 derece döndürüyoruz
    resim.save("yeni/dosya/yolu/yeniresim.png") # dosyayı png formatında kaydediyoruz
```

#### Kaynakça
- [Pillow Resmi Dökümantasyonu](http://pillow.readthedocs.org/)
