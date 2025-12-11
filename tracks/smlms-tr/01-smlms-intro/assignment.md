---
slug: smlms-intro
id: runmieuxmxgv
type: challenge
title: SUSE Multi-Linux Hands-on Workshop'a Hoş Geldiniz!
teaser: SUSE Multi-Linux Hands-on Workshop'a Hoş Geldiniz! Bu bölümde size çalıştayı
  ve ana bileşenlerini tanıtacağız.
notes:
- type: text
  contents: |
    # SUSE Multi-Linux Hands-on Workshop'a Hoş Geldiniz!
    Lütfen laboratuvar ortamınızı kurarken bekleyin.
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: 81lryfdkszuu
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

<b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop'a Hoş Geldiniz
==================================================================

<link  rel="stylesheet" href="https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css" type="text/css" crossorigin="anonymous" fetchpriority="high" />

<style type="text/css">

  @import url("https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css");
  @import "https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css";

  * {
    font-family: suse;
    src: url('https://fonts.google.com/specimen/SUSE');
/*    background-color: #30ba78; */
  }
  .hovereffect {
    border-radius: 25px 25px 25px 25px;
    background: linear-gradient(#30ba78 0 0) var(--hundredpercent, 0) / var(--hundredpercent, 0) no-repeat;
    transition: 0.5s, background-position 0s;
    padding: 5px;
  }
  .hovereffect:hover {
    --hundredpercent: 100%;
    color: white;
    border-radius: 10px 25px 10px 25px;
  }
  .smlmext {
    color: #fe7c3f;
  }
  .smlm {
    color: #fe7c3f;
  }
  .suse {
    color: #30ba78;
  }
  .highlightcopy {
    color: white;
    font-weight: bold;
    padding: 0 10px;
  }


</style>



<img class="logos" alt="Welcome!" src="../assets/logos/01-welcome.jpeg"/>

Bu çalıştayda, <b class="smlmext">SUSE Multi-Linux Manager</b>'ın (<b class="smlm">SMLM</b>) yapabildiği sihrin bir kısmını keşfedeceksiniz; bu, birden fazla Linux dağıtımını birleşik bir arayüzden ölçekli bir şekilde yönetmek için <b class="suse">SUSE</b>'nin çözümüdür. Ayrıca, Linux sistemleri için profesyonel ve güvenilir destek çözümümüz olan <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>) ile eski (legacy) üretim sunucularınızı nasıl desteklenen durumda tutabileceğinizi keşfedeceksiniz.

&emsp;&emsp; Her uçağında bir Linux sunucusu bulunan bir havayolu şirketi olan <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>'da bir **mühendis (engineer)** rolünü üstleneceksiniz.

&emsp;&emsp; Herhangi bir uçak bileşeninde olduğu gibi, bu sunucuların bir veri merkezinde yerde veya bulutların üzerinde uçuyor olsalar da kararlı ve güvenilir kalmaları kritik öneme sahiptir ☁ ☁ ☁


&emsp;&emsp; Bazı uçak modelleri farklı bir Linux çeşidi veya farklı bir CPU mimarisi gerektirecektir. Bu <b class="smlm">SMLM</b> için bir sorun değildir; kolay standardizasyon ve yönetimden vazgeçmek zorunda kalmadan ihtiyaçlarınıza en uygun Linux dağıtımını ve CPU mimarisini seçmekte özgürsünüz.


&emsp;&emsp; Linux ortamını yönetmekten sorumlu bir mühendis olarak, sistem yönetimini kolaylaştırmak ve otomatikleştirmek ve oluşabilecek istisnai sorunları çözmek için <b class="smlm">SMLM</b> ve <b class="smls">SMLS</b>'nin size sunduğu bazı çözümleri inceleyeceksiniz.


Farklı zorluklar (challenges) boyunca aşağıdaki araçlara sahip olacaksınız:

 ✈ **SUSE Multi-Linux Manager**:
   Tüm Linux yığınınızı yönetmek için tek bir cam panel (single pane of glass).

 ✈ **Centos 7**:
   Bazı eski uçaklarda ve yer sistemlerinde hala kullanımda olan eski (legacy) bir dağıtım.

 ✈ **Ubuntu 24**: Pazarlama departmanımızın grafik tasarım uygulamalarını çalıştırmak için ihtiyaç duyduğu belirli bir Linux dağıtımı.

 ✈ **SLES 15**: En kritik sistemlerimizin omurgasını oluşturan, <b class="suse">SUSE</b>'nin son derece güvenilir, kararlı ve güvenli Linux dağıtımı.


## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

Yazılım tanımlı altyapınız için sınıfının en iyisi açık kaynak altyapı yönetim çözümüdür.

&emsp;&emsp; <b class="smlmext">SUSE Multi-Linux Manager</b>, kurumsal DevOps ve IT Operations ekiplerinizin karmaşıklığı azaltmasına ve BT varlıklarınızın kontrolünü yeniden kazanmasına yardımcı olmak için tasarlanmıştır; çeşitli donanım mimarileri, hipervizörlerin yanı sıra konteyner, IoT ve bulut platformlarındaki Linux sistemlerini yönetmek için tek ama çok güçlü bir araçtır.

&emsp;&emsp; Operasyonları optimize etmeye ve maliyetleri düşürmeye yardımcı olarak daha hızlı, tutarlı ve tekrarlanabilir sunucu dağıtımı için Linux sunucusu ve IoT cihazı hazırlama (provisioning), yama uygulama (patching) ve yapılandırmayı otomatikleştirir. Geliştirme, test ve üretim ortamlarınızdaki sistemlerinizin, VM'lerinizin ve konteynerlerinizin otomatik izlenmesi, takibi, denetimi ve raporlanması ile dahili güvenlik politikalarına ve harici düzenlemelere uyumu sağlayabilirsiniz.


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


Mevcut Red Hat Enterprise Linux (RHEL), CentOS, <b class="liberty">SUSE Liberty Linux</b> ve <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) dahil olmak üzere çeşitli Linux dağıtımları için teknik yardım ve bakım sunan kapsamlı bir hizmettir (teklife bağlı olarak).

&emsp;&emsp; Kuruluşların karma Linux ortamlarını tek bir destek çerçevesi altında verimli bir şekilde yönetmesini sağlar.
Satın alınan pakete bağlı olarak, <b class="smlsext">SUSE Multi-Linux Support</b>, bu dağıtımları yönetmek için bir çoklu Linux yönetim aracı olan <b class="smlmext">SUSE Multi-Linux Manager</b>'ı da içerebilir.



 🌅 Instruqt UI'ı Keşfedin
=======================
İlk görevimize başlamadan önce, Instruqt UI'a bakmak için bir dakikanızı ayıralım.

+ Ekranın **sağ tarafı** size bu talimatları ve gezinme kontrollerini sağlar.

+ **Sol taraf**, laboratuvar ortamımızı oluşturan çeşitli makinelere ve hizmetlere erişmenizi sağlar.

Instruqt UI içinde, sol panelin üst kısmındaki sekmelere tıklayarak [button label="SMLM UI" variant="success"](tab-0) ve mevcut [button label="terminals" variant="success"](tab-1) arasında geçiş yapabilirsiniz.


> [!NOTE]
> Web UI üzerinde otomatik yeniden yükleme gerçekleşmez; bazı durumlarda güncellemeleri görmek için Instruqt'un dahili web tarayıcısını yeniden yüklemeniz gerekebilir.


🛫 <b class="smlmext">SUSE Multi-Linux Manager</b>'a Giriş Yapma 🛫
========================================
Sizi ortama alıştıralım.

- [button label="SMLM UI" variant="success"](tab-0) üzerinden laboratuvar içindeki <b class="smlmext">SUSE Multi-Linux Manager</b>'ı açın.


- Aşağıdaki kimlik bilgileriyle giriş yapın:

  - Kullanıcı Adı (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - Şifre (Password):

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

Her şey yolunda gittiyse, `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]` kullanıcısı olarak giriş yapmış bir şekilde <b class="smlmext">SUSE Multi-Linux Manager</b> UI'ında **Overview** sayfasını görmelisiniz.

> [!NOTE]
> <b class="smlmext">SUSE Multi-Linux Manager</b> UI'ına doğrudan tarayıcınız üzerinden erişmek isterseniz bunu da yapabilirsiniz:

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> Sayfa doğru yüklenmezse, laboratuvar ortamı başlatmayı tamamladıktan sonra tarayıcı sekmesini yenilemeniz gerekebilir.




🗺  <b class="smlmext">SUSE Multi-Linux Manager</b>'ı Keşfedin 🗺
======================================

Havalanmadan önce kontrollere aşina olalım. Bu kapsamlı bir tur değil, çalıştay boyunca kullanacağımız temel araçlara kısa bir genel bakıştır. Sizi meraklı olmaya ve keşfetmeye teşvik ediyoruz.


Hadi başlayalım.


- **Systems Menüsü** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  Sol panelde `systems` üzerine tıklayın. Bu, kayıtlı her sunucuyu gösteren filo genel bakışımızdır. Liste şu an küçük, ancak egzersizlerimizi tamamladıkça büyüyecek.

   - **System Lists**

     Bu bölüm kullanışlı, önceden filtrelenmiş görünümler sağlar. Örneğin, `Out of Date` listesi hangi sunucuların güncelleme gerektirdiğini anında göstererek sizi manuel bir arama yapmaktan kurtarır. </p>

  <br/>

  - **System Groups**

    Filomuzu mantıksal olarak düzenlemek için `System Groups` kullanırız; bunları herhangi bir kritere göre kategorize edebilirsiniz. Bunu yaparak eylemleri uygularken veya politikaları tanımlarken zaman kazanabilirsiniz. Oluşturulduktan sonra, örneğin `activation keys` kullanarak sistemleri otomatik olarak bir veya birden fazla gruba ekleyebilirsiniz.


    Şimdi `+ Create Group` üzerine tıklayarak bir tane oluşturmayı denemekten çekinmeyin.

  <br/>

  - **Toplu işlemler (Batch operations)**

    `System Set Manager`, birden fazla sistemde aynı anda işlem gerçekleştirmek için güçlü bir yol sağlar.


    Değişiklikleri tek tek uygulamak yerine, System List'ten veya mevcut System Groups'tan yararlanarak bir sistem koleksiyonu seçebilir ve ardından tek bir işlemde hepsinde görevleri yürütebilirsiniz.

  <br/>

  - **Provisioning**

    <b class="smlmext">SUSE Multi-Linux Manager</b>, yeni sistemlerin hazırlanması (provisioning) ve mevcut olanların yeniden hazırlanması için kapsamlı araçlar sağlar. Bu yetenek, sistem dağıtımı için standartlaştırılmış ve tekrarlanabilir bir süreç oluşturmanıza yardımcı olur.


    Örneğin, `Autoinstallation` bölümü içinde, sistemlerinizin nasıl dağıtılması gerektiğini, hangi yazılımların yükleneceğini, depolama alanının nasıl dağıtılacağını ve daha fazlasını belirtmenize olanak tanıyan dağıtımları ve Kickstart/AutoYaST profillerini tanımlayabilirsiniz.


    Kurulumu basit olan tüm bu otomasyon mekanizmaları, Salt veya Ansible gibi karmaşık ancak daha güçlü otomasyon çözümleriyle birleştirilebilir ve her zorluk için en iyi çözümü seçme özgürlüğünüzü korur.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Patches Menüsü** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    BT'deki en yaygın görevlerden biri, sistemleri güncel tutmak ve zaman zaman aceleyle güvenlik yamaları uygulamaktır!
    SMLM ile türe göre sınıflandırılmış ve etkiledikleri tüm sistemler ve paketler dahil olmak üzere bilmeniz gerekebilecek tüm bilgilerle sağlanan **ilgili** yamaların bir listesini kolayca görebiliriz.

    Satıcı tarafından sağlanan yamaların ötesinde kendi yamalarımızı da oluşturabiliriz. Daha sonra, tüm filomuzda yama yönetimini ve düzenli güncellemeleri yönetmek için sahip olduğumuz farklı seçenekleri inceleyeceğiz.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>
- **Yazılım kanalları (Software channels)** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  `Channel List` üzerinde tüketime uygun tüm paket kanallarını/depolarını/akışlarını görebiliriz; ayrıca yazılımınızı düzenlemek veya kendi paketlerinizi yüklemek için yeni yazılım kanalları oluşturabilirsiniz.

  Şu anda gördüğünüz tüm kanallar SMLM tarafından resmi kaynaklardan alınmıştır ve kolayca senkronize tutulabilir.

  `Package Search` içinde belirli paketleri arayabilir ve içeriklerini ve meta verilerini inceleyebiliriz.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  Kayıt sırasında veya sonrasında sistemlere belirli yapılandırmaları yönetmek ve uygulamak da mümkündür; bunun için `Configuration` bölümünü inceleyebiliriz.

  SMLM, revizyonları yönetmek, dağıtmak ve yapılandırma dosyalarını sistemler arasında karşılaştırmak için kolay bir yol sağlar. Ve hepsi yapılandırma kanalları içinde kolayca gruplandırılabilir.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  `Schedule` içinde planlanmış eylemleri gözlemleyebilir ve yönetebilir, belirli bakım pencereleri tanımlayabiliriz. Bu, birçok sistemi yönetirken düzenli operasyonları otomatikleştirmek veya kanarya dağıtımları (canary deployments) gerçekleştirmek için özellikle yararlıdır. Bunu çalıştay sırasında daha sonra eylem halinde göreceğiz.

<br/>
<br/>

SUSE Multi-Linux Manager sistemlerinizi yönetmek için birçok olanak sunar; hepsini bu çalıştayda ele alamayız ancak her zaman olduğu gibi, soru sormaktan ve keşfetmekten çekinmeyin.

> [!NOTE]
> Kullanıcınız tam yönetici ayrıcalıklarına sahiptir, bu nedenle değişiklikleri yalnızca egzersizleri bitirdikten sonra yapmanızı öneririz.