Düzenli İfadeler Ve Karakter Sınıfları 
=

Düzenli İfadeler (Regular Expressions (Regex))
-
Düzenli ifadeler, özellikle programlama yaparken verilerin aradığımız niteliklere göre sınırlandırılması ve sınırlandırlan verilerin istenildiği şekilde çekilmesi adına bizlere yardım eder.  

Ayrıca anlatımlarda; düzenli ifadelerin daha önce temel linux eğitimde değinmiş olduğumuz **joker karakterleri** de içerisinde barındırdığını ve joker karakterlere benzer ancak daha kapsamlı seçenekler sunduğunu da görmüş olacağız.  Lafı daha fazla uzatmadan örnekler üzerinden düzenli ifadelerin işlevlerine göz atalım. 

Başlamadan evvel, burada yer alan bilgilerin ve kullanımların tam anlaşılabilmesi için buradaki örneklerin haricinde sizlerin de pek çok alıştırma yapması gerektiğini lütfen unutmayın. Bilgilerin kalıcı olması adına lütfen buradaki örneklerin dışına çıkarak, bolca alıştırma yapın.

**[]** 
=

Kullanımı, iki köşeli parantez arasına ulaşmak istediğiniz hedefteki ayırt edici karakterleri yazmak üzerinedir.

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

**{}**
=

Kıvırcık parantez de köşeli paranteze benzer şekilde içerisine girilen ifadelere göre çalışır.

Çalışma yapısını anlamak için aşağıdaki örneklere göz atabilirsiniz.

**{x,y,z} :** içerisinde virgüller ile ayrılmış ifadeleri tek tek basar.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/kvr0.png" width="875">

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/kvr1.png" width="875">


**{x..y} :** iki ifade arasına koyulan **iki nokta**(**..**) sayesinde otomatik olarak başlangıç karaterinden son karaktere gelinceye kadar sıralı çıktılar elde edebiliyoruz. Tam kullanımı `{başlangıç_ifadesi..bitiş_ifadesi}` şeklindedir. 

**Kullanım örnekleri;**
Rakam ya da harflerin istenildiği yerden başlayıp istenildiği kısıma kadar sıralanması sağlanabilir.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/kvr2.png" width="875">

Üstelik bu sıralama birer birer artmak zorunda da değil. İstenilen aralıkta artışın yapılması `{başlangıç_ifadesi..bitiş_ifadesi..artış_aralığı}` şeklindeki kullanım ile sağlanabilir.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/kvr3.png" width="875">


**nokta(.)** 
=

Noktanın bulunduğu yere gelebilecek herhangi bir karakteri temsil eder.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/1.png" width="875">

**^** 
=

Satır başını temsil eder.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/2.png" width="875">

**$**
=

Satır sonunu temsil eder.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/3.png" width="875">

**[^..]** 
=

Kümede belirtilen karakterler haricindeki tüm karakterleri kapsar. Ayrıca şapka işareti yerine **ünlem işareti(!)** de kullananabiliriz.

Şimdi birkaç farklı örnek ile kullanımı ele alalım;

Örneğin sonunda rakam bulunan dosyaları listelemek istemezsek komutumuzu `ls *[^0-9]` şeklinde girebiliriz. Bu sayede `ls` komutu başlangıcı ne olursa olsun sonunda rakam yer alan dosyaları liste dışı bırakıyor.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/4.png" width="875">

Daha net anlaşılması adına bir örnek daha; * işaretinin sona koyulması ile hariç tutma durumu, başlangıcında rakam yer alan dosyalar için de uygulanabilir. 

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/5.png" width="875">

Ayrıca örneklerde ele aldığımız hariç tutma durumunu, ihtiyacımıza göre rakamlar yerine harfler ya da özel karakterler için de kullanabiliyoruz. 

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/6.png" width="875">

 
**\\{x\\}** 
=

Kendisinden önceki karakterin **tam olarak x** kez tekrar edildiğiniz belirtir.

Örneğin **2 kez a** harfinin geçtiği tüm kelimeleri listelemek istersek, `grep` komutu yardımı ile `a\{2\}` düzenli ifadesini kullanabiliriz.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/7.png" width="875">

**\\{x,\\}**   
=

Kendisinden önceki karakterin **en az x kez** tekrar edildiğiniz belirtir.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/8.png" width="875">


**\\+**   
=

Kendisinden önceki karakterin **1 ya da daha fazla** olduğunu, diğer bir deyişle **en az 1 kez** bulunduğu durumları belirtir.
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/10.png" width="875">


**\\?**   
=

Kendisindne önceki karakterin 0 ya da 1 kez oldğunu belirtir.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/11.png" width="875">


**\\|**   
=

Kendisindne bir önceki veya bir sonraki karaktere denk gelir.
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/12.png" width="875">

**xyz\\<**   
=

xyz ile başlayan satırları kapsar.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/13.png" width="875">

**xyz\\>**   
=

xyz ile biten satırları kapsar.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/14.png" width="875">

**\\**   
=

Özel karakterlerin normal karakterler olarak algılanmasını sağlarlar.

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/15.png" width="875">

**Kullanım Örnekleri**



Karakter Sınıfları
-

Karakter sınıflarını; bir önceki kısımda ele aldığımız düzenli ifadelerin sıklıkla kullanılan özelliklerinin kalıplaşmış kısayol hali olarak düşünebilirsiniz. Bu ne demek oluyor ? 

**Açıklayalım;**

Örneğin biz yalnızca noktalama işaretleri içeren verileri almak istediğimizde düzenli ifadeler ile bunları tek tek tanımlamamız gerekiyorken, bunun yerine daha önceden tanımlanıp sınıf haline getirilmiş olan **punct** karakter sınıfını kullanabiliriz. 

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/16.png" width="875">

Kısacası karakter sınıfları sık kullanılan filtreleme seçeneklerinin bir araya getirildiği düzenli ifade demetleridir. Eğer filtreleyeceğimiz veri, bu sık kullanılan düzenli ifade demetine dahil ise, uzun uzadıya yazmak yerine yazdığımız kodun daha derli toplu olması adına karakter sınıfını kullanabiliriz. Ancak filtreleyeceğimiz veri çok daha spesifik ise düzenli ifadeleri kullanmamız gerekir. 

Anlatmak istediğim konuyu en iyi örnekler açıklayacaktır. 

Öncelikle kullanabileceğimiz temel sınıflara aşağıdaki tablo ile göz atalım.

|Sınıf|Özellik|
|--|--|
|digit|Rakamlar. bu‘ **(0-9)** ’ile aynıdır.|
|lower|Küçük karakterler. bu‘ **(a-z)** ’ile aynıdır.|
|upper|Büyük karakterler. bu‘ **(A-Z)** ’ile aynıdır. |
|alpha|Alfabetik karakterler: ‘ **[: lower:]** ’ ve ‘ **[: upper:]** ’; bu‘ **[A-Za-z]** ’ile aynıdır.|
|alnum|Alfanümerik karakterler: ‘ **[: alpha:]** ’ ve ‘ **[: digit:]** ’;  bu‘ **[0-9A-Za-z]** ’ile aynıdır.|
|punct|Noktalama işaretleri.  (``! " # $ % & ' ( ) * + , - . / : ; < = > ? @ [ \ ] ^ _ ` { | } ~``)|)
|graph|Grafiksel karakterler: ‘ **[: alnum:]** ’ ve ‘ **[: punct:]** ’. |
|blank|Boş karakterler: **boşluk(space)** ve **tab** içerenler.|
|space|Herhangi bir boşluk karakteri: **tab, yeni satır, dikey tab, space vb..**|
|print|Yazdırılabilir karakterler: ‘ **[: alnum:]** ’, ‘ **[: punct:]** ’ ve **boşluk(space)**.|
|xdigit|Onaltılı sayı sistemi: `0 1 2 3 4 5 6 7 8 9 A B C D E F a b c d e f`.|

Tablodan da anlayacağınız gibi belirli özellikler için sınırlandırılmış ifadeler bulunuyor. Bu ifadelerin kullanım örneklerine aşağıdaki görsellerden bakabilirsiniz. 

digit
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/17.png" width="875">

lower
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/18.png" width="875">

upper
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/19.png" width="875">

alpha
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/20.png" width="875">

alnum
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/21.png" width="875">

punct
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/22.png" width="875">

graph
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/23.png" width="875">

blank
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/24.png" width="875">

space
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/25.png" width="875">

print
=
<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/26.png" width="875">

xdigit
=

<img src="https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/D%C3%BCzenli%20%C4%B0fadeler/27.png" width="875">

