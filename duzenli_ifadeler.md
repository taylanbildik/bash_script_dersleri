Düzenli İfadeler Ve Karakter Sınıfları 
=

Düzenli İfadeler (Regular Expressions (Regex))
-
Düzenli ifadeler, özellikle programlama yaparken verilerin aradığımız niteliklere göre sınırlandırılması ve sınırlandırlan verilerin istenildiği şekilde çekilmesi adına bizlere yardım eder.  

Ayrıca anlatımlarda; düzenli ifadelerin daha önce temel linux eğitimde değinmiş olduğumuz **joker karakterleri** de içerisinde barındırdığını ve joker karakterlere benzer ancak daha kapsamlı seçenekler sunduğunu da görmüş olacağız.  Lafı daha fazla uzatmadan örnekler üzerinden düzenli ifadelerin işlevlerine göz atalım. 

Başlamadan evvel, burada yer alan bilgilerin ve kullanımların tam anlaşılabilmesi için buradaki örneklerin haricinde sizlerin de pek çok alıştırma yapması gerektiğini lütfen unutmayın. Bilgilerin kalıcı olması adına lütfen buradaki örneklerin dışına çıkarak, bolca alıştırma yapın.

**[]** :  karakterinin kullanımı, iki köşeli parantez arasına ulaşmak istediğiniz hedefteki ayırt edici karakterli yazmak üzerinedir.

Örnek olması açısından "**dosya**" isimli belgelerden sadece sonunda **2,3,4** olanları kapsayacak bir komut olması için konsola `ls -l [234]` komutunu verdim.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/6.png" width="875">

Bir örnek daha verelim.

**[Dd]osya[Aa]dı** şeklinde bir belirtme; **DosyaAdı, Dosyaadı, dosyaAdı, dosyaadı** şeklindeki bütün isimleri kapsayacaktır. Bu sayede ilgili dosyalar için tüm küçük büyük harf kombinasyonu kolaylıkla sağlanmış olur.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/7.png" width="875">

Ayrıca kullanım şekillerine çok fazla örnek verilebilir ancak burada birkaç örnek daha vererek keşfi size bırakıyorum.

**Not** : Burada belirtilen **x y z** temsili değerleri ifade etmektedir !

**[0-9] :** 0'dan 9'a kadar olan rakamları kapsar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/8.png" width="875">

**[x,y,z] :** belirtilen değerlerle eşleşenleri basar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/9.png" width="875">

**[x-z] :** x ile z değerleri arasındaki karakterlerle eşleşir.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/10.png" width="875">

**[xyz] :** belirtilen değerlerle eşleşenleri basar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/11.png" width="875">

**[!xyz] :** Belirtilen karakterlerin dışındakileri diğer tüm karakterleri basar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/12.png" width="875">

**[!x-z] :** Verilen x ile z değeri arasındaki değerler haricindeki karakterler basar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/13.png" width="875">


Örnek olması açısında "**dosya**" isimli belgelerden sadece sonunda **2,3,4** olanları kapsayacak bir komut olması için konsola `ls -l [234]` komutunu verdim.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/6.png" width="875">

Bir örnek daha verelim.

**[Dd]osya[Aa]dı** şeklinde bir belirtme; **DosyaAdı, Dosyaadı, dosyaAdı, dosyaadı** şeklindeki bütün isimleri kapsayacaktır. Bu sayede ilgili dosyalar için tüm küçük büyük harf kombinasyonu kolaylıkla sağlanmış olur.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/7.png" width="875">

Ayrıca kullanım şekillerine çok fazla örnek verilebilir ancak burada birkaç örnek daha vererek keşfi size bırakıyorum.

**Not** : Burada belirtilen **x y z** temsili değerleri ifade etmektedir !

**[0-9] :** 0'dan 9'a kadar olan rakamları kapsar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/8.png" width="875">

**[x,y,z] :** belirtilen değerlerle eşleşenleri basar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/9.png" width="875">

**[x-z] :** x ile z değerleri arasındaki karakterlerle eşleşir.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/10.png" width="875">

**[xyz] :** belirtilen değerlerle eşleşenleri basar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/11.png" width="875">

**[!xyz] :** Belirtilen karakterlerin dışındakileri diğer tüm karakterleri basar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/12.png" width="875">

**[!x-z] :** Verilen x ile z değeri arasındaki değerler haricindeki karakterler basar.

<img src="https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/15-%20Joker%20Karakterler/13.png" width="875">

**nokta(.)** : Noktanın bulunduğu yere gelebilecek herhangi bir karakteri temsil eder.

**^** : Satır başını temsil eder.


**$** : Satır sonunu temsil eder.


**[^..]** : Kümede belirtilen karakterler haricindeki tüm karakterleri kapsar. Ayrıca şapka işareti yerine **ünlem işareti(!)** de kullananabiliriz.

Şimdi birkaç farklı örnek ile kullanımı ele alalım;

Örneğin sonunda rakam bulunan dosyaları listelemek istemezsek komutumuzu `ls *[^0-9]` şeklinde girebiliriz. Bu sayede `ls` komutu başlangıcı ne olursa olsun sonunda rakam yer alan dosyaları liste dışı bırakıyor.



Daha net anlaşılması adına bir örnek daha; * işaretinin sona koylması ile hariç tutma durumu, başlangıcında rakam yer alan dosyalar için de uygulanabilir. 



Ayrıca örneklerde ele aldığımız hariç tutma durumunu, ihtiyacınaza göre rakamlar yerine harfler ya da özel karakterler için de kullanabiliyoruz. 



 
**\{x\}** :  Kendisinden önceki karakterin x kez tekrar edildiğiniz belirtir.


**\{x,y\}** : Kendisinden önceki karakterin en az x en fazla y kez tekrar ettiği durumları kapsar.

**\{x,\}** : Kendisinden önceki karakterin **en az x kez** tekrar edildiğiniz belirtir.

**\+** : Kendisinden önceki karakterin bir ya da daha fazla olduğunuz belirtir.

**\?** : Kendisindne önceki karakterin 0 ya da 1 kez oldğunu belirtir.


**\|** : Kendisindne bir önceki veya bir sonraki karaktere den gelir.

**\(..\)** : Grup olarak düzenli deyimler tanımlar.

**\\** : Özel karakterlerin normal karakterler olarak algılanmasını sağlarlar.

**Kullanım Örnekleri**



Karakter Sınıfları
-

Karakter sınıflarını; bir önceki kısımda ele aldığımız düzenli ifadelerin sıklıkla kullanılan özelliklerinin kalıplaşmış kısayol hali olarak düşünebilirsiniz. Bu ne demek oluyor ? 

**Açıklayalım;**

Örneğin biz yalnızca noktalama işaretleri içeren verileri almak istediğimizde düzenli ifadeler ile bunları tek tek tanımlamamız gerekiyorken, bunun yerine daha önceden tanımlanıp sınıf haline getirilmiş olan **punct** karakter sınıfını kullanabiliriz. 


Kısacası karakter sınıfları sık kullanılan filtreleme seçeneklerinin bir araya getirildiği bir düzenli ifade demetidir. Eğer filtreleyeceğimiz veri, bu sık kullanılan düzenli ifade demetine dahil ise, uzun uzadıya yazmak yerine yazdığımız kodun daha derli toplu olması adına karakter sınıfını kullanabiliriz. Ancak filtreleyeceğimiz veri çok daha spesifik ise düzenli ifadeleri kullanmamız gerekir. 

Anlatmak istediğim konuyu en iyi örnekler açıklayacaktır. 

Öncelikle kullanabileceğimiz temel sınıflara aşağıdaki tablo ile göz atalım.

|Sınıf|Özellik|
|--|--|
|digit|Rakamlar. **(0-9)**|
|lower|Küçük karakterler. **(a-z)** |
|upper|Büyük karakterler. **(A-Z)** |
|alpha|Alfabetik karakterler: ‘**[: lower:]**’ ve ‘**[: upper:]**’; bu‘ **[A-Za-z]** ’ile aynıdır.|
|alnum|Alfanümerik karakterler: ‘**[: alpha:]**’ ve ‘**[: digit:]**’;  bu‘ **[0-9A-Za-z]** ’ile aynıdır.|
|punct|Noktalama işaretleri. (``! " # $ % & ' ( ) * + , - . / : ; < = > ? @ [ \ ] ^ _ ` { | } ~``)|
|graph|Grafiksel karakterler: ‘**[: alnum:]**’ ve ‘**[: punct:]**’. |
|blank|Boş karakterler: **boşluk(space)** ve **tab** içerenler.|
|space|Herhangi bir boşluk karakteri: **tab, yeni satır, dikey tab, space vb..**|
|print|Yazdırılabilir karakterler: ‘**[: alnum:]**’, ‘**[: punct:]**’ ve **boşluk(space)**.|
|xdigit|Onaltılı sayı sistemi: `0 1 2 3 4 5 6 7 8 9 A B C D E F a b c d e f`.|

Tablodan da anlayacağınız gibi belirli özellikler için sınırlandırılmış ifadeler bulunuyor. 

Örneğin yalnızca noktalama işaretleri geçen ifadeleri yazdırmak istersek, [:punct:] karakter sınıfını kullanabiliriz.
Örneğin bizler yalnızca alfanumerik karakterleri listelemek istersek; düzenli ifadeleri kullanarak [0-9A-Za-z] komutunu girebilir ya da karakter sınıfından yararlanarak [:alnum:] komutunu kullanabiliriz. 
