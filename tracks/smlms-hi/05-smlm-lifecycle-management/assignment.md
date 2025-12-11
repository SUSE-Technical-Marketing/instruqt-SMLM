---
slug: smlm-lifecycle-management
id: ohhrcqsqo78l
type: challenge
title: लाइफसाइकिल मैनेजमेंट
tabs:
- id: g2flahefy27o
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 लाइफसाइकिल मैनेजमेंट (Lifecycle management)
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

इस भाग में हम व्यक्तिगत रखरखाव कार्यों से हटकर बदलाव के प्रबंधन (managing change) के लिए एक फ्लीट-व्यापी, प्रमाणित प्रक्रिया स्थापित करने की ओर बढ़ेंगे। हम पता लगाएंगे कि <b class="smlmext">SUSE Multi-Linux Manager</b> में कंटेंट लाइफसाइकिल मैनेजमेंट (Content Lifecycle Management) हमारी एयरलाइन की मांग के अनुसार संरचना और सुरक्षा कैसे प्रदान करता है।



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] में, निर्माता से आते ही यात्री जेट पर कोई नया हिस्सा स्थापित नहीं किया जाता है। यह एक कठोर प्रमाणीकरण (certification) प्रक्रिया से गुजरता है।

सबसे पहले, इसे एक नियंत्रित कार्यशाला (**Development** / विकास) में जांचा और परखा जाता है। इसके बाद, इसे एक गैर-वाणिज्यिक परीक्षण विमान में फिट किया जाता है और भीषण जमीनी और उड़ान परीक्षणों (**Quality Assurance** / गुणवत्ता आश्वासन - QA) के माध्यम से रखा जाता है। हर कल्पनीय जांच पास करने के बाद ही इसे हमारे सक्रिय बेड़े (**Production** / उत्पादन) में स्थापना के लिए प्रमाणित किया जाता है।



यह व्यवस्थित, चरणबद्ध दृष्टिकोण एक भी दोषपूर्ण घटक को विमान को उड़ान भरने से रोकने (grounding) से बचाता है, जिससे हमारे यात्रियों की सुरक्षा और हमारे संचालन की विश्वसनीयता सुनिश्चित होती है। हम अपने आईटी सिस्टम पर ठीक यही दर्शन लागू करते हैं। एक सॉफ़्टवेयर अपग्रेड या एक नया एप्लिकेशन एक "घटक" (component) है जो, यदि दोषपूर्ण है, तो हमारे डिजिटल संचालन को रोक सकता है। कंटेंट लाइफसाइकिल मैनेजमेंट सभी सॉफ़्टवेयर परिवर्तनों के लिए हमारी आधिकारिक प्रमाणन प्रक्रिया है।



## <b class="hovereffect">आपके उद्देश्य:</b>

- एक कंटेंट लाइफसाइकिल प्रोजेक्ट (Content Lifecycle Project) बनाएं।

- हमारे सिस्टम के लिए सॉफ़्टवेयर अपडेट को प्रबंधित और प्रमाणित करने के लिए प्रोजेक्ट का उपयोग करें।



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


हमारा सॉफ़्टवेयर प्रमाणन मार्ग बनाना
==============================================

इस अभ्यास में, हम सॉफ़्टवेयर अपडेट के प्रवाह को नियंत्रित करने के लिए एक कंटेंट लाइफसाइकिल प्रोजेक्ट बनाएंगे। यह सुनिश्चित करता है कि हमारे महत्वपूर्ण उत्पादन सर्वर तक पहुंचने से पहले एक पैच का पूरी तरह से परीक्षण किया गया है।

<br/>

हमारा लक्ष्य एक `Dev ✈ QA ✈ Prod` पाइपलाइन बनाना है।

1.  **Development (Dev):** प्रारंभिक कार्यशाला। सभी नए पैच और पैकेज पहले यहां आते हैं।
2.  **Quality Assurance (QA):** परीक्षण का मैदान। हम अपनी परीक्षण टीमों के सत्यापन के लिए Dev से QA तक कंटेंट के एक विशिष्ट संस्करण (version) को बढ़ावा (promote) देंगे।
3.  **Production (Prod):** सक्रिय बेड़ा। केवल QA-अनुमोदित, पैच का प्रमाणित सेट Production में बढ़ावा दिया जाता है, जहां इसे सुरक्षित रूप से हमारे लाइव सिस्टम पर लागू किया जा सकता है।



<br/>

## <b class="hovereffect">प्रोजेक्ट बनाएं</b>

- `Content Lifecycle` ✈ `Projects` पर नेविगेट करें और क्लिक करें ![Create Project](../assets/SMLM5.1/bottom-create_project.png)

- प्रोजेक्ट विवरण भरें:

- **Project Name** (प्रोजेक्ट का नाम):

```txt
Airtrain SLES15 SPx
```

- **Project Label** (प्रोजेक्ट लेबल):

```txt
at-sles15_spx
```

- **Project Description** (प्रोजेक्ट विवरण):

```txt
Certified software channel for Airtrain SLES 15 systems.
```


- क्लिक करें ![Create](../assets/SMLM5.1/bottom-create.png)

अब इसे आबाद (populate) करते हैं, `Attach/Detach Sources` पर क्लिक करें

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- **New Base Channel** पर <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b> चुनें और ![Save](../assets/SMLM5.1/bottom-save.png) पर क्लिक करें

<br/>

## <b class="hovereffect">Dev एनवायरनमेंट बनाएं</b>

Development Environment Lifecycle (विकास वातावरण जीवनचक्र) बनाएं

- `Add Environment` पर क्लिक करें

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- निम्नलिखित के साथ भरें:
  * **Name:** <b class="highlightcopy">Development</b>
  * **Label:** <b class="highlightcopy">dev</b>

- क्लिक करें ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">QA एनवायरनमेंट बनाएं</b>

Quality Assurance Environment Lifecycle (गुणवत्ता आश्वासन वातावरण जीवनचक्र) बनाएं

- `Add Environment` पर क्लिक करें

- निम्नलिखित के साथ भरें:
  * **Name:** <b class="highlightcopy">QA</b>
  * **Label:** <b class="highlightcopy">qa</b>

- क्लिक करें ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Prod एनवायरनमेंट बनाएं</b>

Production Environment Lifecycle (उत्पादन वातावरण जीवनचक्र) बनाएं

- `Add Environment` पर क्लिक करें

- निम्नलिखित के साथ भरें:
  * **Name:** <b class="highlightcopy">Production</b>
  * **Label:** <b class="highlightcopy">prod</b>

- क्लिक करें ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">पॉपुलेट (Populate)</b>

अब हमारे पास तीनों वातावरण हैं, चलिए उन्हें कंटेंट से भरते हैं।

हम इस मामले में फिल्टर का उपयोग नहीं करेंगे क्योंकि <b class="sles">SLES</b> पहले से ही स्थिर पैकेज संस्करण प्रदान करता है।

[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] की परीक्षण के लिए ताल (cadence) वर्तमान में एक महीने की है, इसलिए हम इस निर्माण (build) का नाम वर्तमान महीने, अक्टूबर के नाम पर रखेंगे।

- क्लिक करें ![Build](../assets/SMLM5.1/bottom-build.png)

- **Version Message** में टाइप करें

```txt
October
```


- `Build` पर क्लिक करें

> [!NOTE]
> इस प्रक्रिया में कुछ मिनट लग सकते हैं, आप 'cloning' जैसे कुछ चरण देखेंगे, लेकिन आपको यह जानकर राहत मिल सकती है कि इसके लिए बहुत अधिक स्टोरेज की आवश्यकता नहीं है। क्लोनिंग प्रक्रिया केवल पैकेज इंडेक्स पॉइंट पर लागू होती है, वास्तविक पैकेज पर नहीं।


<br/>

## <b class="hovereffect">कंटेंट को प्रोमोट करना</b>

अब, चलिए कंटेंट को अगले चरणों में प्रोमोट (promote) करते हैं।

- Development और QA के बीच `Promote` बटन पर क्लिक करें
- **Promote version 1 into QA** शीर्षक वाली एक और स्क्रीन दिखाई देगी, बस फिर से `Promote` पर क्लिक करें।

Production के लिए यही चरण दोहराएं।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

हमारे सिस्टम को अपग्रेड करें।
====================

अब देखते हैं कि यह कैसे काम करता है।

हम करने जा रहे हैं:
- अपने कुछ सिस्टम को नए वातावरण में जोड़ना।
- कंटेंट का एक नया संस्करण बनाना
- नए संस्करण को प्रोमोट करना और सिस्टम को अपडेट करना

<br/>

## <b class="hovereffect">सिस्टम जोड़ें</b>

चलिए `Systems` ✈ `System List` ✈ `All` पर चलते हैं

- **at-ct-qa** सिस्टम पर क्लिक करें
- `Software` ✈ `Software Channels` पर जाएं
- **Custom Channels** पर, **at-sles15_spx-qa-...** चैनल के लिए चेकबॉक्स चुनें और ![Next](../assets/SMLM5.1/bottom-next.png) पर क्लिक करें
- क्लिक करें ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


वापस जाएं `Systems` ✈ `System List` ✈ `All`

- इसके द्वारा फ़िल्टर करें:

```txt
at-
```

- **-pro** के साथ समाप्त होने वाले सभी सिस्टम का चयन करें
- `Systems` ✈ `System Set Manager` पर जाएं
- `Channels` पर जाएं
- **Custom Channels** पर, **at-sles15_spx-prod-...** चैनल के लिए चेकबॉक्स चुनें और ![Next](../assets/SMLM5.1/bottom-next.png) पर क्लिक करें
- सभी अनुशंसित चैनलों की सदस्यता लेने के लिए 'include recommended' पर क्लिक करें:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">एक नया संस्करण (version) बनाएं</b>


एक महीना बीत चुका है और हम अपग्रेड की अपनी स्थिर प्रक्रिया को जारी रखना चाहते हैं।
आप डेवलपर टीम के लिए सॉफ़्टवेयर चैनलों की एक स्थिर, अपरिवर्तनीय प्रति (copy) बनाने जा रहे हैं।

कोई भी नया पैच अचानक प्रकट नहीं होगा और उनके काम को बाधित नहीं करेगा।

- वापस जाएं `Content Lifecycle` ✈ `Projects` और उस प्रोजेक्ट पर क्लिक करें जिसे हमने अभी बनाया है।

- क्लिक करें ![Build](../assets/SMLM5.1/bottom-build.png)

- **Version Message** में टाइप करें

```txt
November
```


- `Build` पर क्लिक करें

ध्यान दें कि संस्करण संख्या स्वचालित रूप से बढ़ गई है।

अब डेवलपर्स SUSE द्वारा प्रदान की गई लाइब्रेरी और एप्लिकेशन के नए और पैच किए गए संस्करणों का उपयोग करके अपना काम कर सकते हैं।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">Dev से QA में कंटेंट प्रोमोट करें</b>

मान लेते हैं कि हमारे डेवलपर्स ने अपनी मंजूरी दे दी है। QA टीम के लिए एक स्थिर संस्करण बनाने का समय आ गया है ताकि सभी प्री-प्रोडक्शन परीक्षण किए जा सकें।

- Development और QA के बीच `Promote` बटन पर क्लिक करें
- **Promote version 2 into QA** शीर्षक वाली एक और स्क्रीन दिखाई देगी, बस फिर से `Promote` क्लिक करें।

अब चलिए हमारे QA सिस्टम पर चलते हैं और एक अपग्रेड करते हैं।

- `Systems` ✈ `System List` ✈ `All`
- **at-ct-qa** सिस्टम पर क्लिक करें
- `Software` ✈ `Packages` ✈ `Upgrade` पर जाएं
- क्लिक करें:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


अब हमारे QA इंजीनियर बिना किसी व्यवधान के सुरक्षित रूप से अपने परीक्षण कर सकते हैं।


> [!NOTE]
> हमारे पास परिवर्तनों को आते देखने के लिए पर्याप्त समय नहीं है, वास्तविक परिदृश्य में संस्करण 2 में प्रचारित (promote) करने के लिए पैकेजों के नए संस्करण उपलब्ध होने चाहिए।

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">Production में प्रोमोट करें</b>

QA टीम ने `v2` पर अपना कठोर परीक्षण पूरा कर लिया है और इसे मुख्य बेड़े (fleet) के लिए स्थिर और सुरक्षित के रूप में प्रमाणित किया है। अब इसे हमारे उत्पादन सिस्टम के लिए उपलब्ध कराने का समय आ गया है।

हम अपने उत्पादन वातावरण पर QA के लिए की गई उसी प्रक्रिया को दोहराने जा रहे हैं:

- सबसे पहले, कंटेंट को प्रोमोट करें।
  यह नए पैकेजों को हमारे उत्पादन सर्वर के लिए उपलब्ध कराएगा।
  आपने सफलतापूर्वक सुनिश्चित कर लिया है कि केवल परीक्षित और अनुमोदित अपडेट ही आपके सबसे महत्वपूर्ण सिस्टम तक पहुंच सकते हैं।

- दूसरा, हमारे Production सिस्टम को अपग्रेड करें, यहाँ एकमात्र अंतर यह है कि हम **कल 14:00 बजे** के लिए अपग्रेड को शेड्यूल करने जा रहे हैं ताकि हमारी सभी टीमें तैयार रहें और एक नियंत्रित प्रक्रिया हो सके।


<br/>

यह [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] के लिए महत्वपूर्ण क्यों है?
=================================================================================

- हम सुरक्षा द्वारों (safety gates) की एक श्रृंखला बनाते हैं, जिससे हमारी परिचालन रणनीति के मुख्य सिद्धांत को लागू करना आसान हो जाता है: **जोखिम प्रबंधन** (risk management)।
- **Dev** वातावरण में पेश किए गए एक भी खराब पैच को राजस्व-सृजन करने वाले सिस्टम को प्रभावित करने का मौका मिलने से बहुत पहले पकड़ा और ठीक किया जा सकता है।
- यह प्रक्रिया पैचिंग और अपडेट को एक जोखिम भरा, परेशान करने वाली घटना से एक अनुमानित, नियमित रखरखाव प्रक्रिया में बदल देती है, जो एक विश्वसनीय एयरलाइन की आधारशिला है।


<br/>

अधिक जानकारी
================

* [Maintenance Windows (रखरखाव विंडोज़)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [Patch Management (पैच प्रबंधन)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [Content Lifecycle Management (कंटेंट लाइफसाइकिल मैनेजमेंट)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [SUSE Multi-Linux Manager Product Page](https://www.suse.com/products/suse-manager/)