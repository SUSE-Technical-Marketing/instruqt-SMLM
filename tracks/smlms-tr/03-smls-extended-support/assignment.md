---
slug: smls-extended-support
id: nurgewpmnmlc
type: challenge
title: Eski (legacy) sistemler için genişletilmiş destek
tabs:
- id: rtbmsxhyyvvj
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: zdoyoiqteas4
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: 1afftqochlvv
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Eski (legacy) sistemler için genişletilmiş destek
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
  ul {
    list-style-image: url('../assets/logos/chameleon_icon.png')
  }
</style>

<img style="width: 10px;" src="../assets/logos/chameleon_icon.png" />
<img class="logos" alt="Welcome!" src="../assets/logos/03_extended_support.jpeg"/>

# Eski (Legacy) Filomuzun Ömrünü Uzatma

Herhangi bir havayolu şirketinde, size yıllarca hizmet etmiş ancak henüz yerine yenisini koyamadığınız eski, güvenilir uçaklarınız vardır. Bizim için, bu eski filonun bir parçası CentOS 7 sistemlerimizdir. Kararlıdırlar ancak ömürlerini tamamlamışlardır (end-of-life), bu da artık orijinal üreticilerinden kritik güvenlik güncellemelerini almadıkları anlamına gelir. Bir havayolu şirketi için, desteksiz uçmak, göze alamayacağımız bir risktir.

Geleneksel çözüm, her birinin tam ve maliyetli bir değişimi olacaktır.
Ancak, minimum kesinti ile yerinde modernize ederek bir ömür uzatma yükseltmesi gerçekleştirebilseydik ne olurdu? İşte bu zorluğun misyonu tam olarak budur. Bu sistemleri güvenli bir şekilde geçirmek ve daha modern bir işletim sistemi (OS) ile değiştirene kadar hizmette tutmak için <b class="smlmext">SUSE Multi-Linux Manager</b>'ın gücünü <b class="smlsext">SUSE Multi-Linux Support</b> ile birlikte kullanacağız.



## <b class="hovereffect">Uçuş planımız:</b>

- Centos 7 çalıştıran mevcut eski sistemleri inceleyin

- QA sistemini dahil edin (Onboard) ve mevcut yamaları uygulayın

- Varsa güncellemeleri belirleyin ve uygulayın.

- Sistemi liberate formülü ile serbest bırakın (Liberate).

- Her iki sistem arasında nelerin değiştiğini gözlemleyin

- Bunun bir geçiş (migration) olup olmadığını belirleyin.

<br/>

## <b class="hovereffect">Uçaklarımız</b>

- CentOS 7 QA ✈ Test ve geliştirme sunucumuz.

- CentOS 7 Prod ✈ <b class="smlm">SMLM</b>'e zaten kayıtlı üretim sunucumuz

<br/><br/>


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



Centos 7 QA'yı Dahil Etme (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">Mevcut eski sistemleri inceleme</b>

[button label="Centos 7 QA" variant="success"](tab-1) sekmesinden sistem terminaline erişin

Sistemin mevcut sürümünü kontrol edin:

```bash,run
rpm -qi centos-release centos-logos
```


Şimdi sistemi <b class="smlm">SMLM</b>'e kaydetmek için aşağıdaki komutu çalıştırın:


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


Bu, önceki laboratuvarda Ubuntu'yu dahil etmek için kullandığımıza benzerdir, değişen şudur:

- **Activation key** (Aktivasyon anahtarı): Varsayılan olarak sisteme uygulanacak ayarlara bir referanstır, bu durumda sadece sistemin hangi yazılım kanallarına kaydedileceğini belirtmek için oluşturulmuştur.

- **Profile name** (Profil adı): Belirtmezsek ana bilgisayar adını (hostname) kullanır ancak bu durumda Centos 7 Prod ile kullandığımız aynı adlandırma kuralına sahip daha anlamlı bir isme sahip olmasını istiyoruz.


**İsteğe Bağlı:** Merak ediyorsak ve yükseltme yapıp Liberate formülünü çalıştırdığımızda ne olacağını görmek istiyorsak, her iki sistemde de ( [button label="Centos 7 QA" variant="success"](tab-1) ve [button label="Centos 7 Prod" variant="success"](tab-2) ) aşağıdaki komutu çalıştırabiliriz:


```bash,run
journalctl -f
```

Ve terminallerde görünen günlükleri (logs) görün.


<br/><br/>


## <b class="hovereffect"><b class="liberty">Liberty</b> depolarından güncellemeleri belirleyin ve uygulayın</b>

Bu Centos 7 sistemleri, yukarı akışta (upstream) sağlanan en son paketlerle gelir, yeni hataların düzeltildiğinden ve sorun olduğunda bize yardımcı olacak dost canlısı bir destek personeline sahip olduğumuzdan emin olmak istiyoruz, şimdi kayıt işlemi sırasında Centos 7 sistemlerini SUSE tarafından sağlanan yazılım depolarına zaten abone yaptık, bu yüzden hepsini yamalayalım:



Şimdi [button label="SMLM UI" variant="success"](tab-0) sekmesine geçelim


- Sol menüdeki `Systems` ✈ `System List` yolunu izleyin.

- Ana bilgisayarınız **airco-dh4a-qa**'yı bulun ve üzerine tıklayın.

- `Software` ✈ `Packages` seçeneğini seçin

- `Update Packages List` üzerine tıklayın, bunun tamamlanması yaklaşık bir dakika sürecektir

- `Software` ✈ `Patches` seçeneğini seçin

- Mevcut yamaların bir listesini göreceksiniz.

`Select All`'a tıklayın, ardından sağ üstteki `Apply Patches`'a ve son olarak `Confirm`'e tıklayın. <b class="smlmext">SUSE Multi-Linux Manager</b> şimdi CentOS sisteminde yükseltme prosedürünü planlayacak ve gerçekleştirecektir.


> [!NOTE]
> Sisteme uygulanabilecek yamaların listesini görebilmeniz için paket listesinin alınması birkaç dakika sürebilir.


Bu biraz zaman alabileceğinden, kaputun altında neler olduğuna bakalım.
`Events` sekmesine, ardından `History`'ye gidin, sistem <b class="smlm">SMLM</b>'e kaydedildiğinden beri gerçekleşen olayların bir listesini görmelisiniz, ilk satırlarda *Combined Patch*'e benzer bir şey içeren bir olay bulabilmeliyiz.


Üzerine tıklarsak tüm detayları görebiliriz, göz atmaktan çekinmeyin, aksi takdirde simge yeşil olana kadar bekleyin:

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

Mevcut paketlerdeki hataları düzelten yamaları az önce uyguladık, bu yamalanmış paketler doğrudan SUSE'den geliyor, bu bir geçiş (migration) değildir.

<br/>

Bunu henüz güncellemediğimiz üretim sistemiyle karşılaştıralım.

Lütfen `Software` ✈ `Packages` ✈ `Profiles` yolunu izleyin

Üretim sürümü olan `airco-dh4a-prod` sistemini seçin, ardından şuna tıklayın:

![Compare](../assets/SMLM5.1/bottom-compare.png)


Çoğu paket sürümünün değişmediğini, hala aynı sürüm ( **X.X.X**-xyz ) olduğunu ancak bir yama uygulandığını ( X.X.X-**xyz** ) görebiliriz.

Bir sonraki bölüme geçmeden önce, saklanan bir profil (stored profile) oluşturalım, bu, bir sonraki bölümde liberate formülünü uyguladıktan sonra farklılıkları daha net görmemize yardımcı olacaktır.


Lütfen `Software` ✈ `Packages` ✈ `Profile` yolunu izleyin ve `Create System Profile` üzerine tıklayın. İsim olarak şunu verebilirsiniz:

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


Sistemi serbest bırakın (Liberate) (isteğe bağlı)
==============================

Bu **isteğe bağlı** bir adımdır ve destek almak için gerekli değildir.

Şimdi sistemi serbest bırakalım (liberate):

- `Formulas` sekmesine gidin, **Liberate**'i arayın ve bulunduğunda onu seçin ve sağ üstteki `Save` düğmesine tıklayın.

Ekranın üst kısmında mavi renkte bir mesaj göreceksiniz, göremiyorsanız yukarı kaydırın:

![Formula saved](../assets/SMLM5.1/formula_saved.png)


`Highstate` yazan yere tıklayın, başka bir sekmeye yönlendirileceksiniz (`States` ✈ `Highstate`).

Alt kısımdaki özette liberate formülünün listelendiğini görebilirsiniz.

Serbest bırakma (liberation) sürecini başlatmak için tıklayın:

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

Bu biraz zaman alacaktır, lütfen `Events` -> `History`'yi kontrol edin, **Apply highstate scheduled** adlı bir olay görmelisiniz.

Bitmesi için birkaç dakika bekleyelim, bu arada terminal [button label="Centos 7 QA" variant="success"](tab-1)'e bakarak neler olduğunu gözlemleyebilirsiniz.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">Neyin değiştiğini gözlemleyin</b>


Tamamlandığında, farkı görmek için sistemi tekrar karşılaştıralım, eğer zaten orada değilsek `airco-dh4a-qa` sistem adına tıklayalım.

Ardından `Software` ✈ `Packages` ✈ `Profile` yolunu izleyin

**Compare to Stored Profile** altında şuna tıklayın: ![Compare](../assets/SMLM5.1/bottom-compare.png)

Değişen tek şeyin aşağıdaki paketler olduğunu görebiliriz:

- **centos-logos**, **sles_es-logos** ile değiştirildi

- **centos-release**, **sles_es-release-server** ile değiştirildi

Gerisi aynı kalır ancak artık <b class="liberty">Liberty Linux</b> için <b class="suse">SUSE</b> tarafından sağlanan tüm desteğe, yükseltmelere ve yamalara sahipsiniz.

Aynı durum CentOS ve RHEL'in daha modern sürümleri için de geçerlidir, bunları <b class="liberty">Liberty</b>'ye dönüştürebilir ve gerçek yazılım ve kütüphanelerde herhangi bir değişiklik yapmak zorunda kalmadan <b class="suse">SUSE</b> tarafından desteklenmesini sağlayabilirsiniz.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



Üretim sunucusunu serbest bırakın (Liberate) (isteğe bağlı)
=========================================

QA'deki eski Centos 7 sunucumuzu nasıl yamalayacağımızı ve serbest bırakacağımızı (Liberate) gördük, şimdi aynısını üretim sistemiyle yapma zamanı, ancak bu sefer farklı bir sırayla yapacağız.

- İlk olarak, **Liberate** formülünü uygulayacağız

  Üretim sunucumuz `airco-dh4a-prod`'a gidelim ve `Create System Profile` yapalım

  Sonrasında QA sisteminde yaptığımız gibi **Liberate** formülünü uygulayalım.

- Tamamlandığında, sistemi az önce oluşturduğumuz profille karşılaştıralım, görebileceğimiz gibi tek değişiklik **centos-logos** ve **centos-release** paketleri oldu, gerisi tamamen aynı kaldı.


Bu bir geçiş (migration) mi?
==================

Bir geçiş; yepyeni bir sunucu oluşturmayı, tüm uygulamaları sıfırdan yeniden yüklemeyi ve verileri dikkatlice taşımayı içerir; bu zaman alıcı, pahalı ve risk dolu bir süreçtir.

Yaptığımız şey çok daha zarifti. Yerinde yükseltme (in-place upgrade) gerçekleştirdik.

Sunucunun kimliği, ana bilgisayar adı, uygulamaları ve kullanıcı verileri tamamen dokunulmadan kaldı. Sadece güncellemeler için temel kaynağını değiştirdik ve bu ömrünü tamamlamış bileşenler artık yama alan, tam desteklenen bileşenler oldu.

Sistemimizin ömrünü başarıyla uzattık, güvenlik uyumluluğuna geri döndürdük ve tüm bunları tam bir geçişin kesintisi olmadan yaptık. İşte [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]'u yükseklerde uçuran verimlilik budur.




[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] için bu neden önemlidir?
=================================================================================

- [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]'un çalışan sistemlerini desteklenen durumda tutmasına olanak tanır, satıcı ihtiyaçları yerine iş ihtiyaçlarına bağlı olarak geçiş yapmak için onlara zaman tanır.

- Genişletilmiş destek sunarak desteklenmeyen sistemlere sahip olmanın getirdiği riski azaltır. Bu yaklaşım, acil bir geçiş ihtiyacını ortadan kaldırır, her şey her zamanki gibi çalışır ancak artık çağrılarınıza cevap verebilecek bir grup uzman vardır.

- Uzun geçişlerden geçmeden destek sağlayıcısını değiştirme özgürlüğü verir ve bunu ölçekli (at scale) bir şekilde yapmanıza olanak tanır.



Daha fazla bilgi
================

- [RHEL 7 veya CentOS Linux 7'yi SUSE Manager ile Kaydetme](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [SUSE Multi-Linux Support 7 için OpenSCAP uyumluluk taramalarını çalıştırma](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [CentOS Linux 7'yi SUSE Customer Center ile Kaydetme](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)