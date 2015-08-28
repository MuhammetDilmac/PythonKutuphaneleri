# PrettyTable

#### Kısa Açıklama
PrettyTable, komut satırı programlarında güzel bir tablo çıktısı çıkaran python kütüphanesidir.

#### Detaylı Açıklama
PrettyTable ile tablo şeklinde çıktı alabilirsiniz. İster Python koduyla tablo yaratır, ister .csv dosyasından veya SQL veritabanından tablo alır, ister de HTML kodlarıyla tablo yaratırsınız.

###### Python koduyla tablo yaratmak
Bu şekilde tablo yaratmak için iki yol vardır.Biri satır satır tablo yaratmak:
```python
  from prettytable import PrettyTable

  tablo = PrettyTable(["Sütun 1", "Sütun 2"])
  tablo.align["Sütun 1"] = "l" # Sütun 1'i sola kaydır.
  tablo.padding_width = 1 # Tablo içeriği ve kenarları arasına 1 boşluk koy.
  tablo.add_row(["1 1", "2 1"]) #Tabloya bilgileri satır satır ekle.
  tablo.add_row(["1 2", "2 2"])
  tablo.add_row(["1 3", "2 3"])
  tablo.add_row(["1 4", "2 4"])
  tablo.add_row(["1 5", "2 5"])
  tablo.add_row(["1 6", "2 6"])
  tablo.add_row(["1 7", "2 7"])
  print tablo #Tabloyu komut satırında yazdır.
```
Diğer ise sütun sütun tablo yaratmak:
```python
  from prettytable import PrettyTable

  tablo = PrettyTable()
  tablo.add_column("Sütun 1", ["1 1","1 2","1 3","1 4","1 5","1 6","1 7"])
  tablo.add_column("Sütun 2", ["2 1","2 2","2 3","2 4","2 5","2 6","2 7"])
```

###### HTML koduyla tablo yaratmak
Bu şekilde tablo yaratmak (bana göre) çok kolaydır.Sadece yapmanız gereken HTML tablo kodunu from_html(htmlkodu) şeklinde kullanmanız yeterli olacaktır.
```python
  from prettytable import from_html

  htmlkodu = "<table> <tr> <th>Sütun 1</th><th>Sütun 2</th> </tr> <tr> ..."
  tablo = from_html(htmlkodu)
```

###### .csv dosyasından tablo almak
Eğer tablonuzu bir .csv dosyası şeklinde oluşturmuşsanız ve bir daha Python koduyla oluşturmaya uğraşmak istemiyorsanız şu şekilde .csv dosyasını açarak bir tablo olarak yazdırabilirsiniz:
```python
  from prettytable import from_csv

  csvdosya = open("tablo.csv", "r")
  tablo = from_csv(csvdosya)
  csvdosya.close() # Dosyayı kapatmayı unutmayın.
```

###### SQL veritabanından bilgi alarak tablo oluşturmak
Eğer bir SQL veritabanına bilgilerinizi kaydetmişseniz basit bir SELECT komutuyla bu bilgilerden bir tablo yaratabilirsiniz.
```python
  # db_cur, veritabanınız için bir imleç objesidir.
  from prettytable import from_db_cursor

  db_cur.execute("SELECT * FROM tablom")
  tablo = from_db_cursor(db_cur)
```

#### Kaynakça
- [PrettyTable Dökümantasyonu](https://code.google.com/p/prettytable/wiki/Tutorial) 
