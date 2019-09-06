Düzenli İfadeler Ve Karakter Sınıfları 
=

Düzenli İfadeler (Regular Expressions (Regex))
-
Düzenli ifadeler, özellikle programlama yaparken verilerin aradığımız niteliklere göre sınırlandırılması ve sınırlandırlan verilerin istenildiği şekilde çekilmesi adına bizlere yardım eder.  

Ayrıca anlatımlarda; düzenli ifadelerin daha önce temel linux eğitimde değinmiş olduğumuz **joker karakterleri** de içerisinde barındırdığını ve joker karakterlere benzer ancak daha kapsamlı seçenekler sunduğunu da görmüş olacağız.  Lafı daha fazla uzatmadan örnekler üzerinden düzenli ifadelerin işlevlerine göz atalım. 

Başlamadan evvel, burada yer alan bilgilerin ve kullanımların tam anlaşılabilmesi için buradaki örneklerin haricinde sizlerin de pek çok alıştırma yapması gerektiğini lütfen unutmayın. Bilgilerin kalıcı olması adına lütfen buradaki örneklerin dışına çıkarak, bolca alıştırma yapın.

**[]** :  iki köşeli parantez arasına ulaşmak istediğiniz hedefteki ayırt edici karakterli yazmak üzerinedir.

**nokta(.)** : Noktanın bulunduğu yere gelebilecek herhangi bir karakteri temsil eder.

**^**
**$**
**[^..]**
**\{n\}**
**\{n,m\}**
**\{n,\}**
**\+**
**\?**
**\|**
**\(..\)**
**\\**

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
