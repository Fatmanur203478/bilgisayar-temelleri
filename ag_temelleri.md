# AĞ TEMELLERİ (NETWORKING)

## IP(Internet Protocol)
Internete bağlı her cihazın kimlik numarasıdır. Örneğin; 192.168.1.1
Bilgisayarlar internette IP adresi sayesinde birbirini bulurlar .
Ne işe yararlar?
Verinin hangi cihazdan çıkıp hangi cihaza gideceğini belirler.
Günlük hayattan benzetme olarak ;bir evin posta adresi gibidir. Adres olmadan kargo nereye gideceğini bilemez.

## PORT 
Bir cihazın içindeki uygulama kapısıdır. Aynı IP üzerinde birden fazla servis çalışabilir.
örnek;
80=> web (HTTP)
443=> GÜVENLİ WEB(HTTPS)
3306=> MySQL
Gelen verinin hangi programa gideceğini söyler . Port , apartmandaki daire numarası gibidir. Bina aynı olsa bile hangi daireye gideceğini port belirler.

## DNS (Domain Name System)
Alan adlarını IP adreslerine çevirir. insanların Ip ezberlemesini engeller .
DNS, telefon rehberi gibidir. Kişinin adını yazarsın , sistem sana numarasını bulur.
ÖRNEĞİN; google.com >> 142.250.xxx.xxx
İnsanların ezberlemesi zor IP'ler yerine isimle siteye girmesini sağlar.

## TCP (Transmission Control Protocol)
Güvenli ve sıralı veri iletimi sağlar.Eksik veri varsa tekrar gönderir.
TCP, taahhütlü kargo gibidir. Paket eksik veya hasarlıysa yeniden gönderilir.
web siteleri,e-posta,dosyan indirmede kullnılır. Yavaş ama hatasızdır.

## UDP (User Datagram Protocol)
Hızlı ama kontrolsüz veri gönderir.
Paket kaybolursa tekrar istemez.
 Nerede kullanılır?
Online oyunlar
Canlı yayınlar
Video / ses görüşmeleri
📌 Özellik:
✔ Çok hızlı ama paket kaybı olabilir.
UDP, canlı konuşma gibidir. Bir kelimeyi kaçırırsan geri alamazsın ama konuşma hızlı akar.

## PAKET YAPISI
Büyük veri küçük parçalara (paketlere) bölünür.
Her pakette:
Gönderen IP
Alıcı IP
Port bilgisi
Veri parçası bulunur
Paketler hedefe ulaştığında tekrar birleştirilir.
Avantaj:
İnternet trafiği daha hızlı ve yönetilebilir olur.
Büyük bir eşyayı taşırken parçalara ayırmak gibidir. Parçalar ayrı ayrı taşınır, varınca birleştirilir.
## AĞ TEST KOMUTLARI
Ping:
İki cihaz arasında erişim var mı diye kontrol eder.Gecikme süresini ölçer.
Ne gösterir?
“Bu siteye ulaşabiliyor muyum?”
Birine “Orada mısın?” diye seslenmek gibidir. Cevap gelirse bağlantı vardır.

## TRACEROUTE
Verinin hedefe giderken hangi noktalardan geçtiğini gösterir.
Ne gösterir?
“Bağlantı nerede yavaşlıyor veya kopuyor?”
Navigasyonun “şu yollardan geçtin” demesi gibidir. Nerede takıldığını görürsün.

## NSLOOKUP
Bir domainin IP adresini ve DNS bilgisini gösterir.
Ne gösterir?
“Bu site hangi sunucuda barınıyor?”
Bir şirketin adını aratıp adresini öğrenmek gibidir.
