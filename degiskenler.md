Değişkenler
=
Bu kısımda değişkenleri ele alacağız, peki ama nedir bu değişkenler ?

Kısaca değişkenler, girdiğimiz değerleri alan veya programın çalışmasıyla bazı değerlerin atandığı veri tutucularıdır.  Biz bir değişkene değer atayarak o değeri tekrar tekrar tanımlamak yerine tek bir değişken üzerinden istediğimiz zaman çağırabiliyoruz. Eğer bu tanımdan bir şey anlamadıysanız sorun yok arkadaşlar, konuyu örnekler ile ele aldıkça tam olarak ne demek istediğimi anlıyor olacaksınız.

Hemen basit bir örnek ile açıklamaya başlayalım;
Değişken tanımlarken öncelikle değişken adını girerek eşittir işaretini koyduktan sonra değişkene atamak istediğimiz değeri tırnak işareti içerisine yazıyoruz.
Örneğin ben `sistem="linux"` şeklinde yazarsam, **sistem** isimli değişkene "**linux**" değerini atamış oluyorum. 
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)
Değişkenimin tanımlanıp tanımlanmadığını hemen konsol üzerinden çağırarak kontrol edelim. 
Tanımladığımız herhangi bir değişkeni çağırırken `echo $degisken` şeklinde komut girmemiz yeterli oluyor. 
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)

Bizim tanımladığımız değişken de **sistem** isimli değişken olduğu için konsola `echo $sistem` komutunu girdiğimde, gördüğünüz gibi karşıma "**linux**" ifadesi basılmış oldu. 

Bir örnek daha yapalım ve bu sefer değişkenimize, değer olarak sayı atayalım. Bunun için `rakamlar="12345"` ifadesini konsola giriyorum ve `echo $rakamlar` komutu ile atadığım değişkene ulaşıyorum. 
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)

İşte değişken tanımlamak bu kadar basit. Ancak yine de değişken tanımlarken dikkat etmemiz gereken önemli birkaç detay bulunuyor.

Değişken Tanımlanırken Dikkat Edilmesi Gerekenler
-

 - Değişken isimleri tanımlarken Türkçe karakter kullanmadan alfanümerik(**A-Z, a-z**) karakter kullanmamız gerekiyor.
 Örneğin konsola içerisinde Türkçe karakter geçen, `çalı="bitki"` gibi bir değişken tanımlamak istersem, konsol bana çıktı olarak "**böyle bir komut yok**" hatasını basıyor. 
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)
 
Bunun nedeni de değişken tanımlarında Türkçe karakter kullanımının geçersiz olmasıdır arkadaşlar. Bu kullanımın doğrusu Türkçe karakter içermeyen `cali="bitki"` şeklinde olmalıydı. 
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)

 
- Türkçe karakter dışında, değişken ismi tanımlarken alt tire işareti haricinde herhangi bir sembol kullanımı da hataya yol açmaktadır. Örneğin ben `yeni-yeni="yeni değer"` gibi bir değişken tanımlamaya kalkarsam , konsol bana çıktı olarak "**komut yok**" hatasını basacaktır. 
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)
Bunun nedeni değişken isminde geçen **tire**(**-**)işaretidir. 

Şimdi aynı örneği **alt tire**(**_**)ile deneyerek bu durumu teyit edelim. Bunun için konsola `yeni_yeni="yeni değer"` ifadesini giriyorum ve tanımladığım değişkeni `echo $yeni_yeni` komutunu girerek sorguluyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)

Ve gördüğünüz gibi değişken başarılı şekilde tanımlanmış bulunuyor. Tekrar belirtmiş olalım, hatalı bir kullanıma yol açmamak adına değişken tanımlarken **alt tire işareti haricinde hiç bir sembol kullanmayın**. Yani **yeni+yeni**..**yeni#yeni**..**yeni@yeni** vb tüm kullanımlar hatalıdır.
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)

- Dikkat etmemiz gereken bir diğer husus ise tanımlanacak değişken isimlerinin **kesinlikle rakam ile başlamamasıdır**. Fakat başlangıcı hariç değişken isimlerinde rakam kullanılabilir. 

Yani örneğin herhangi bir değişken tanımlarken **1kitap** hatalı bir kullanım iken **kitap1** ya da **kit1ap** doğru kullanıma örnektir. 
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)
Rakam başta olmadığı sürece tüm kombinasyonlar rakam kullanımına uygundur.
**k1itap**..**ki2tap**..**kit3ap**..**kit33ap**..**kita555p**.. vb.
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)


- Bir başka dikkat edilmesi gereken ayrıntı da; değişken tanımlarken kullanılan tanımların, Linux sistemlerinde olduğu gibi **büyük küçük harf duyarlılığına** sahip olduğudur. 
Örneğin tamamı büyük harflerden oluşan `TEST="ilk ifade"` şeklindeki bir tanım ile tamamı küçük harflerden oluşan `test="ikinci ifade"` tanımı, bash diline göre iki farklı değişkeni temsil eder. Hemen `echo` komutu yardımıyla bu durumu teyit edelim.
![alt text](https://raw.githubusercontent.com/taylanbildik/Linux_Dersleri/master/img/1-%20Komut%20Sat%C4%B1r%C4%B1/1.png)
Gördüğünüz gibi biri küçük diğer büyük harflerden oluşan iki değişken de sistem tarafından farklı algılanarak konsola ayrı ayrı çıktılar basmış oldu. 

- Bunun haricinde değişken tanımlarken **eşittir**(**=**) işaretinin **sağında ve solunda boşluk olmamasına** dikkat etmemiz gerekiyor. Aksi takdirde sistem bizlerin değişken tanımlamak istediğini anlayamadığından, kaçınılmaz olarak konsola "komut yok" şeklinde hata çıktısı basıyor. Aşağıdaki kullanımlar yanlış kullanımlara örnektir.

- Ayrıca değişken tanımlarken ve tanımlamış olduğumuz değişkeni çağırırken kullandığımız çift ve tek tırnak kullanımı ile ilgili de dikkat etmemiz gereken bir kaç önemli husus bulunuyor. Sırasıyla bu detaylara değinecek olursak.
Değişken tanımlarken, atayacağımız değeri tırnak içine yazdırmak istersek uygulayabileceğimiz iki metod bulunuyor.
Örneğin ben konsola tam olarak çift tırnak işareti ile birlikte **"metin"** ifadesini bastırmak istersem; bastırmak istediğim ifadeyi tek tırnak içerisine alarak `' "metin" '` şeklinde yazmam gerekiyor. Şayet tek tırnak ile ekrana basılsın istersem de bu sefer tek tırnaklı ifadeyi çift tırnak içerisine alarak `" 'metin' "` şeklinde yazmam gerekiyor.
Bu yöntem haricinde herhangi bir ifadeyi tırnak içerisinde bastırmak için tırnak işaretlerinden önce **ters slash**( \ ) işaretini `\"metin\"` şeklinde kullanmamız yeterli oluyor.

Tüm bunların dışında konu anlatımın başında değişkenlerin programlar çalışırken farklı değerleri alabildiğinden bahsetmiştik. Bu da eğer bizler herhangi bir kısıtlama getirmezsek, sürekli olarak değişkenlerin  üzerine yeni değerler yazılabileceği anlamına geliyor. Bu durumu daha iyi anlamak adına `spor="tenis"` komutu ile spor isimli bir değişken tanımlayalım ve `echo $spor` komutu ile değişkenimizi çağıralım.

Gördüğünüz gibi bu şekilde spor isimli değişkeni ne zaman çağırsam karşıma **tenis** değeri basılmış oluyor. Ancak değişkenin değerini özellikle sabitlemediğimiz sürece, istenildiği zaman bu değer değiştirilebilir. Bunun için aynı isimli değişkeni farklı bir değer ile tekrar tanımlamamız yeterli oluyor arkadaşlar. Hemen aynı değişkeni bu sefer **futbol** değeri ile tanımlayıp, bu durumu teyit edelim. Konsola `spor="futbol"` şeklinde yazıyorum ve echo komutu ile değişkenimin yeni değerini teyit ediyorum. 

Gördüğünüz gibi önceleri spor değişkenini çağırdığımda karşıma **tenis** değerini basıyorken, değişkenimizi tekrar tanımlamamız yani diğer bir değişle üzerine yeni değer yazmamız sonucu, aldığımız çıktı **futbol** olarak değişmiş oldu. İlerleyen kısımlarda değiştirilemez değişkenler tanımlama konusuna ayrıca değiniyor olacağız ancak şimdilik basit değişken tanımlama işlemleri ile yapılan tanımlamaların değiştirilebilir değerler aldığını unutmayın lütfen.

Değişkenler yeniden tanımlanabildiği için sistemin çalışmasında rol oynayan, varsayılan olarak tanımlanmış olan değişkenlerle aynı isimlere sahip yeni değişkenler oluşturmama konusunda da dikkatli olmamız gerekiyor. Eğer farkında olmadan sisteme ait değişkenleri yeninden tanımlarsanız sistemle ilgili pek çok soruna yol açabilirsiniz. Bu yüzden, tanımlayacağınız değişkenin daha önce kullanılıp kullanılmadığından tam olarak emin değilseniz, değişkeninizi tanımlamadan önce sistem üzerinde var olup olmadığını kontrol etmenizde fayda var.
Peki ama nasıl kontrol edebiliriz derseniz,  konsola `echo` yazıp `$` işareti koyduktan sonra **Tab** tuşuna basarak tanımlı tüm değişkenleri listeleyebilirsiniz. Bu sayede halihazırda sistemde tanımlı olan değişkenlere müdahale etmeden daha bilinçli şekilde yeni değişkenler tanımlayabilirsiniz.


Şimdiye kadar pek çok değişken tanımladık ancak tanımladığımız değişkenler herhangi bir sınıfta yer almıyordu.  Buradaki sınıftan kastım tanımladığımız değişkenin hangi türden veriyi içerisinde barındırabileceğinin belirlenmesidir. Yani örneğin değişken sayısal bir değişken mi olacak yoksa bir diziyi mi temsil edecek ya da değişkenimiz sabit değerli mi olacak henüz bunlardan bahsetmedik.

Şimdi sırasıyla farklı türden değişkenleri nasıl tanımlarız bunlara göz atalım.
Değişkenlerin belirli türlerde değer almasını sağlamak için `declare` komutunu kullanıyoruz. 

Aşağıdaki tablodan komutun parametrelerine ve yerine getirebildiği işlevlerine göz atabilirsiniz.
|Parametre  | İşlev |
|--|--|
|-a|Dizi tanımlama işlevindedir. Array(dizi) ifadesinin kısaltmasıdır.|
|-f|Fonksiyon özelliği tanımlama işlevindedir. Function(fonksiyon) ifadesinin kısaltmasıdır.|
|-i|Sayısal değişken tanımlama işlevindedir. İnteger(tam sayı) ifadesinin kısaltmasıdır.|
|-p|Değişkenin niteliklerini bastırma işlevindedir. Print(yazdır) ifadesinin kısaltmasıdır.|
|-r|Sabit değişken atama işlevindedir. Readonly(yalnızca okunabilir) ifadesinin kısaltmasıdır.|
|-t|Değişkene trace(iz) niteliği verme işlevindedir.|
|-x|Değişkeni export(ihraç) ederek, alt kabuklara aktarma işlevindedir.|

`declare` komutunu kullanıyorken, eğer değişkenlere özellik eklemek istiyorsak `-` işaretini, şayet var olan özellikleri çıkarmak istiyorsak da `+` işaretini çıkarmak istediğimiz özelliğin parametresini belirterek kullanmamız yeterli oluyor.


Sayısal Değişken Tanımlama
-

Anlatımlara ilk olarak sayısal değişken tanımlama işlemi ile başlayalım.
Sayısal değişken tanımlamak için konsola `declare -i değişken tanımı` şeklinde komutumuzu girmemiz gerekiyor. 

Ben 9 değerine sahip **rakam** isimli bir sayısal değişken tanımlamak istediğim için konsola `declare -i rakam="9"` komutumu giriyorum. 

Böylelikle **rakam** isimli sayısal değişkenime **9** rakamını atamış oldum ve  bu değişkenim ben aksini istemedikçe yalnızca sayısal ifadeler alan bir değişken olarak sınıflandırılmış oldu.

Bu durumu teyit etmek için öncelikle değişkenimin sınıfını sorgulamak üzere `declare` komutunun **p** parametersi ile `declare -p rakam` komutunu giriyorum. 

Sizlerin de gördüğü gibi konsol bana çıktı olarak `declare -i rakam` şeklinde bir çıktı bastı. Bu çıktı ile değişkenimizin sayısal bir değişken olduğunu teyit etmiş olsak da kesin olarak emin olmak adına değişkenimize sayısal değerlerin dışında herhangi bir değer atamaya çalışarak bu durumu netleştirelim. 

Bunun için konsola `rakam="test"` komutumu girdikten sonra, değişkenimin durumunu sorgulamak için `declare -p rakam` komutunu kullanıyorum. 

Ve sizlerin de gördüğü üzere çıktıda rakam değişkenimin değeri "**0**" olarak karışıma gelmiş oldu. Bunun nedeni değişkenime sonradan atamaya çalıştığım "**test**" ifadesinin sayısal bir karşılığının olmamasıdır. Neticede değişkenin sayısal değişken olarak tanımladıktan sonra sayısal değerlerin dışında herhangi bir değer almadığını test ederek, rakam isimli değişkenimizin kesin olarak sayısal bir değişken olduğunu teyit etmiş olduk.

Ancak tanımladığımız sayısal değişkenler her zaman sayısal değişken olarak kalmak zorunda da değil. Değişkenimizin sınıfını tekrar eski hale getirmek istersek ekleme işleminde kullandığımız **-** işareti yerine  bu sefer **+** işaretini kullanmamız yeterli oluyor. Yani ben **rakam** isimli sayısal değişkenimin, sayısal değişken tutma özelliğini kaldırmak istersem; konsola `declare +i rakam` şeklinde komut girmem yeterli oluyor. Bu şekilde, `declare` komutunu kullanarak istediğimiz değişkene sayısal değişken özelliği ekleyip çıkartabiliyoruz.



Dizi Tanımlama
-
Birden fazla değeri tek bir değişken içerisine toparlamak istediğimizde dizileri kullanabiliriz. Bu işlem için `declare` komutunun `a` parametresini kullanıyoruz. Komutumuzun kullanımı `declare -a dizi=(değer1 değer2 değer3)` şeklindedir.
Ayrıca `declare` komutunu kullanmadan `dizi=(değer1 değer2 değer3 )` şeklinde de dizi belirtebiliyoruz.

Dizilerin kullanımına en basit örnek alışveriş listesi olarak verilebilir. 

Örneğin ben liste isimli bir değişken tanımlayıp bu değişkenin içerisine istediğim sayıda değer atayabilir ve atadığım değerleri tek tek çağırabilirim. Örnek olması için; konsola `liste=(su süt çay elma ekmek)` şeklinde komutumu girerek, **liste** isimli değişkene birden fazla değer atamış oluyorum.

Böylelikle her bir değere **0** dan başlayarak sırasıyla birer index değeri atanmış oldu. Yani örneğin **su** ifadesi ilk değer olduğu için **0** index numarasını almışken, **çay** değerinin index numarası **2** olmuş oldu.
Bizler de sıralı şekilde atanan bu index değerleri sayesinde istediğimiz değerleri diziden çağırabiliyoruz.
Örneğin dizide yer alan ilk değeri çağırmak istesem konsola `echo ${liste[0]}` komutunu girmem yeterli oluyor.

Gördüğünüz gibi **0** index numarası ile ilk değerimizi ekran bastırmış olduk.
Bu işlemi aynı şekilde diğer değerlerimizi bastırmak için de kullanabiliriz.

Eğer tüm değişkenleri tek sefer bastırmak istersek `*` ya da `@` işaretini kullanabiliriz.

Tanımlanmış olan dizi elemanının kaç karakterden oluştuğunu öğrenmek için, komutumuzu `echo ${#dizi[değişken indexi]}` şeklinde giriyoruz. Ayrıca bu kullanım sadece diziler için değil değişkenler ve sabitler içinde geçerlidir.

Eğer komutumuzda index numarası ile herhangi bir dizi elemanı belirtmezsek varsayılan olarak dizide yer alan ilk eleman işleme alınıyor.

Ayrıca dizi içerisinde kaç tane değişken olduğunu öğrenmek için de `#` simgesini ile birlikte index numarası kısmında  `*` simgesini kullanmamız yeterli. `echo ${#dizi[*]}`



**Değişken değerini kırpma :** 
Değişkene atanan değer içerisinde belirli bir kısımı almak istersek komutumuzu **${degisken:offset:uzunluk}**  şeklinde kullanıyoruz.
**Offset :** Kırpma işleminin başlanacağı yer. Boş bırakılırsa başlangıçtan itibaren alınır.
**Uzunluk :** Kırpma işleminin nereye kadar yapılacağı. Boş bırakıldığı takdirde kırpma işlemi değerin sonuna kadar yapılacaktır. 
**" ${degisken:5} "** = "degisken" adlı değişken değerinin 5. karakterinden sonra hepsi. 
**" ${degisken:5:3} "** = "degisken" adlı değişken değerinin 5. karakterinden itibaren 3 karakter.


**Değişken değeri içerisinde silme :** 
Değişkenimizin içerisinde yer alan değerleri silmek için iki farklı kullanım metodu bulunuyor. Bunlardan ilki değerleri başlangıçtan itibaren silen **#** işareti ve ikincisi ise tersi şekilde istenilen ifadelerin değerlerin sonundan itibaren silen **%** işaretidir. Sırasıyla açıklayacak olursak;

Örneğin **silinecek=(sal salı salıncak )** şeklinde tanımlanmış bir değişkenin değerlerinin başından başlayarak;
Bir harf grubunu silmek istersek; `${silinecek[*]##silinecek_harf_grubu*}`
Yalnızca ilgili harfleri silmek istersek;`${silinecek[*]#silinecek_harf*}`
Komutunu kullanıyoruz. 
Komut içerisinde yer alan kısımları açıklayacak olursak;
**[*]** şeklinde belirtilen kısım dizideki tüm elemanları kapsıyor.
Kare işareti(**#**) de silme işlevini yerine getiriyor. Eğer silinecek ifade birleşik harf grubu ise çift kare(**##**) işareti kullanılmalıdır.
En son kullandığımız `*` işareti ise silinecek harfin geri kalan kısmının otomatik olarak tamamlanmasını sağlıyor.

Örneğin ben dizi içerisinde yer alan tüm **a** harflerini silmek istersem komutumu `${silinecek[*]#a*}` şeklinde kullanmam yeterli.
Ayrıca tüm ifadelerin dışında özel olarak bir ifadeyi de hedefleyebiliriz, örneğin sadece 3. değerde yer alan **a** harflerini silmek için komutumu `${silinecek[2]#a*}` şeklinde kullanabilirim.
Eğer sileceğim kısım bir harf bütünü ise, örneğin dizilerde yer alan tüm **sa** ifadelerini silmek için `${silinecek[*]##sa*}` komutunu kullanırım.

Değerlerimizi sondan itibaren silmek üzere;
Aynı komutları bu sefer **%** işareti ile olacak şekilde kullanmamız yeterli.

**Değişken içerisinde kelime değiştirme :** Değişkenin değeri içerisinde kırpma işlemi yerine değiştirme yapabilirsiniz. **${degisken/aranan_kelime/değiştirilecek_kelime} ${degisken//aranan_kelime/değiştirilecek_kelime}** İlk kullanım, bir adet ters eğik çizgi ile, sadece ilk eşleşmeyi değiştirme, ikinci kullanım, iki adet eğik çizgi ile bütün eşleşmeleri değiştirme işlemi yapılır. Herhangi bir yazı içerisinde beş adet "skript" kelimesi olsun, tek eğik çizgi ile sadece ilk "skript" kelimesi değişikliğe uğrayacaktır. Bunun aksine çift ters eğik çizgi ile kullanıldığı zaman bütün eşleşen "skript" kelimeleri değişikliğe uğrayacaktır.

Değişken içerisinde kelime değiştirme yada silme işlemleri sadece o onki işlemler için geçerlidir. Orjinal değer değişmeyecektir. Değiştirme işlemi sadece istenilen yerde olacaktır, herhangi bir kaydetme durumu sözkonusu değildir. Mesela "degisken" adlı değişken değeri içerisinde kelimeleri değiştirip ekrana yazdırmak için bu yöntemi kullandığınız zaman, işlem sorunsuz olarak gerçekleşecek, Terminal ekranına değiştirilmiş veri yazılacaktır. Fakat orjinal veri kendini koruyacaktır. ileriki derslerimizde kalıcı olarak değiştirme işlemlerini göstereceğiz.










Sabit Değişken Tanımlama
-

Şimdi ise tanımladığımız değişkenin değerinin, değiştirilemez şekilde sabit kalmasını nasıl sağlarız bunu görelim. Bu işlem için `readonly` komutunu ya da `declare` komutunun `r` parametresini kullanabiliyoruz.

Örneğin ben **sabit** isimli bir değişkenin değerini sabitlemek üzere konsola `readonly sabit="sabit değer"` şeklinde komutumu giriyorum. Daha sonra atadığım sabit değeri değiştirmeye çalışarak, değerin gerçekten de sabit olup olmadığını teyit etmek için, sabit isimli değişkenime yeni değer atamaya çalışıyorum. 

Ve gördüğünüz gibi **sabit** isimli değişkenimin değeri sabit olduğu için içerisine yeni bir değer atanamadı. Ayrıca biliyorsunuz ki sabit değer atama işlemini `readonly` komutu yerine, `declare` komutu ile de gerçekleştirebilirdik. Hemen bu şekilde de bir örnek yapmak adına  konsola `declare -r sabit1="sabit değer 1"` şeklinde de komutumu girip değişkenimin özelliğini `p` parametresi ile teyit ediyorum. 

Son olarak bu değerimi de değiştirmeye çalışarak değişkenimin sabit olup olmadığını teyit ediyorum. 

Ve yine gördüğünüz gibi atadığımız değişken sabit olduğundan yeni bir değer atanamadı.

Sabit değişken tanımlarken dikkat edilmesi gereken nokta, sabit değişkenlerin bir kez tanımlandıktan sonra kesinlikle silinip, değiştirilemeyeceğidir. Sabit değişken bir kez tanımlandıktan sonra sabit şekilde kalır.
Bu durumu teyit etmek için değişkenimizin sabitlik özelliğini `declare +r` komutu ile kaldırmayı deneyelim. 

Komutumuzu girdik ancak gördüğünüz gibi değişken sabit değere sahip olduğundan konsol bu işlemin mümkün olmadığını belirtiyor. 
Peki ama sabit değişkenler gerçekten sonsuza kadar tanımlandığı şekilde mi kalıyor ?

Aslında bu durum; yalnızca değişkenin tanımlandığı konsol ekranı için geçerli olduğundan, konsol kapatıldığında tanımlanan tüm değişkenlerle birlikte sabit değişkenler de sıfırlanmasıyla sonuçlanır.
Bu durumun daha net anlamak için lütfen okumaya devam edin.


Değişkenlerin export Edilmesi
=
[http://www.belgeler.org/lis/archive-tlkg-lis-6g.html](http://www.belgeler.org/lis/archive-tlkg-lis-6g.html)

Bu kısıma kadar temel olarak değişkenleri nasıl tanımlayabileceğimizden ve tanımlama yaparken nelere dikkat etmemiz gerektiğinden bahsettik. Ancak henüz değinmediğimiz ve önemli olan başka bir konu da; değişkenlerin export edilmediği sürece yalnızca tanımlandıkları konsol üzerinden çağırılabiliyor olduklarıdır. Bu export etme yani dışarı aktarma(ihraç) kavramı nedir diyecek olursanız, kavramların daha net anlaşılabilmesi adına açıklamaya temelden başlamamız gerekiyor;

Biz bilgisayarı çalıştırıp GNU/Linux işletim sistemini boot ettiğimizde bizden kullanıcı adı ve şifre bilgisi istemeden çalışan kabuğa "Login Shell" ,kullanıcı adı ve parola ile giriş yaptıktan sonra açılan kabuğa ise "Interactive Shell" deniyor. Interactive Shell üzerinde 6 farklı oturum açıp, 6 oturumda birden farklı işlemler gerçekleştirebiliyoruz.
Interactive shell üzerinde açtığımız kabuklar "**tty_konsol_numarası**"  şeklinde ifade edilerek numarasına göre, tty1,tty2,tty3,tty4,tty5,tty6 şeklinde isimlendiriliyor. Bu 6 kabuktan 2 si varsayılan olarak grafiksel arayüz ile çalışıyor.

**----Düzenlenecek----**
Sistemde oturum açtığımız zaman Linux bizlere üzerinde çalışabileceğimiz bir kabuk tahsis etmiş oluyor

Sisteme girdiğiniz zaman Linux size bir kabuk tahsis eder ve kabuk üzerinde değişkenler tanımlayabilmenize izin verir. Kabuk içinde bir kabuk betiği (script) çalıştırılınca sistem tarafından bir alt kabuk daha yaratılır. Bu andan itibaren iki kabuk çalışır, birisi sisteme girdiğiniz anda tahsis edilen, diğeri de programın çalıştırılabilmesi için sistem tarafından çağırılan. Program bittiği anda alt kabuğun işlevi sona erer ve sistem tarafından öldürülür.