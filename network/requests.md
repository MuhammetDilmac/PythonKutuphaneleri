# Requests

#### Kısa Açıklama
HTTP protokolü ile ilgili işlemlerinizi kolayca yapmanızı sağlayan kütüphanedir. Urllib2'ye göre çok daha kullanışlı ve zahmetsizdir.

#### Detaylı Açıklama
Requests kütüphanesi ile http protokolü üzerinde yani web bağlantılarında kolayca işlemler yapabiliriz. Örnek olarak bir siteye get isteğinde bulunalım ve dönen veriyi json objesi olarak görüntüleyelim.

```python
	import requests
    r = requests.get('https://api.github.com/events')
    r.json()
```

#### Kaynakça
- [Requests Resmi Dökümantasyonu](http://docs.python-requests.org/en/latest/)