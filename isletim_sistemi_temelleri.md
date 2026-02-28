# İşletim Sistemi Temelleri
## Kernel Nedir?
Kernel (çekirdek) işletim sisiteminin en temel kısmıdır. 
Şunları yönetir:
.CPU'yu kim kullanacak (zamanlama)
.Belleği kim kullanacak(memory managment)
.Dosyalar/disk
.Cihazlar(klavye,ekran,ağ)
.Programların güvenli şekilde çalışması
Örnek benzetme: Kernel= "trafik polisi+belediye+güvenlik" gibi. Her şeyi o düzenler.

## Process(süreç)
Çalışan programın kendi dünyasıdır.
Kendi adres alanı(memory space) vardır.
Başka processten genelde izole çalışır.

## Thread (iş parçacığı)
Bir processin içindeki "çalışma akışıdır."
Aynı process içindeki threadler aynı bellek alanını paylaşır.
Daha hafiftir"oluşturma ve geçişi daha kolaydır."
BENZETME:
PROCESS=AYRI EV
THREAD=AYNI EVİN İÇİNDEKİ ODALARDA ÇALIŞAN İNSANLAR(MUTFAK/SALON ORTAK)

## Bellek Yönetimi Naıl Yapılır?
OS bellek yönetiminde şunları yapar:
.VİRTUAL MEMEORY(SANAL BELLEK): Her process'e sanki çok bellek varmış gibi ayrı bir alan gösterir.
.SAYFALAMA(PAGİNG): Bellek küçük parçalara(page) ayrılır; RAM yetmezse disk(swap)kullanır.

HEAP/STACK:
STACK:Fonksiyon çağrıları yerel değişkenler.
HEAP:New/malloc ile dinamik bellek.
AMAÇ: Koruma+verim+çakışma olmaması
NOT: Kodla"tam OS paging'i" yönetemzsin ama heap/stack davranışını gözlemleyebilirsin.

## CPU Zamanlayıcıları Nedir?
CPU aynı anda tek çekirdekte bir anda tek işi çalıştırır.Schedular(zamanlayıcı)karar verir.
."Sıradaki kim çalışacak?"
."Ne kadar süre çalışacak?"  (time slice)
Bazı temel algoritmalar:
.FCFS: İlk gelen ilk çalışır.
.ROUND ROBİN: Herkes sırayla kısa süre.
.PRİORİTY: Önceliği göre.
.MULTİLEVEL FEEDBACK QUEUE:  Dinamik kuyruklar(modern sistemlerde yaygın)
NOT: Thread / processlerin "paylaşmalı" görünmesi: schedular hızlı hızlı değiştirir.

