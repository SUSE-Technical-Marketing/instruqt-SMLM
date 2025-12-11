---
slug: smlm-simplify-upgrade-sles
id: gdto6nxqmxvt
type: challenge
title: Basit ve güvenilir bakım
tabs:
- id: 8ov5fjfhuxno
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: hkahivu7lrzk
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Basit ve güvenilir bakım
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

<img class="logos" alt="Welcome!" src="../assets/logos/04-upgrade.jpeg"/>

Şimdiye kadar, karma filomuzun çeşitliliğini yönetmeye ve hatta eski (legacy) sistemlerimizin ömrünü uzatmaya odaklandık. Şimdi, dikkatimizi havayolu şirketimizin çekirdeğine çeviriyoruz: amiral gemisi <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) sistemlerimiz.


Bunları son teknoloji ürünü, uzun menzilli jetlerimiz olarak düşünün. Güvenilirlikleri çok önemlidir ve onları en iyi durumda tutmak, düzenli, planlı servis yamaları ve yükseltmeleri içerir. Bir sonraki egzersiz tam olarak budur: Herhangi bir kritik sistemin yaşam döngüsünü yönetmede yaygın bir görev olan sürüm yükseltme sürecinden geçeceğiz.



Ve örnek olarak SLES kullanıyor olsak da, evrensel kontrol kulemizin temel ilkesini hatırlayın: Gerçekleştirmek üzere olduğunuz işlem, diğer herhangi bir Linux dağıtımı için kullanacağınız işlemin aynısıdır. Arayüz ve metodoloji değişmez.


## <b class="hovereffect">Hedefleriniz:</b>

- Test uçağımız olarak hizmet vermesi için yeni bir SLES 15 SP5 sistemini dahil edin (Onboard).
- SP5'ten SP6'ya büyük bir servis yükseltmesi (major service upgrade) gerçekleştirin.



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






Dahil etme ve hazırlık (Onboarding and preparation)
==========================

[button label="SLES 15" variant="success"](tab-1) sekmesinden sistem terminaline erişin


Sistemi <b class="smlm">SMLM</b> içinde **sles15** olarak kaydedelim

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


Şimdi, [button label="SMLM UI" variant="success"](tab-0) sekmesine geçelim


Yükseltmeyi yürütme (Executing the upgrade)
=====================

Onu yakında sistemler listesinde görmeliyiz, `Systems` ✈ `System List` ✈ `All` yoluna gidelim, görmüyorsanız lütfen dahili tarayıcıda yenile'ye tıklayın.


Üzerine tıklayalım ve `Software` ✈ `Packages` ✈ `Upgrade` yoluna gidelim.


Sorunsuz bir geçiş sağlamak için en son güncellemeleri uygulamak en iyisidir.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Şuna tıklayın </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Bunun tamamlanması biraz zaman alabilir.

<br/>


## <b class="hovereffect">Ürün geçişi (Product migration)</b>


Tamamlandığında, lütfen `Software` ✈ `Product Migration` yoluna gidin



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">**Target Products** adlı bir bölüm göreceksiniz. <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b>'ün seçili olduğundan emin olun, ardından şuna basın: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

Size bir özet ve ek seçenekler içeren bir onay ekranı gösterilecektir. Varsayılanları olduğu gibi bırakın ve tıklayın: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

Sistem önce bir deneme (dry run) yapmanızı isteyecektir, bunu görmezden gelin ve basın: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

Bu biraz zaman alacaktır. Durumu izlemek için `Events` ✈ `History`'ye gidin ve **Product Migration** olayını izleyin. Durum simgesi yeşile döndüğünde geçiş tamamlanmış demektir. `Software` ✈ `Software Channels`'a giderek ve sistemin artık yeni SP6 kanallarına abone olduğunu onaylayarak bunu doğrulayabilirsiniz.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">Geçiş Sonrası Yeniden Başlatma (Post-Migration Reboot)</b>

- `Systems` ✈ `System List` ✈ `All` yoluna geri dönün

- `sles15` sisteminin yanında artık bir yeniden başlatma simgesi olduğuna dikkat edin:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  Bu, genellikle büyük bir çekirdek (kernel) güncellemesi nedeniyle yeniden başlatmanın gerekli olduğunu gösterir.

- Üzerine tıklayın, şuna benzer bir şey göreceğiz:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- `Schedule System Reboot` üzerine tıklayın ve sonraki ekranda şuna tıklayın ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> Yeniden başlatma hemen gerçekleşmeyecektir.

<br/>


## <b class="hovereffect">Zamanlamanın Önemi (The importance of Scheduling)</b>

Bu eylemleri hemen gerçekleşecek şekilde planladık, ancak bu her zaman arzu edilen bir durum değildir. <b class="smlm">SMLM</b>, Bakım Pencerelerinin (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`) oluşturulmasını destekler, bu da yeniden başlatmalar gibi büyük olayların yalnızca önceden onaylanmış bu dönemlerde gerçekleşmesini sağlamanıza olanak tanır.



Zamanlama, özellikle üretim sistemleri için yararlıdır, çünkü sistem gruplarında dikkatlice planlanmış değişikliklere ve hatta aşamalı "kanarya" (canary) dağıtımlarına olanak tanır.

<br/>

> [!NOTE]
> KLP ile çekirdek canlı yama (live patching) yapmak mümkündür, bu, yeniden başlatmadan Linux çekirdeklerine en son güvenlik güncellemelerini uygulamayı mümkün kılar.



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] için bu neden önemlidir?
=================================================================================

- Sistem yükseltmeleri ve diğer rutin görevler basit ve tekrarlanabilir olmalıdır, aksi takdirde maliyetli hatalar yapma riskiyle karşı karşıya kalırız. Bu araçlarla, eylemleri tam olarak ne zaman ve nerede gerçekleştireceğimizi kontrol edebilir, filomuz için kritik bakımı güvenle planlayabiliriz.


- Eylemleri ne zaman ve nerede gerçekleştireceğimizi kontrol edebilir ve yerdeki filomuzda bakım operasyonları planlayabiliriz.


Daha fazla bilgi
================

- [KLP ile canlı çekirdek yaması (Live kernel patching)](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Bakım Pencereleri (Maintenance Windows)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Yönetim Kılavuzu (Administration Guide)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)