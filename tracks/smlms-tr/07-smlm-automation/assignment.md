---
slug: smlm-automation
id: adwvwfhmlhbq
type: challenge
title: Otomasyon (İsteğe Bağlı)
tabs:
- id: n1sprltinyjn
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Otomasyon ve yapılandırma yönetimi
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

<img class="logos" alt="Welcome!" src="../assets/logos/07-automation.jpeg"/>

Bu bölümde, görevleri otomatikleştirmek için mevcut olan bazı seçeneklere bakacağız.

Bu laboratuvarda, manuel görevleri yapmaktan, mevcut olan bazı seçenekleri kullanarak otomasyon oluşturmaya geçiyoruz.
<b class="smlmext">SUSE Multi-Linux Manager</b>, BT operasyonlarımız için "otopilot" görevi görerek, yapılandırma standartlarını uygulamamıza ve rutin görevleri tüm filomuzda hassasiyet ve güvenilirlikle otomatikleştirmemize olanak tanır.

Yüzlerce sunucuyu manuel olarak yapılandırmak ve bir adımı kaçırmamayı ummak yerine, süreci ve durumu tanımlarız ve insan operasyonunu sadece bir kez bir zamanlama tanımlamaya indirgeriz.



## <b class="hovereffect">Hedefleriniz:</b>

- Geliştirme sistemlerinizde düzenli olarak güncellemeler gerçekleştiren bir zamanlama oluşturun.

- Sistemin ortamına bağlı olarak farklı bir oturum açma başlığı (banner) göstermek için bir komut dosyası oluşturun.

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


Yinelenen güncellemeleri ayarlama (Setup recurring updates)
=======================

Geliştiricilerin SUSE tarafından sağlanan en son kararlı güncellemelerle çalışmasını istiyoruz, ancak insanların sistemlerini her gün güncellemeyi hatırlamalarına güvenemeyiz, bu yüzden tam olarak bunu yapan yinelenen bir zamanlama oluşturacağız.


Bunu dev grubundaki tüm sistemlere uygulayacağız, böylece her sistemde ayrı ayrı yapılmasına gerek kalmayacak.

- `Systems` ✈ `System Groups` yoluna gidelim.
- `dev` grubuna tıklayın.

Atanmış hiçbir sistemi olmadığını fark ettik, bir tane ekleyelim.

- `Target Systems` üzerine tıklayın ve `sles15`'i seçin
- ardından ![Add Systems](../assets/SMLM5.1/bottom-add_system.png) üzerine tıklayın.

Artık bir sistemimiz olduğuna göre, yinelenen eylemi oluşturalım.

- `Recurring Actions`'a gidin
- ![Create](../assets/SMLM5.1/bottom-create.png) üzerine tıklayın
- Şimdi formu aşağıdaki ayrıntılarla dolduralım:
	+ **Action Type (Eylem Türü):** 'Custom state'
 	+ **Schedule Name (Zamanlama Adı):** 'Update Dev systems'
	+ **Daily (Günlük):** '03:00'
	+ **Configure states to execute (Yürütülecek durumları yapılandırın):** **uptodate:** seçeneğinin seçili olduğundan emin olun
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- Şuna tıklayın:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



Yinelenen eylemler listemizi gözlemlemek için `Schedule` ✈ `Recurring Actions` yoluna gidebiliriz.

Artık tüm dev sistemleri günlük olarak UTC saatiyle 03:00'te güncellenecek.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




Her sistemin bir oturum açma mesajına sahip olduğundan emin olun
==========================================


Yönettiğimiz her sistemin uygun bir oturum açma mesajı içerdiğinden emin olmak için bir yapılandırma kanalı oluşturacağız.



- `Configuration` ✈ `Channels` yoluna gidelim.
- ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png) üzerine tıklayın.
- Formu aşağıdaki ayrıntılarla doldurun:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png) üzerine tıklayın.

Yapılandırma kanalını oluşturduğumuza göre şimdi dolduralım.

- `Add Files` ✈ `Create File` yoluna gidin.
- Aşağıdaki ayrıntıları doldurun:
	+ **Filename/Path:** <b class="highlightcopy">/etc/motd</b>
	+ **File Contents:**
<pre>
This system is the property of [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]].

Server ID: {{ grains['id'] }}
{%- if 'custom_info' in pillar %}
{%- if 'application' in pillar['custom_info'] %}
Running Application "{{ pillar['custom_info']['application'] }}"
{%- else %}
No applications running on this server
{%- endif %}
{%- else %}
No applications running on this server
{%- endif %}
</pre>


- ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png) üzerine tıklayın.

Şimdi organizasyondaki her sistemi yeni yapılandırma kanalına abone yapalım.

- `Admin` ✈ `Organizations` yoluna gidelim.
- **Organization** organizasyonuna tıklayın (Bu varsayılan organizasyondur).
- `States`'e gidin ve az önce oluşturduğumuz kanalı seçin.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- Şuna tıklayın:


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


Bu hemen gerçekleşmeyecek, sistemleri kontrol edelim. Web arayüzü üzerinden basit bir komut çalıştıracağız; çok erken çalıştırılırsa, eski mesajı olan sistemleri ve dosyanın güncellendiği sistemleri görebilirsiniz.

- `Salt` ✈ `Remote Commands` yoluna gidelim.
- Aşağıdakini yazın:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- `Find targets` üzerine tıklayın.
- Sistemlerin bir listesini görmelisiniz, `Run command` üzerine tıklayın.

Şimdi şuna benzer bir şey görmelisiniz:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> Bu işlem birkaç dakika sürebilir, MOTD'yi görmezseniz lütfen birkaç dakika sonra komutu yeniden çalıştırın.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] için bu neden önemlidir?
=================================================================================



- Binlerce sistemi yönetirken her şeyi tek tek yapma lüksümüz yok, görevlerin otomatize edilmesi gerekiyor ki evcil hayvanları (pets) değil, sığırları (cattle) yönetelim.



- "Doğru durumu" tanımlayarak yapılandırma sapmasını (configuration drift) ortadan kaldırıyoruz. Filodaki her sunucu, tıpkı her pilotun aynı kontrol listesini kullanması gibi, aynı oyun kitabından çalışır.



- Yüzlerce sunucuda manuel olarak yapılması saatler sürecek görevler dakikalar içinde tamamlanır. Bu, mühendislerimizi tekrarlayan el emeği yerine yenilik ve iyileştirme üzerinde çalışmaları için özgürleştirir.


- Otomasyon, insan hatasına karşı nihai savunmadır. Manuel yapılandırma sırasında unutulan bir adım veya yazım hatası bir kesintiye yol açabilir. Otomatik, test edilmiş bir süreç her seferinde mükemmel bir şekilde yürütülür ve tüm havayolu şirketimizin güvenilirliğini ve güvenliğini artırır.




Daha fazla bilgi
================


* [SUSE Multi-Linux Manager Ürün Sayfası](https://www.suse.com/products/suse-manager/)

* [Ansible Entegrasyonu](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Salt Kılavuzu](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)