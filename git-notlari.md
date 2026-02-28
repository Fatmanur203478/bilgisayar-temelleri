# Git Notlarım(BTK AKADEMİ)

## git commit --amend
Son attığım commit mesajını değiştirmek için kullanılır. Yeni commit oluşturmaz,son commmiti düzenler.

## git restore <dosya>
Staging alanına eklenmiş bir dosyayı geri alır.Dosya commit edilmeden önceki hale döner.

## git log
repositoryde atılmış tüm commitlerin geçmişini gösterir. yani kim ne zaman neyi kaydetmiş.
Commit ID(hash),commit mesajı, commiti atan kişiyi,tarihi görürüm.

## git status
Dosyalar değişmiş ama commite hazır değil.

## git add .
Klasörde ne değişti ise hepsini commite hazırla .
Tekrar git status yapınca artık commiti atmaya hazırım.

## git commit -m "ilk satır kodlarımızı yazdık"
Değişiklikleri kalıcı olarak kaydetti. Yani bir commit oluşturdu.

## git commit
Staging alanına eklenen dosyaları kalıcı olarak kaydeder. Yapılan değişiklikler commit mesajı ile birlikte saklanır.

## gitignore
Git tarafından takip edilmesini istemediğimiz dosya ve klasörleri belirtmek için kullanılır. Bu dosyalar commit edilmez ve repositi'ye eklenmez.
Nasıl kullanılır?
1. adım = Dosya Oluştur= touch .gitignore
2. adım = İçine Kurallar Yaz= # Python
__pyache--/ ...
3. adım = Kontrol et= git status
yukarıdaki dosyalar artık listelenmez.
yani kısacası .gitignore=Gitin görmezden geleceği dosyalar dizisidir.

# Git Branch

## Head 
Git içerisinde hangi committe olduğumuzu gösteririr. Hem branch hem commit olarak.
Örneğin= HEAD -> master

## git branch feat
Bu komut feat adlı yeni bir branch (dal) oluşturur. Sadece oluşturur , o branche geçmez.
Mevcut branchten ayrılan yeni bir geliştirme dalıdır.

## git switch master
Bu komut , aktif branchi master branchine geçirir. Yani şaunda hangi brancteysem , ana dala (master) dön.
Çalışılan branch'ten çıkıp master branch'ine geçmek için kullanılır. Aktif branch değiştirilir.

Ne zaman kullanılır?
feat gibi bir branchte işin bittiğinde,ana branche dönmek istediğinde , merge yapmadan önce.

Kontrol etmek için
git branch
* master 
feat
* aktif branchi gösteririr.
Eğerki kaydedilmemiş (commit edilmemiş) değişiklik varsa Git izin vermeyebilir.
o zaman önce= git status 
git add .
git commit -m "geçici commit"

 ESKİ KOMUTLA FARK
 git chekout master # eski ama hala çalışır
 git switch master  # yeni ve daha temiz kullanım
 # MERGE
 Bir branche yapılan değişiklikleri başka bir branch ile birleştirme işlemidir. İki dalı tek dal haline getirir. Genellikle feature branchleri master branchine eklemek için kullanılır.

## git merge feat
feat branchinde yapılan değişiklikleri aktif branch ile birleştirir. Genellikle master branchine yeni özellik eklemek içim kullanılır.

## Repository (repo)
Git tarafından takip edilen proje klasörüdür. Dosyaların geçmişi ve yapılan değişiklikler burada tutulur.

## Branch
ana projeyi etkilemeden paralel geliştirme yapmayı sağlar.

## Fast-forward
Branch’ler arasında çatallanma yoksa, Git’in merge sırasında
yeni bir commit oluşturmadan branch’i ileri taşımasıdır.

## Stash
git stash, commit etmeden yaptığın değişiklikleri geçici olarak kenara kaldırır.branch değiştirmeden önce çalışma alanını temizler. ÖNEMLİ: Stash commit değildir. Uuzn süre tutulmamalı. Merge conflıct çıkabilir. Yani stash, commit etmeden sakla demektir.

## pop

git stash pop, saklanan değişiklikleri geri yükler ve stash listesinden kaldırır.


## checkout
Eski Git sürümlerinde hem branch değiştirmek hemde dosyayı eski haline getirmek için kullanılırdı
- Yeni Git’te bu iş için genelde:
  - `git switch` (branch değiştir)
  - `git restore` (dosyayı geri al)
  tercih edilir.

Ne zaman kullanılır?
- Branch değiştirmek (eski alışkanlık)
- Belirli bir commit’teki dosyayı görmek/geri almak

Örnek
bash
git checkoutmain                  (eski) main branch'e geç
git checkout -b feature/login     (eski) yeni branch oluştur ve geç


## git reset
commit geçmişini geri alır.Yapılan commitleri sanki hiç yapılmamış gibi siler.Daha çok local(yerel) çalışmalarda kullanılır.
'Git reset' commit geçmişini değiştirdiği için paylaşılan (push) edilmiş commitlerde dikkatli kullanılmalıdır.
Yanlış commit atıldığında yada GitHub'a push etmeden önce bir hata fark ettiğimde  kullanırım.

##soft reset
Commit silinir ama dosyalar staging alanında kalır.
git reset --soft HEAD-1 
MİXED RESET: Commit silinir, dosyalar staging'den  çıkar ama silinmez.(git reset HEAD-1)
HARD RESET: Commit ve dosya değişiklikleri tamamen silinir.(git reset --hard HEAD-1)



## git revert 
Eski bir commiti iptal eden yeni bir commit oluşturur.Commit geçmişini bozmaz ve en güvenli geri alma yöntemidir.
Commit GitHub'a push edildiyse , takım çalışması varsa ve geçmişi silmeden hatayı düzeltmek istiyorsan kullanılır.  git revert Id gir commitin 

## git diff
Dosyalarda yapılan değişiklikleri karşılaştırır.
Henüz commit edilmemiş değişiklikleri görmeni sağlar.
Ne değişti? sorusunun cevabıdır.
Commit atmadan önce kontrol etmek için , hangi satırların değiştiğini görmek için hata ayıklarken (debug) farklarını incelemek için kullanılır.

Henüz git add . yapılmamış değişiklikleri gösterir.i
'''bash 
git diff
## rebase
Commitleri başka bir branchinin en güncel halinin üzerine taşır.Commit geçmişini daha temiz ve düz (linear) hale getirir. Bu branch mainden en güncel halini alsın ama geçmiş karışmasın demektir.

Feature branchini mainin son haliyle güncellenmek istendiğinde,daha okunabilir temiz bir commit geçmişi oluşturmak istendiğinde ve henüz push edilmemiş commitlerle çalışırken kullanılır.

