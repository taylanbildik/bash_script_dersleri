Değişkenler
=
Bu kısımda değişkenleri ele alacağız, peki ama nedir bu değişkenler ?

Kısaca değişkenler, girdiğimiz değerleri alan veya programın çalışmasıyla bazı değerlerin atandığı veri tutucularıdır.  Biz bir değişkene değer atayarak o değeri tekrar tekrar tanımlamak yerine tek bir değişken üzerinden istediğimiz zaman çağırabiliyoruz. Eğer bu tanımdan bir şey anlamadıysanız sorun yok arkadaşlar, konuyu örnekler ile ele aldıkça tam olarak ne demek istediğimi anlıyor olacaksınız.

Hemen basit bir örnek ile açıklamaya başlayalım;

Değişken tanımlarken öncelikle değişken adını girerek eşittir işaretini koyduktan sonra değişkene atamak istediğimiz değeri tırnak işareti içerisine yazıyoruz.

Örneğin ben `sistem="linux"` şeklinde yazarsam, **sistem** isimli değişkene "**linux**" değerini atamış oluyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/1.png)

Değişkenimin tanımlanıp tanımlanmadığını hemen konsol üzerinden çağırarak kontrol edelim. Tanımladığımız herhangi bir değişkeni çağırırken `echo $degisken` şeklinde komut girmemiz yeterli oluyor. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/2.png)

Bizim tanımladığımız değişken de **sistem** isimli değişken olduğu için konsola `echo $sistem` komutunu girdiğimde, gördüğünüz gibi karşıma "**linux**" ifadesi basılmış oldu. 

Bir örnek daha yapalım ve bu sefer değişkenimize, değer olarak sayı atayalım. Bunun için `rakamlar="12345"` ifadesini konsola giriyorum ve `echo $rakamlar` komutu ile atadığım değişkene ulaşıyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/3.png)

İşte değişken tanımlamak bu kadar basit. Ancak yine de değişken tanımlarken dikkat etmemiz gereken önemli birkaç detay bulunuyor.

Değişken Tanımlanırken Dikkat Edilmesi Gerekenler
-

 - Değişken isimleri tanımlarken **Türkçe karakter kullanmadan** alfanümerik(**A-Z, a-z**) karakter kullanmamız gerekiyor.
 
Örneğin konsola içerisinde Türkçe karakter geçen, `çalı="bitki"` gibi bir değişken tanımlamak istersem, konsol bana çıktı olarak "**komut yok**" hatasını basıyor. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/4.png)
 
Bunun nedeni de değişken tanımlarında Türkçe karakter kullanımının geçersiz olmasıdır arkadaşlar. Bu kullanımın doğrusu Türkçe karakter içermeyen `cali="bitki"` şeklinde olmalıydı. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/5.png)

<hr>
 
- Türkçe karakter dışında, değişken ismi tanımlarken **alt tire işareti haricinde** herhangi bir sembol kullanımı da hataya yol açmaktadır. 

Örneğin ben `yeni-yeni="yeni değer"` gibi bir değişken tanımlamaya kalkarsam , konsol bana çıktı olarak "**komut yok**" hatasını basacaktır. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/6.png)

Bunun nedeni değişken isminde geçen **tire**(**-**)işaretidir. 

Şimdi aynı örneği **alt tire**(**_**) işareti ile deneyereki bu durumu teyit edelim. Bunun için konsola `yeni_yeni="yeni değer"` ifadesini yazıyorum ve tanımladığım değişkeni `echo $yeni_yeni` komutunu girerek sorguluyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/7.png)

Ve gördüğünüz gibi değişken başarılı şekilde tanımlanmış bulunuyor. 

Tekrar belirtmiş olalım, hatalı bir kullanıma yol açmamak adına değişken tanımlarken **alt tire işareti haricinde hiç bir sembol kullanmayın**. Yani **yeni+yeni**..**yeni#yeni**..**yeni@yeni** vb tüm kullanımlar hatalıdır.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/8.png)

<hr>

- Dikkat etmemiz gereken bir diğer husus ise tanımlanacak değişken isimlerinin **kesinlikle rakam ile başlamamasıdır**. Fakat başlangıcı hariç, değişken isimlerinde rakam kullanılabilir. 

Yani örneğin herhangi bir değişken tanımlarken **1kitap** hatalı bir kullanım iken **kitap1** ya da **kit1ap** doğru kullanıma örnektir. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/9.png)

Rakam başta olmadığı sürece tüm kombinasyonlar rakam kullanımına uygundur.
(**k1itap**..**ki2tap**..**kit3ap**..**kit33ap**..**kita555p**.. vb.)

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/10.png)

<hr>

- Bir başka dikkat edilmesi gereken ayrıntı da; değişken tanımlarken kullanılan tanımların, Linux sistemlerinde olduğu gibi **büyük küçük harf duyarlılığına** sahip olduğudur. 

Örneğin tamamı büyük harflerden oluşan `TEST="ilk ifade"` şeklindeki bir tanım ile tamamı küçük harflerden oluşan `test="ikinci ifade"` tanımı, bash diline göre iki farklı değişkeni temsil eder. Hemen `echo` komutu yardımıyla bu durumu teyit edelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/11.png)

Gördüğünüz gibi aynı isime sahip olan biri küçük diğeri büyük harflerden oluşan iki değişken, sistem tarafından iki farklı değişken olarak algılanarak konsola ayrı ayrı çıktılar basmış oldu. 

<hr>

- Bunun haricinde değişken tanımlarken **eşittir**(**=**) işaretinin **sağında ve solunda boşluk olmamasına** dikkat etmemiz gerekiyor. Aksi takdirde sistem bizlerin değişken tanımlamak istediğini anlayamadığından, kaçınılmaz olarak konsola "**komut yok**" şeklinde hata çıktısı basıyor. 

**Aşağıdaki kullanımlar yanlış kullanımlara örnektir.**

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/12.png)

Ayrıca değişkenlerin değerini belirtirken kullandığımız tırnak işaretleri, değerin birden fazla kelime bütünü içerdiği durumda sistem tarafından **değerin tamamının** doğru algılanabilmesi adına çok önemlidir. Yani örneğin ben `kalem="kırmızı"` ya da `kalem1=mavi` şeklinde değişken tanımlayabilirim. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/12-1.png)

Fakat değerin `kalem="kırmızı pilot"` gibi daha fazla öge içerdiği durumlarda mutlaka tırnak içerisinde yazılması gerekiyor. Bu durumu aşağıdaki çıktılara göz atarak teyit edebilirsiniz. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/12-2.png)

<hr>

Hatırlarsanız konu anlatımının başında değişkenlerin program çalışırken farklı değerler alabildiğinden bahsetmiştik. Bu da eğer bizler herhangi bir kısıtlama getirmezsek, sürekli olarak değişkenlerin üzerine yeni değerler yazılabileceği anlamına geliyor. Bu durumu daha iyi anlamak adına `spor="tenis"` komutu ile **spor** isimli bir değişken tanımlayalım ve `echo $spor` komutu ile değişkenimizi çağıralım.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/13.png)

Gördüğünüz gibi bu şekilde **spor** isimli değişkeni ne zaman çağırsam karşıma **tenis** değeri basılmış oluyor. Ancak değişkenin değerini özellikle sabitlemediğimiz sürece, istenildiği zaman bu değer değiştirilebilir. Değişken değerini değiştirmek için aynı isimli değişkeni farklı bir değer ile tekrar tanımlamamız yeterli oluyor arkadaşlar. 

Hemen aynı değişkeni bu sefer **futbol** değeri ile tanımlayıp, bu durumu teyit edelim. Konsola `spor="futbol"` şeklinde yazıyorum ve `echo` komutu ile değişkenimin yeni değerini teyit ediyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/14.png)

Gördüğünüz gibi önceleri **spor** değişkenini çağırdığımda karşıma **tenis** değeri basılıyorken, değişkenimizi tekrar tanımlamamız yani diğer bir deyişle üzerine yeni değer yazmamız sonucu, aldığımız çıktı **futbol** olarak değişmiş oldu. 

İlerleyen kısımlarda değiştirilemez(sabit(readonly)) değişkenler tanımlama konusuna da ayrıca değiniyor olacağız ancak şimdilik basit değişken tanımlama işlemleri ile yapılan tanımlamaların değiştirilebilir değerler aldığını unutmayın lütfen.

Değişkenler yeniden tanımlanabildiği için sistemin çalışmasında rol oynayan, varsayılan olarak tanımlanmış olan değişkenlerle aynı isimlere sahip yeni değişkenler oluşturmama konusunda da dikkatli olmamız gerekiyor. Eğer farkında olmadan sisteme ait değişkenleri yeniden tanımlarsanız, sistemle ilgili pek çok soruna yol açabilirsiniz. Bu yüzden, tanımlayacağınız değişkenin daha önce kullanılıp kullanılmadığından tam olarak emin değilseniz, değişkeninizi tanımlamadan önce sistem üzerinde var olup olmadığını kontrol etmenizde fayda var.

Konsola `echo` yazıp `$` işareti koyduktan sonra <kbd>**Tab**</kbd> tuşuna basarak tanımlı tüm değişkenleri listeleyebilirsiniz. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/15.png)
![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/16.png)

Bu sayede halihazırda sistemde tanımlı olan değişkenlere müdahale etmeden daha bilinçli şekilde yeni değişkenler tanımlayabilirsiniz.


Şimdiye kadar pek çok değişken tanımladık ancak tanımladığımız değişkenler herhangi bir sınıfta yer almıyordu.  Buradaki sınıftan kastım tanımladığımız değişkenin hangi türden veriyi içerisinde barındırabileceğinin belirlenmesidir. Yani örneğin değişken sayısal bir değişken mi olacak yoksa bir diziyi mi temsil edecek ya da değişkenimiz sabit değerli mi olacak henüz bunlardan bahsetmedik.

Şimdi sırasıyla farklı türden değişkenleri nasıl tanımlarız bunlara göz atalım.

Sınıfına Göre Değişken Tanımlamak
=

Değişkenlerin belirli türlerde değer almasını sağlamak için `declare` komutunu kullanıyoruz. 

Aşağıdaki tablodan komutun parametrelerine ve yerine getirebildiği işlevlerine göz atabilirsiniz.
 

|Parametre  | İşlev |
|--|--|
|-p|Değişkenin niteliklerini bastırma işlevindedir. **p**rint(yazdır) ifadesinin kısaltmasıdır.|
|-i|Sayısal değişken tanımlama işlevindedir. **i**nteger(tam sayı) ifadesinin kısaltmasıdır.|
|-a|Dizi tanımlama işlevindedir. **a**rray(dizi) ifadesinin kısaltmasıdır.|
|-r|Sabit değişken atama işlevindedir. **r**eadonly(yalnızca okunabilir) ifadesinin kısaltmasıdır.|
|-x|Değişkeni **e**xport(ihraç) ederek, alt kabuklara aktarma işlevindedir.|

`declare` komutunu kullanıyorken; eğer değişkenlere özellik eklemek istiyorsak `-` işaretini, şayet var olan özellikleri çıkarmak istiyorsak da `+` işaretini, eklemek ya da çıkarmak istediğimiz özelliğin parametresini de belirterek kullanmamız yeterli oluyor. 


Sayısal Değişken Tanımlamak
-

Anlatımlara ilk olarak sayısal değişken tanımlama işlemi ile başlayalım.

Sayısal değişken tanımlamak için konsola `declare -i değişken="değeri"` şeklinde komutumuzu girmemiz gerekiyor. 

Ben **9** değerine sahip **rakam** isimli bir sayısal değişken tanımlamak istediğim için konsola `declare -i rakam="9"` komutumu giriyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/17.png)

Böylelikle **rakam** isimli sayısal değişkenime **9** rakamını atamış oldum ve  bu değişkenim ben aksini istemedikçe yalnızca sayısal ifadeler alan bir değişken olarak sınıflandırılmış oldu. Bu durumu teyit etmek için öncelikle değişkenimin sınıfını sorgulamak üzere `declare` komutunun **p** parametersini kullanarak `declare -p rakam` komutunu giriyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/18.png)

Sizlerin de gördüğü gibi konsol bana çıktı olarak `declare -i rakam="9"` şeklinde bir çıktı bastı. Bu çıktı ile değişkenimizin sayısal bir değişken olduğunu teyit etmiş olsak da kesin olarak emin olmak adına, değişkenimize sayısal değerlerin dışında herhangi bir değer atamaya çalışarak bu durumu netleştirelim. 

Bunun için konsola `rakam="test"` komutumu girdikten sonra, değişkenimin durumunu sorgulamak üzere `declare -p rakam` komutunu kullanıyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/19.png)

Gördüğünüz gibi çıktıda rakam değişkenimin değeri "**0**" olarak karşıma gelmiş oldu. Bunun nedeni değişkenime sonradan atamaya çalıştığım "**test**" ifadesinin sayısal bir karşılığının olmamasıdır. 

Hatırlarsanız değişken tanımlama anlatımlarının başında **rakamlar** isimli değişkene **12345** ifadesini atamış ve bu değişkenimizi bastırmıştık. Şimdi aynı değişkeni atayıp değerini "**"test**" ifadesi ile değiştirerek, sayısal değer alma özelliği olan değişkenler ile sıradan değişken arasındaki farkı görelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/20.png)

Gördüğünüz gibi sayısal özellik atamadığım değişkenin içeriğindeki sayısal veriler kolaylıkla değişmiş oldu. Böylelikle sayısal değişken ile sıradan değişken tanımlamanın farkını kıyaslayarak görmüş olduk.

Ancak tanımladığımız sayısal değişkenler her zaman sayısal değişken olarak kalmak zorunda da değil. Değişkenimizin sınıfını tekrar eski hale getirmek istersek ekleme işleminde kullandığımız **-** işareti yerine  bu sefer **+** işaretini kullanmamız yeterli oluyor. Yani ben **rakam** isimli sayısal değişkenimin, sayısal değişken tutma özelliğini kaldırmak istersem; konsola `declare +i rakam` şeklinde komut girmem yeterli oluyor. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/21.png)

Bu şekilde, `declare` komutunu kullanarak istediğimiz değişkene sayısal değişken özelliği ekleyip çıkartabiliyoruz.



Dizi Tanımlamak
-
Birden fazla değeri tek bir değişken içerisine toparlamak istediğimizde dizileri kullanabiliyoruz. 

Dizi tanımlamak için `declare` komutunun `a` parametresini `declare -a dizi=(değer1 değer2 değer3)` şeklinde kullanabiliyoruz.

Ayrıca `declare` komutunu kullanmadan, dizide yer alacak ifadeleri parantez içine `dizi=(değer1 değer2 değer3 )` şeklinde alarak da dizi belirtebiliyoruz. Buradaki parantezler o değişkenin bir dizi olduğunu otomatik olarak belirtiyor.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/22.png)

Dizilerin kullanımına en basit örnek alışveriş listesi olarak verilebilir. 

Örneğin ben **liste** isimli bir değişken tanımlayıp bu değişkenin içerisine istediğim sayıda değer atayabilir ve atadığım değerleri tek tek çağırabilirim. Örnek olması için; konsola `liste=(su süt çay elma ekmek)` şeklinde komutumu girerek, **liste** isimli değişkene birden fazla değer atamış oluyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/23.png)

Böylelikle her bir değere **0 dan başlayarak** sırasıyla birer index numarası atanmış oldu. Yani örneğin **su** ifadesi ilk değer olduğu için **0** index numarasını almışken, 3. sıradaki **çay** değerinin index numarası **2** olmuş oldu.

Bizler de sıralı şekilde atanan bu index değerleri sayesinde istediğimiz değerleri diziden çağırabiliyoruz.

Örneğin dizide yer alan ilk değeri çağırmak istersem konsola `echo ${liste[0]}` komutunu girmem yeterli oluyor.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/24.png)

Gördüğünüz gibi **0** index numarası ile ilk değerimizi ekran bastırmış olduk.

Bu işlemi aynı şekilde diğer değerlerimizi tek tek bastırmak için de kullanabiliriz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/25.png)

Eğer tüm değişkenleri tek sefer bastırmak istersek `*` ya da `@` işaretini kullanabiliriz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/26.png)

Tanımlanmış olan dizi elemanının kaç karakterden oluştuğunu öğrenmek için **#** simgesini kullanarak , komutumuzu `echo ${#dizi[değişken indexi]}` şeklinde giriyoruz. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/27.png)

Üstelik bu kullanım sadece diziler için değil değişkenler ve sabitler için de geçerlidir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/28.png)

Eğer komutumuzda index numarası ile herhangi bir dizi elemanı belirtmezsek varsayılan olarak dizide yer alan ilk eleman işleme alınıyor.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/29.png)

Ayrıca dizi içerisinde kaç tane değişken olduğunu öğrenmek için de `#` simgesini ile birlikte index numarası kısmında  `*` simgesini kullanmamız yeterli.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/30.png)




Sabit Değişken Tanımlamak
-

Şimdi ise tanımladığımız değişkenin değerinin, değiştirilemez şekilde sabit kalmasını nasıl sağlarız bunu görelim. Bu işlem için `readonly` komutunu ya da `declare` komutunun `r` parametresini kullanabiliyoruz.

Örneğin ben **sabit** isimli bir değişkenin değerini sabitlemek üzere konsola `readonly sabit="sabit değer"` şeklinde komutumu giriyorum. Daha sonra atadığım sabit değeri değiştirmeye çalışarak, değerin gerçekten sabit olup olmadığını teyit etmeye çalışıyorum.

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

Aslında bu durum; yalnızca değişkenin tanımlandığı konsol ekranı için geçerli olduğundan, konsol kapatıldığında tanımlanan tüm değişkenlerle birlikte sabit değişkenlerin de sıfırlanmasıyla sonuçlanır.
Bu durumun daha net anlamak için lütfen okumaya devam edin.


Değişkenlerin export Edilmesi
=

Bu kısıma kadar temel olarak değişkenleri nasıl tanımlayabileceğimizden ve tanımlama yaparken nelere dikkat etmemiz gerektiğinden bahsettik. Ancak henüz değinmediğimiz ve önemli olan başka bir konu da; değişkenlerin **export** edilmediği sürece yalnızca tanımlandıkları konsol üzerinden çağırılabiliyor olduklarıdır. 

Örneğin bir betik dosyasını çalıştırdığımızda mevcut **kabuk**(**shell**) bu işlem için **çatallama**(**fork**) yaparak bir **alt kabuk**(**subshell**) oluşturur ve betiği bu alt kabukta çalıştırır. Daha sonra görev tamamlanınca alt kabuk öldürülerek ana kabuğa dönülür. Böylelikle tek bir kabuk altında birden fazla alt kabuk oluşturularak aynı anda pek çok işlemin gerçekleştirilmesi mümkün olur. Kabuğun çalışma yapısını daha iyi anlamak adına aşağıdaki örnek çalışma şablonuna göz atabilirsiniz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/alt-kabuk.png)

İşte kabuğun çalışma yapısı böyle olduğundan, bizler herhangi bir değişken tanımladığımızda bu değişkenin alt kabuklarda da tanınmasını istiyorsak mutlaka `export` komutu ile değişkenimizi alt kabuklara ulaştırmalıyız.

Bu durumu gözlemlemek için çalışmakta olduğum kabuk üzerinde `degisken="yeni değer"` şeklinde bir değişken tanımlayıp konsola bastırıyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/35.png)

Tanımladığımız kabuk üzerinde değişkenimizi kolaylıkla bastırdık, şimdi de aynı değişkeni betik dosyası içerisinden çağırarak bastırmayı deneyelim. Bu işlem için **test.sh** isimli bir betik dosyası oluşturup, daha öncesinde tanımlamış olduğum değişkeni çağırmak üzere `echo $degisken` komutumu yazıyorum. Ayrıca betik dosyası içerisinde de `degisken1="deneme"` şeklinde yeni bir değişken tanımlayıp `echo $degisken1`komutu ile bu değişkenin çağırılmasını sağlıyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/36.png)

Tanımlamaları yaptık şimdi de betik dosyamızı çalıştırarak sonuçları gözlemleyelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/37.png)

Gördüğünüz gibi betik dosyası içerisinde tanımlamış olduğum **degisken1** basılırken daha önce tanımlamış olduğum **degisken** basılmadı. Bunun nedeni başta da belirtiğim şekilde, tanımlanan değişkenlerin `export` edilmediği sürece yalnızca tanımlandığı kabuk üzerinde çalışabildiğidir.
Biz betik dosyasını çalıştırdığımızda bulunduğumuz kabuk altında hemen bir alt kabuk oluşturuldu ve betik dosyamız bu alt kabuk üzerinde yürütüldü. Dolayısı ile üst kabukta tanımlanmış olan değişken alt kabuğa `export` edilmediği için alt kabuk tarafından tanınamadı ve değeri basılamadı.

Şimdi aynı işlemi `export` ederek tekrarlayalım.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/38.png)


Gördüğünüz gibi değişkenimizi `export` ettikten sonra alt kabukta çalıştırılan betik dosyası içerisinden de bu değişkeni çağırabildik. Böylelikle `export` komutunun işlevini test ederek görmüş olduk. Ayrıca `export` komutu yerine aynı işlem için `declare` komutunun `x` parameteresini `declare -x degisken` şeklinde de kullanabilirdik.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/39.png)

Değişkenlerin Sıfırlanması (unset)
-
Tanımladığımız değişkenleri sıfırlamak yani tanımsız hale getirmek istersek `unset` komutunu kullanabiliyoruz.
Şimdi örnek olması açısından çeşitli değişkenleri sıfırlamayı deneyelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/unset-1.png)
![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/unset-2.png)
![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/unset-3.png)


Gördüğünüz gibi sabit değişkenler hariç diğer değişkenler `unset` komutu sayesinde kolaylıkla sıfırlanabiliyor.
Sabit değişkenlerin sıfırlanmasının ancak değişkenin tanımlandığı kabuğun kapatılması ile mümkün olacağını zaten biliyorsunuz. O yüzden sabit değişkenler hariç, tanımlamış olduğunuz diğer değişkenleri tanımsız yapmak isterseniz `unset` komutunu kullanmanız yeterli.


Değişken Değerlerin Farklı Şekillerde Bastırılması
=

Bu kısıma kadar pek çok değişken tanımlayıp bu değişkenlerin değerlerini konsola bastırdık. Ancak şu ana kadar ki bastırmış olduğumuz değerler bizlerin atadığı değerlerin birebir aynısıydı. Fakat her zaman basılan bu değerlerin tamamına ihtiyaç duymayabiliyoruz. İşte bu gibi durumlarda alacağımız çıktıları düzenlemek, yani örneğin bir kısmını bastırmak ya da bir kısımını silmek gibi işlevleri yerine getirmek için birkaç farklı kullanım şekli bulunuyor. Şimdi genel olarak bu kullanımları ele alalım.

Değerin bir kısmını bastırmak :
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

Değişkenimizin çıktısında basılacak olan değerleri silmek için iki farklı kullanım metodu bulunuyor. 

Bunlardan ilki değerleri **başlangıçtan itibaren** silen **#** işareti, ikincisi ise tersi şekilde değeri **sondan itibaren** silen **%** işaretidir. Sırasıyla bu kullanımları açıklayacak olursak;

Öncelikle örnek üzerinden ilerlemek üzere `silinecek=(sal salı salıncak)` şeklinde değişkenimizi tanımlayalım.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/44.png)

Örneğin `silinecek=(sal salı salıncak)` şeklinde tanımlanmış bir değişkenin değerlerinin **başından** başlayarak;

**Bir harf grubuna kadar olan kısmını silmek istersek;** `${silinecek[@]##*silinecek_harf_grubu}` komutunu kullanıyorken..

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/45.png)

**Yalnızca ilgili harfleri içeren kısıma kadar olan kısımı baştan itibaren silmek istersek;** `${silinecek[@]#*silinecek_harf}`komutunu kullanıyoruz. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/46.png)

Komut içerisinde yer alan kısımları açıklayacak olursak;

**[@]** şeklinde belirtilen kısım dizideki tüm elemanları kapsıyor.(Bu ifade yerine yıldız(asterix) `*` işaretini de kullanabilirdik.)

Kare işareti(**#**) de silme işlevini yerine getiriyor. Eğer silinecek ifade birleşik harf grubu ise çift kare(**##**) işareti kullanılmalıdır.

Ayrıca silinecek harf veya harf gurubundan önce kullandığımız `*` işareti, ilgili harfe ya da harf grubuna kadar olan tüm ifadelerin otomatik olarak tamamlanabilmesi sağlıyor.


Ayrıca tüm ifadelerin tek seferde kapsamak yerine özel olarak bir ifadeyi de hedefleyebiliriz, örneğin dizide yer alan 3. değerde yer alan **c** harflerine kadar olan kısımı silmek için komutumu `${silinecek[2]#*c}` şeklinde kullanabilirim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/47.png)

<hr>

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


Şimdiye kadar birkaç farklı metod uygulayarak, orjinal değerleri istediğimiz şekilde manipüle edip tam ihtiyacımıza göre çıktılar elde ettik. **Ancak bu aldığımız çıktıların geçici değerler olduğunu ve orjinal değerlerde kalıcı değişikliğe yol açmadığını lütfen unutmayın.** Farklı şekillerde bastırma işlemleri ile bizler sadece aldığımız çıktıları ihtiyacımıza göre şekillendirmiş olduk arkadaşlar.

Ayrıca yeri gelmişken değişkenleri bastırırken kullandığımız `echo` komutununun çoklu işlevlerini kullanarak farklı çıktılar elde etmeyi de ele almak istiyorum. Hangi parametrenin hangi işlevde olduğunu kısaca aşağıdaki tabloya bakayarak anlayabilirsiniz.

|Seçenekler| Açıklama |
|--|--|
|**-e**|Ters eğik çizgi ile belirtilen özelliklerin yorumlanmasını sağlar. |
|**-n**|Sonraki satırı atlamaz.|
|**\n**|Yeni satıra atlar.|
|**\b**|Soldan bir karakter siler. |
|**\e**|Sağdan bir karakter siler. |
|**\c**|Sağında yer alan her şeyi siler. |
|**\r**|Satır başına göre tamamlama yapar.|
|**\t**|Tab tuşu görevi görür.|
|**\v**|Dikey tab görevi görür.|
|**\\\\**|Ters eğik çizgi basmak üzere kullanılır. |
|**\a**|Çıktı ile birlikte konsoldan uyarı sesi çıkmasını sağlar.|
|**$(komut)**|Komutların echo komutu üzerinden basılmasını sağlar.|
|**'komut'**| Komutların echo komutu üzerinden basılmasını sağlar.|


Şimdi sırasıyla işlevleri örnekler üzerinden açıklayarak devam edelim.

-e
-

`echo` komutunun ardından gireceğimiz **ters slash** işaretli özel parametrelerin doğru şekilde yorumlanabilmesini sağlar. Yani `echo` komutunun farklı bastırma seçeneklerini kullanmak istiyorsak mutlaka **-e** parametresini kullanmamız gerekiyor. Bu durumu örnekler üzerinden çok daha net kavramış olacaksınız.

-n
-

Satır atlanmasını engeller. İşlevini anlamak için aşağıdaki iki çıktıyı dikkatlice incelemeniz yeterlidir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo0.png)

\n
-

Kullanıldığı yerden sonra, bir alt satıra geçerek çıktıları bastırır. Yani bir satır atlamış olur.

Örnek olması açısından **"test metni"** ifadesini alt alta basılacak şekilde ayarlamak istiyorum.
Bunun için `echo` komutunun ardından **-e** parametresini kullanıp bir alt satıra geçmek istediğim kısıma **\n** ifadesini ekliyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo1.png)

Gördüğünüz gibi **metni** ifadesinin hemen öncesinde kullanmış olduğum **\n** parametresi **metni** ifadesinin bir alt satırda basılmasını sağladı. Aynı işlemi **-e** parametresi olmadan yapmaya çalışsaydık, `echo` komutu **\n** ifadesinin işlevini algılayamayacağından **metni** ifadesini bir alt satıra basamayacaktı. Bu durumu aşağıdaki çıktıya bakarak gözlemleyebilirsiniz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo2.png)

\b
-

Parametrenin kullanıldığı yerin solundaki bir karakteri silme işlevindedir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo3.png)

\e
-

Parametrenin kullanıldığı yerin sağındaki bir karakteri silme işlevindedir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo4.png)

\c
-

Parametrenin kullanıldığı yerin sağındaki her şeyi silme işlevindedir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo5.png)

Gördüğünüz gibi sağ tarafta yer alan her şeyi sildiğinden, bir alt satıra geçme işlevi de siliniyor ve çıktı ile yeni komut girişi aynı satırda gözüküyor. Hatta son çıktıya dikkatlice bakacak olursanı, satırın sonuna eklemiş olduğum **\c** parametresi tıpkı **-n** parametresi gibi işlev görerek bir sonraki satıra atlamadan aynı satırdan devam edilmesini sağlıyor.

\r
-

Parametrenin kullanıldığı kısımdan önceki kısımda yer alan karakter sayısına göre, parametrenin kullanıldığı kısımdan sonraki karakterler önceki karakterlerden tamamlanır. 

Yani örneğin **12345 abcd** şeklinde bir çıktıda kullanırsak;

Eğer **abcd** ifadesinden hemen önce **\r** parametresini eklersem, **abcd** 4 karakterden oluştuğundan ve önündeki **12345** ifadesi ise 5 karakterden oluştuğundan **abcd** ifadesinin eksik kalan 5. karakteri ifadenin 5. karakterinden otomatik tamamlanıyor. Yani **\r** parametresi kullanılan yerden önceki ifadenin uzunluğu ile, **\r** parametresinden sonraki ifadenin uzunluğu eşit olmak zorunda. **\r** parametresinden sonraki kısım, önceki kısıma oranla daha kısa bir ifade ise otomatik olarak eksik kalan kısımlar **\r** parametresinden önceki ifadeden tamamlanıyor.

Bu açıklamadan bir şey anlamadıysanız aşağıdaki çıktılara dikkatli şekilde bakarak ve komutu bizzat uygulayarak ne demek istediğimi rahatlıkla anlayabilirsiniz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo6.png)

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo7.png)

\t
-
Kullanıldığı kısımdan sonrası için tab tuşu görevi görür.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo8.png)

\v
-

Kullanıldığı kısımdan sonrasını aynı hizada bir alt satırda basar, bir nevi dikey tab görebi görür.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo9.png)

3'lü ya da 4'lü Ters Slash
-

Eğer bastıracağımız ifadenin içerisinde **ters slash** geçiyorsa bunun **-e** parametresinin özellikleri dışında algılanabilmesi için ya **3** ya da **4**'lü şekilde kullanılması gerekiyor. **-e** parametresini kullanmadığımızda zaten ters slash ifadesi özel bir anlam kazanmadığından bu kadar çok yazmamız gerekmeiyor, ancak tek bir ifade içerisinde hem **-e** parametresinin sağlayacağı avantajları kullanmak hem de ters slash işareti basmak isteyebiliriz. İşte bu durumlarda bu şeklide çoklu kullanım şarttır.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo10.png)


\a
-

Basılan ifade ile birlikte eğer konsol destekliyorsa uyarı sesinin çıkmasını sağlar, bir nevi zildir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo11.png)

$(komut) ya da 'komut'
-

**Dolar** işaretinden sonra **parantez içerisinde** yazacağımız komutla ya da **ters tırnak**(<kbd>Alt Gr + ,</kbd>) içerisinde yazacağımız komut ile `echo` komutu üzerinden konsol komutlarını bastırabiliriz. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo12.png)

Dikkat ettiyseniz `echo` komutu üzerinden konsol komutlarını bastırırken her seferinde **çift tırnak** kullandık. Bunun nedeni `echo` komutu ile kullanılan tek tırnak ifadesinin konsol komutlarını bastırmıyor olmasıdır. Bu durumu aşağıdaki çıktılara bakarak gözlemleyebilirsiniz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/echo13.png)


Ayrıca hatırlatmak isterim ki; aldığımız çıktılardan da görebileceğiniz gibi, `echo` komutu üzerinden konsol komutlarını çalıştırdığımızda, renklendirme ve içerik düzeni gibi bash kabuğunun sahip olduğu pek çok işlevsel özellik de kayboluyor. Yani bu kullanımı genel olarak yalnızca temel çıktılar elde etmede kullanacağımızı unutmayın lütfen.



Sistemde Tanımlı Ortam(Çevre) Değişkenleri
=

Bu kısıma kadar kendimiz nasıl değişken tanımlarız bunu ele aldık. Şimdi de sistemde tanımlı olan değişkenlerden bahsederek anlatımlara devam edelim.


Ortam Değişkenlerini Görüntülemek
-

Sistemin işleyişinde pek çok konuda kolaylık sunan çeşitli ortam değişkenleri vardır.  Bunları görmek istersek komut satırına <code>set</code> , <code>env</code> ya da <code>printenv</code> komutlarından birini ihtiyacımıza göre kullanabiliriz. Bu üç komut arasındaki farklar aşağıdaki şekildedir.

**set :** Shell'e ait olan değişkenlerin adını ve değerlerini verir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/set.png)

**printenv :** Sistemde bulunan bütün çevresel değişkenleri verir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/printenv.png)

**env :** Sistemde bulunan bütün "export" edilmiş yani dışa(alt kabuklara) aktarılmış değişkenlerle beraber değişkenleri gösterir.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/env.png)

Ben komutların tam çıktıları çok uzun olduğu için hepsini burada vermedim, ancak sizler 3 komutu da kullanarak aralarındaki farkları mutlaka gözlemleyin.

Ayrıca mevcut kabuk üzerinde tanımlı değişkenleri görmek için de `echo $` komutundan sonra <kbd>Tab</kbd> tuşuna basmanız yeterli.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/15.png)
![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/16.png)

Temel ve sık kullanılan değişkenlerden birkaçını da kısaca açıklayacak olursak:

**SHELL:** Çalışmakta olan kabuk programının adını ve yerini verir.

**PATH:** Konsola komut girildiğinde, komut için gereken ilgili dosyaların aranacağı dizinler diğer bir adıyla yol.

**HOME:** Kullanıncının ev dizinini içeren değişken.

**TERM:** Komut satırı uygulamalarının hangi terminalde çalışacağını belirtir. Birçok çeşidi vardır ancak xterm yaygın şekilde karşımıza çıkmaktadır.

Ortam değişkenlerinin değerlerini tek tek kontrol etmek istersek, konsola <code>echo $ORTAM_DEĞİŞKENİ</code> şeklinde komut vererek ilgili bilgilere ulaşabiliriz. Örneğin **PATH** değişkenine bir bakalım.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/p.png)

Gördüğünüz üzere konsol **PATH** değişkeni çıktı olarak **/usr/local/sbin: /usr/local/bin: /usr/sbin: /usr/bin: /sbin: /bin** değerini basmış oldu.

Çıktının bize gösterdiği yani konsolun demek istediği şu: 

**Konsoldan girilen herhangi bir komutu çalıştırabilmem için sırasıyla bu <kbd>/usr/local/sbin: /usr/local/bin: /usr/sbin: /usr/bin: /sbin: /bin</kbd> dizinlere bakmam gerek. Eğer verilen komutun çalıştırılabilir dosyası bu dizinlerin içerisinde ise çalıştırırım, yoksa çalıştıramam.**

Çıktıda görülen iki nokta üst üste (<kbd>:</kbd>) işareti ile ayrılmış dizinlere **PATH(yol)** ortam değişkeni deniyor. 

Hazır yeri gelmişken gelin **PATH** yoluna ekli olmayan bir programı bu yola ekleyip konsoldan vereceğimiz bir komutla direk olarak çalışmasını sağlayalım. Yani örneğin ben konsola gedit yazdığımda dosya konumu belirtmeme gerek kalmadan gedit programı otomatik olarak açılıyorsa, bu PATH yolu üzerinde tanımlı olmasındandır. Örnek olması açısında biz de daha önce yazmış olduğumuz **selam.sh** isimli betik dosyamızı bu şekilde istenilen konumdan ismi ile çalıştırılabilir kılalım. Adım adım ilerleyelim;

Benim çalıştırmak istediğim dosya daha önce yazmış olduğum **selam.sh** isimli betik dosyası. 

Ben bu dosyanın konumundayken dosyayı `./selam.sh` komutu ile çalıştırabiliyorum ancak dosyanın bulunduğu dizin dışından herhangi bir konumdayken bu dosyamı doğrudan çalıştıramıyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/p1.png)

Yapmamız gereken şey, dosyamızın bulunduğu konumu **PATH** yoluna eklemek ya da dosyamızı **PATH** yolu üzerinde yer alan bir konuma taşımak olacak arkadaşlar. Bu sayede konsola `selam.sh` komutunu girdiğimizde **PATH** yolu taranacak ve dosyamız bu yol üzerindeki herhangi bir konumda ise bulunup çalıştırılacak. Her iki şekilde de bu durumu test edelim.

Öncelikle dosyamı **PATH** yolu üzerinde bulunan bir konuma taşıyorum. Ve ardından dosyamı herhangi bir konumdayken yalnızca ismini belirterek çalıştırmayı deniyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/p2.png)

Gördüğünüz gibi betik dosyam PATH yolu üzerinde bulunan bir konuma eklenince her yerden ismi girilerek çalıştırılabilir oldu.

Aynı şekilde dosyamızın bulunduğu konumu **PATH** yoluna ekleyerek de her yerden ulaşılabilir kılabiliriz. Bunun için **/etc** dizini altında bulunan ve her oturum açılışında otomatik olarak okunan **profile** dosyası içerisine `PATH="path yoluna eklenecek dizin":$PATH` şeklinde yeni **PATH** yolunu belirtmeliyiz.

Ben taşımış olduğum **selam.sh** dosyasını eski konumuna taşıyarak, bu konumu yani root kullanısının ana dizinini **profile** dosyasına `PATH="/root/:$PATH"` şeklinde ekleyerek her yerden ulaşılabilir kılıyorum. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/p3.png)

Yaptığımız değişikliklerin geçerli olabilmesi için oturumu kapatıp tekrar giriş yaptıktan sonra, değişikliğin geçerli olup olmadığını test etmek için **PATH** değişkenini bastırıp farklı konumlardan betik dosyamızı çalıştırmayı deneyebiliriz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/p4.png)

Ve en nihayetinde **PATH** değişkeni sayesinde betik dosyamızı her yerden çalıştırılabilir yapmış olduk.

Neticede sizlerin de gördüğü gibi; bizlerin tanımladığı değişkenler ile sistemde varsayılan olarak tanımlı değişkenleri bastırıken komut kullanımı açısından hiç bir fark bulunmuyor. Buradaki tek küçük fark, sistemde varsayılan olarak tanımlı değişkenlerin daha ayırt edici olması açısında genellikle istisnalar dışında tamamı büyük harflerden oluşacak şekilde tanımlanmış olmalarıdır.

Şimdiye kadar hem kendi tanımladığımız hem de sistemde varsayılan olarak tanımlı değişkenleri ele aldık. Şimdi de tanımlanan değişkenlerin kapsamlarını 3 kategori altında tek tek ele alalım; 

- **konsola(terminal) özel :** yalnızca açık olan mevcut konsoldaki uygulamalar için kullanılabilen
- **kullanıcıya özel:** yalnızca tek kullanıcı için geçerli olan ve o kullanıcının her oturum açtığında kullanabildiği
- **sistem geneli :** sisteme öntanımlı olarak ayarlanmış sürekli kullanılabilir

Gelin şimdi teker teker kullanımlarına değinelim.

### Mevcut Konsola Özel

**Sadece o an kullanmakta olduğumuz konsola özel olan ve konsolu kapattıktan sonra sıfırlanan ortam değişkenidir.** Aşağıdaki örnek ile adım adım açıklayalım bu durumu:

Konsola `isim="taylan"` şeklinde bir değişken tanımlıyıp, bu değişkeni bastırıyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/53.png)

Daha sonra yeni bir konsol açarak **isim** değişkenini konsola bastırmayı deniyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/54.png)

Gördüğünüz gibi yeni açmış olduğum konsoldaki çıktı boş oldu. Bunun nedeni tanımladığım değişkenin, bu şekilde tanımlandığına yalnızca tanımlandığı konsol üzerinden çağırılabileceğidir. **Yani bu şekilde yapılan tüm değişiklikler sadece yapıldığı konsol için geçerli oluyor.** 

Hatta bu değişkeni **export** etmediğimizde alt kabuklarda dahi bastırılamadığını sizler de biliyorsunuz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/55.png)


### Kullanıcıya (Oturuma) Özel

Daha önce BASH kabuğundan bahsetmiştik ve mevcut sistemimizde bulunup bulunmadığını da kontrol etmiştik. 

BASH, her oturum açtığımızda tüm ayarlarını ve davranışlarını kullanıcıya özel olan ve kullanıcının ana dizininde bulunan <kbd>.bashrc</kbd> isimli gizli bir dosyadan okuyor. Yani eğer bizler mevcut oturumumuzdaki değişkenler üzerinde kalıcı değişiklik yapmak istiyorsak; değişiklikleri <kbd>.bashrc</kbd> isimli dosyaya eklememiz gerekiyor ki, her oturum açtığımızda sistem burada yaptığımız değişiklikleri otomatik olarak görüp sisteme tanımlayabilsin.

Örnek olması açısında bu sefer de `soyisim="bildik"` değişkenini **yalnızca root kullanıcısına özel** olarak tanımlamayı ele alıyorum.

Öncelikle ana dizinde bulunan <kbd>.bashrc</kbd> dosyasını açmak üzere <code>nano ~/.bashrc</code> komutunu girelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/56.png)

Komutumuzu girdikten sonra karşımıza konsol ekranı içerisinde <kbd>.bashrc</kbd> dosyasının içeriği geliyor. Klavyedeki yön tuşlarını kullanarak en alt satıra inelim ve root kullanıcısına özel olarak tanımlamak istediğimiz değişkeni `export soyisim="bildik"` şeklinde girip, <kbd>Ctrl + X</kbd> tuş kombinasyonu ile yaptığımız değişikliği kaydedelim. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/57.png)


Artık böylelikle değişiklik yaptığımız bu root kullanıcı oturumunu ne zaman açarsak, tanımladığımız **soyisim** değişkeni geçerli olacak. 

Ancak dosyada değişikliği yaptığımız anda değişken sisteme hemen tanımlanmıyor. Bunun nedeni <kbd>.bashrc</kbd> dosyasının oturum açılırken okunmasıdır. Yani yaptığımız değişikliklerin geçerli olabilmesi için oturumun kapatılıp tekrar açılması ya da alternatifi olan `source` komutunun `source .bashrc` şeklinde kullanıması gerekiyor.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/58.png)

Şimdi **root** kullanıcı hesabında ve baska bir kullanıcı hesabı olan **ali** kullanıcı hesabında **soyisim** değişkenini bastırmayı deneyelim.

Öncelikle **root** kullanıcı hesabında konsola `echo $soyisim` yazarak değişken değerimi bastırıyorum.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/59.png)

Hatta root kullanıcı hesabındayken birden fazla konsol üzerinden bile **soyisim** değişkenini çağırabiliyorum. Hatırlarsanız yanlızca konsola özel olarak tanımladığımız değişkeni yalnızca tanımlandığı konsol üzerinde bastırabiliyorken, kullanıcıya özel olarak tanımlanmış değişkeni kullanıcı hesabında açtığımız tüm konsollar üzerinden bastırabiliyoruz.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/60.png)

Şimdi de **ali** isimli kullanıcı hesabına geçerek `echo $soyisim` komutu ile değişkeni bastırmayı deneyelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/61.png)

Gördüğünüz gibi **root** kullanıcısına özel olarak tanımladığımız **soyisim** değişkenine, **root** kullanıcısı dışında diğer kullanıcılar ulaşamıyor.


### Sistem Genelinde

Eğer yaptığımız değişiklik bütün kullanıcı oturumlarında aynı şekilde geçerli olsun istiyorsak, değişkenin sistemde her oturum açıldığında okunan bir dosyada bulunması gerekiyor. Bu yüzden tanımlayacağımız değişkeni <kbd>/etc</kbd> dizini altında yer alan <kbd>bash.bashrc</kbd> dosyasına uygun şekilde eklemeliyiz. 

Öncelikle dosyamızı açmak üzere konsola <code>nano /etc/bash.bashrc</code> komutunu girelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/62.png)

Bu kez de örnek olması için `lokasyon="istanbul"` değişkenini <kbd>bash.bashrc</kbd> dosyamıza ekleyip kaydedelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/63.png)

Sıra geldi değişikliklerin sistem tarafından tanınmasına. Yapılan değişikliğin sistem bütününde geçerli olabilmesi için daha önce de bahsi geçen <code>source</code> komutunu <kbd>bash.bashrc</kbd> dosyası için <code>source /etc/bash.bashrc</code> şeklinde kullanalım. 

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/64.png)

Ardından değişikliklerin geçerli olup olmadığını denemek için birden fazla kullanıcı hesabında **lokason** değişkenini bastırmayı deneyelim.

Öncelikle **root** kullanıcısı için test edelim.
![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/65.png)

Şimdi **ali** kullanıcısı üzerinden değişkenimizi bastırmayı deneyelim.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/66.png)

Son olarak da **can** kullanıcısı üzerinden değişkenimizi çağıralım.

![alt text](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/De%C4%9Fi%C5%9Fkenler/67.png)

Çıktılarımızın hepsinde **lokasyon** değişkeninin değeri olarak **istanbul** ifadesini gördüğümüze göre, değişkenimizi sistem genelinde tanımlamayı başarmışız demektir. Yaptığımız bu değişiklik bütün kullanıcılar için yani sistem geneli için geçerlidir. Bu durumu başka bir hesap oluşturarak kendiniz de gözlemleyebilirsiniz.

Ayrıca değişiklikleri geri almak isterseniz eklediğiniz ifadeyi ilgili dosyadan silin ve sistemi <code>source ilgili_dosya_adı</code> şeklindeki komut bütünü ile yeniden konfigüre edin, böylelikle bütün değişiklikler sıfırlanmış olacaktır.
