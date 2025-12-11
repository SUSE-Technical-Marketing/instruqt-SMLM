---
slug: smlm-simplify-upgrade-sles
id: vitic9uxoxxh
type: challenge
title: सरल और विश्वसनीय रखरखाव
tabs:
- id: yu1xbrzxcdpi
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: le48k2rgbeum
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 सरल और विश्वसनीय रखरखाव
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

अब तक, हमने अपने मिश्रित बेड़े की विविधता को प्रबंधित करने और यहां तक कि हमारे पुराने (legacy) सिस्टम के जीवन को बढ़ाने पर ध्यान केंद्रित किया है। अब, हम अपना ध्यान अपनी एयरलाइन के मूल (core) की ओर मोड़ते हैं: हमारे प्रमुख (flagship) <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) सिस्टम।


इनके बारे में हमारे अत्याधुनिक, लंबी दूरी के जेट के रूप में सोचें। उनकी विश्वसनीयता सर्वोपरि है, और उन्हें चरम स्थिति (peak condition) में रखने के लिए नियमित, नियोजित सर्विस पैचिंग और अपग्रेड शामिल हैं। यह अगला अभ्यास ठीक यही है: हम एक संस्करण अपग्रेड (version upgrade) की प्रक्रिया से गुजरने वाले हैं, जो किसी भी महत्वपूर्ण सिस्टम के जीवनचक्र के प्रबंधन में एक सामान्य कार्य है।



और जब हम उदाहरण के तौर पर SLES का उपयोग कर रहे हैं, तो हमारे यूनिवर्सल कंट्रोल टॉवर के प्रमुख सिद्धांत को याद रखें: जिस प्रक्रिया को आप निष्पादित करने वाले हैं, वह वही है जिसे आप किसी अन्य Linux डिस्ट्रीब्यूशन के लिए उपयोग करेंगे। इंटरफ़ेस और कार्यप्रणाली (methodology) नहीं बदलती है।


## <b class="hovereffect">आपके उद्देश्य:</b>

- हमारे परीक्षण विमान के रूप में काम करने के लिए एक नया SLES 15 SP5 सिस्टम ऑनबोर्ड (Onboard) करें।
- SP5 से SP6 तक एक प्रमुख सर्विस अपग्रेड (mayor service upgrade) करें।



Lab details
===========

उपयोगकर्ता नाम (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

पासवर्ड (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>






ऑनबोर्डिंग और तैयारी (Onboarding and preparation)
==========================

टैब [button label="SLES 15" variant="success"](tab-1) से सिस्टम टर्मिनल तक पहुंचें


आइए सिस्टम को <b class="smlm">SMLM</b> के भीतर **sles15** के रूप में पंजीकृत करें

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


अब, चलिए [button label="SMLM UI" variant="success"](tab-0) टैब पर स्विच करते हैं


अपग्रेड निष्पादित करना (Executing the upgrade)
=====================

हमें इसे जल्द ही सिस्टम की सूची में देखना चाहिए, चलिए `Systems` ✈ `System List` ✈ `All` पर चलते हैं, यदि आप इसे नहीं देखते हैं तो कृपया आंतरिक ब्राउज़र पर रिफ्रेश क्लिक करें।


आइए इस पर क्लिक करें और `Software` ✈ `Packages` ✈ `Upgrade` पर जाएं।


सुचारू माइग्रेशन सुनिश्चित करने के लिए नवीनतम अपडेट लागू करना सबसे अच्छा है।



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">क्लिक करें </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


इसे पूरा होने में कुछ समय लग सकता है।

<br/>


## <b class="hovereffect">प्रोडक्ट माइग्रेशन (Product migration)</b>


एक बार जब यह समाप्त हो जाए, तो कृपया `Software` ✈ `Product Migration` पर जाएं



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">आपको **Target Products** नामक एक अनुभाग दिखाई देगा। सुनिश्चित करें कि <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> चयनित है, फिर दबाएं: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

आपको सारांश और अतिरिक्त विकल्पों के साथ एक पुष्टिकरण स्क्रीन दिखाई देगी। डिफॉल्ट को वैसे ही छोड़ दें और क्लिक करें: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

सिस्टम आपसे पहले ड्राई रन (dry run) करने के लिए कहेगा, इसे अनदेखा करें और दबाएं: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

इसमें कुछ समय लगेगा। स्थिति की निगरानी के लिए, `Events` ✈ `History` पर जाएं और **Product Migration** ईवेंट देखें। एक बार जब इसका स्टेटस आइकन हरा हो जाता है, तो माइग्रेशन पूरा हो जाता है। आप `Software` ✈ `Software Channels` पर जाकर और यह पुष्टि करके कि सिस्टम अब नए SP6 चैनलों की सदस्यता ले चुका है (subscribed), इसे सत्यापित कर सकते हैं।

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">पोस्ट-माइग्रेशन रिबूट (Post-Migration Reboot)</b>

- वापस नेविगेट करें `Systems` ✈ `System List` ✈ `All`

- ध्यान दें कि `sles15` सिस्टम के बगल में अब एक रिबूट आइकन है:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  यह इंगित करता है कि रिबूट आवश्यक है, आमतौर पर एक प्रमुख कर्नेल अपडेट के कारण।

- इस पर क्लिक करें, हम इसके समान कुछ देखेंगे:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- `Schedule System Reboot` पर क्लिक करें और अगली स्क्रीन में क्लिक करें ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> रिबूट तुरंत नहीं होगा।

<br/>


## <b class="hovereffect">शेड्यूलिंग का महत्व (The importance of Scheduling)</b>

हमने इन कार्यों को तुरंत होने के लिए शेड्यूल किया है, लेकिन यह हमेशा वांछनीय नहीं होता है। <b class="smlm">SMLM</b> रखरखाव विंडोज़ (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`) के निर्माण का समर्थन करता है जो आपको यह सुनिश्चित करने की अनुमति देता है कि रिबूट जैसी प्रमुख घटनाएं केवल उन पूर्व-अनुमोदित अवधि के दौरान हों।



शेड्यूलिंग उत्पादन सिस्टम (production systems) के लिए विशेष रूप से उपयोगी है, क्योंकि यह सिस्टम के समूहों पर सावधानीपूर्वक नियोजित परिवर्तनों और यहां तक कि चरणबद्ध "कैनरी" (canary) परिनियोजन की अनुमति देता है।

<br/>

> [!NOTE]
> KLP के साथ कर्नेल लाइव पैचिंग (live patching) करना संभव है, यह रिबूट किए बिना Linux कर्नेल पर नवीनतम सुरक्षा अपडेट लागू करना संभव बनाता है।



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] के लिए यह महत्वपूर्ण क्यों है?
=================================================================================

- सिस्टम अपग्रेड और अन्य नियमित कार्य सरल और दोहराए जाने योग्य होने चाहिए, अन्यथा, हम महंगी गलतियाँ करने का जोखिम उठाते हैं। इन उपकरणों के साथ, हम ठीक से नियंत्रित कर सकते हैं कि हम कब और कहाँ कार्य करते हैं, आत्मविश्वास के साथ हमारे बेड़े के लिए महत्वपूर्ण रखरखाव का समय निर्धारण (scheduling) करते हैं।


- हम नियंत्रित कर सकते हैं कि हम कब और कहाँ कार्य करते हैं, और हमारे ग्राउंडेड बेड़े पर रखरखाव कार्यों को शेड्यूल कर सकते हैं।


अधिक जानकारी
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)