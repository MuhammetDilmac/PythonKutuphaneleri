# Pyspriter

#### Kısa Açıklama
Python için yazılmış sprite oluşturma kütüphanesidir.

#### Detaylı Açıklama
pyspriter, Python projelerinizde kullanabileceğiniz bir sprite oluşturma kütüphanesidir. Sprite olarak çıkaracağınız görselleri images/ klasörünün içine yerleştirir, yönünü (sağa, sola, yukarı ve aşağıya doğru) verirsiniz, pyspriter bu görselleri verdiğiniz yöne doğru birleştirerek yeni bir sprite görseli oluşturur.

```python
	from pyspriter import Sprite
	sprite = Sprite("images/", "png", "transparent", "right")
	output = sprite.generate()
	output.save("sprites/my_sprite.png")
```


#### Kaynakça
- [Pyspriter](https://github.com/halilkaya/pyspriter)