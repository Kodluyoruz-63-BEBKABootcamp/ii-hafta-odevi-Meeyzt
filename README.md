# II. Hafta Ödevleri

## Yeni bir Gitthub repository oluştururken, repomuza ekleyebileceğimiz lisanslar nelerdir, bu lisanslar arasındaki farklar nelerdir?
* **GPL (Genel Kamu Lisansı)**
  * GPL lisansı ilk olarak 1989 yılında yayınlanmıştır. Güncel sürümü GPL V3 dür. En çok kullanılan özgür yazılım lisansı diyebiliriz. GPL teşvik edici gelişime açık bir lisansdır. Hem geliştirici hem de kullanıcı açısından büyük olanaklar sağlar. GPL’in en çok dikkat ettiği konu üretilen yazılımın kaynak kodları ile beraber dağıtılmasıdır.    

  * GPL lisansını kullanan bir yazılımı alıp kendi projenize eklerseniz siz de kaynak kodunuzu GPL ile lisanslamalısınız ve açık kaynak olarak dağıtmalısınız. GPL, yazılımın ücretlendirme konusunda fikir beyan etmez, yazılımlar ücretsiz olmak zorunda değildir. Bu ibare lisansta bulunmasına rağmen GPL lisanslı yazılımların çoğu ücretsizdir.  

  * GPL in dezavantajı diyebileceğimiz bir yanı ise GPL ile lisanslanmış yazılımın başkaları tarafından değiştirilerek geliştirilmesi sonucunda elde ettiği gelire hiç bir konuda maddi talepte bulunamazsınız. Yaptığınız yazılımın ya da kütüphaneden gelir elde etmek gibi bir durumunuz varsa başka lisanslarla lisanslamanız gerekir.   
* **LGPL (Kısıtlı Genel Kamu Lisansı)**
  * Kısıtlı Genel Kamu Lisansı (LGPL) genel ağırlıklıkta kütüphane olarak geliştirilen yazılımlarda kullanılır. GPL in aksine LGPL’de geliştirdiğiniz bir kütüphaneyi özel mülk yazılımın içerisinde kapalı kaynak olarak kullanabilirsiniz. Ancak LGPL ile geliştirilmiş kütüphanenin içerisinde herhangi bir değişiklik yapmış veya yama geliştirmiş iseniz bu kısmı açmak zorundasınız.
  * Büyük yazılım firmaları LGPL ile ilgili kütüphaneleri kendi projelerine eklerken script dosyaları yazarak kendi projelerine bağlarlar. Böylelikle LGPL de bir değişikliği kolaylıkla açık olarak yayınlama imkanına sahip olurlar.
* **BSD Lisansı**
  * BSD lisansı adını Berkeley Software Distribution dan alır. Özgür yazılım lisans ailesindendir. Yazılım üzerine neredeyse hiç bir sınırlama koymaz. İstenilen şekilde değiştirebilirsiniz, kodu kapatabilirsiniz ve üzerinden para kazanabilirsiniz. İsteyen herkes istediği gibi kullanabilmektedir.
* **MPL (Mozilla Kamu Lisansı)**
  * MPL açık kaynak lisans ailesi içerisindedir. Genel olarak BSD lisansının olanaklarıyla Genel Kamu Lisansını bir araya getirmeye çalışan bir lisansdır.
* **MIT Lisansı**
  * MIT lisansı üzerinde geliştirilmiş olan yazılımın bir kopyasını dağıtma, kullanma, kopyalama, değiştirme, alt lisanslama gibi imkanların hepsini sağlar. Ticari ve hususi olarak kullanma imkanını sağlar. Zorunlu yapmanız gereken MIT lisans ibaresini kodunuza eklemeniz gerekmektedir ve telif bulundurmanız gerekmektedir. Yazarları sorumlu tutamazsınız.
* **Apache Lisansı**
  * Apache lisansı yazılan programın kodlarının tüm kopyaları, değiştirilmiş ve ya değiştirilmemiş, lisansın bir kopyası eşliğinde dağıtabilir ya da kullanabilir. Üzerinde yapılan değişiklikler değiştirilmiş olarak işaretlenmelidir. Ticari kullanım olarak kullanım imkanı sağlar.
## Merge-Rebase-Squash arasındaki farklar nelerdir?
 * **Rebase**
   * Rebase, bir branchin orijinal temel taahhüdünü değiştirir. Bu genellikle, diğer ekip üyelerinin ana geliştirme dalına aktif katkılarının bir sonucu olarak bir izleme branchi eski bir üsse işaret ettiğinde gerçekleşir. Bir geri ödeme sürecinde, taahhütleriniz geçici olarak kaldırılır, böylece temel taahhüt yukarı yönlü değişikliklerle güncellenebilir ve ardından taahhütleriniz güncellenmiş temel taahhüdün üzerine uygulanır. Aşağıdaki şema bu süreci görselleştirmektedir. Bir geri ödemenin tek amacı, yukarı akış değişikliklerini yerel şubenize entegre ederken doğrusal bir geçmişi korumaktır.
   ![Rebase](https://seesparkbox.com/uploads/article_uploads/after-rebasing.png)   
* **Merge**
  * Bir dalı birleştirmek, orijinal dallanma yapısını sağlam tutarken bir dalı başka bir dala çekmeyi içerir. Ayrıntılı geçmiş adına, ayrı bir birleştirme işlemi kaydedilir (** dallara ayrıldığınızdan veya birleştirme komutunuzu bir ```-no-ff``` bayrakla eklediğinizden beri kaynak dalının değiştiği varsayılarak ). Taahhütler böylece bir kapsayıcı özelliğin veya sabit dalın parçası olarak gruplanır ve dallar, bir dal silindikten çok sonra da görünür kalır. Bu, özellikle uzun vadede ekibiniz tarafından görünürlük ve izlenebilirliğe değer verildiğinde yararlıdır.    
  ![Merge](https://seesparkbox.com/uploads/article_uploads/before-after-merge.png)   
  ** Not: Normalde, bir dalı değişmemiş bir kaynak dalına geri birleştirdiğinizde (dallanmadan bu yana hiçbir taahhütte bulunulmamıştır), git, bir birleştirme kaydı oluşturmadan veya birleştirilen dalı korumadan kaynak dalın üstüne taahhütlerinizi ekler . Buna hızlı ileri birleştirme denir [Şema 1'e bakın]. Bazı takımlar, şube geçmişlerini olduğu gibi tutmayı -no-ffve birleştirme komutuna bir (hızlı ileri alma yok) bayrağı eklemeyi tercih eder, böylece git, birleştirmede bir kesinleştirme oluşturmaya zorlar. Buna üç yollu birleştirme denir.
* **Squash**
  * Öncelikle git squash nedir buradan başlayalım, git squash komutu aslında farklı bir rebase kullanımı olarak değerlendirmek daha doğru olacaktır. Geçmişte atılan commit’leri yeniden düzenlemek, isimlendirmek veya birleştirmek için kullanıyoruz.
Bu geçmişte atılan commit’ler, local’de veya uzak bir git sunucusunda olabilir. Unutmamamız gereken bir nokta da, git squash işlemi yaptıktan sonra ‘force push’ kullanmamız gerektiğidir. İstenilen commit aralığını geri gidip yeniden düzenleme yaptıgımız için ‘force push’ kullanımı zorunludur.
## Agile-Scrum-Kanban kavramlarını araştırınız
* **Agile**
  * Sprint, bir projenin belirli bir aşaması için ayrılan süredir. Sprintlerin süresi dolduğunda proje tamamlanmış sayılır. Ekip üyeleri arasında, gelişimin tatmin edici olup olmadığı konusunda anlaşmazlıklar olabilir; ancak, projenin belirli bir aşamasında bu konuda daha fazla çalışma yapılmayacaktır. Projenin kalan aşamaları, kendi zaman dilimleri içinde geliştirilmeye devam edecektir.
* **Scrum**
  * Agile proje yönetim metodolojilerinden biridir. Kompleks yazılım süreçlerinin yönetilmesi için kullanılır. Bunu yaparken bütünü parçalayan; tekrara dayalı bir yöntem izler. Düzenli geri bildirim ve planlamalarla hedefe ulaşmayı sağlar. Bu anlamda ihtiyaca yönelik ve esnek bir yapısı vardır. Müşteri ihtiyacına göre şekillendiği için müşterinin geri bildirimine göre yapılanmayı sağlar. İletişim ve takım çalışması çok önemlidir. 3 temel prensip üzerine kurulmuştur;
    * **Şeffaflık**; Projenin ilerleyişi, sorunlar,gelişmeler herkes tarafından görülebilir olmalıdır.
    * **Denetleme;** Projenin ilerleyişi düzenli olarak kontrol edilir.
    * **Uyarlama;** Proje, yapılabilecek değişikliklere uyum sağlayabilmelidir.
  ![Scrum](https://miro.medium.com/max/640/0*Yn_O2-N315idD9Du.jpg)
* **Kanban**
  *  Yalın Üretim tekniklerinden biri olup üretimi yönetmek için kullanılan görsel bir metottur. Çekme sistemi ile hangi ürünün ne zaman ve ne miktarda üretildiğini kontrol eder.
Kanban sistemini anlayabilmek için öncelikle tam zamanında üretim(Japonların araba üretirken Kullandığı JIT sistemi) kavramını özümsemek gerekir.
* **Kanban ve Scrum arasındaki farklardan birkaç tanesi**
  | Kanban  | Scrum   |
  |---|---|
  | Geliştirme belirlenen zaman limiti içinde başlar ve biter. Sprint…   | Geliştirme sürekli olarak devam eder. Limit belirlemek opsiyoneldir.   |
  | Planlama, süreç iyileştirmeleri ve teslim için farklı ritimlere sahip olabilir. Sprint Planlama, Sprint Retrospektif ve Teslim Planlaması farklı zamanlarda yapılabilir.   |Yaşanılan gelişmelere göre aksiyon alınır. Önceden belirlenmiş toplantılar ya da aktiviteler bulunmamaktadır.   |
  | Geliştirme Takımları’nın çapraz fonksiyonel olması kuraldır.   | Geliştirme Takımları’nın çapraz fonksiyonel olması opsiyoneldir. Uzmanlıkların ön planda olduğu takımlar kurulabilir.   |
  | İş maddeleri bir Sprint içinde tamamlanacak küçük parçalara bölünmelidir.  | İş maddeleri büyüklükleri farklılık gösterebilir. Belirlenen alt ya da üst bir limit yoktur.  |
## Git flow
 * Mükemmel komut satırı yardımı ve çıktısı sağlar. Birleştirme tabanlı bir çözümdür. Özellik şubelerini yeniden sunmaz.
Git Flow , bir teknoloji yığınının Git Araçları kategorisindeki bir araçtır .
Git Flow , 2.2K GitHub yıldızları ve 537 GitHub çatalları içeren açık kaynaklı bir araçtır .
   * **Git**
    Git, ücretsiz ve açık kaynak dağıtılmış bir sürüm kontrol sistemidir ...
   * **Pre-Commit**
    Pre-commit, siz kodunuzu işlemeden önce hatalar için kontrol eder. ön işleme yapılandırılabilir.
   * **Atlassian Stash**
    Güvenlik duvarının arkasındaki Git depolarını yönetmek için merkezi bir çözümdür.
   * **Diff So Fancy**
    Diff-so-fancy, git Contrib'un fark vurgulamasının iyi görünen çıktısına dayanır.
   * **TortoiseGit**
    Windows Shell Extension olarak uygulanan bir Git revizyon kontrol istemcisidir ...
   * **Git-Repo**
    Git komut satırından uzak git barındırma hizmetlerinizi kontrol edin.
   * **GVFS**
    GVFS, git deponuzun altındaki dosya sistemini sanallaştırır.
   * **pre-commit by Yelp**
    Eğer javascript düzenlerken Node yüklü değilse kullanılır.
## Gang of Four(GOF) araştırınız.
 "Design Patterns : Elements of Reusable Object – Oriented Software" Kitabının yazarları olarak bilinen Eric Gamma, Richard Helm, Ralph Johnson ve John Vlissides'dir.
  Bu dörtlü kitaplarında 3 kategoride 23 farklı kalıba yer vermişlerdir.  
  \*En çok kullanılanları şöyle listeleyebiliriz
  * **Creational Kalıplar**
   Yazılım sistemindeki nesnelerin yaratılışı hakkında yol gösterirler.
    * Factory Method
    * Singelton
    * Abstract Factory
    * Builder
  * **Structural Kalıplar**
   Yazılım sistemindeki nesnelerin birbirleriyle olan ilişkilerini gösteren kalıptır.
    * Adapter
    * Decorator
    * Facade
    * Proxy
   * **Behavioral Kalıplar**
    Nesne davranışlarını takip eden kalıptır.
     * Iterator
     * Observer
     * Memento
     * Mediator
 ## Interface ve Abstract sınıflar arasındaki farklar nelerdir?
 ![Abstract ve interface](https://miro.medium.com/max/661/1*vmQhGSTGAeIIsCX0jEPUqg.jpeg)

### KAYNAKLAR
> * https://medium.com/@AntriKod/%C3%B6zg%C3%BCr-yaz%C4%B1l%C4%B1m-lisanslar%C4%B1-%C3%BCzerine-c28e66c2b6ef
> * https://seesparkbox.com/foundry/to_squash_or_not_to_squash
> * https://medium.com/neyasistechnology/git-rebase-squash-ile-ge%C3%A7mi%C5%9Fi-yeniden-d%C3%BCzenlemek-9de36441f947
> * https://toptalent.co/agile-nedir-agile-metodu-nasil-uygulanir#:~:text=Agile%20(%C3%A7evik)%20y%C3%B6ntem%2C%20yaz%C4%B1l%C4%B1m,art%C4%B1ml%C4%B1%2C%20yinelemeli%20i%C5%9F%20dizilerini%20kullan%C4%B1r.
> * https://www.donusumdanismanlik.com/kanban-nedir-uygulama-rehberi/
> * https://toptalent.co/agile-nedir-agile-metodu-nasil-uygulanir#:~:text=Agile%20(%C3%A7evik)%20y%C3%B6ntem%2C%20yaz%C4%B1l%C4%B1m,art%C4%B1ml%C4%B1%2C%20yinelemeli%20i%C5%9F%20dizilerini%20kullan%C4%B1r.
> * https://medium.com/@secilcor/scrum-nedi%CC%87r-6a4326951dd8
> * http://www.yilmazcihan.com/scrum-ve-kanban-arasindaki-benzerlikler-ve-farkliliklar/
> * https://medium.com/nsistanbul/design-patterns-factory-method-pattern-615457e9560b
> * https://stackshare.io/git-flow/alternatives#:~:text=Git%2C%20pre%2Dcommit%2C%20Atlassian,and%20competitors%20to%20Git%20Flow.
> * https://medium.com/software-development-turkey/abstract-class-ve-interface-aras%C4%B1ndaki-farklar-nelerdir-3c0a4f956eba
