**Kabuk Programla Müfredat**

Giriş
=

Bash script nedir ne işe yarar ?
-


Bash script kavramının tam olarak anlaşılabilmesi için öncelikle bahsetmemiz gereken birkaç önemli kavram bulunuyor. Şimdi sırasıyla bu kavramları bir örnek üzerinden ele alalım.

Örneğin ben bulunduğum konumda yeni bir dosya oluşturmak istiyorum diyelim. Bu dosyayı oluşturmak için iki farklı seçeneğim buluyor. Dosyayı oluşturmak için ya grafiksel arayüzü kullanacağım ya da komut girerek ilgili dosyanın oluşmasını sağlayacağım. Her iki şekilde de benim yaptığım işlem bilgisayara ne yapması gerektiğini anlatmak oluyor. Yani ben grafiksel arayüzden tıklama işlemleri ile ya da konsoldan komut girerek bilgisayara iş buyurduğumda aslında arkaplanda, girilen işlem emri yorumlanarak donanıma iş yaptırıyor. Ancak bu işlem emrini bilgisayar doğrudan anlayamaz,  anlayamadığı için onun anlayacağı dile çevrilmesi gerekiyor. Bu yüzden çevirme işleminde görevli yapılar bulunuyor. 

Bu açıklamadan sonra örneğimizi tekrar ele alarak arkaplanda gerçekleşen işlemleri ve görevli yapıları kısaca açıklayalım.
Ben dosya oluşturmak istiyorum ve bunu bilgisayara ifade etmeliyim. İfade biçimi olarak grafiksel arayüz de olabilir komut kullanımı da olabilir. Ben komut kullanımını tercih ediyorum ve komutumu bilgisayara aktarmak için konsol denilen yapıyı kullanmam gerekiyor. 
Konsol benim komutlarımı sisteme iletmemdeki yardımcı bir araçtır. Ben komutlarımı bu konsol aracılığı ile sisteme ulaştırırım. Komutumu konsola giriyorum ve komutu onayladığımda, yazmış olduğum komut, shell yani kabuk denilen yapı tarafından alınarak kernel yani çekirdeğe iletiliyor. Çekirdek de aldığı emri donanımlara ifade ederek gerekli işlemi yerine getirtiyor.

Yapıyı tekrar kısaca ele alacak olursak ben yapılmasını istediğim işlemi doğrudan donanımın anlayacağı şekilde ifade edemeyeceğim için bunun yerine shell denilen yapıya bash kabuk programı diğer bir değişle bash dili aracılığı ile derdimi anlatıyorum shell de benden aldığı bilgileri çekirdeğe aktarıyor. Çekirdekte donanıma iş yaptırıyor. Yani buradaki aracı yapıların hepsinin temel görevi tercümanlık oluyor.

İşte en başında dosya oluşturmak için konsola girdiğim komut da bash dilinin bir komutu, ben bu komut sayesinde shell denilen yapı ile iletişim kurdum, shell de benden aldığımı emri kernel yani çekirdeğe aktardı. Neticede çekirdek de ilgili donanımlara gerekli işi yaptırarak dosyanın oluşmasını sağladı.

Ben shell ile bash dili aracılığı ile iletişim kurdum dedim ancak ; shell denilen yapı, yalnızca bash kabuk dili ile iletişim kuruyor gibi bir anlam çıkmasın, yani shell denilen yapı ile iletişim kurma konusunda bash tek alternatif değil. **Linux** sistemlerinde **BASH** dışında (**ksh,tcsh,zsh,fish...**) gibi birçok **Shell** (**kabuk**) dili bulunuyor. Ancak yetenekleri dolayısıyla **en çok tercih edilen kabuk programı BASH kabuk programıdır**. 

Bash kabuk programı Stephen Bourne'nin UNIX için geliştirmiş olduğu sh kabuk dilini temel alarak geliştirildiği için; **B**ourne-**A**gain **SH**ell kelimelerinin kısaltması olan **BASH** şeklinde adlandırılmıştır. Bash kabuk dilinin bu kadar yetenekli olmasının nedeni; **sh** dili haricinde **ksh**(korn shell) ve **csh**(C shell) gibi kabuk çeşitli kabuk dillerinin en iyi özelliklerini içerisinde barındırarak, hem etkileşimli hem de programlama için kullanımını işlevsel olarak arttıran geliştirmeler içermesidir. 

Bu gibi sebeplerden ötürü, GNU işletim sistemlerinde **BASH** dışında da kabuk dilleri barındırılmasına rağmen, sistemin varsayılan kabuk yorumlayıcısı **BASH** kabuğudur.

Bizler de bu eğitim serisinde bash kabuk programının komutlarını tek bir dosya içerisinde uygun şekilde toparlayarak toplu işlemleri yerine getirmeyi öğreneceğiz. Bu yapacağımız işlem **bash shell scripting** yani Türkçe olarak **bash kabuk senaryosu** olarak geçiyor. Böyle ifade edilmesinin nedeni de kabuk dili olan bash dilinin yerine getirebileceği işlemleri tek tek yapmak yerine senaryolaştırılarak tek seferde tek elden gerçekleşmesinin sağlanmasıdır. 
Yani kısacası bizler gerekli tüm komutları tek bir dosyada uygun şekilde toparlayarak; durumlara özel senaryolar oluşturacağız ve oluşturduğumuz senaryolara göre de sistem verilen emirleri otomatik olarak gerçekleştirecek.

Bu neden önemli diyecek olursanız, olası senaryolara bir kaç örnek verelim. Örneğin sistem dosyalarının her gün yedeklenmesinin gerektiği bir durumda bu işlemi otomatikleştirmek yerine her gün elle yapmak gereksiz bir uğraş olacaktır. Yine bir diğer örnek olarak, sistemin online olup olmadığını her daim kontrol etmek yerine bu iş için bir script yazarak 7/24 sistem çalışma durumunun gözetlenmesini ve olası bir kesinti durumunda bizleri haberdar etmesini sağlayabiliriz.  Bu gibi pek çok örnek verebilir ve ayrıca yapılabilecek işlemleri yalnızca böylesine basit işlem adımları olarak da düşünmeyin, bu otomatikleştirilebilir işlemlere oldukça karmaşık olan görevler de atanabilir. Örneğin sistemdeki işleyişin kontrolü için 50 duruma göre 100 karmaşık komutu her gün dikkatli şekilde konsola girmeniz gerektiği bir durumda, bu işlemleri bash schell scripting ile otomatikleştirerek kullanmak oldukça verimli ve stabil sonuçlar doğuracaktır.

Kısacası bash script kullanarak, sistemle ilgili otomatikleştirilebilir her türlü işi tek seferde kolayca yerine getirtebiliyoruz.
Üstelik bash bir kabuk dili olduğundan diğer dillere oranla sistemle çok daha hızlı etkileşim kurarak, bizlere yüksek performans sağlıyor. En nihayetinde ihtiyaçlarımıza göre script yazarak bizler için çalışan ve yorulmak bilmeyen binlerce sistem yöneticisi üretebiliriz. Eğitimimizin ilerleyen kısımlarda hız ve işlevsellik konusunda bana katılıyor olacağınıza kesinlikle eminim. Hazırsanız bu üstün gücü nasıl kontrol edebileceğimizi öğrenmeye başlayalım :)



