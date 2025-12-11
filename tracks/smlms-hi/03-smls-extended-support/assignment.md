---
slug: smls-extended-support
id: ngdtfbxm9y5z
type: challenge
title: पुराने (Legacy) सिस्टम के लिए विस्तारित सपोर्ट
tabs:
- id: 0urujeafrqjy
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: oamcur5rho0f
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: yflaxnbd63f8
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 पुराने (Legacy) सिस्टम के लिए विस्तारित सपोर्ट
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

# हमारे पुराने (Legacy) बेड़े का जीवन बढ़ाना

किसी भी एयरलाइन में, आपके पास पुराने, विश्वसनीय विमान होते हैं जिन्होंने वर्षों तक आपकी सेवा की है लेकिन जिनके लिए आपके पास अभी तक कोई प्रतिस्थापन (replacement) नहीं है। हमारे लिए, उस पुराने बेड़े का एक हिस्सा हमारे CentOS 7 सिस्टम हैं। वे स्थिर हैं लेकिन जीवन के अंत (end-of-life) पर हैं, जिसका अर्थ है कि उन्हें अब अपने मूल निर्माता से महत्वपूर्ण सुरक्षा अपडेट प्राप्त नहीं होते हैं। एक एयरलाइन के लिए, बिना समर्थन के उड़ान भरना एक ऐसा जोखिम है जिसे हम बस नहीं उठा सकते।

पारंपरिक समाधान हर एक का पूर्ण, महंगा प्रतिस्थापन होगा।
लेकिन क्या होगा अगर हम न्यूनतम व्यवधान के साथ उन्हें आधुनिक बनाते हुए, जीवन-विस्तार (life-extension) अपग्रेड कर सकें? इस चुनौती के लिए यही मिशन है। हम इन सिस्टम को सुरक्षित रूप से बदलने (transition) और सेवा में रखने के लिए <b class="smlmext">SUSE Multi-Linux Manager</b> और <b class="smlsext">SUSE Multi-Linux Support</b> की शक्ति का उपयोग करेंगे जब तक कि हम उन्हें अधिक आधुनिक OS के साथ बदल नहीं सकते।



## <b class="hovereffect">हमारी उड़ान योजना (Flight plan):</b>

- Centos 7 चलाने वाले वर्तमान पुराने (legacy) सिस्टम की जांच करें

- QA सिस्टम को ऑनबोर्ड (Onboard) करें और उपलब्ध कोई भी पैच लागू करें

- यदि कोई अपडेट हो तो उन्हें पहचानें और लागू करें।

- liberate फॉर्मूले के साथ सिस्टम को मुक्त (Liberate) करें।

- देखें कि दोनों प्रणालियों के बीच क्या बदला है

- पहचानें कि क्या यह एक माइग्रेशन (migration) है।

<br/>

## <b class="hovereffect">हमारे हवाई जहाज</b>

- CentOS 7 QA ✈ हमारा परीक्षण और विकास सर्वर।

- CentOS 7 Prod ✈ हमारा उत्पादन (production) सर्वर जो पहले से ही <b class="smlm">SMLM</b> में पंजीकृत है

<br/><br/>


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



Centos 7 QA को ऑनबोर्ड करना (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">वर्तमान पुराने (legacy) सिस्टम की जांच करना</b>

टैब [button label="Centos 7 QA" variant="success"](tab-1) से सिस्टम टर्मिनल तक पहुंचें

सिस्टम के वर्तमान संस्करण की जाँच करें:

```bash,run
rpm -qi centos-release centos-logos
```


अब सिस्टम को <b class="smlm">SMLM</b> में पंजीकृत करने के लिए निम्नलिखित कमांड चलाएँ:


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


यह पिछले लैब में Ubuntu को ऑनबोर्ड करने के लिए उपयोग किए गए कमांड के समान है, जो बदलता है वह है:

- **Activation key** (सक्रियण कुंजी): उन सेटिंग्स का एक संदर्भ है जो डिफ़ॉल्ट रूप से सिस्टम पर लागू होंगी, इस मामले में इसे केवल यह इंगित करने के लिए बनाया गया है कि सिस्टम किन सॉफ़्टवेयर चैनलों में पंजीकृत होगा।

- **Profile name** (प्रोफ़ाइल नाम): यदि हम निर्दिष्ट नहीं करते हैं तो यह होस्टनाम (hostname) का उपयोग करेगा लेकिन इस मामले में हम चाहते हैं कि इसका एक अधिक सार्थक नाम हो, उसी नामकरण परंपरा के साथ जो हमने Centos 7 Prod के साथ उपयोग की थी।


**वैकल्पिक:** यदि हम उत्सुक हैं और देखना चाहते हैं कि जब हम अपग्रेड करते हैं और Liberate फ़ॉर्मूला निष्पादित करते हैं तो क्या होता है, तो हम दोनों सिस्टम ( [button label="Centos 7 QA" variant="success"](tab-1) और [button label="Centos 7 Prod" variant="success"](tab-2) ) पर निम्नलिखित कमांड चला सकते हैं:


```bash,run
journalctl -f
```

और टर्मिनलों में लॉग (logs) दिखाई देते हुए देखें।


<br/><br/>


## <b class="hovereffect"><b class="liberty">Liberty</b> रिपॉजिटरी से अपडेट पहचानें और लागू करें</b>

यह Centos 7 सिस्टम अपस्ट्रीम प्रदान किए गए नवीनतम पैकेजों के साथ आता है, हम यह सुनिश्चित करना चाहते हैं कि नए बग ठीक हो जाएं और जब कोई समस्या हो तो हमारी मदद करने के लिए हमारे पास एक मित्रवत सपोर्ट व्यक्ति हो, अब हमने पंजीकरण प्रक्रिया के दौरान पहले ही Centos 7 सिस्टम को SUSE द्वारा प्रदान की गई सॉफ़्टवेयर रिपॉजिटरी की सदस्यता (subscribe) दी है, तो चलिए उन सभी को पैच करते हैं:



अब चलिए [button label="SMLM UI" variant="success"](tab-0) टैब पर स्विच करते हैं


- बाएं हाथ के मेनू में `Systems` ✈ `System List` पर जाएं।

- अपने होस्ट **airco-dh4a-qa** को खोजें और उस पर क्लिक करें।

- `Software` ✈ `Packages` का चयन करें

- `Update Packages List` पर क्लिक करें, इसे पूरा होने में लगभग एक मिनट लगेगा

- `Software` ✈ `Patches` का चयन करें

- आपको उपलब्ध पैच की एक सूची दिखाई देगी।

`Select All` पर क्लिक करें, फिर ऊपरी दाईं ओर `Apply Patches` और अंत में `Confirm` पर क्लिक करें। <b class="smlmext">SUSE Multi-Linux Manager</b> अब CentOS सिस्टम पर अपग्रेड प्रक्रिया को शेड्यूल और निष्पादित करेगा।


> [!NOTE]
> सिस्टम पर लागू किए जा सकने वाले पैच की सूची देखने से पहले पैकेज की सूची प्राप्त करने में कुछ मिनट लग सकते हैं।


चूंकि इसमें कुछ समय लग सकता है, आइए देखें कि हुड के नीचे (under the hood) क्या होता है।
`Events` टैब पर जाएं, फिर `History` पर, आपको उन घटनाओं की एक सूची देखनी चाहिए जो सिस्टम के <b class="smlm">SMLM</b> में पंजीकृत होने के बाद से हुई हैं, पहली पंक्तियों में हमें एक ऐसी घटना मिलनी चाहिए जिसमें *Combined Patch* के समान कुछ हो।


यदि हम उस पर क्लिक करते हैं तो हम सभी विवरण देख सकते हैं, बेझिझक देखें, अन्यथा आइकन के हरे होने तक प्रतीक्षा करें:

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

हमने अभी-अभी मौजूदा पैकेजों में बग फिक्स करने वाले पैच लागू किए हैं, ये पैच किए गए पैकेज सीधे SUSE से आ रहे हैं, यह कोई माइग्रेशन नहीं है।

<br/>

आइए इसकी तुलना उत्पादन (production) सिस्टम से करें जिसे हमने अभी तक अपडेट नहीं किया है।

कृपया `Software` ✈ `Packages` ✈ `Profiles` पर जाएं

सिस्टम `airco-dh4a-prod` का चयन करें, जो उत्पादन संस्करण है, फिर इस पर क्लिक करें:

![Compare](../assets/SMLM5.1/bottom-compare.png)


हम देख सकते हैं कि अधिकांश पैकेज संस्करण नहीं बदले हैं, अभी भी वही संस्करण ( **X.X.X**-xyz ) लेकिन एक पैच लागू होने के साथ ( X.X.X-**xyz** )।

अगले भाग पर जाने से पहले आइए एक संग्रहीत प्रोफ़ाइल (stored profile) बनाएँ, इससे हमें अगले भाग में liberate फ़ॉर्मूला लागू करने के बाद अंतरों को अधिक स्पष्ट रूप से देखने में मदद मिलेगी।


कृपया `Software` ✈ `Packages` ✈ `Profile` पर जाएं और `Create System Profile` पर क्लिक करें। नाम के लिए आप इसे बुला सकते हैं:

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


सिस्टम को मुक्त (Liberate) करें (वैकल्पिक)
==============================

यह एक **वैकल्पिक** कदम है और समर्थन प्राप्त करने के लिए आवश्यक नहीं है।

अब चलिए सिस्टम को मुक्त (liberate) करते हैं:

- `Formulas` टैब पर जाएं, **Liberate** खोजें, और एक बार मिल जाने पर, इसे चुनें और ऊपर दाईं ओर `Save` पर क्लिक करें।

आपको स्क्रीन के शीर्ष पर नीले रंग में एक संदेश दिखाई देगा, यदि आप नहीं देख सकते हैं तो ऊपर स्क्रॉल करें:

![Formula saved](../assets/SMLM5.1/formula_saved.png)


उस जगह पर क्लिक करें जहां `Highstate` लिखा है, आपको दूसरे टैब (`States` ✈ `Highstate`) पर निर्देशित किया जाएगा।

आप नीचे सारांश में देख सकते हैं कि liberate फ़ॉर्मूला सूचीबद्ध है।

मुक्ति (liberation) प्रक्रिया शुरू करने के लिए, क्लिक करें:

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

इसमें कुछ समय लगेगा, कृपया `Events` -> `History` देखें, आपको **Apply highstate scheduled** नामक एक ईवेंट देखना चाहिए

इसके पूरा होने के लिए कुछ मिनट प्रतीक्षा करें, इस बीच आप टर्मिनल [button label="Centos 7 QA" variant="success"](tab-1) को देखकर निरीक्षण कर सकते हैं कि क्या हो रहा है।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">देखें कि क्या बदला है</b>


एक बार यह पूरा हो जाने के बाद, अंतर देखने के लिए सिस्टम की फिर से तुलना करें, यदि हम पहले से वहां नहीं हैं तो सिस्टम नाम `airco-dh4a-qa` पर क्लिक करें।

फिर `Software` ✈ `Packages` ✈ `Profile` पर जाएं

**Compare to Stored Profile** के तहत क्लिक करें: ![Compare](../assets/SMLM5.1/bottom-compare.png)

हम देख सकते हैं कि केवल निम्नलिखित पैकेज बदले हैं:

- **centos-logos**, को **sles_es-logos** द्वारा प्रतिस्थापित किया गया

- **centos-release**, को **sles_es-release-server** द्वारा प्रतिस्थापित किया गया

बाकी सब वही रहता है लेकिन अब आपके पास <b class="liberty">Liberty Linux</b> के लिए <b class="suse">SUSE</b> द्वारा प्रदान किया गया पूरा सपोर्ट, अपग्रेड और पैच हैं।

यही बात CentOS और RHEL के अधिक आधुनिक संस्करणों पर भी लागू होती है, आप उन्हें <b class="liberty">Liberty</b> में बदल सकते हैं और वास्तविक सॉफ़्टवेयर और लाइब्रेरी में कोई बदलाव किए बिना <b class="suse">SUSE</b> द्वारा उनका समर्थन (support) प्राप्त कर सकते हैं।



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



उत्पादन सर्वर को मुक्त (Liberate) करें (वैकल्पिक)
=========================================

हमने देखा है कि QA में अपने पुराने Centos 7 सर्वर को कैसे पैच और Liberate किया जाए, अब उत्पादन सिस्टम के साथ भी ऐसा ही करने का समय है, लेकिन इस बार हम इसे एक अलग क्रम में करेंगे।

- सबसे पहले, हम **Liberate** फ़ॉर्मूला लागू करेंगे

  चलिए हमारे उत्पादन सर्वर `airco-dh4a-prod` पर चलते हैं और `Create System Profile` करते हैं

  इसके बाद चलिए **Liberate** फ़ॉर्मूला लागू करते हैं जैसा हमने QA सिस्टम के साथ किया था।

- एक बार यह पूरा हो जाने के बाद, चलिए सिस्टम की तुलना उस प्रोफ़ाइल से करते हैं जिसे हमने अभी बनाया है, जैसा कि हम देख सकते हैं कि केवल **centos-logos** और **centos-release** पैकेज में बदलाव हुआ है, बाकी सब बिल्कुल वैसा ही है।


क्या यह एक माइग्रेशन (migration) है?
==================

एक माइग्रेशन में एक बिल्कुल नया सर्वर बनाना, स्क्रैच से सभी एप्लिकेशन को फिर से इंस्टॉल करना और डेटा को सावधानीपूर्वक स्थानांतरित करना शामिल है, एक ऐसी प्रक्रिया जो समय लेने वाली, महंगी और जोखिम से भरी है।

हमने जो किया वह कहीं अधिक सुंदर (elegant) था। हमने इन-प्लेस अपग्रेड (in-place upgrade) किया।

सर्वर की पहचान, होस्टनाम, एप्लिकेशन और उपयोगकर्ता डेटा पूरी तरह से अछूता रहा। हमने बस अपडेट के लिए इसके अंतर्निहित स्रोत को बदल दिया, और वे एंड-ऑफ-लाइफ घटक अब पूरी तरह से समर्थित घटक हैं जो पैच प्राप्त कर रहे हैं।

हमने अपने सिस्टम के जीवन को सफलतापूर्वक बढ़ाया है, इसे सुरक्षा अनुपालन में वापस लाया है, और यह सब पूर्ण माइग्रेशन के व्यवधान के बिना किया है। यही वह दक्षता है जो [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] को ऊंची उड़ान भरने में मदद करती है।




यह [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] के लिए महत्वपूर्ण क्यों है?
=================================================================================

- यह [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] को अपने चल रहे सिस्टम को समर्थित रखने की अनुमति देता है, जिससे उन्हें विक्रेता की जरूरतों के बजाय अपनी व्यावसायिक जरूरतों के आधार पर माइग्रेट करने का समय मिलता है।

- यह विस्तारित समर्थन (extended support) प्रदान करके असमर्थित सिस्टम होने के जोखिम को कम करता है। यह दृष्टिकोण तत्काल माइग्रेशन की आवश्यकता से बचाता है, सब कुछ हमेशा की तरह चलता है लेकिन अब विशेषज्ञों का एक समूह है जो आपके कॉल का जवाब दे सकता है।

- यह आपको लंबी माइग्रेशन से गुज़रे बिना सपोर्ट प्रदाता बदलने की स्वतंत्रता देता है, और आपको इसे बड़े पैमाने (at scale) पर करने की अनुमति देता है।



अधिक जानकारी
================

- [Registering RHEL 7 or CentOS Linux 7 with SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Running OpenSCAP compliance scans for SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registering CentOS Linux 7 with the SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)