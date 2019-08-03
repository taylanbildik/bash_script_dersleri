Değişkenler
=
Bu kısımda değişkenleri ele alacağız, peki ama nedir bu değişkenler ?

Kısaca değişkenler, girdiğimiz değerleri alan veya programın çalışmasıyla bazı değerlerin atandığı veri tutucularıdır.  Biz bir değişkene değer atayarak o değeri tekrar tekrar tanımlamak yerine tek bir değişken üzerinden istediğimiz zaman çağırabiliyoruz. Eğer bu tanımdan bir şey anlamadıysanız sorun yok arkadaşlar, konuyu örnekler ile ele aldıkça tam olarak ne demek istediğimi anlıyor olacaksınız.

Hemen basit bir örnek ile açıklamaya başlayalım;
Değişken tanımlarken öncelikle değişken adını girerek eşittir işaretini koyduktan sonra değişkene atamak istediğimiz değeri tırnak işareti içerisine yazıyoruz.
Örneğin ben `sistem="linux"` şeklinde yazarsam, **sistem** isimli değişkene "**linux**" değerini atamış oluyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/1.png)

Değişkenimin tanımlanıp tanımlanmadığını hemen konsol üzerinden çağırarak kontrol edelim. 
Tanımladığımız herhangi bir değişkeni çağırırken `echo $degisken` şeklinde komut girmemiz yeterli oluyor. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/2.png)

Bizim tanımladığımız değişken de **sistem** isimli değişken olduğu için konsola `echo $sistem` komutunu girdiğimde, gördüğünüz gibi karşıma "**linux**" ifadesi basılmış oldu. 

Bir örnek daha yapalım ve bu sefer değişkenimize, değer olarak sayı atayalım. Bunun için `rakamlar="12345"` ifadesini konsola giriyorum ve `echo $rakamlar` komutu ile atadığım değişkene ulaşıyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/3.png)

İşte değişken tanımlamak bu kadar basit. Ancak yine de değişken tanımlarken dikkat etmemiz gereken önemli birkaç detay bulunuyor.

Değişken Tanımlanırken Dikkat Edilmesi Gerekenler
-

 - Değişken isimleri tanımlarken Türkçe karakter kullanmadan alfanümerik(**A-Z, a-z**) karakter kullanmamız gerekiyor.
 
Örneğin konsola içerisinde Türkçe karakter geçen, `çalı="bitki"` gibi bir değişken tanımlamak istersem, konsol bana çıktı olarak "**komut yok**" hatasını basıyor. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/4.png)
 
Bunun nedeni de değişken tanımlarında Türkçe karakter kullanımının geçersiz olmasıdır arkadaşlar. Bu kullanımın doğrusu Türkçe karakter içermeyen `cali="bitki"` şeklinde olmalıydı. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/5.png)

 
- Türkçe karakter dışında, değişken ismi tanımlarken alt tire işareti haricinde herhangi bir sembol kullanımı da hataya yol açmaktadır. 

Örneğin ben `yeni-yeni="yeni değer"` gibi bir değişken tanımlamaya kalkarsam , konsol bana çıktı olarak "**komut yok**" hatasını basacaktır. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/6.png)

Bunun nedeni değişken isminde geçen **tire**(**-**)işaretidir. 

Şimdi aynı örneği **alt tire**(**_**)ile deneyerek bu durumu teyit edelim. Bunun için konsola `yeni_yeni="yeni değer"` ifadesini giriyorum ve tanımladığım değişkeni `echo $yeni_yeni` komutunu girerek sorguluyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/7.png)

Ve gördüğünüz gibi değişken başarılı şekilde tanımlanmış bulunuyor. Tekrar belirtmiş olalım, hatalı bir kullanıma yol açmamak adına değişken tanımlarken **alt tire işareti haricinde hiç bir sembol kullanmayın**. Yani **yeni+yeni**..**yeni#yeni**..**yeni@yeni** vb tüm kullanımlar hatalıdır.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/8.png)

- Dikkat etmemiz gereken bir diğer husus ise tanımlanacak değişken isimlerinin **kesinlikle rakam ile başlamamasıdır**. Fakat başlangıcı hariç değişken isimlerinde rakam kullanılabilir. 

Yani örneğin herhangi bir değişken tanımlarken **1kitap** hatalı bir kullanım iken **kitap1** ya da **kit1ap** doğru kullanıma örnektir. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/9.png)

Rakam başta olmadığı sürece tüm kombinasyonlar rakam kullanımına uygundur.
**k1itap**..**ki2tap**..**kit3ap**..**kit33ap**..**kita555p**.. vb.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/10.png)


- Bir başka dikkat edilmesi gereken ayrıntı da; değişken tanımlarken kullanılan tanımların, Linux sistemlerinde olduğu gibi **büyük küçük harf duyarlılığına** sahip olduğudur. 

Örneğin tamamı büyük harflerden oluşan `TEST="ilk ifade"` şeklindeki bir tanım ile tamamı küçük harflerden oluşan `test="ikinci ifade"` tanımı, bash diline göre iki farklı değişkeni temsil eder. Hemen `echo` komutu yardımıyla bu durumu teyit edelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/11.png)

Gördüğünüz gibi biri küçük diğer büyük harflerden oluşan iki değişken de sistem tarafından farklı algılanarak konsola ayrı ayrı çıktılar basmış oldu. 

- Bunun haricinde değişken tanımlarken **eşittir**(**=**) işaretinin **sağında ve solunda boşluk olmamasına** dikkat etmemiz gerekiyor. Aksi takdirde sistem bizlerin değişken tanımlamak istediğini anlayamadığından, kaçınılmaz olarak konsola "**komut yok**" şeklinde hata çıktısı basıyor. Aşağıdaki kullanımlar yanlış kullanımlara örnektir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/12.png)

Tüm bunların dışında konu anlatımın başında değişkenlerin programlar çalışırken farklı değerleri alabildiğinden bahsetmiştik. Bu da eğer bizler herhangi bir kısıtlama getirmezsek, sürekli olarak değişkenlerin  üzerine yeni değerler yazılabileceği anlamına geliyor. Bu durumu daha iyi anlamak adına `spor="tenis"` komutu ile **spor** isimli bir değişken tanımlayalım ve `echo $spor` komutu ile değişkenimizi çağıralım.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/13.png)

Gördüğünüz gibi bu şekilde **spor** isimli değişkeni ne zaman çağırsam karşıma **tenis** değeri basılmış oluyor. Ancak değişkenin değerini özellikle sabitlemediğimiz sürece, istenildiği zaman bu değer değiştirilebilir. Bunun için aynı isimli değişkeni farklı bir değer ile tekrar tanımlamamız yeterli oluyor arkadaşlar. Hemen aynı değişkeni bu sefer **futbol** değeri ile tanımlayıp, bu durumu teyit edelim. Konsola `spor="futbol"` şeklinde yazıyorum ve `echo` komutu ile değişkenimin yeni değerini teyit ediyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/14.png)

Gördüğünüz gibi önceleri spor değişkenini çağırdığımda karşıma **tenis** değerini basıyorken, değişkenimizi tekrar tanımlamamız yani diğer bir değişle üzerine yeni değer yazmamız sonucu, aldığımız çıktı **futbol** olarak değişmiş oldu. İlerleyen kısımlarda değiştirilemez(sabit) değişkenler tanımlama konusuna ayrıca değiniyor olacağız ancak şimdilik basit değişken tanımlama işlemleri ile yapılan tanımlamaların değiştirilebilir değerler aldığını unutmayın lütfen.


Değişkenler yeniden tanımlanabildiği için sistemin çalışmasında rol oynayan, varsayılan olarak tanımlanmış olan değişkenlerle aynı isimlere sahip yeni değişkenler oluşturmama konusunda da dikkatli olmamız gerekiyor. Eğer farkında olmadan sisteme ait değişkenleri yeninden tanımlarsanız sistemle ilgili pek çok soruna yol açabilirsiniz. Bu yüzden, tanımlayacağınız değişkenin daha önce kullanılıp kullanılmadığından tam olarak emin değilseniz, değişkeninizi tanımlamadan önce sistem üzerinde var olup olmadığını kontrol etmenizde fayda var.
Peki ama nasıl kontrol edebiliriz derseniz,  konsola `echo` yazıp `$` işareti koyduktan sonra **Tab** tuşuna basarak tanımlı tüm değişkenleri listeleyebilirsiniz. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/15.png)
![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/16.png)

Bu sayede halihazırda sistemde tanımlı olan değişkenlere müdahale etmeden daha bilinçli şekilde yeni değişkenler tanımlayabilirsiniz.


Şimdiye kadar pek çok değişken tanımladık ancak tanımladığımız değişkenler herhangi bir sınıfta yer almıyordu.  Buradaki sınıftan kastım tanımladığımız değişkenin hangi türden veriyi içerisinde barındırabileceğinin belirlenmesidir. Yani örneğin değişken sayısal bir değişken mi olacak yoksa bir diziyi mi temsil edecek ya da değişkenimiz sabit değerli mi olacak henüz bunlardan bahsetmedik.

Şimdi sırasıyla farklı türden değişkenleri nasıl tanımlarız bunlara göz atalım.

Sınıfına Göre Değiken Tanımlamak
=

Değişkenlerin belirli türlerde değer almasını sağlamak için `declare` komutunu kullanıyoruz. 

Aşağıdaki tablodan komutun parametrelerine ve yerine getirebildiği işlevlerine göz atabilirsiniz.
 

|Parametre  | İşlev |
|--|--|
|-p|Değişkenin niteliklerini bastırma işlevindedir. Print(yazdır) ifadesinin kısaltmasıdır.|
|-i|Sayısal değişken tanımlama işlevindedir. İnteger(tam sayı) ifadesinin kısaltmasıdır.|
|-a|Dizi tanımlama işlevindedir. Array(dizi) ifadesinin kısaltmasıdır.|
|-f|Fonksiyon özelliği tanımlama işlevindedir. Function(fonksiyon) ifadesinin kısaltmasıdır.|
|-r|Sabit değişken atama işlevindedir. Readonly(yalnızca okunabilir) ifadesinin kısaltmasıdır.|
|-t|Değişkene trace(iz) niteliği verme işlevindedir.|
|-x|Değişkeni export(ihraç) ederek, alt kabuklara aktarma işlevindedir.|

`declare` komutunu kullanıyorken, eğer değişkenlere özellik eklemek istiyorsak `-` işaretini, şayet var olan özellikleri çıkarmak istiyorsak da `+` işaretini eklemek ya da çıkarmak istediğimiz özelliğin parametresini de belirterek kullanmamız yeterli oluyor. 


Sayısal Değişken Tanımlama
-

Anlatımlara ilk olarak sayısal değişken tanımlama işlemi ile başlayalım.
Sayısal değişken tanımlamak için konsola `declare -i değişken tanımı` şeklinde komutumuzu girmemiz gerekiyor. 

Ben **9** değerine sahip **rakam** isimli bir sayısal değişken tanımlamak istediğim için konsola `declare -i rakam="9"` komutumu giriyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/17.png)

Böylelikle **rakam** isimli sayısal değişkenime **9** rakamını atamış oldum ve  bu değişkenim ben aksini istemedikçe yalnızca sayısal ifadeler alan bir değişken olarak sınıflandırılmış oldu.Bu durumu teyit etmek için öncelikle değişkenimin sınıfını sorgulamak üzere `declare` komutunun **p** parametersi ile `declare -p rakam` komutunu giriyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/18.png)

Sizlerin de gördüğü gibi konsol bana çıktı olarak `declare -i rakam` şeklinde bir çıktı bastı. Bu çıktı ile değişkenimizin sayısal bir değişken olduğunu teyit etmiş olsak da kesin olarak emin olmak adına değişkenimize sayısal değerlerin dışında herhangi bir değer atamaya çalışarak bu durumu netleştirelim. 

Bunun için konsola `rakam="test"` komutumu girdikten sonra, değişkenimin durumunu sorgulamak için `declare -p rakam` komutunu kullanıyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/19.png)

Gördüğünüz gibi çıktıda rakam değişkenimin değeri "**0**" olarak karışıma gelmiş oldu. Bunun nedeni değişkenime sonradan atamaya çalıştığım "**test**" ifadesinin sayısal bir karşılığının olmamasıdır. 

Hatırlarsanız değişken tanımlama anlatımlarının başında **rakamlar** isimli değişkene **12345** ifadesini atamış ve bu değişkenimizi bastırmıştık. Şimdi aynı değişkeni atayıp değerini "**"test**" ifadesi ile değiştirerek sayısal değer alma özelliği olan değişkenler ile sıradan değişken arasındaki farkı görelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/20.png)

Gördüğünüz gibi sayısal özellik atamadığım değişkenin içeriğindeki sayısal veriler kolaylıkla değişmiş oldu. Böylelikle sayısal değişkenin sıradan değişken tanımlamaktan farkını kıyaslayarak görmüş olduk.

Ancak tanımladığımız sayısal değişkenler her zaman sayısal değişken olarak kalmak zorunda da değil. Değişkenimizin sınıfını tekrar eski hale getirmek istersek ekleme işleminde kullandığımız **-** işareti yerine  bu sefer **+** işaretini kullanmamız yeterli oluyor. Yani ben **rakam** isimli sayısal değişkenimin, sayısal değişken tutma özelliğini kaldırmak istersem; konsola `declare +i rakam` şeklinde komut girmem yeterli oluyor. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/21.png)

Bu şekilde, `declare` komutunu kullanarak istediğimiz değişkene sayısal değişken özelliği ekleyip çıkartabiliyoruz.



Dizi Tanımlama
-
Birden fazla değeri tek bir değişken içerisine toparlamak istediğimizde dizileri kullanabiliriz. Bu işlem için `declare` komutunun `a` parametresini kullanıyoruz. Komutumuzun kullanımı `declare -a dizi=(değer1 değer2 değer3)` şeklindedir.
Ayrıca `declare` komutunu kullanmadan, dizide yer alacak ifadeleri parantez içine alarak da `dizi=(değer1 değer2 değer3 )` şeklinde dizi belirtebiliyoruz. Buradaki parantezler o değişkenin bir dizi olduğunu otomatik olarak belirtiyor.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/22.png)

Dizilerin kullanımına en basit örnek alışveriş listesi olarak verilebilir. 

Örneğin ben **liste** isimli bir değişken tanımlayıp bu değişkenin içerisine istediğim sayıda değer atayabilir ve atadığım değerleri tek tek çağırabilirim. Örnek olması için; konsola `liste=(su süt çay elma ekmek)` şeklinde komutumu girerek, **liste** isimli değişkene birden fazla değer atamış oluyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/23.png)

Böylelikle her bir değere **0** dan başlayarak sırasıyla birer index değeri atanmış oldu. Yani örneğin **su** ifadesi ilk değer olduğu için **0** index numarasını almışken, **çay** değerinin index numarası **2** olmuş oldu.

Bizler de sıralı şekilde atanan bu index değerleri sayesinde istediğimiz değerleri diziden çağırabiliyoruz.
Örneğin dizide yer alan ilk değeri çağırmak istesem konsola `echo ${liste[0]}` komutunu girmem yeterli oluyor.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/24.png)

Gördüğünüz gibi **0** index numarası ile ilk değerimizi ekran bastırmış olduk.
Bu işlemi aynı şekilde diğer değerlerimizi bastırmak için de kullanabiliriz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/25.png)

Eğer tüm değişkenleri tek sefer bastırmak istersek `*` ya da `@` işaretini kullanabiliriz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/26.png)

Tanımlanmış olan dizi elemanının kaç karakterden oluştuğunu öğrenmek için **#** simgesini kullanarak , komutumuzu `echo ${#dizi[değişken indexi]}` şeklinde giriyoruz. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/27.png)

Ayrıca bu kullanım sadece diziler için değil değişkenler ve sabitler içinde geçerlidir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/28.png)

Eğer komutumuzda index numarası ile herhangi bir dizi elemanı belirtmezsek varsayılan olarak dizide yer alan ilk eleman işleme alınıyor.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/29.png)

Ayrıca dizi içerisinde kaç tane değişken olduğunu öğrenmek için de `#` simgesini ile birlikte index numarası kısmında  `*` simgesini kullanmamız yeterli.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/30.png)




Sabit Değişken Tanımlama
-

Şimdi ise tanımladığımız değişkenin değerinin, değiştirilemez şekilde sabit kalmasını nasıl sağlarız bunu görelim. Bu işlem için `readonly` komutunu ya da `declare` komutunun `r` parametresini kullanabiliyoruz.

Örneğin ben **sabit** isimli bir değişkenin değerini sabitlemek üzere konsola `readonly sabit="sabit değer"` şeklinde komutumu giriyorum. Daha sonra atadığım sabit değeri değiştirmeye çalışarak, değerin gerçekten de sabit olup olmadığını teyit etmek için, sabit isimli değişkenime yeni değer atamaya çalışıyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/31.png)

Ve gördüğünüz gibi **sabit** isimli değişkenimin değeri sabit olduğu için içerisine yeni bir değer atanamadı. 

Ayrıca biliyorsunuz ki sabit değer atama işlemini `readonly` komutu yerine, `declare` komutu ile de gerçekleştirebilirdik. Hemen bu şekilde de bir örnek yapmak adına  konsola `declare -r sabit1="sabit değer 1"` şeklinde de komutumu girip değişkenimin özelliğini `p` parametresi ile teyit ediyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/32.png)

Son olarak bu değerimi de değiştirmeye çalışarak değişkenimin sabit olup olmadığını teyit ediyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/33.png)

Ve yine gördüğünüz gibi atadığımız değişken sabit olduğundan yeni bir değer atanamadı.

**Sabit değişken tanımlarken dikkat edilmesi gereken nokta, sabit değişkenlerin bir kez tanımlandıktan sonra kesinlikle silinip, değiştirilemeyeceğidir**. Sabit değişken bir kez tanımlandıktan sonra sabit şekilde kalır.
Bu durumu teyit etmek için değişkenimizin sabitlik özelliğini `declare +r` komutu ile kaldırmayı deneyelim. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/34.png)

Komutumuzu girdik ancak gördüğünüz gibi değişken sabit değere sahip olduğundan konsol bu işlemin mümkün olmadığını belirtiyor. 
Peki ama sabit değişkenler gerçekten sonsuza kadar tanımlandığı şekilde mi kalıyor ?

Aslında bu durum; yalnızca değişkenin tanımlandığı konsol ekranı için geçerli olduğundan, konsol kapatıldığında tanımlanan tüm değişkenlerle birlikte sabit değişkenler de sıfırlanmasıyla sonuçlanır.
Bu durumun daha net anlamak için lütfen okumaya devam edin.


Değişkenlerin export Edilmesi
=

Bu kısıma kadar temel olarak değişkenleri nasıl tanımlayabileceğimizden ve tanımlama yaparken nelere dikkat etmemiz gerektiğinden bahsettik. Ancak henüz değinmediğimiz ve önemli olan başka bir konu da; değişkenlerin **export** edilmediği sürece yalnızca tanımlandıkları konsol üzerinden çağırılabiliyor olduklarıdır. 

Örneğin bir betik dosyasını çalıştırdığımızda mevcut **kabuk**(**shell**) bu işlem için çatallama(fork) yaparak bir **alt kabuk**(**subshell**) oluşturur ve betiği bu alt kabukta çalıştırır. Daha sonra görev tamamlanınca alt kabuk öldürülerek ana kabuğa dönülür. Böylelikle tek bir kabuk altında birden fazla alt kabuk oluşturularak aynı anda pek çok işlemin gerçekleştirilmesi mümkün olur. Kabuğun çalışma yapısını daha iyi anlamak adına aşağıdaki örnek çalışma şablonuna göz atabilirsiniz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/alt-kabuk.png)

İşte kabuğun çalışma yapısı böyle olduğundan, bizler herhangi bir değişken tanımladığımızda bu değişkenin alt kabuklarda da tanınmasını istiyorsak mutlaka `export` komutu ile değişkenimizi alt kabuklara ulaştırmalıyız.

Bu durumu gözlemlemek için çalışmakta olduğum kabuk üzerinde `degisken="yeni değer"` şeklinde bir değişken tanımlayıp konsola bastırıyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/35.png)

Tanımladığımız kabuk üzerinde değişkenimizi kolaylıkla bastırdık, şimdi de aynı değişkeni betik dosyası içerisinden çağırarak bastırmayı deneyelim. Bu işlem için **test.sh** isimli bir betik dosyası oluşturup, daha öncesinde tanımlamış olduğum değişkeni çağırmak üzere `echo $degisken` komutumu yazıyorum. Ayrıca betik dosyası içerisinde de `degisken1="deneme"` şeklinde yeni bir değişken tanımlayıp `echo $degisken1`komutu ile bu değişkenin çağırılmasını sağlıyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/36.png)

Tanımlamaları yaptık şimdi de betik dosyamızı çalıştırarak sonuçları gözlemleyelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/37.png)

Gördüğünüz gibi betik dosyası içerisinde tanımlamış olduğum **degisken1** basılırken daha önce tanımlamış olduğum **degisken** basılmadı. Bunun nedeni başta da belirtiğim şekilde, tanımlanan değişkenlerin **export** edilmediği sürece yalnızca tanımlandığı kabuk üzerinde çalışabildiğidir.
Biz betik dosyasını çalıştırdığımızda bulunduğumuz kabuk altında hemen bir alt kabuk oluşturuldu ve betik dosyamız bu alt kabuk üzerinde yürütüldü. Dolayısı ile üst kabukta tanımlanmış olan değişken alt kabuğa **export** edilmediği için alt kabuk tarafından tanınamadı ve değeri basılamadı.

Şimdi aynı işlemi export ederek tekrarlayalım.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/38.png)


Gördüğünüz gibi değişkenimizi **export** ettikten sonra alt kabukta çalıştırılan betik dosyası içerisinden de bu değişkeni çağırabildik. Böylelikle `export` komutunun ivleşini test ederek görmüş olduk. Ayrıca `export` komutu yerine aynı işlem için `declare` komutunun `x` parameteresi `declare -x degisken` şeklinde de kullanabilirdik.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/39.png)


Değişken Değerlerin Farklı Şekillerde Bastırılması
=

Bu kısıma kadar pek çok değişken tanımlayıp bu değişkenlerin değerlerini konsola bastırdık. Ancak şu ana kadarki bastırmış olduğumuz değerler bizlerin atadığı değerlerin birebir aynısıydı. Fakat her zaman basılan bu değerlerin tamamına ihtiyaç duymayabiliyoruz. İşte bu gibi durumlarda alacağımız çıktıları düzenlemek, yani örneğin bir kısmını bastırmak ya da bir kısımını silmek gibi işlevleri yerine getirmek için birkaç farklı kullanım şekli bulunuyor. Şimdi genel olarak bu kullanımları ele alalım.

Değerin bir kısmını seçmek :
-

Değişkene atanan değer içerisinde belirli bir kısımı almak istersek komutumuzu **${degisken:başlangıç:uzunluk}**  şeklinde kullanıyoruz.

**Başlangıç :** Seçme işleminin başlanacağı yeri temsil eder. Boş bırakılırsa en baştan itibaren seçer.

**Uzunluk :** Seçme işleminin ne kadar uzunlukta olacağını belirtir. Bu kısım boş bırakılırsa seçme işlemi otomatik olarak değerin sonuna kadar yapılır.

***Örnek Kullanımları;***

**deneme** isimli değişkene "**123456789**" değerini atıyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/40.png)

**" ${deneme::3} "** = değişken değerinin ilk 3 karakteri.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/41.png)

**" ${deneme:2} "** = değişken değerinin 2. karakterinden sonra hepsi. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/42.png)

**" ${deneme:2:4} "** = değişken değerinin 2. karakterinden itibaren 4 karakter.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/43.png)


Değişken değeri silmek :
-

Değişkenimizin çıktısında basılacak olan değerleri silmek için iki farklı kullanım metodu bulunuyor. Bunlardan ilki değerleri başlangıçtan itibaren silen **#** işareti, ikincisi ise tersi şekilde değeri sondan itibaren silen **%** işaretidir. Sırasıyla bu kullanımları açıklayacak olursak;

Örneğin **{}** şeklinde tanımlanmış bir değişkenin değerlerinin **başından** başlayarak;

Öncelikle örnek üzerinden ilerlemek üzere `silinecek=(sal salı salıncak)` şeklinde değişkenimizi tanımlayalım.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/44.png)

**Bir harf grubuna kadar olan kısmını silmek istersek;** `${silinecek[@]##*silinecek_harf_grubu}` komutunu kullanıyorken..

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/45.png)

**Yalnızca ilgili harfleri içeren kısıma kadar olan kısımı baştan itibaren silmek istersek;** `${silinecek[@]#*silinecek_harf}`komutunu kullanıyoruz. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/46.png)

Komut içerisinde yer alan kısımları açıklayacak olursak;

**[@]** şeklinde belirtilen kısım dizideki tüm elemanları kapsıyor.(Bu ifade yerine yıldız(asterix) `*` işaretini de kullanabilirdik.)

Kare işareti(**#**) de silme işlevini yerine getiriyor. Eğer silinecek ifade birleşik harf grubu ise çift kare(**##**) işareti kullanılmalıdır.

Ayrıca silinecek harf veya harf gurubundan önce kullandığımız `*` işareti, ilgili harfe ya da harf gurubuna kadar olan tüm ifadelerin otomatik olarak tamamlanabilmesi sağlıyor.


Ayrıca tüm ifadelerin tek seferde kapsamak yerine özel olarak bir ifadeyi de hedefleyebiliriz, örneğin sadece 3. değerde yer alan **c** harflerine kadar olan kısımı silmek için komutumu `${silinecek[2]#*c}` şeklinde kullanabilirim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/47.png)


Değerlerimizi sondan itibaren silmek üzere;

Aynı komutları bu sefer **%** işareti ile olacak şekilde kullanmamız yeterli.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/48.png)

Bu kullanımları daha iyi anlamak adına lütfen kendiniz de buradaki örnekler haricinde bol bol alıştırma yapın. 


Değişken değerinin değiştirilmesi(Bul-Değiştir İşlemi) :
-

Alacağımız çıktılarda yer alan ifadeleri istediğimiz ifadeler ile değiştirmek istesek, bu işi iki farklı şekilde gerçekleştirebiliyoruz;

Örnek olması açısında içerisinde birden fazla "Linux" ifadesinin geçtiği metni kullanıyor olacağız.

Eğer **yalnızca ilk eşleşmede** yer alan ifadeyi değiştirmek istersek komutumuzu **tek slash(/)** ile `${degisken/aranan/değiştirilecek}` şeklinde kullanmamız gerekiyor.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/49.png)

Şayet **eşleşmelerde yer alan tüm ifadeleri** değiştirmek istersek de bu sefer **çift slash(//)** ile komutumuzu `${degisken//aranan/değiştirilecek}` şeklinde giriyoruz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/50.png)

Çıktılarda yer alan ifadeleri kıyasladığınızda tek ve çift slash kullanımının farkını çok daha net kavrayabilirsiniz. 

Ayrıca fark ettiyseniz daha önce de bahsettiğimiz **küçük büyük harf duyarlılığı bu kullanım için de geçerli** olduğundan, yalnızca aradığımız "**linux**" ifadesi bulunup "**çekirdek**" ifadesi ile değiştirilmiş oldu. 

Bunun dışında değişiklik yapmak istediğiniz ifade illa bir kelime bütünü olmak zorunda değil. Örneğin yalnızca tek bir harfi de değiştirebiliriz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/51.png)


Şimdiye kadar birkaç farklı metod uygulayarak, orjinal değerleri istediğimiz şekilde manipüle edip tam ihtiyacımıza göre çıktılar elde ettik. **Ancak bu aldığımız çıktıların geçici değerler olduğunu ve orjinal değerlerde kalıcı değişikliğe yol açmadığını lütfen unutmayın.** Farklı şekillerde bastırma işlemleri ile bizler sadece aldığımız çıktıları ihtiacımıza göre şekillendirmiş olduk arkadaşlar.

Değişkenlerin Sıfırlanması (unset)
-
Tanımladığımız değişkenleri sıfırlamak yani tanımsız hale getirmek istersek `unset` komutunu kullanabiliyoruz.
Şimdi örnek olması açısından çeşitli değişkenleri sıfırlamayı deneyelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/unset-1.png)
![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/unset-2.png)
![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/unset-3.png)


Gördüğünüz gibi sabit değişkenler hariç diğer değişkenler `unset` komutu sayesinde kolaylıkla sıfırlanabiliyor.
Sabit değişkenlerin sıfırlanmasının ancak değişkenin tanımlandığı kabuğun kapatılması ile mümkün olacağını zaten biliyorsunuz. O yüzden sabit değişkenler hariç, tanımlamış olduğunuz diğer değişkenleri tanımsız yapmak isterseniz `unset` komutunu kullanmanız yeterli.


