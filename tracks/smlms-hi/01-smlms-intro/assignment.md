---
slug: smlms-intro
id: y1mxf79hbl2p
type: challenge
title: SUSE Multi-Linux Hands-on Workshop में आपका स्वागत है!
teaser: SUSE Multi-Linux Hands-on Workshop में आपका स्वागत है! इस खंड में हम आपको
  वर्कशॉप और इसके मुख्य घटकों
notes:
- type: text
  contents: |
    # SUSE Multi-Linux Hands-on Workshop में आपका स्वागत है!
    कृपया प्रतीक्षा करें जब तक हम आपका लैब वातावरण सेटअप करते हैं।
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: kekjyizrbpre
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

<b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop में आपका स्वागत है
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

इस वर्कशॉप में आप उस जादू का कुछ हिस्सा देखेंगे जो <b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) कर सकता है; यह एक एकीकृत इंटरफ़ेस (unified interface) से बड़े पैमाने पर कई Linux डिस्ट्रीब्यूशन को प्रबंधित करने के लिए <b class="suse">SUSE</b> का समाधान है। और आप यह भी जानेंगे कि आप अपने पुराने (legacy) प्रोडक्शन सर्वर को <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>) के साथ कैसे समर्थित रख सकते हैं, जो Linux सिस्टम के लिए हमारा पेशेवर और विश्वसनीय सपोर्ट समाधान है।

&emsp;&emsp; आप <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> में एक **इंजीनियर (engineer)** की भूमिका अपनाएंगे, एक एयरलाइन जहां हर विमान में एक Linux सर्वर होता है।

&emsp;&emsp; किसी भी हवाई जहाज के घटक की तरह, यह महत्वपूर्ण है कि वे सर्वर स्थिर और विश्वसनीय बने रहें, चाहे वे किसी डेटासेंटर में जमीन पर स्थित हों या बादलों के ऊपर उड़ रहे हों ☁ ☁ ☁


&emsp;&emsp; कुछ विमान मॉडलों को एक अलग Linux फ्लेवर, या एक अलग CPU आर्किटेक्चर की आवश्यकता होगी। <b class="smlm">SMLM</b> के लिए यह कोई समस्या नहीं है; आप उस Linux डिस्ट्रीब्यूशन और CPU आर्किटेक्चर को चुनने के लिए स्वतंत्र हैं जो आपकी आवश्यकताओं के लिए बेहतर है, बिना आसान मानकीकरण और प्रबंधन को छोड़े।


&emsp;&emsp; Linux लैंडस्केप के प्रबंधन के लिए जिम्मेदार एक इंजीनियर के रूप में, आप उन कुछ समाधानों से गुजरेंगे जो <b class="smlm">SMLM</b> और <b class="smls">SMLS</b> आपको सिस्टम प्रबंधन को आसान और स्वचालित करने और हो सकने वाली असाधारण समस्याओं को हल करने के लिए प्रदान करते हैं।


विभिन्न चुनौतियों के दौरान आपके पास निम्नलिखित उपकरण उपलब्ध होंगे:

 ✈ **SUSE Multi-Linux Manager**:
   आपके संपूर्ण Linux स्टैक को प्रबंधित करने के लिए एकमात्र फलक (single pane of glass)।

 ✈ **Centos 7**:
   एक लीगेसी डिस्ट्रीब्यूशन जो अभी भी कुछ पुराने विमानों और ग्राउंड सिस्टम पर उपयोग में है।

 ✈ **Ubuntu 24**: हमारे मार्केटिंग विभाग द्वारा उनके ग्राफिक डिज़ाइन एप्लिकेशन को चलाने के लिए आवश्यक एक विशिष्ट Linux डिस्ट्रीब्यूशन।

 ✈ **SLES 15**: <b class="suse">SUSE</b> का अत्यधिक विश्वसनीय, स्थिर और सुरक्षित Linux डिस्ट्रीब्यूशन जो हमारे सबसे महत्वपूर्ण सिस्टम की रीढ़ बनाता है।


## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

यह आपके सॉफ़्टवेयर-डिफाइंड इंफ्रास्ट्रक्चर के लिए अपनी श्रेणी में सर्वश्रेष्ठ ओपन सोर्स इंफ्रास्ट्रक्चर प्रबंधन समाधान है।

&emsp;&emsp; <b class="smlmext">SUSE Multi-Linux Manager</b> को आपकी एंटरप्राइज़ DevOps और IT Operations टीमों को जटिलता कम करने और अपनी IT संपत्ति पर नियंत्रण पाने में मदद करने के लिए डिज़ाइन किया गया था, जो विभिन्न हार्डवेयर आर्किटेक्चर, हाइपरवाइजर के साथ-साथ कंटेनर, IoT और क्लाउड प्लेटफॉर्म पर Linux सिस्टम को प्रबंधित करने के लिए एक एकल लेकिन बहुत शक्तिशाली उपकरण है।

&emsp;&emsp; यह तेजी से, सुसंगत और दोहराए जाने योग्य सर्वर परिनियोजन (deployment) के लिए Linux सर्वर और IoT डिवाइस प्रोविजनिंग, पैचिंग और कॉन्फ़िगरेशन को स्वचालित करता है, जिससे संचालन को अनुकूलित करने और लागत कम करने में मदद मिलती है। और आपके विकास, परीक्षण और उत्पादन वातावरण में अपने सिस्टम, VMs और कंटेनरों की स्वचालित निगरानी, ​​ट्रैकिंग, ऑडिटिंग और रिपोर्टिंग के साथ, आप आंतरिक सुरक्षा नीतियों और बाहरी नियमों का अनुपालन सुनिश्चित कर सकते हैं।


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


यह एक व्यापक सेवा है जो विभिन्न Linux डिस्ट्रीब्यूशन के लिए तकनीकी सहायता और रखरखाव प्रदान करती है, जिसमें आपके मौजूदा Red Hat Enterprise Linux (RHEL), CentOS, <b class="liberty">SUSE Liberty Linux</b>, और <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) शामिल हैं, जो पेशकश पर निर्भर करता है।

&emsp;&emsp; यह संगठनों को एकल सपोर्ट ढांचे के तहत मिश्रित Linux वातावरण को कुशलतापूर्वक प्रबंधित करने में सक्षम बनाता है।
खरीदे गए पैकेज के आधार पर, <b class="smlsext">SUSE Multi-Linux Support</b> में <b class="smlmext">SUSE Multi-Linux Manager</b> भी शामिल हो सकता है, जो इन डिस्ट्रीब्यूशन को प्रबंधित करने के लिए एक मल्टी-Linux प्रबंधन उपकरण है।



 🌅 Instruqt UI का अन्वेषण करें
=======================
इससे पहले कि हम अपना पहला कार्य शुरू करें, आइए Instruqt UI को देखने के लिए एक पल लें।

+ स्क्रीन का **दायां भाग** आपको ये निर्देश और नेविगेशन नियंत्रण प्रदान करता है।

+ **बायां भाग** आपको विभिन्न मशीनों और सेवाओं तक पहुंच प्रदान करता है जो हमारे लैब वातावरण को बनाते हैं।

Instruqt UI के भीतर आप बाएं पैनल के शीर्ष पर टैब पर क्लिक करके [button label="SMLM UI" variant="success"](tab-0) और उपलब्ध [button label="terminals" variant="success"](tab-1) के बीच कूद सकते हैं।


> [!NOTE]
> वेब UI पर कोई स्वचालित रीलोडिंग नहीं होती है, कुछ मामलों में अपडेट देखने के लिए आपको Instruqt के आंतरिक वेब ब्राउज़र को रीलोड करना पड़ सकता है।


🛫 <b class="smlmext">SUSE Multi-Linux Manager</b> में लॉग इन करना 🛫
========================================
आइए आपको वातावरण से परिचित कराते हैं।

- [button label="SMLM UI" variant="success"](tab-0) से लैब के अंदर <b class="smlmext">SUSE Multi-Linux Manager</b> खोलें


- निम्नलिखित क्रेडेंशियल्स के साथ लॉग इन करें:

  - उपयोगकर्ता नाम (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - पासवर्ड (Password):

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

यदि सब कुछ ठीक रहा, तो आपको <b class="smlmext">SUSE Multi-Linux Manager</b> UI में **Overview** पृष्ठ देखना चाहिए जो `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]` उपयोगकर्ता के रूप में लॉग इन है।

> [!NOTE]
> यदि आप सीधे अपने ब्राउज़र के माध्यम से <b class="smlmext">SUSE Multi-Linux Manager</b> UI तक पहुंचना चाहते हैं तो आप ऐसा भी कर सकते हैं:

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> यदि पृष्ठ सही ढंग से लोड नहीं होता है, तो लैब वातावरण शुरू होने के बाद आपको ब्राउज़र टैब को रीफ्रेश करने की आवश्यकता हो सकती है।




🗺  <b class="smlmext">SUSE Multi-Linux Manager</b> का अन्वेषण करें 🗺
======================================

इससे पहले कि हम उड़ान भरें, आइए नियंत्रणों से परिचित हों। इसका मतलब विस्तृत दौरा करना नहीं है, बल्कि उन प्रमुख उपकरणों का संक्षिप्त अवलोकन है जिनका उपयोग हम पूरे वर्कशॉप में करेंगे। हम आपको जिज्ञासु होने और अन्वेषण करने के लिए प्रोत्साहित करते हैं।


चलिए शुरू करते हैं।


- **Systems मेनू** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  बाएं हाथ के पैनल पर, `systems` पर क्लिक करें। यह हमारा बेड़े (fleet) का अवलोकन है, जो प्रत्येक पंजीकृत सर्वर को दिखाता है। सूची अभी छोटी है, लेकिन जैसे-जैसे हम अपने अभ्यास पूरा करेंगे, यह बढ़ती जाएगी।

   - **System Lists**

     यह अनुभाग सुविधाजनक, पूर्व-फ़िल्टर किए गए दृश्य प्रदान करता है। उदाहरण के लिए, `Out of Date` सूची आपको तुरंत दिखाती है कि किन सर्वरों को अपडेट की आवश्यकता है, जिससे आपको मैन्युअल खोज करने से बचा जा सकता है। </p>

  <br/>

  - **System Groups**

    हमारे बेड़े को तार्किक रूप से व्यवस्थित करने के लिए, हम `System Groups` का उपयोग करते हैं; आप उन्हें किसी भी मानदंड के आधार पर वर्गीकृत कर सकते हैं। ऐसा करके आप कार्रवाई लागू करते समय या नीतियां परिभाषित करते समय समय बचा सकते हैं। एक बार बनने के बाद आप सिस्टम को स्वचालित रूप से एक या कई समूहों में संलग्न कर सकते हैं, उदाहरण के लिए `activation keys` का उपयोग करके।


    `+ Create Group` पर क्लिक करके अभी एक बनाने का प्रयास करने के लिए स्वतंत्र महसूस करें।

  <br/>

  - **Batch operations**

    `System Set Manager` एक साथ कई सिस्टम पर कार्रवाई करने का एक शक्तिशाली तरीका प्रदान करता है।


    एक-एक करके बदलाव लागू करने के बजाय, आप सिस्टम का एक संग्रह चुन सकते हैं, या तो व्यक्तिगत रूप से System List से या मौजूदा System Groups का लाभ उठाकर, और फिर उन सभी पर एक ही ऑपरेशन में कार्य निष्पादित कर सकते हैं।

  <br/>

  - **Provisioning**

    <b class="smlmext">SUSE Multi-Linux Manager</b> नए सिस्टम की प्रोविजनिंग और मौजूदा सिस्टम की री-प्रोविजनिंग के लिए व्यापक उपकरण प्रदान करता है। यह क्षमता आपको सिस्टम परिनियोजन के लिए एक मानकीकृत और दोहराए जाने योग्य प्रक्रिया स्थापित करने में मदद करती है।


    उदाहरण के लिए, `Autoinstallation` अनुभाग के भीतर आप डिस्ट्रीब्यूशन और Kickstart/AutoYaST प्रोफाइल को परिभाषित कर सकते हैं जो आपको यह निर्दिष्ट करने की अनुमति देता है कि आपके सिस्टम को कैसे तैनात किया जाना चाहिए, उनमें कौन सा सॉफ़्टवेयर इंस्टॉल होगा, स्टोरेज स्पेस कैसे वितरित किया जाएगा और बहुत कुछ।


    इन सभी सरल सेटअप स्वचालन तंत्रों को Salt या Ansible जैसे जटिल लेकिन अधिक शक्तिशाली स्वचालन समाधानों के साथ जोड़ा जा सकता है, जो प्रत्येक चुनौती के लिए सबसे अच्छा समाधान चुनने की आपकी स्वतंत्रता को बनाए रखता है।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Patches मेनू** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    IT में सबसे आम कार्यों में से एक सिस्टम को अप-टू-डेट रखना और समय-समय पर जल्दबाजी में सुरक्षा पैच लागू करना है!
    SMLM के साथ हम आसानी से **प्रासंगिक** पैच की सूची देख सकते हैं, जिन्हें प्रकार द्वारा वर्गीकृत किया गया है, और उन सभी सूचनाओं के साथ प्रदान किया गया है जिन्हें आपको जानने की आवश्यकता हो सकती है, जिसमें वे सभी सिस्टम और पैकेज शामिल हैं जिन्हें वे प्रभावित करते हैं।

    विक्रेता द्वारा आपूर्ति किए गए पैच से परे हम अपने स्वयं के पैच भी बना सकते हैं। बाद में हम अपने पूरे बेड़े में पैचिंग और नियमित अपडेट को प्रबंधित करने के लिए हमारे पास मौजूद विभिन्न विकल्पों का पता लगाएंगे।

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>
- **Software Channels** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  `Channel List` पर हम खपत के लिए उपलब्ध सभी पैकेज चैनल/रिपॉजिटरी/स्ट्रीम देख सकते हैं; आप अपने सॉफ़्टवेयर को व्यवस्थित करने या अपने स्वयं के पैकेज अपलोड करने के लिए नए सॉफ़्टवेयर चैनल भी बना सकते हैं।

  वर्तमान में आप जो भी चैनल देखते हैं, उन्हें SMLM द्वारा आधिकारिक स्रोतों से पुनर्प्राप्त किया गया है और उन्हें आसानी से सिंक में रखा जा सकता है।

  `Package Search` में हम विशिष्ट पैकेज खोजने और उनकी सामग्री और मेटाडेटा का निरीक्षण करने में सक्षम हैं।

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  पंजीकरण पर या बाद में, सिस्टम पर विशिष्ट कॉन्फ़िगरेशन को प्रबंधित और लागू करना भी संभव है; उसके लिए हम `Configuration` अनुभाग का निरीक्षण कर सकते हैं।

  SMLM सिस्टम में संशोधनों को प्रबंधित करने, तैनात करने और कॉन्फ़िगरेशन फ़ाइलों की तुलना करने का एक आसान तरीका प्रदान करता है। और सभी को आसानी से कॉन्फ़िगरेशन चैनलों में समूहीकृत किया जा सकता है।

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  `Schedule` में हम अनुसूचित कार्यों का निरीक्षण और प्रबंधन कर सकते हैं, विशिष्ट रखरखाव विंडो (maintenance windows) परिभाषित कर सकते हैं। कई सिस्टम को प्रबंधित करते समय नियमित संचालन को स्वचालित करने या कैनरी परिनियोजन (canary deployments) करने के लिए यह विशेष रूप से उपयोगी है। हम वर्कशॉप के दौरान बाद में इसे क्रियान्वित देखेंगे।

<br/>
<br/>

SUSE Multi-Linux Manager आपके सिस्टम को प्रबंधित करने के लिए कई संभावनाएं प्रदान करता है; हम इस वर्कशॉप में उन सभी को कवर नहीं कर सकते हैं लेकिन, हमेशा की तरह, बेझिझक प्रश्न पूछें और अन्वेषण करें।

> [!NOTE]
> आपके उपयोगकर्ता के पास पूर्ण व्यवस्थापक (admin) विशेषाधिकार हैं, इसलिए हम अनुशंसा करते हैं कि अभ्यास समाप्त करने के बाद ही परिवर्तन करें।
