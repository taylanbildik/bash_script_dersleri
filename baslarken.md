Başlarken
=
Gerekli çalışma ortamını kurduk ve artık çalışmak için hazırız. Anlatımlara başlamadan belirtmem gerekiyor ki biz bu eğitimde komutların kullanımını ayrıntılı şekilde ele almayacağız. Komutları **senaryo** haline getirme yani **scripting** kısmına odaklanacağız. 
Bunun nedeni de konu kapsamını mümkün oldukça dağıtmadan verimli şekilde öğrenmenizi sağlamaktır. Ancak ben yine de komutları kullandıkça kullandığım komutlar hakkında kısa hatırlatmalarda bulunacağım. 

Kısacası bu eğitimden verim alabilmeniz için temel linux komutlarını ve kullanımını biliyor olmanızı şiddetle tavsiye ederim. Şayet bu konuda eksiğiniz varsa, benim bir önceki video eğitimim olan "[Kali Linux ile Sıfırdan Temel Linux Eğitimi](https://www.udemy.com/kali-linux-ile-sifirdan-temel-linux-egitimi/?couponCode=DOKUMAN)" kursuma kaydolmanızı ya da "[Temel Linux Eğitimi](https://github.com/taylanbildik/Linux_Dersleri#s%C4%B1ral%C4%B1-%C5%9Fekilde-konu-konu-linux-komut-sat%C4%B1r%C4%B1-dok%C3%BCmantasyon-m%C3%BCfredat%C4%B1)" dokümantasyonuma göz atamnızı öneririm. Zira bu eğitim temel linux eğitimimin devamı niteliğinde, eğitimden maksimum verim alabilmek adını her iki eğitimi de bir bütün olarak ele almanız çok daha iyi olacaktır.

Bu girizgahtan sonra artık esas konumuza dönebiliriz. 

Öncelikle kullanmakta olduğumuz sistemde varsayılan olarak hangi kabuk programı kullanılıyor buna bakalım.
Bakmak için birden fazla yol bulunuyor, örneğin konsola `echo $SHELL` komutunu girersek konsol bize mevcut oturumda kullanılan **shell** yani **kabuk** programını çıktı olarak basıyor.

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/1.png)

Bunun dışında eğer süreç sorgusu yaparsak da karşımıza çalışmakta olan shell programı çıkacaktır. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/2.png)

Bu şekilde sistemde kullanılmakta olan mevcut kabuk programını kolaylıkla öğrenebiliyoruz. 

Ayrıca sistemde yalnızca tek bir kabuk programı da bulunmuyor, bunu da **etc** dizini altında yer alan **shells** isimli dosyanın içeriğine bakarak teyit edebiliriz.Konsola `cat /etc/shells` komutunu girerek dosyamızın içeriğini sorgulayalım. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/3.png)

Gördüğünüz gibi sistemde yüklü bulunan kabuk programlarının hepsi bu dosya içerisinde listelenmiş bulunuyor. Listeye baktığınızda sizde yer alan kabuk program çeşitleri bende listelenmiş olanlardan farklı olabilir. Bunun nedeni sistemde yer alan kabuk program çeşitlerinin, kullanılan dağıtıma göre değişkenlik gösterebiliyor olmasındandır. Yani benimle bire bir aynı çıktıları almadıysanız da bir problem yok. 

En nihayetinde, daha önce de belirttiğimiz şekilde birden fazla kabuk programının olduğunu ve bunların aynı sistemde yüklü bulunabileceğini de hep birlikte teyit etmiş olduk.

Şimdi asıl odak noktamız olan bash kabuk programını ele alarak ilk scriptimizi yazmaya başlayalım.

Script Dosyası(Betik) Oluşturma
-

Bash script yazarken ilk olarak dosyanın başına **#!/bin/bash** ifadesini eklememiz gerekiyor. Neden diyecek olursanız, bu satır sonraki alt satırların hangi kabuk tarafından yorumlanacağını bildiren standart bir tanımdır ve  komutların doğru yorumlanabilmesi için her bash scriptinde olmalıdır. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/4.png)

Program çalıştırıldığında sistem tarafından öncelikle ilk satır okunur ve ilk satırda geçen kabuk diline göre program ilgili kabuk dili aracılığı ile çalıştırılır. Şayet ilk satıra hiç bir ifade eklemezseniz program varsayılan olarak mevcut kabuk üzerinden script dosyasını çalıştırmayı dener. Yani aslında mevcut sisteminizde kullanılan kabuk bash ise, **#!/bin/bash** ifadesini betik dosyanıza eklemeseniz de betik dosyanız sistemde varsayılan kabuk bash olduğundan sorunsuz şekilde çalışacaktır. Ancak yine de yazmış olduğunuz betik dosyasının diğer sistemlerde de doğru şekilde çalıştırılabilmesi için bu ifadeyi eklemek son derece önemlidir. Zira çoğu sistem bash kabuğunu varsayılan olarak kullansa da, istisnai durumlarda farklı kabukların kullanıldığı da olabiliyor.

Bu biraz da clean code denilen düzenli(temiz) kod yazma kültürünün bir parçası, ve bu gibi alışkanlıklar uzun vadede verimli çalışmalar ortaya koymak adına oldukça önemli. İlerleyen zamanlarda kendi yazmış olduğunuz programları açıp incelediğinizde, ya da diğer insanların yazmış olduğu kapsamlı programları incelerken bu gibi düzenli çalışmaların, programın çalışma yapısını anlamada ne kadar kolaylık sağladığını sizler de görmüş olacaksınız.

Evet, neticede script içerisinde kullanılan kabuk program çeşidini dosyamızın en başına yazdığımıza göre artık script yazmaya tamamen hazırız. 

İlk scriptimize standart örnek olan konsol ekranına çıktı basan program örneği ile başlayalım istiyorum.
Bunun için konsola çıktı basan komutumuz olan `echo` komutunu kullanacağız. Örneğin ben konsola `echo "selamlar"` yazarsam çıktı olarak **selamlar** ifadesi konsola basılıyor gördüğünüz gibi. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/5.png)

İşte bizler de bu komutu betik dosyamız içerisine yazıp kaydedersek, bu dosyamızı her çalıştırdığımızda konsol ekranına **selamlar** ifadesi basılacak. 

Hemen test edelim, ben `echo "selamlar"` komutumu betik dosyamın içerisine yazıp, dosyamı "**selam.sh**" ismi ile kaydediyorum. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/6.png)

Dosyamı kaydederken dosya isminin sonunda **.sh** ifadesini eklemem mecburi olmasa da biraz önce bahsettiğimiz düzenli çalışma adına önemli bir ayrıntı. Yine de betik dosyamız, sonunda **sh** ifadesi olmadan da çalışabilir ancak ileride hangi dosyaların betik dosyası olduğunu anlama konusunda dosyaların sonlarındaki **sh** ifadeleri bizlere yardımcı olabilir. Zira linux sistemlerinde dosyayı çalıştırırken dosyanın uzantısının bir önemi yoktur ancak bu gibi uzantıları eklemek dosyanın daha sonra kolay bulunabilmesi adına sınıflandırmaya katkı sunar. Bu durumu daha iyi anlamak adına örneğin yüzlerce dosyanın bulunduğu bir klasör ve bu klasördeki dosyaların hiç birinde ayırt edici uzantı bulunmadığı bir durum hayal edin. Böyle bir durumda hangi dosyanın betik dosyası ya da farklı bir dosya olduğunu anlamanın tek yolu, dosyaların her birini tek tek açarak içlerine bakmayı gerektirir. Tahmin edebileceğiniz gibi bu işlemde inanılmaz vakit alacaktır.  Bu gibi vakit kayıplarını önlemenin en ideal yolu dosya isimlerinin sonunda dosya türlerini belirterek, dosyaları sınıflandırabilir kılmaktır. 

Daha somut bir örnek görmek adına örneğin ben içerisinde bir çok dosyanın bulunduğu klasörede iken konsola 
`ls *.sh` gibi kısacık bir komut girerek sonunda **.sh** ifadesi geçen tüm betik dosyalarını tek seferde listeleyebiliyorum. 
 
![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/7.png)
![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/8.png)

Ayrıca dosyalara uzantı eklemek, dosyayı çalıştırabilecek programların dosyaları kolay algılayabilmesini de sağlar. Yani kısacası ben dosyamı sonunda **sh** ifadesi olmadan da kaydetsem çalışacaktır ancak bu ifadeyi ekleyerek kazanacağım düzen sayesinde eklemek oldukça mantıklıdır.

Dosya isimlendirmedeki ayrıntıya da değindiğimize göre şimdi dosyamızı çalıştırmak için kullanabileceğimiz yöntemlere göz atalım.

Betik Dosyalarını Çalıştırmak 
-

Yazmış olduğumuz betiği çalıştırmanın birden fazla yolu bulunmaktadır. Bunlar içinde biri, konsola `bash betik dosyası adı` şeklinde komut vermektir. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/9.png)

Ayrıca bir diğer yol da `bash` yerine `sh` ifadesini kullanarak konsola `sh betik dosyası adı` şeklinde komutumuzu girmektir. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/10.png)

Burada yapmış olduğumuz işlem, betik yazarken kullanmış olduğumuz kabuk dilini konsola ifade ederek betik dosyasının çalıştırılmasını sağlamak oldu. Biz betik dosyamızı oluştururken **sh** kabuk dilinin gelişmiş hali olan **bash** kabuk dilini kullandığımız için, konsola her iki şekilde de yani **bash** ya da **sh** ifadeleri ile de betik dosyamızın çalıştırılabileceği kabuk dilini ifade etmiş olduk.

Bash ile sh arasındaki farkı merak ediyorsanız, belirttiğim şekilde bash kabuk dili sh kabuk dilininin daha da gelişmiş halidir. Bu gelişmeler daha çok kullanıcı deneyimini arttırmaya yönetilik işlevselliklerin eklenmesi yönündedir. Örneğin bash kabuğunu kullanıyorken konsola bir komutun yarısını yazıldıktan sonra <kbd>Tab</kbd> tuşuna basılırsa komutun geri kalan kısmı otomatik olarak tamamlanıyor. İşte bu gibi özellikler kullanıcı deneyimini arttırmaya, dolayısı ile sistem yönetimini daha verimli hale getirmeye yöneliktir. Yani sh ile bash kabuk dillerinin temel yapıları benzer olup, işlevsellik bakımından farklılık gösterdiklerinden, bash kabuk dili ile yazdığımız betik dosyasını hem sh hem de bash ile çalıştırabiliyoruz.

Ayrıca betik dosyamızı konsola `./betik` şeklinde komut girerek de çalıştırabiliyoruz. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/11.png)

Ancak bu kullanımda diğer iki kullanımdan farklı olarak, dosyamızın çalıştırma yetkisinin bulunması gerekiyor. Aksi takdirde gördüğünüz gibi dosyamız erişim yetkisi hatası("Erişim engellendi") belirterek çalıştırılamıyor. Hatta `ls -la` komutu ile dosyamızın yetkilerini inceleyecek olursak, dosyamızda çalıştırma yetkisinin bulunmadığını görüyoruz. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/12.png)

Bu sorunu aşmak için dosyamıza `chmod` komutu ile gereken çalıştırma yetkisini vermemiz gerekiyor.

Bunun için konsola `chmod +x selam.sh` şeklinde komutumu giriyorum ve `ls -la` komutu ile dosyamın aldığı yetkiyi teyit ediyorum. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/13.png)

Gördüğünüz gibi vermiş olduğumuz yetki ile birlikte konsol çıktımızda dosyamızın renki yeşile dönerek, artık çalıştırılabilir bir dosya olduğunu belirtiyor. Hemen dosyamızı çalıştırarak bu durumu teyit edelim. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/14.png)

Ve gördüğünüz gibi betik dosyamız aldığı yetki sayesinde sorunsuz şekilde çalışmış oldu.

Dosyamızı çalıştırdık ancak, dosyamızı çalıştırmak üzere girmiş olduğumuz komutun çalışma yapısını daha iyi anlamak adına, kullanmış olduğumuz `./ ` komutunu açıklamak istiyorum.

Komutumuzda kullandığımız `.`(nokta) ifadesi bildiğiniz gibi şu anda bulunduğumuz konumu ifade ediyor. 

Noktadan sonra kullanmış olduğumuz `/`(Slash) ifadesi ise bulunduğumuz konumdaki betik dosyasına ulaşmamızı sağlıyor. 

Yani benim konsola `./selamlar.sh` şeklinde yazmamla `/root/selam.sh` şeklinde yazmam aynı şeyi ifade ediyor. 

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/15.png)

Bu yüzden ilk kullanım ile yani `./` komutunu kullanarak işlemi çok daha kolay yerine getirebiliyorum.

Şu ana kadar her şey harika gitti ve betik dosyamızı üç farklı yoldan nasıl çalıştırabileceğimizi görmüş olduk.

Peki ama daha öncesinde `bash` ve `sh` komutu ile aynı dosyamızı çalıştırma yetkisi bulunmamasına rağmen nasıl çalıştırabilmiştik ? 

Yani `bash selamlar.sh` ile `./selamlar.sh` ya da `sh selamlar.sh` ile `./selamlar.sh` kullanımlarının arasındaki yetki almayı gerektiren fark neydi ?

Bu durumun nedeni `bash` ya da `sh` komutunu kullandığımızda konsola "**bu bir bash ya da sh kabuk programıdır, bu programı bash ya da sh dili aracılığı ile çalıştırabilirsin**" demiş oluyorduk. Ve bu sayede konsol çalıştıracağı dosyanın içeriğine bakmadan bunun bir **bash** ya da **sh** dosyası olduğunu anlayıp doğrudan **bash** ya da **sh** dili aracılığı ile çalıştırıyordu. 

Ancak bizler konsola `./betik` şeklinde komut girdiğimizde, konsol bu dosyanın ne tür bir dosya olduğunu doğrudan bilmediği için ilgili dosyayı açıp ilk satırına bakıyor ve ilk satırda yer alan ifadeye göre dosyanın ne türden olduğunu anlamlandırmaya çalışıyor. Eğer bizler ilk satırı boş bırakmışsak konsol sistemde varsayılan olarak kullanılan kabuk dili aracılığı ile dosyamızı çalıştırmayı deniyor. Şayet ilk satıra başka bir kabuk dili eklemişsek de bu dile göre dosyayı çalıştırıyor. Hatta bu durumu dosyamızın başına alakasız bir kabuk konumu belirterek deneyelim.

Dosyamın başına **/bin/bash** yerine **/bin/deneme** şeklinde bir ifade ekleyip kaydediyorum. Ve dosyamı `./betik` şeklinde çalıştırmayı deniyorum.

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/16.png)

Bu işlemin sonucunda konsol bana "***hatalı yorumlayıcı: Böyle bir dosya ya da dizin yok***" şeklinde çıktı basarak betik dosyasının ilk satırında geçen kabuk programı konumunun geçersiz olduğunu belirterek betik dosyasını çalıştıramadı.

Aynı dosyayı `bash betik` komutu ile çalıştırdığımızda ise konsol ilk satırda yer alan özel kabuk tanımını okumaya ihtiyaç duymadığından dosyamızı **bash** dili aracılığı ile sorunsuzca çalıştırabildi.

![](https://raw.githubusercontent.com/taylanbildik/bash_script_dersleri/master/img/Ba%C5%9Flarken/15.png)

Buradaki önemli ayrım; bizler `bash` ya da `sh` komutunu kullanarak, konsola "**bu dosyayı bash ya da sh dili aracılığı ile çalıştır**"  diye emir veriyoruz. Ancak ikinci kullanımda yani `./betik` şeklindeki kullanım ile konsola "**bu dosyanın ilk satırındaki tanıma bakarak hangi kabuk ile çalışacağını tespit et daha sonra dosyanın çalıştırılabilirlik yetkisi varsa çalıştır**" demiş oluyoruz. Bu sebepten `./betik` şeklindeki kullanım betik dosyasını çalıştırmak için dosyanın çalıştırılabilirlik yetkisine ihtiyaç duyuyor.

Böylelikle ilk bash shell scriptimizi diğer bir değişle ilk betiğimizi yazıp çalıştırmış olduk.

Bir sonraki kısımda anlatıma değişkenler ile devam edeceğiz.
