# PYCURL

#### Kısa Açıklama
cURL işlemlerinin python ile yapılabilmesi için hazırlanmış bir kütüphane.

#### Detaylı Açıklama
pycurl, libcurl için arayüz paketidir. FTP, FTPS, HTTP, HTTPS, GOPHER, TELNET, DICT, FILE and LDAP yanı sıra HTTPS sertifikaları, HTTP POST, HTTP PUT, FTP uploads, proxies, cookies, basic authentication ve dahasını desteklemektedir.

	import pycurl
	try:
	    # python 3
	    from urllib.parse import urlencode
	except ImportError:
	    # python 2
	    from urllib import urlencode

	c = pycurl.Curl()
	c.setopt(c.URL, 'http://pycurl.sourceforge.net/tests/testpostvars.php')

	post_data = {'field': 'value'}
	# Form data must be provided already urlencoded.
	postfields = urlencode(post_data)
	# Sets request method to POST,
	# Content-Type header to application/x-www-form-urlencoded
	# and data to send in request body.
	c.setopt(c.POSTFIELDS, postfields)

	c.perform()
	c.close()


#### Kaynakça
- [PYCURL Web Sitesi](http://pycurl.sourceforge.net/doc/index.html) 