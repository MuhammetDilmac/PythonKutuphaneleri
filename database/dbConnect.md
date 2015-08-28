# dbConnect

#### Kısa Açıklama
dbConnect, uygulamanız üzerinden MySQL veritabanınızı kullanmanızı sağlayan bir Python kütüphanesidir.

#### Detaylı Açıklama
dbConnect ile Python'da yazdığınız uygulamanızdan veritabanınıza bağlanabilir, standart Python değişken türlerini kullanarak veritabanına kayıt ekleyebilir, güncelleyebilir, kayıt çekebilirsiniz. Bunlara ek olarak dilerseniz SQL sorgusu da çalıştırabilirsiniz.

```python
	from dbConnect import dbConnect
	# Make connection:
	con, cur = dbConnect.connect()

	# Some code
	cur.execute("select * from listings order by id desc limit 5")

	dbConnect.disconnect(con)
```


#### Kaynakça
- [dbConnect](https://github.com/EmiXLabs/dbConnect)