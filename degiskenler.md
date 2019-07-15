Değişkenler
=
Bu kısımda değişkenleri ele alacağız, peki ama nedir bu değişkenler ?
Kısaca değişkenler, girdiğimiz değerleri alan veya programın çalışmasıyla bazı değerlerin atandığı veri tutucularıdır.  Biz bir değişkene değer atayarak o değeri tekrar tekrar tanımlamak yerine tek bir değişken üzerinden istediğimiz zaman çağırabiliyoruz. Eğer bu tanımdan bir şey anlamadıysanız sorun yok arkadaşlar, konuyu örnekler ile ele aldıkça tam olarak ne demek istediğimi anlıyor olacaksınız.
Hemen basit bir örnek ile açıklamaya başlayalım;
Değişken tanımlarken öncelikle değişken adını girerek eşittir işaretini koyduktan sonra değişkene atamak istediğimiz değeri tırnak işareti içerisine yazıyoruz.
Örneğin ben `sistem="linux"` şeklinde yazarsam, sistem isimli değişkene "linux" değerini tanımlamış oluyorum. Şimdi de değişkenimin tanımlanıp tanımlanmadığını hemen konsol üzerinden çağırarak kontrol edelim. 
Tanımladığımız herhangi bir değişkeni çağırırken `echo $degisken` şeklinde komut girmemiz yeterli oluyor. Bizim tanımladığımız değişken de sistem isimli değişken olduğu için konsola `echo $sistem` komutunu girdiğimde, gördüğünüz gibi karşıma "linux" ifadesi basılmış oluyor. 

Bir örnek daha yapalım ve bu sefer değişkenimize değer olarak sayı atayalım. Bunun için `rakamlar="12345"` ifadesini konsola giriyorum ve `echo $rakamlar` komutu ile atadığım değişkene ulaşıyorum. İşte değişken tanımlamak bu kadar basit. Ancak yine de değişken tanımlarken dikkat etmemiz gereken önemli bir kaç detay bulunuyor.

Değişken Tanımlanırken Dikkat Edilmesi Gerekenler
-

 - Değişken isimleri tanımlıyorken Türkçe karakter kullanmadan alfanümerik(A-Z, a-z) karakter kullanmamız gerekiyor.
 Örneğin konsola içerisinde Türkçe karakter geçen, `çalı="bitki"` gibi bir değişken tanımlamak istersem, konsol bana çıktı olarak "böyle bir komut yok" hatasını basıyor. Bunun nedeni de değişken tanımlarında Türkçe karakter kullanımının geçersiz olmasıdır arkadaşlar. Bu kullanımın doğrusu Türkçe karakter içermeyen `cali="bitki"` şeklinde olmalıydı. 
 
- Türkçe karakter dışında değişken tanımlarken alt tire işareti haricinde herhangi bir sembol kullanımı da hataya yol açmaktadır. Örneğin ben `yeni-yeni="yeni değer"` gibi bir değişken tanımlamaya kalkarsam , konsol bana çıktı olarak "komut yok" hatasını basacaktır. Bunun nedeni değişken isminde geçen **tire**(**-**)işaretidir. 
Şimdi aynı örneği **alt tire**(**_**)ile deneyerek bu durumu teyit edelim. Bunun için konsola `yeni_yeni="yeni değer"` ifadesini giriyorum ve tanımladığım değişkeni `echo $yeni_yeni` komutunu girerek sorguluyorum. Ve gördüğünüz gibi değişken başarılı şekilde tanımlanmış bulunuyor. Tekrar belirtmiş olalım, hatalı bir kullanıma yol açmamak adına değişken tanımlarken **alt tire işareti haricinde hiç bir sembol kullanmayın**. Yani **yeni+yeni**..**yeni#yeni**..**yeni&yeni** vb tüm kullanımlar hatalıdır.


- Dikkat etmemiz gereken bir diğer husus ise tanımlanacak değişken isimlerinin kesinlikle rakam ile başlamamasıdır. Fakat başlangıcı hariç değişken isimlerinde rakam kullanılabilir. 
Yani örneğin herhangi bir değişken tanımlarken **1kitap** hatalı bir kullanım iken **kitap1** ya da **kit1ap** doğru kullanıma örnektir. Rakam başta olmadığı sürece tüm kombinasyonlar rakam kullanımına uygundur.
**k1itap**..**ki2tap**..**kit3ap**..**kit33ap**..**kita555p**.. vb.
 
- Bir başka dikkat edilmesi gereken ayrıntı da; değişken tanımlarken kullanılan tanımların, Linux sistemlerinde olduğu gibi büyük küçük harf duyarlılığına sahip olduğudur. 
Örneğin tamamı büyük harflerden oluşan `TEST="ilk ifade"` şeklindeki bir tanım ile tamamı küçük harflerden oluşan `test="ikinci ifade"` tanımı, bash diline göre iki farklı değişkeni temsil eder. Hemen `echo` komutu yardımıyla bu durumu teyit edelim.
Gördüğünüz gibi biri küçük diğer büyük harflerden oluşan iki değişken de sistem tarafından farklı algılanarak konsola ayrı ayrı çıktılar basmış oldu. 

- Bunun haricinde değişken tanımlarken **eşittir**(**=**) işaretinin sağında ve solunda boşluk olmamasına dikkat etmemiz gerekiyor. Aksi takdirde sistem bizlerin değişken tanımlamak istediğini anlayamadığından, kaçınılmaz olarak konsola "komut yok" şeklinde hata çıktısı basıyor. Aşağıdaki kullanımlar yanlış kullanımlara örnektir.

- Ayrıca değişken tanımlarken ve tanımlamış olduğumuz değişkeni çağırırken kullandığımız çift ve tek tırnak kullanımı ile ilgili de dikkat etmemiz gereken bir kaç önemli husus bulunuyor. Sırasıyla bu detaylara değinecek olursak.
Değişken tanımlarken, atayacağımız değeri tırnak içine yazdırmak istersek uygulayabileceğimiz iki metod bulunuyor.
Örneğin ben konsola tam olarak çift tırnak işareti ile birlikte **"metin"** ifadesini bastırmak istersem; bastırmak istediğim ifadeyi tek tırnak içerisine alarak `' "metin" '` şeklinde yazmam gerekiyor. Şayet tek tırnak ile ekrana basılsın istersem de bu sefer tek tırnaklı ifadeyi çift tırnak içerisine alarak `" 'metin' "` şeklinde yazmam gerekiyor.
Bu yöntem haricinde herhangi bir ifadeyi tırnak içerisinde bastırmak için tırnak işaretlerinden önce **ters slash**( \ ) işaretini \"metin\" şeklinde kullanmamız yeterli oluyor.

Tüm bunların dışında konu anlatımın başında değişkenlerin programlar çalışırken farklı değerleri alabildiğinden bahsetmiştik. Bu da eğer bizler herhangi bir kısıtlama getirmezsek, sürekli olarak değişkenlerin  üzerine yeni değerler yazılabileceği anlamına geliyor. Bu durumu daha iyi anlamak adına spor="tenis" şeklinde bir değişken tanımlayalım. Gördüğünüz gibi bu şekilde spor isimli değişkeni ne zaman çağırsam karşıma tenis değeri basılmış oluyor. Ancak bu değişkenin değerini özellikle sabitlemediğimiz sürece sonsuza kadar bu şekilde kalmak zorunda değil, yani bu değeri değiştirmek mümkün. Bunun için aynı isimli değişkeni farklı bir değer ile tekrar tanımlamamız yeterli oluyor arkadaşlar. Hemen aynı değişkeni bu sefer futbol değeri ile tanımlayıp, bu durumu teyit edelim. Konsola spor="futbol" şeklinde yazıyorum. Ve echo komutu ile teyit ediyorum. Gördüğünüz gibi önceleri spor değişkenini çağırdığımda karşıma tenis değerini basıyorken, değişkenimizi tekrar tanımlamamız yani diğer bir değişle üzerine yeni değer yazmamız sonucu aldığımız çıktı futbol olarak değişmiş oldu. İlerleyen kısımlarda değiştirilemez değişkenler tanımlama konusuna ayrıca değiniyor olacağız ancak şimdilik basit değişken tanımlama işlemleri ile yapılan tanımlamaların değiştirilebilir değerler aldığını unutmayın lütfen.

Değişkenler yeniden tanımlanabildiği için sistemin çalışmasında rol oynayan, varsayılan olarak tanımlanmış olan değişkenlerle aynı isimlere sahip yeni değişkenler oluşturmama konusunda da dikkatli olmamız gerekiyor. Eğer farkında olmadan sisteme ait değişkenleri yeninden tanımlarsanız sistemle ilgili pek çok soruna yol açabilirsiniz. Bu yüzden, tanımlayacağınız değişkenin daha önce kullanılıp kullanılmadığından tam olarak emin değilseniz öncelikle sistem üzerinde var olup olmadığını kontrol etmenizde fayda var.
Peki ama nasıl kontrol edebiliriz derseniz,  konsola echo yazıp $ işareti koyduktan sonra tab tuşuna basarak tanımlı tüm değişkenleri listeleyebilirsiniz. Bu sayede halihazırda sistemde tanımlı olan değişkenlere müdahale etmeden daha bilinçli şekilde yeni değişkenler tanımlayabilirsiniz.

Değişkenlerin EXPORT edilmesi !
=


Bu kısıma kadar temel olarak nasıl değişken tanımlanacağından ve tanımlama yaparken nelere dikkat etmemiz gerektiğinden bahsettik. Ancak şu ana kadar ele aldığımız ve örneklediğimiz değişkenler herhangi bir sınıfta yer almıyordu. Buradaki sınıftan kastım tanımladığımız değişkenin hangi türden veriyi içerisinde barındırabileceğinin belirlenmesidir. Yani örneğin değişken sayısal bir değişken mi olacak yoksa bir diziyi mi temsil edecek henüz bunlardan bahsetmedik.

Şimdi sırasıyla farklı türden değişkenleri nasıl tanımlarız bunlara göz atalım.
Değişkenlerin belirli türlerde değer almasını sağlamak için `declare` komutunu kullanıyoruz. 

Aşağıdaki tablodan komutun parametrelerine ve yerine getirebildiği işlevlerine göz atabilirsiniz.
|Parametre  | İşlev |
|--|--|
|-a|Dizi tanımlama..|
|-f|Fonksiyon isimleri belirtme..|
|-i|Sayısal değişken tanımlama|
|-p|Değişken niteliklerini, tanımlanma şeklini,kriterlerini gösterme.|
|-r|Değişkenin sadece okunabilir(readonly) yani değerinin sabit olduğunu ayarlama.|
|-t|Her değişkene trace(iz) niteliği verme.|
|-x|Her değişkeni diğer komutlar için işaretleme.|

Kısaca tekrar etmemiz gerekirse declare komutunu kullanıyorken, eğer değişkenlere özellik eklemek istiyorsak - işaretini, şayet var olan özellikleri çıkarmak istiyorsak da + işaretini çıkarmak istediğimiz özelliğin parametresini belirterek kullanmamız yeterli oluyor.


Sayısal Değişken Tanımlama
-

Anlatımlara ilk olarak sayısal değişken tanımlama işlemi ile başlayalım.
Sayısal değişken tanımlamak için konsola `declare -i değişken tanımı` şeklinde komutumuzu girmemiz gerekiyor. Ben **rakam** isimli bir sayısal değişken tanımlamak istediğim için konsola `declare -i rakam="9"` komutumu giriyorum. Böylelikle rakam isimli sayısal değişkenime 9 rakamını atamış oldum ve  bu değişkenim ben aksini istemedikçe yalnızca sayısal ifadeler alan bir değişken olarak sınıflandırılmış oldu.
Bu durumu teyit etmek için öncelikle değişkenimin sınıfını sorgulamak üzere `declare` komutunun **p** parametersi ile `declare -p rakam` komutunu giriyorum. Sizlerin de gördüğü gibi konsol bana çıktı olarak `declare -i rakam` şeklinde bir ifade bastı. Bu çıktı ile değişkenimizin sayısal bir değişken olduğunu teyit etmiş olsak da kesin olarak emin olmak adına değişkenimize sayısal değerlerin dışında herhangi bir değer atamaya çalışarak bu durumu netleştirelim. 
Bunun için konsola `rakam="test"` komutumu giriyorum. Daha sonra değişkenimin durumunu sorgulamak için `declare -p rakam` komutunu kullanıyorum. Ve sizlerin de gördüğü üzere çıktıda rakam değişkenimin değeri "0" olarak karışıma gelmiş oldu. Bunun nedeni değişkenime sonradan atamaya çalıştığım "test" ifadesinin sayısal bir karşılığının olmamasındır. Neticede herhangi bir değişkenin sayısal değişken olarak tanımladıktan sonra sayısal değerlerin dışında herhangi bir değer almadığını test ederek, rakam isimli değişkenimizin kesin olarak sayısal bir değişken olduğunu teyit etmiş olduk.

Ancak tanımladığımız sayısal değişkenler her zaman sayısal değişken olarak kalmak zorunda değil. Değişkenimizin sınıfını tekrar eski hale getirmek istersek ekleme işleminde kullandığımız - işareti yerine  bu sefer + işaretini kullanmamız yeterli oluyor. Yani ben rakam isimli sayısal değişkenimin sayısal değişen tutma özelliğini kaldırmak istersem konsola declare +i rakam şeklinde komut girmem yeterli oluyor. Bu şekilde declare komutunu kullanarak istediğimiz değişkene sayısal değişken özelliği ekleyip çıkartabiliyoruz.

Sabit Değişken Tanımlama
-

Şimdi ise tanımladığımız değişkenin değerinin değiştirilemez şekilde sabit kalmasını nasıl sağlarız bunu görelim. Bu işlem için readonly komutunu ya da declare komutunun r parametresini kullanabiliyoruz.
Örneğin ben sabit isimli bir değişkenin değerini sabitlemek üzere konsola readonly sabit="sabit değer" şeklinde komutumu giriyorum. Daha sonra atadığım sabit değeri değiştirmeye çalışarak, değerin gerçekten de sabit olup olmadığını teyit etmek için sabit isimli değişkenime yeni değer atamaya çalışıyorum. Ve gördüğünüz gibi sabit isimli değişkenimin değeri sabit olduğu için içerisine yeni bir değer atanamadı. Sabit değer atama işlemini declare komutu ile de gerçekleştirebilirdik, hemen bu şekilde de  bir örnek yapmalım. Yeni bir sabit değer atamak üzere konsola declare -r sabit1="sabit değer 1" şeklinde de komutumu giriyorum. Ve bu değerimi de değiştirmeye çalışarak değişkenimin sabit olup olmadığını teyit ediyorum. Ve yine gördüğünüz gibi atadığımız değişken sabit olduğundan yeni bir değer atanamadı. Ayrıca biliyorsunuz değişkenimizin durumunu declare komutunun p parametresi ile de kontrol edip sabit değişken olduğunu teyit edebiliriz. 
Sabit değişken tanımlarken dikkat edilmesi gereken nokta, sabit değişkenlerin bir kez tanımlandıktan sonra kesinlikle silinip, değiştirilemeyeceğidir. Sabit değişken bir kez tanımlandıktan sonra sabit şekilde kalır.
Bu durumu teyit etmek için değişkenimizin sabitlik özelliğini declare komutu ile kaldırmayı deneyelim. Bunun için konsola declare +r sabit komutumu giriyorum. Ve gördüğünüz gibi değişken sabit değere sahip olduğundan konsol bu işlemin mümkün olmadığını belirtiyor.

Dizi Tanımlama
-
Birden fazla değeri tek bir değişken içerisine toparlamak istediğimizde dizileri kullanabiliriz. Bu işlem için declare komutunun a parametresini kullanıyoruz. Komutumuzun kullanımı declare -a dizi=(değer1 değer2 değer3) şeklindedir.
Ayrıca declare komutunu kullanmadan dizi=(değer1 değer2 değer3 ) şeklinde de dizi belirtebiliyoruz.

Dizilerin kullanımına en basit örnek alışveriş listesi olarak verilebilir. 

Örneğin ben liste isimli bir değişken tanımlayıp bu değişkenin içerisine istediğim sayıda değer atayabilir ve atadığım değerleri tek tek çağırabilirim. Örnek olması için konsola liste=(su süt çay elma ekmek) şeklinde komutumu girerek, liste isimli değişkene birden fazla değer atamış oldum. 

Böylelikle her bir değere 0 dan başlayarak sırasıyla birer index değeri atanmış oldu. Yani örneğin su ifadesi ilk değer olduğu için 0 index numarasını almışken, çay değerinin index numarası 2 olmuş oldu.
Bizler de bu sıralı şekilde atanan index değerleri sayesinde istediğimiz değerleri diziden çağırabiliyoruz.
Örneğin dizide yer alan ilk değeri çağırmak istesem konsola echo ${liste[0]} komutunu girmem yeterli oluyor.

Gördüğünüz gibi 0 index numarası ile ilk değerimizi ekran bastırmış olduk.
Bu işlemi aynı şekilde diğer değerlerimizi bastırmak için de kullanabiliriz.

Eğer tüm değişkenleri bastırmak istersek * ya da @ işaretini kullanabiliriz.

Ayrıca kaç tane değişken olduğunu öğrenmek için de # simgesini değişkenimizden önce kullanmamız yeterli. echo ${#dizi[*]}


Tüm değişken numaralarını sıralı şekilde bastırmak istersek de bu sefer ! işaretini kullanmamız gerekiyor. echo ${!dizi[*]}
