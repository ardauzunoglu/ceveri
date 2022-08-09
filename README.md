![ÇeVeri](https://raw.githubusercontent.com/ardauzunoglu/ceveri/main/readme/ceveri-readme.png)

ÇeVeri, yoğunlukla **Batı dilleri** ekseninde toplanmış metin temelli veri setlerinin **Türkçe’ye kazandırılmasını** ve böylece geliştiricilerin yaşadığı en büyük sorunlardan biri olan **Türkçe veri eksikliğinin önüne geçilmesini** amaçlayan bir makine çevirisi aracıdır. 

[ceveri.herokuapp.com](https://ceveri.herokuapp.com)

# README.md İçeriği

[ÇeVeri Kütüphanesi](#çeveri-kütüphanesi) <br>
[ÇeVeri Websitesi](#çeveri-websitesi) <br>
[ÇeVeri Dokümantasyonu](#çeveri-dokümantasyonu) <br>
[ÇeVeri Klasik Veri Setleri](#çeveri-klasik-veri-setleri) <br>
[Demo](#demo) <br>
[Geliştirmeye Yönelik Hedefler](#geliştirmeye-yönelik-hedefler) <br>
[Geliştirici Ekip](#geliştirici-ekip) <br>

# ÇeVeri Kütüphanesi
### Kurulum
ÇeVeri Python kütüphanesini kullanmak için pip kullanabilirsiniz:
```
!pip install ceveri
```
En çok sayıda uzantıyı, en optimize biçimde çevirebilmek için son sürümü kurabilirsiniz:
```
!pip install ceveri==1.0.3
```
### Kullanım
ÇeVeri kütüphanesi tek bir ana fonksiyondan ve bu fonksiyonun alt fonksiyonlarından faydalanmaktadır.

Örnek kullanım:
```python
from ceveri import cevir
cevir("D:/files/ingilizce_dosya.json", "D:/files/cevrilmis_dosya.json", "en")
```
Çıktı:
```
Çeviri işlemi başladı.
Dosya başarıyla çevrildi.
İşlem süresi: 304.320070028305 saniye.
Çevrilen dosyaya D:/files/cevrilmis_dosya.json adresinden erişebilirsiniz.
```

<br>

Bir diğer örnek kullanım:
```python
from ceveri import cevir
cevir("D:/files/rusca_dosya.txt", "D:/files/turkce_dosya.txt")
```
Çıktı:
```
Çeviri işlemi başladı.
Dosya başarıyla çevrildi.
İşlem süresi: 275.215596311885 saniye.
Çevrilen dosyaya D:/files/turkce_dosya.txt adresinden erişebilirsiniz.
```

[pypi.org/project/ceveri/](https://pypi.org/project/ceveri/)

# ÇeVeri Websitesi
### Gereksinimler 
ÇeVeri websitesini kendi cihazınızda çalıştırmak isterseniz repository'u klonlayıp aşağıdaki komutu çalıştırabilirsiniz.
```
!pip install -r requirements.txt
```
Gerekli kütüphanelerin kurulumu gerçekleştikten sonra app.py dosyasındaki dosya yollarını değiştirerek ÇeVeri websitesini kullanmaya başlayabilirsiniz.

### ÇeVeri Websitesi Çalışma Akışı
![ÇeVeri Çalışma Akışı](https://raw.githubusercontent.com/ardauzunoglu/ceveri/main/readme/calisma-akisi.png)

ÇeVeri websitesi frontend'de HTML5, CSS3 ve JavaScript kullanırken backend'de Python'ın Flask kütüphanesinden faydalanmaktadır. Kullanıcının yüklediği dosyalar boto3 kütüphanesi kullanılarak Amazon Web Services (AWS)'in ilk 5GB için ücretsiz sunduğu S3 platformunda depolanmaktadır. S3'e senkronize edilen dosyalara boto3 kütüphanesi aracılığı ile erişilmekte ve dosyada yer alan metinler googletrans kütüphanesi aracılığıyla Google Translate kullanılarak çevrilmektedir. Çevrilen dosya S3'te depolanıp S3 üzerinden kullanıcıya aktarılmaktadır. Tüm bu çalışma akışı, repository'deki app.py dosyası ve templates klasörü altındaki .html dosyaları üzerinden yürümekte olup Heroku platformuna deploy edilmiştir.

### ÇeVeri Websitesi Kullanım Rehberi
**Adım 1**: Ana sayfaya gidin.<br>
[ceveri.herokuapp.com](https://ceveri.herokuapp.com) adresi üzerinden ana sayfaya gidin.

**Adım 2**: Çevirmek istediğiniz dosyayı yükleyin.<br>
**Browse** butonunu kullanarak yüklemek istediğiniz dosyayı bulun ve yükleyin.

**Adım 3**: Bekleyin.<br>
Yüklemiş olduğunuz dosyanın boyutuna ve uzantısına göre çeviri işlemleri **3 saniye ile 10 dakika** arasında sürebilmektedir. Eğer yüklediğiniz dosyanın boyutu büyükse bir süre beklemeniz gerekebilir.

**Adım 4**: Çevrilen dosyayı indirin.
Çeviri sonrası ekrana gelen arayüzde yer alan "dosyayı indirmek için **tıklayınız**" butonuna tıklayarak çevrilmiş olan dosyayı indirin. Eğer çevirmek istediğiniz başka bir dosya varsa ekranın alt kısmında yer alan "başka bir dosya çevirmek için **tıklayınız**" butonuna tıklayabilir veya ana sayfaya dönebilirsiniz.

[ceveri.herokuapp.com](https://ceveri.herokuapp.com)

# ÇeVeri Dokümantasyonu

ÇeVeri dokümantasyonu; ÇeVeri kütüphanesinin, ÇeVeri websitesinin ve ÇeVeri klasik veri setlerinin kullanımını kolaylaştırmak ve kullanıcılara yol göstermek amacıyla oluşturulmuş bir dokümantasyondur. ÇeVeri dokümantasyonunda ÇeVeri kütüphanesinin kurulumuna ve kullanımına, ÇeVeri websitesinin kullanıma ve ÇeVeri klasik veri setlerinde yer alan veri setlerine ait bilgilere ulaşabilirsiniz.

[ceveri.readthedocs.io](https://ceveri.readthedocs.io)

# ÇeVeri Klasik Veri Setleri
Yayla takımı olarak ÇeVeri’yi kullanarak oluşturduğumuz, doğal dil işleme çalışmalarında sıklıkla kullanılmaları sonucu birer standart haline gelmiş, toplamda 21 adet veri setini Türkçe’ye kazandırmanın ve geliştiricilerle paylaşmanın gururunu yaşıyoruz. 

![ÇeVeri Çalışma Akışı](https://raw.githubusercontent.com/ardauzunoglu/ceveri/main/readme/klasikler.png)

ÇeVeri klasik veri setleri, toplam 34 eşsiz görev üzerinde kullanılmakta olup toplamda 473MB’ın üzerinde alan kaplamaktadır. Çevrilen veri seri setleri arasında bilgisayarlı biyoloji (computational biology), görsel açıklama (image captioning), duygu tespiti (emotion recognition) gibi daha önce Türkçe veri barındırmayan alanlarda kullanılan veri setleri de yer almaktadır. Tüm bunlarla birlikte, Türkçe doğal dil işlemeye kazandırdığımız veri setleri, etki faktörü yüksek konferanslarda ve dergilerde yayınlanmış, seçkin kurumlar tarafından hazırlanmış ve akademide ve endüstride birer standart ve temel haline gelmiş veri setleri arasından seçilmiştir.

[ÇeVeri Klasik Veri Setleri](https://ceveri.herokuapp.com/klasikler)

# Demo
| Yabancı Dildeki Dosya | ÇeVeri ile Türkçeleştirilen Dosya | Dosya Uzantısı | Çevirilen Karakter Sayısı | İşlem Süresi  | Video | 
| ------------- | ------------- | ------------  | ------------- | ------------- | ------------- | 
| [ornek_en.csv](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_en.csv)  | [ornek_tr.csv](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_tr.csv)  | .csv  | 1901 | 4.91sn | [Youtube](https://youtu.be/lO6-XNPkgzo) | 
| [ornek_en.json](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_en.json)  | [ornek_tr.json](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_tr.json)  | .json  | 725 | 2.72sn | [Youtube](https://youtu.be/WYbdMlAR8PM) | 
| [ornek_en.xlsx](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_en.xlsx)  | [ornek_tr.xlsx](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_tr.xlsx)  | .xlsx  | 1650 | 5.91sn | [Youtube](https://youtu.be/m01T2mAROjQ) | 
| [ornek_en.txt](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_en.txt)  | [ornek_tr.txt](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_tr.txt)  | .txt | 1611 | 1.14sn | [Youtube](https://youtu.be/H2i1r43prZY) | 
| [ornek_en.xml](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_en.xml)  | [ornek_tr.xml](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_tr.xml)| .xml  | 4164 | 9.65sn | [Youtube](https://youtu.be/hh317RC5IvI) | 
| [ornek_en.docx](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_en.docx)  | [ornek_tr.docx](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_tr.docx)  | .docx  | 1177 | 0.33sn | [Youtube](https://youtu.be/hmRUy2stK0c) | 
| [ornek_en.pkl](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_en.pkl)  | [ornek_tr.pkl](https://github.com/ardauzunoglu/ceveri/blob/main/readme/ornek_tr.pkl)  | .pkl  | 1642 | 4.88sn | [Youtube](https://youtu.be/Co-7mRet_M8) | 

# Geliştirmeye Yönelik Hedefler

### Güncel Durum
ÇeVeri, güncel olarak 7 farklı dosya uzantısını desteklemekte. Desteklenen formatlar arasında .xlsx, .csv, .json, .xml, .txt, .pkl, ve .docx yer almakta. Kullanıcılar, ÇeVeri websitesine güncel olarak maksimum 1MB boyutundaki dosyaları yükleyebilmekteyken ÇeVeri kütüphanesinde herhangi bir dosya boyutu sınırlaması bulunmamaktadır.

### Hedefler
**1 - Desteklenen Uzantıların Arttırılması**<br>
Desteklenen uzantılar listemize yeni uzantılar ekleyerek ÇeVeri'nin destek kapsamını arttırmayı amaçlıyoruz. Bu sayede geliştiriciler, yabancı dildeki verilerin formatlarını ve uzantılarını değiştirmekle zaman kaybetmeyecek, doğrudan ÇeVeri aracılığı ile verilerini Türkçeleştirerek çalışmalarında kullanabilecekler.

**2 - Üyelik Sistemine Geçilmesi**<br>
ÇeVeri, güncel olarak üyelik veya abonelik gereksinimi olmadan herkesin kullanımı açıktır. Bununla birlikte, bu durum kullanıcıların yükleyebileceği dosya boyutuna doğal olarak bir sınırlandırma getirilmesini gerektirmektedir. Planladığımız üyelik modeli ile birlikte ÇeVeri üyesi olan kullanıcıların yükleyebileceği maksimum dosya boyutunda artışa gitmeyi ön görüyoruz.

**3 - Üretilen Verinin Depolanması**<br>
ÇeVeri, çoğunlukla Batı dilleri ekseninde yoğunlaşan metin temelli verilerin Türkçe'ye kazandırılmasını amaçlamaktadır. Bu amaç doğrultusunda ÇeVeri kullanımı ile elde edilen verilerin, kullanıcı onayı ile birlikte, herkese açık bir şekilde paylaşılmasını sağlayan yeni bir servis modeli entegre etmeyi hedefliyoruz.



# Geliştirici Ekip
Geliştirici Ekip: **Yayla** <br>
Takım Kaptanı: **Arda Uzunoğlu** → [Github](https://github.com/ardauzunoglu), [Twitter](https://twitter.com/ardauzunogluuu) <br>
Takım Danışmanı: **Gözde Gül Şahin** → [Github](https://github.com/gozdesahin), [Twitter](https://twitter.com/gozde_gul_sahin), [Website](https://gozdesahin.github.io) <br>
