---
slug: smlm-lifecycle-management
id: zksrqkgljah5
type: challenge
title: Yaşam döngüsü yönetimi
tabs:
- id: atopi6jd0yaj
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Yaşam döngüsü yönetimi (Lifecycle management)
===================================

<style type="text/css">
  * {
    font-family: suse;
    src: url('https://fonts.google.com/specimen/SUSE');
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
  .smls {
    color: #2453ff;
  }
  .smlsext {
    color: #2453ff;
  }
  .companyname {
    color: #008657;
  }
  .liberty {
    color: #efefef;
  }
  .sles {
    color: #90ebcd;
  }
  .highlightcopy {
    color: white;
    font-weight: bold;
    padding: 0 10px;
  }

  .bottoms {
    vertical-align: middle;
    height: 50%;
    width: 50%;
    margin: 0px;
    padding: 0px;
    object-fit: contain;
  }

  img.animatedgif {
    --borderthickness: 5pt;
    --colors: #0000 25%,#30ba78 0;
    padding: 10px;
    background:
      conic-gradient(from 90deg  at top    var(--borderthickness) left  var(--borderthickness),var(--colors)) 0    0,
      conic-gradient(from 180deg at top    var(--borderthickness) right var(--borderthickness),var(--colors)) 100% 0,
      conic-gradient(from 0deg   at bottom var(--borderthickness) left  var(--borderthickness),var(--colors)) 0    100%,
      conic-gradient(from -90deg at bottom var(--borderthickness) right var(--borderthickness),var(--colors)) 100% 100%;
    background-size: 50px 50px;
    background-repeat: no-repeat;
    transition: 1s;
  }

  img.animatedgif:hover {
    background-size: 51% 51%;
  }

  img.logos {
    border-radius: 10px;
  }

</style>

<img class="logos" alt="Welcome!" src="../assets/logos/05-lifecycle.jpeg"/>

Bu bölümde, bireysel bakım görevlerinden, değişikliği yönetmek için filo çapında, sertifikalı bir süreç oluşturmaya geçeceğiz. <b class="smlmext">SUSE Multi-Linux Manager</b> içindeki İçerik Yaşam Döngüsü Yönetimi'nin (Content Lifecycle Management), havayolu şirketimizin talep ettiği yapıyı ve güvenliği nasıl sağladığını keşfedeceğiz.



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]'da, yeni bir parça üreticiden geldiği anda bir yolcu jetine takılmaz. Titiz bir sertifikasyon sürecinden geçer.

İlk olarak, kontrollü bir atölyede incelenir ve test edilir (**Geliştirme / Development**). Daha sonra, ticari olmayan bir test uçağına takılır ve zorlu yer ve uçuş testlerinden geçirilir (**Kalite Güvencesi / Quality Assurance - QA**). Ancak akla gelebilecek her türlü kontrolden geçtikten sonra aktif filomuzda kurulum için sertifikalandırılır (**Üretim / Production**).



Bu metodik, aşamalı yaklaşım, tek bir hatalı bileşenin bir uçağı yerde tutmasını önleyerek yolcularımızın güvenliğini ve operasyonlarımızın güvenilirliğini sağlar. Aynı felsefeyi BT sistemlerimize de uyguluyoruz. Bir yazılım yükseltmesi veya yeni bir uygulama, hatalı olması durumunda dijital operasyonlarımızı durdurabilecek bir "bileşen"dir. İçerik Yaşam Döngüsü Yönetimi, tüm yazılım değişiklikleri için resmi sertifikasyon sürecimizdir.



## <b class="hovereffect">Hedefleriniz:</b>

- Bir İçerik Yaşam Döngüsü Projesi (Content Lifecycle Project) oluşturun.

- Projeyi, sistemlerimiz için yazılım güncellemelerini yönetmek ve sertifikalandırmak üzere kullanın.



Laboratuvar detayları (Lab details)
===========

Kullanıcı Adı (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Şifre (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


Yazılım Sertifikasyon Yolumuzu Oluşturma
==============================================

Bu alıştırmada, yazılım güncellemelerinin akışını kontrol etmek için bir İçerik Yaşam Döngüsü Projesi oluşturacağız. Bu, bir yamanın kritik üretim sunucularımıza ulaşmadan önce iyice test edilmesini sağlar.

<br/>

Hedefimiz bir `Dev ✈ QA ✈ Prod` boru hattı (pipeline) oluşturmaktır.

1.  **Geliştirme (Dev):** İlk atölye. Tüm yeni yamalar ve paketler önce buraya gelir.
2.  **Kalite Güvencesi (QA):** Test sahası. Test ekiplerimizin doğrulaması için içeriğin belirli bir sürümünü Dev'den QA'ya yükselteceğiz (promote).
3.  **Üretim (Prod):** Aktif filo. Yalnızca QA onaylı, sertifikalı yama seti Üretime (Production) yükseltilir ve burada canlı sistemlerimize güvenle uygulanabilir.



<br/>

## <b class="hovereffect">Projeyi oluşturun</b>

- `Content Lifecycle` ✈ `Projects` yolunu izleyin ve ![Create Project](../assets/SMLM5.1/bottom-create_project.png)'e tıklayın.

- Proje detaylarını doldurun:

- **Project Name** (Proje Adı):

```txt
Airtrain SLES15 SPx
```

- **Project Label** (Proje Etiketi):

```txt
at-sles15_spx
```

- **Project Description** (Proje Açıklaması):

```txt
Certified software channel for Airtrain SLES 15 systems.
```


- ![Create](../assets/SMLM5.1/bottom-create.png)'e tıklayın.

Şimdi dolduralım, `Attach/Detach Sources`'a tıklayın.

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- **New Base Channel** üzerinde <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b>'ü seçin ve ![Save](../assets/SMLM5.1/bottom-save.png)'e tıklayın.

<br/>

## <b class="hovereffect">Dev ortamını oluşturun</b>

Geliştirme Ortamı Yaşam Döngüsünü (Development Environment Lifecycle) oluşturun

- `Add Environment`'a tıklayın.

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- Aşağıdakilerle doldurun:
  * **Name:** <b class="highlightcopy">Development</b>
  * **Label:** <b class="highlightcopy">dev</b>

- ![Save](../assets/SMLM5.1/bottom-save.png)'e tıklayın.

<br/>

## <b class="hovereffect">QA ortamını oluşturun</b>

Kalite Güvencesi Ortamı Yaşam Döngüsünü (Quality Assurance Environment Lifecycle) oluşturun

- `Add Environment`'a tıklayın.

- Aşağıdakilerle doldurun:
  * **Name:** <b class="highlightcopy">QA</b>
  * **Label:** <b class="highlightcopy">qa</b>

- ![Save](../assets/SMLM5.1/bottom-save.png)'e tıklayın.

<br/>

## <b class="hovereffect">Prod ortamını oluşturun</b>

Üretim Ortamı Yaşam Döngüsünü (Production Environment Lifecycle) oluşturun

- `Add Environment`'a tıklayın.

- Aşağıdakilerle doldurun:
  * **Name:** <b class="highlightcopy">Production</b>
  * **Label:** <b class="highlightcopy">prod</b>

- ![Save](../assets/SMLM5.1/bottom-save.png)'e tıklayın.

<br/>

## <b class="hovereffect">Doldur (Populate)</b>

Şimdi üç ortamımız da var, onları içerikle dolduralım.

<b class="sles">SLES</b> zaten kararlı paket sürümleri sağladığı için bu durumda bir filtre kullanmayacağız.

[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]'un test etme sıklığı şu anda bir aydır, bu nedenle bu derlemeyi (build) mevcut ay olan Ekim (October) adıyla adlandıracağız.

- ![Build](../assets/SMLM5.1/bottom-build.png)'e tıklayın.

- **Version Message** kısmına şunu yazın:

```txt
October
```


- `Build`'e tıklayın.

> [!NOTE]
> Bu işlem birkaç dakika sürebilir, 'cloning' (klonlama) gibi bazı adımlar göreceksiniz, ancak bunun çok fazla depolama alanı gerektirmediğini bilmek sizi rahatlatabilir. Klonlama işlemi gerçek paketlerin kendilerine değil, yalnızca paket indeks noktalarına uygulanır.


<br/>

## <b class="hovereffect">İçeriği yükseltme (Promoting)</b>

Şimdi, içeriği sonraki aşamalara yükseltelim (promote).

- Development ve QA arasındaki `Promote` düğmesine tıklayın.
- **Promote version 1 into QA** başlıklı başka bir ekran görünecektir, tekrar `Promote`'a tıklayın.

Production (Üretim) için aynı adımı tekrarlayın.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

Sistemlerimizi yükseltin.
====================

Şimdi nasıl çalıştığını deneyelim.

Şunları yapacağız:
- Sistemlerimizden bazılarını yeni ortama eklemek.
- İçeriğin yeni bir sürümünü oluşturmak.
- Yeni sürümü yükseltmek (promote) ve sistemleri güncellemek.

<br/>

## <b class="hovereffect">Sistemleri ekle</b>

`Systems` ✈ `System List` ✈ `All` yoluna gidelim.

- **at-ct-qa** sistemine tıklayın.
- `Software` ✈ `Software Channels` yoluna gidin.
- **Custom Channels** üzerinde, **at-sles15_spx-qa-...** kanalı için onay kutusunu seçin ve ![Next](../assets/SMLM5.1/bottom-next.png)'e tıklayın.
- ![Confirm](../assets/SMLM5.1/bottom-confirm.png)'e tıklayın.


`Systems` ✈ `System List` ✈ `All` yoluna geri dönün.

- Şuna göre filtreleyin:

```txt
at-
```

- **-pro** ile biten tüm sistemleri seçin.
- `Systems` ✈ `System Set Manager` yoluna gidin.
- `Channels` yoluna gidin.
- **Custom Channels** üzerinde, **at-sles15_spx-prod-...** kanalı için onay kutusunu seçin ve ![Next](../assets/SMLM5.1/bottom-next.png)'e tıklayın.
- Önerilen tüm kanallara abone olmak için 'include recommended' (önerilenleri dahil et) seçeneğine tıklayın:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">Yeni bir sürüm oluşturun</b>


Bir ay geçti ve kararlı yükseltme sürecimize devam etmek istiyoruz.
Geliştirici ekibi için yazılım kanallarının statik, değişmeyen bir kopyasını oluşturacaksınız.

Hiçbir yeni yama aniden ortaya çıkıp çalışmalarını bozmayacak.

- `Content Lifecycle` ✈ `Projects` yoluna geri dönün ve az önce oluşturduğumuz projeye tıklayın.

- ![Build](../assets/SMLM5.1/bottom-build.png)'e tıklayın.

- **Version Message** kısmına şunu yazın:

```txt
November
```


- `Build`'e tıklayın.

Sürüm numarasının otomatik olarak arttığına dikkat edin.

Artık geliştiriciler, SUSE tarafından sağlanan kütüphanelerin ve uygulamaların yeni ve yamalanmış sürümlerini kullanarak işlerini yapabilirler.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">İçeriği Dev'den QA'ya yükseltin</b>

Geliştiricilerimizin onay verdiğini varsayalım. Tüm üretim öncesi testlerin yapılabilmesi için QA ekibi için kararlı bir sürüm oluşturma zamanı geldi.

- Development ve QA arasındaki `Promote` düğmesine tıklayın.
- **Promote version 2 into QA** başlıklı başka bir ekran görünecektir, tekrar `Promote`'a tıklayın.

Şimdi QA sistemlerimize gidelim ve bir yükseltme yapalım.

- `Systems` ✈ `System List` ✈ `All`
- **at-ct-qa** sistemine tıklayın.
- `Software` ✈ `Packages` ✈ `Upgrade` yoluna gidin.
- Şuna tıklayın:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Artık QA mühendislerimiz testlerini kesinti olmadan güvenle gerçekleştirebilirler.


> [!NOTE]
> Değişikliklerin geldiğini görmek için yeterli zamanımız yok, gerçek bir senaryoda sürüm 2'de yükseltilebilecek paketlerin yeni sürümleri mevcut olmalıdır.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">Production'a Yükseltin</b>

QA ekibi `v2` üzerindeki titiz testlerini tamamladı ve ana filo için kararlı ve güvenli olduğunu onayladı. Şimdi bunu üretim sistemlerimizin kullanımına sunma zamanı.

QA için yaptığımız işlemin aynısını üretim ortamımızda tekrarlayacağız:

- İlk olarak, içeriği yükseltin (promote).
  Bu, yeni paketleri üretim sunucularımızın kullanımına sunacaktır.
  Yalnızca test edilmiş ve onaylanmış güncellemelerin en kritik sistemlerinize ulaşabileceğini başarıyla garanti ettiniz.

- İkinci olarak, Üretim sistemlerimizi yükseltin (upgrade), buradaki tek fark, tüm ekiplerimizin hazırlıklı olmasını ve kontrollü bir sürece sahip olmasını sağlamak için yükseltmeyi **yarın saat 14:00**'e planlayacak olmamızdır.


<br/>

[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] için bu neden önemlidir?
=================================================================================

- Bir dizi güvenlik kapısı inşa ediyoruz, bu da operasyonel stratejimizin temel bir ilkesini uygulamayı kolaylaştırıyor: **risk yönetimi**.
- **Dev** ortamına giren tek bir kötü yama, gelir getiren sistemleri etkileme şansı bulmadan çok önce yakalanıp düzeltilebilir.
- Bu süreç, yama ve güncellemeleri riskli, sinir bozucu bir olaydan, güvenilir bir havayolu şirketinin temel taşı olan öngörülebilir, rutin bir bakım prosedürüne dönüştürür.


<br/>

Daha fazla bilgi
================

* [Bakım Pencereleri (Maintenance Windows)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [Yama Yönetimi (Patch Management)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [İçerik Yaşam Döngüsü Yönetimi (Content Lifecycle Management)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [SUSE Multi-Linux Manager Ürün Sayfası](https://www.suse.com/products/suse-manager/)