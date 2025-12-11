---
slug: smlm-managing-linux-distros
id: ajrioagmcyud
type: challenge
title: विभिन्न Linux डिस्ट्रीब्यूशन का प्रबंधन
tabs:
- id: n9hmplsl7n6m
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: 7y2jxuoqq28g
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 विभिन्न Linux डिस्ट्रीब्यूशन का प्रबंधन
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

<img class="logos" alt="Welcome!" src="../assets/logos/02-managing_linux_distros.jpeg"/>

यहाँ [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] में, <b class="smlmext">SUSE Multi-Linux Manager</b> हमारे Linux डिस्ट्रीब्यूशन और आर्किटेक्चर के विविध बेड़े (fleet) को एक ही फलक (single pane of glass) से प्रबंधित करने की कुंजी है। इसने हमें उन अतिरिक्त अनुकूलन (customizations) से बचने में मदद की है जो इंजीनियरों के रूप में हमारे काम को जटिल बनाते थे, जिससे हमारी सिस्टम नीतियों को बनाए रखने और लागू करने के लिए आवश्यक लागत और समय बढ़ जाता था।

इस उपकरण के साथ, हम किसी एक वेंडर, आर्किटेक्चर या ऑटोमेशन प्लेटफ़ॉर्म में लॉक नहीं हैं। हम अपने वातावरण के लिए जो आवश्यक है उसे चुनने और उन सभी को एक ही तरीके से प्रबंधित करने के लिए स्वतंत्र हैं। कल्पना कीजिए कि यदि हमारे बेड़े में हर प्रकार के विमान के लिए, हमें अपनी भाषा और प्रक्रियाओं के साथ एक अलग हवाई यातायात नियंत्रण टॉवर की आवश्यकता होती। परिचालन की जटिलता असहनीय होगी, और लागत निषेधात्मक होगी।

हम सभी जानते हैं कि एक निश्चित विमान मॉडल एक विशिष्ट मार्ग के लिए बेहतर है; आधे घंटे की उड़ान के लिए जंबो जेट उड़ाना लागत प्रभावी नहीं है। यही बात हमारे Linux डिस्ट्रीब्यूशन पर भी लागू होती है। जबकि SUSE के अपने डिस्ट्रीब्यूशन उत्कृष्ट हैं, हमारे कुछ अनुप्रयोगों की विशिष्ट आवश्यकताएं हैं। <b class="smlm">SMLM</b> यह सुनिश्चित करता है कि हम कभी भी लॉक-इन न हों और हाथ में मौजूद कार्य के लिए हमेशा सर्वोत्तम समाधान को एकीकृत कर सकें।


## <b class="hovereffect">आपके उद्देश्य:</b>

- एक Ubuntu 24.04 LTS सिस्टम को ऑनबोर्ड (Onboard) करें, जो हमारी मार्केटिंग टीम के लिए आवश्यक एक विशेष सिस्टम है।

- प्रदर्शित करें कि हम इस नए, अलग सिस्टम को उसी टूल और पैचिंग प्रक्रियाओं का उपयोग करके कैसे प्रबंधित करते हैं जैसे हमारे बाकी बेड़े को करते हैं।



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


Ubuntu को ऑनबोर्ड करना (Onboarding Ubuntu)
=================

हमारे मार्केटिंग विभाग से एक नया सेवा अनुरोध आया है। उनके ग्राफिक डिजाइनर एक विशिष्ट रचनात्मक सुइट (creative suite) पर भरोसा करते हैं जो केवल Ubuntu पर समर्थित है। हम उनके सिस्टम को ऑनबोर्ड करने जा रहे हैं ताकि हम इसे प्रबंधित कर सकें और सुनिश्चित कर सकें कि यह हमारे सुरक्षा और अनुपालन मानकों को पूरा करता है, उसी तरह जैसे हम दूसरों के साथ करते हैं।

चलो शुरू करें।
<br/>

- [button label="Ubuntu 2404 LTS" variant="success"](tab-1) टैब से सिस्टम टर्मिनल तक पहुंचें

  इससे पहले कि हम कोई बदलाव करें, आइए जांचें कि यह पैकेज कहां से प्राप्त कर रहा है:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

यह वर्कस्टेशन सीधे सार्वजनिक Ubuntu रिपॉजिटरी से सॉफ़्टवेयर खींच रहा है। यह दो समस्याएं प्रस्तुत करता है: पहला, लागू किए जा रहे पैच पर हमारा कोई नियंत्रण नहीं है, जो एक सुरक्षा चिंता है। दूसरा, जैसा कि मार्केटिंग टीम ने बताया, हर बार जब ये वर्कस्टेशन अपडेट प्राप्त करते हैं, तो वे कार्यालय के इंटरनेट कनेक्शन को धीमा कर सकते हैं, जिससे अन्य कर्मचारियों के लिए निराशा होती है।


आइए इस सिस्टम को हमारे प्रबंधन के तहत लाएं। यह सभी सॉफ़्टवेयर आवश्यकताओं के लिए इसे हमारे आंतरिक <b class="smlmext">SUSE Multi-Linux Manager</b> इंस्टेंस से जोड़कर दोनों समस्याओं का समाधान करेगा।

हम ऐसा करने के लिए [button label="web UI" variant="success"](tab-0) का उपयोग करने जा रहे हैं:

- `Home` ✈ `Overview` के तहत, चलिए `Register Systems` पर क्लिक करते हैं

- निम्नलिखित विवरण भरें:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:**

  ```txt
  root
  ```

  - **Password:**

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** <b class="highlightcopy">1-ubuntu2404</b>

- बाकी को वैसे ही छोड़ दें और क्लिक करें

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- पंजीकरण प्रक्रिया को पूरा होने में कुछ मिनट लग सकते हैं, चलिए [button label="terminal" variant="success"](tab-1) पर जाते हैं और यह देखने के लिए कि क्या बदला है, पहला कमांड एक बार और चलाते हैं:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


हम देख सकते हैं कि नई फाइलें दिखाई दी हैं:

**/etc/apt/sources.list.d/susemanager:***

वे सिस्टम को <b class="smlm">SMLM</b> में हमारे केंद्रीय रूप से प्रबंधित और नियंत्रित चैनलों की ओर इंगित करते हैं।


हम यह भी देख सकते हैं कि मूल फ़ाइल, **/etc/apt/sources.list.d/ubuntu.sources**, को सभी सार्वजनिक रिपॉजिटरी को अक्षम करने के लिए संशोधित किया गया है लेकिन हटाया नहीं गया है, यह हमें ज़रूरत पड़ने पर आसानी से वापस (roll back) जाने की अनुमति देगा।


> [!NOTE]
> पंजीकरण के लिए पासवर्ड प्रमाणीकरण के साथ SSH के माध्यम से root का उपयोग करना केवल प्रदर्शन उद्देश्यों के लिए है और उत्पादन (production) के लिए अनुशंसित नहीं है।


> [!NOTE]
> डिफ़ॉल्ट रूप से हमें UI के माध्यम से या कमांड लाइन < salt-key -A -y > के माध्यम से प्रत्येक सिस्टम के पंजीकरण को स्वीकार करना होगा, यहाँ <b class="smlm">SMLM</b> को स्वतः स्वीकार (auto approve) करने के लिए कॉन्फ़िगर किया गया है।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



अब [button label="SMLM UI" variant="success"](tab-0) टैब पर स्विच करें


- हम `Systems` ✈ `System List` ✈ `All` पर नेविगेट करते हैं

  हम वह सिस्टम देख सकते हैं जिसे हमने अभी पंजीकृत किया है `Ubuntu2404lts`, ध्यान दें कि डिफ़ॉल्ट रूप से यह होस्टनाम (hostname) के तहत पंजीकृत होगा।

  आइए इस पर क्लिक करें, हम सीधे `Details` - `Overview` पर जाएंगे जहां हम अन्य सूचनाओं के बीच देख सकते हैं:

  - सिस्टम की स्थिति।
  - होस्टनाम, आईपी पता, वर्चुअलाइजेशन का प्रकार, उपयोग किया गया कर्नेल और इंस्टॉल किए गए उत्पादों जैसी सभी जानकारी।
  - वे चैनल जिन्हें इसने सब्सक्राइब किया है।

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

कई Linux डिस्ट्रीब्यूशन का प्रबंधन
=====================================


जैसा कि पहले बताया गया है, <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> में हम विभिन्न Linux डिस्ट्रीब्यूशन का उपयोग करते हैं, जैसे हम विभिन्न हवाई जहाज मॉडल और कंपनियों का उपयोग करते हैं। यह हमें हमारी प्रत्येक आवश्यकता के लिए सबसे उपयुक्त उत्पाद का उपयोग करके प्रतिस्पर्धा से आगे रहने में मदद करता है।

<b class="smlmext">SUSE Multi-Linux Manager</b> के साथ हम उन सभी को समान प्रक्रियाओं, समान समय सारिणी, आदि के साथ प्रबंधित कर सकते हैं... समान इंटरफ़ेस और तंत्र का उपयोग करके।

नीचे हम पता लगाएंगे कि आपके सिस्टम पर विभिन्न कार्यों को कैसे निष्पादित किया जाए, उसी प्रक्रिया का पालन करते हुए चाहे हमारे सिस्टम कोई भी OS चला रहे हों, बिना अनावश्यक अनुकूलन (customizations) बनाए।


## <b class="hovereffect">अतिरिक्त जानकारी जोड़ें</b>


आइए उस सिस्टम के साथ जारी रखें जिसे हमने अभी पंजीकृत किया है, हम इसमें कुछ सेटिंग्स और जानकारी जोड़ने जा रहे हैं:

- आइए `Properties` में क्लिक करें, जहां हम सिस्टम के बारे में अतिरिक्त जानकारी जोड़ेंगे और कुछ सेटिंग्स बदलेंगे।


  - पैच के स्वचालित अनुप्रयोग को सक्षम करें (Enable Automatic application of patches):

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    प्रासंगिक पैच होने पर यह स्वचालित रूप से सिस्टम को पैच करेगा।



  - सिस्टम के लिए निम्नलिखित विवरण जोड़ें:


| फ़ील्ड (Field) | सामग्री (Content)                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- आइए देखें कि यह किस हार्डवेयर पर चल रहा है:

  - क्लिक करें `Details` ✈ `Hardware`


<br/>

> [!NOTE]
> यह सब API के माध्यम से स्वचालित किया जा सकता है।

<br/>

अब हम कस्टम कीज़ (custom keys) का उपयोग करके सिस्टम में कुछ अतिरिक्त जानकारी जोड़ने जा रहे हैं, इस जानकारी को बाद में आपके ऑटोमेशन स्क्रिप्ट में आसानी से उपयोग किया जा सकता है।


- क्लिक करें `Details` ✈ `Custom Info`

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- `application` पर क्लिक करें और **value** (मान) को निम्नलिखित के साथ भरें:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> हमने आपके लिए कस्टम की **application** पहले ही बना दी है, यदि आप अपनी खुद की कीज़ (keys) बनाना चाहते हैं तो यह उतना ही सरल है जितना कि यहाँ जाना: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

आइए Systems सूची पर वापस जाएं

`Systems` ✈ `System List` ✈ `All`


आइए किसी भी सिस्टम पर क्लिक करें और `Details` ✈ `Custom Info` पर जाएं।

हमने पहले से ही प्रत्येक सिस्टम को एक मान (value) के साथ आबाद (populate) कर दिया है,

<br/>

अब `Details` ✈ `Overview` पर जाएं और **Installed Products** और **Subscribed Channels** पर ध्यान दें, ये आपके Ubuntu सिस्टम वाले से अलग हैं क्योंकि वे एक अलग ऑपरेटिंग सिस्टम चला रहे हैं।



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">एक साथ कई सिस्टम पर कमांड चलाएं</b>


आइए हमारे पास मौजूद सभी सिस्टम पर कुछ करें, `Systems` ✈ `System List` ✈ `All` पर वापस जाएं और सभी का चयन करें:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

**Base Channel** कॉलम पर ध्यान दें, हमारे पास तीन अलग-अलग OS चलाने वाले सिस्टम हैं।

<br/>

संचालित करने के लिए इच्छित सभी सिस्टम का चयन करने के बाद, आइए एक समूह कार्रवाई (group action) करने चलते हैं:

`Systems` ✈ `System Set Manager`

आइए उन सभी पर एक कमांड चलाएं, उसके लिए हम यहां जा सकते हैं:

`Misc` ✈ `Remote Command`

फिर निम्नलिखित विवरण भरें और बाकी को डिफ़ॉल्ट मानों के साथ छोड़ दें:


स्क्रिप्ट (Script):

```bash,run
cat /etc/os-release
```

शेड्यूल (schedule) को संशोधित न करें, हम चाहते हैं कि यह जल्द से जल्द चले, क्लिक करें:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

आपको शीर्ष पर एक नीला नोटिस दिखाई देगा जो दर्शाता है कि कार्य निर्धारित किया गया है।

आइए परिणाम देखने चलते हैं, उसके लिए हम यहां जाएंगे:

`Schedule` ✈ `Completed Actions`

हम कार्रवाइयों की एक सूची देखेंगे, **Filter by Action** फ़ील्ड में टाइप करें:

```text
Run
```
सूची में दिखाई देने वाली शीर्ष प्रविष्टि पर क्लिक करें, यह इसके समान होनी चाहिए:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


वहां हम **Completed Systems** पर जा सकते हैं और सिस्टम नाम पर क्लिक करके परिणाम की जांच कर सकते हैं।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

इसके साथ हम इस भाग को पूरा करते हैं, हम वर्कशॉप के दौरान कई Linux सिस्टम को प्रबंधित करने के तरीके के और उदाहरण देखेंगे।



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] के लिए यह महत्वपूर्ण क्यों है?
=================================================================================

- कोई वेंडर लॉक-इन नहीं, बदलते बाजारों पर तेजी से प्रतिक्रिया करने के लिए पसंद की स्वतंत्रता और लचीलापन बनाए रखें।

- अनुकूलन (customizations) पर अतिरिक्त काम से बचकर सरल बनाएं और समय बचाएं।

- सभी को प्रबंधित करने के लिए एक एकल UI जटिलता को कम करता है और भविष्य की समस्या निवारण (troubleshooting), स्केलिंग, पैचिंग और ऑटोमेशन को बहुत अधिक चुस्त और कम समय लेने वाला बना देगा।



अधिक जानकारी
================

समर्थित डिस्ट्रीब्यूशन की सूची के लिए कृपया देखें:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)