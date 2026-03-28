# Dosya Sistemleri ve Depolama Mantığı

## NTFS – ext4 – APFS farkları
### NTFS nedir?

NTFS, Windows işletim sisteminin sık kullandığı dosya sistemidir.
Dosyaların diskte nasıl saklanacağını, isimlendirileceğini, korunacağını ve yönetileceğini belirler.

Özellikleri:

Windows ile çok uyumludur.
Büyük dosyaları destekler.
İzinler ve güvenlik özellikleri vardır.
Günlükleme (journaling) yapar, yani ani kapanmalarda veri kaybını azaltmaya çalışır.

Neden önemli?
Çünkü Windows bilgisayarda dosyaların nasıl düzenli tutulduğunu anlamanı sağlar.

Günlük hayat benzetmesi:
NTFS’yi, düzenli klasörleri, kilitli çekmeceleri ve etiketleri olan büyük bir ofis dolabı gibi düşünebilirsin.
Her dosya doğru çekmeceye gider ve kimlerin erişebileceği kontrol edilir.

### ext4 nedir?

ext4, Linux sistemlerde çok yaygın kullanılan dosya sistemidir.

Özellikleri:
Hızlı ve kararlıdır.
Linux ile çok uyumludur.
Büyük dosya ve büyük disk desteği vardır.
Journaling kullanır.
Sunucu ve Linux bilgisayarlarda çok tercih edilir.

Neden önemli?
Çünkü Linux tarafında depolamanın nasıl çalıştığını anlamanı sağlar.

Günlük hayat benzetmesi:
ext4, çok iyi organize edilmiş bir depo gibidir.
Kutular sağlam raflara yerleştirilir, her şey hızlı bulunur ve depo yöneticisi sistemi verimli kullanır.

### APFS nedir?
APFS, Apple’ın macOS ve iPhone/iPad gibi cihazlarda kullandığı modern dosya sistemidir.

Özellikleri:
SSD için optimize edilmiştir.
Hızlı kopyalama ve anlık görüntü (snapshot) desteği vardır.
Şifreleme desteği güçlüdür.
Apple cihazlarla uyumu çok yüksektir.

Neden önemli?
Çünkü Mac kullanıyorsan, sisteminin dosyaları nasıl yönettiğini anlaman için çok önemlidir.

Günlük hayat benzetmesi:
APFS’yi, akıllı bir dijital arşiv sistemi gibi düşünebilirsin.
Bir belgeyi kopyalarken hemen ikinci bir fiziksel kopya oluşturmadan, akıllıca yönetir ve alan tasarrufu sağlar.

## Blok Yapısı Nedir?
Diskte veriler tek tek harf harf değil, bloklar halinde saklanır.
Blok, verinin diskte tutulduğu küçük parçalardan biridir.

Örneğin bir dosya 1 KB ise, sistem bunu bir veya birden fazla blok içinde saklar.
Bilgisayar diske “tek tek byte” yazmak yerine, veriyi belli büyüklükte parçalar halinde yazar.
Bu daha düzenli ve daha hızlıdır.

Neden önemli?
Çünkü dosyanın neden bazen küçük olsa bile daha fazla yer kapladığını anlamanı sağlar.

Mesela:

Dosya 2 KB olabilir.Ama blok boyutu 4 KB ise diskte 4 KB yer kaplar.
Yani boş kalan alan da olur.

Günlük hayat benzetmesi:

Blok yapısını, yumurta kolisi gibi düşünebilirsin.
Bir koli 10 yumurta alıyorsa ve sen sadece 6 yumurta koysan bile o koli tamamen yer kaplar.
Aynı şekilde küçük bir dosya da tam bir bloğu kullanabilir.

Blok yapısının önemi:
veri düzenli saklanır
okuma ve yazma daha kolay olur
işletim sistemi dosyaları daha rahat takip eder.

Blok, diskte verinin tutulduğu küçük depolama kutusudur.

## HDD ve SSD Çalışma Prensipleri

### HDD Nedir?
HDD, veriyi dönen manyetik diskler üzerinde saklayan depolama birimidir.

Nasıl çalışır?
İçinde dönen plakalar vardır
Okuma/yazma kafası bu plakalar üzerinde hareket eder.
Veri manyetik olarak yazılır ve okunur.

Özellikleri:
Daha eski teknolojidir.
Genelde daha ucuzdur.
Büyük depolama kapasitesi uygun fiyatlı olabilir.
Ama mekanik olduğu için daha yavaştır.

Neden yavaştır?
Çünkü:
Disk dönecek.
Kafa doğru yere gidecek ve sonra veri okunacak.Yani fiziksel hareket vardır.

Günlük hayat benzetmesi:

HDD’yi, dönen bir plak üzerinde şarkı bulmaya çalışan pikap iğnesi gibi düşünebilirsin.
Önce plak dönüyor, sonra iğne doğru yere geliyor, sonra veri okunuyor.

### SSD Nedir?
SSD, veriyi hareketli parça olmadan, elektronik hafıza hücrelerinde saklayan depolama birimidir.

Nasıl çalışır?
İçinde dönen disk yoktur
Veri çipler üzerinde tutulur
Elektronik olarak çok hızlı erişilir

Özellikleri
HDD’den daha hızlıdır
Sessiz çalışır
Daha dayanıklıdır
Açılış ve program yükleme süreleri daha kısadır.

Neden hızlıdır?
Çünkü mekanik hareket yoktur.
Veriye doğrudan elektronik erişim vardır.

Günlük hayat benzetmesi

SSD’yi, aranan dosyayı anında açan dijital bir tablet gibi düşünebilirsin.
Bir yere gidip çekmece açmak gerekmez, dokununca hemen açılır.

### HDD ve SSD Farkı
HDD:

mekanik yapı
dönen disk
daha yavaş
daha ucuz olabilir


SSD:

elektronik yapı
hareketli parça yok
çok daha hızlı
daha modern

## Veri Okuma ve Yazma Hızları Nereden Gelir?
Depolama hızını etkileyen şeyler şunlardır:

1. Donanım tipi
HDD ise mekanik olduğu için yavaş olabilir.
SSD ise elektronik olduğu için hızlıdır.

2. Dosya sistemi
Kullanılan dosya sistemi veriyi nasıl düzenlediğini etkiler.
Daha iyi optimize edilmiş sistemlerde erişim daha verimli olabilir.

3. Blok yapısı
Veri bloklar halinde tutulduğu için okuma/yazma düzeni buna göre yapılır.

4. Arabirim
Diskin bilgisayara nasıl bağlandığı da önemlidir:
SATA
NVMe
PCIe

Bunlar veri yolunun hızını etkiler.

Günlük hayat benzetmesi:

Bunu bir kargo sistemi gibi düşün:

HDD = motoru yavaş eski kamyon
SSD = hızlı elektrikli teslimat aracı
Dosya Sistemi = kargonun depo düzeni
Blok Yapısı = kutular
Bağlantı Türü = yolun genişliği

Yani sadece araç değil, depo düzeni ve yol da hızda etkilidir.