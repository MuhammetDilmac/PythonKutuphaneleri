# Pyspriter

#### Kısa Açıklama
Python için yazılmış sprite oluşturma kütüphanesidir.

#### Detaylı Açıklama
Pyspriter, Python projelerinizde kullanabileceğiniz bir sprite oluşturma kütüphanesidir. Sprite olarak çıkaracağınız görselleri images/ klasörünün içine yerleştirir, yönünü (sağa, sola, yukarı ve aşağıya doğru) verirsiniz, pyspriter bu görselleri verdiğiniz yöne doğru birleştirerek yeni bir sprite görseli oluşturur.
Pyspriter, [Pillow](https://github.com/MuhammetDilmac/PythonKutuphaneleri/blob/master/imaging/pillow.md) kütüphanesini kullanır.

```python
	from pyspriter import Sprite
	sprite = Sprite("images/", "png", "transparent", "right")
	output = sprite.generate()
	output.save("sprites/my_sprite.png")
```


#### Kaynakça
- [Pyspriter](https://github.com/halilkaya/pyspriter)