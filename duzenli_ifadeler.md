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
