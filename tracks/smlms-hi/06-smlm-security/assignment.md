---
slug: smlm-security
id: xcxwgcbkbwfo
type: challenge
title: सुरक्षा और पैचिंग
tabs:
- id: 9ju8xt80wj60
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 सुरक्षा और पैचिंग (Security and patching)
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

<img class="logos" alt="Welcome!" src="../assets/logos/06-security.jpeg"/>



इस लैब में, हम अपनी सबसे महत्वपूर्ण जिम्मेदारियों में से एक से निपटेंगे: हमारे पूरे डिजिटल बेड़े की सुरक्षा सुनिश्चित करना। हम पता लगाएंगे कि <b class="smlmext">SUSE Multi-Linux Manager</b> हमें विश्व स्तरीय एयरलाइन के लिए आवश्यक गति और सटीकता के साथ सुरक्षा खतरों का जवाब देने की अनुमति कैसे देता है।




## <b class="hovereffect">आपके उद्देश्य:</b>

- OpenSCAP का उपयोग करके अपने सिस्टम पर सुरक्षा अनुपालन ऑडिट (security compliance audit) करें।

- प्रासंगिक सुरक्षा कमजोरियों (security vulnerabilities) से प्रभावित सिस्टम की पहचान करें।

- सभी प्रभावित सिस्टम पर एक साथ आवश्यक पैच (patches) लागू करें।



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




अपने सिस्टम का ऑडिट करें (Audit your systems)
==================

हम अपने प्रोडक्शन सिस्टम का ऑडिट करना चाहते हैं ताकि यह सुनिश्चित हो सके कि वे अनुपालन (compliant) करते हैं।

हमने पहले ही सत्यापित कर लिया है कि निम्नलिखित पैकेज इंस्टॉल हैं:

- openscap-utils
- scap-security-guide


प्रोडक्शन ग्रुप का चयन करें

- चलिए `Systems` ✈ `System Groups` पर चलते हैं
- **prod** ग्रुप खोजें और `Use in SSM` पर क्लिक करें
![Next](../assets/SMLM5.1/prod_group_selection.png)

हमें **System Set Manager Overview** पृष्ठ पर निर्देशित किया जाएगा, जैसा कि हमने पहले देखा था, यहाँ से हम एक साथ कई सिस्टम पर कार्रवाई लागू कर सकते हैं।

- `Audit` टैब पर जाएं
- `OpenSCAP` के तहत निम्नलिखित विवरणों के साथ फॉर्म को पूरा करें, बाकी को डिफ़ॉल्ट रहने दें:
  - **Command-line Arguments:** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document:** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- दबाएं


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



इसमें कुछ मिनट लगेंगे।


परिणाम देखने के लिए `Audit` ✈ `OpenSCAP` ✈ `All Scans` पर जाएं

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

यदि हम इन परिणामों में से किसी एक पर क्लिक करते हैं, तो हम अधिक विस्तृत विवरण देख सकते हैं।

- **report.html** पर क्लिक करके, आप उस रिपोर्ट का एक बेहतर संस्करण देख सकते हैं जिसे OpenSCAP द्वारा जनरेट किया गया था।

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


रिपोर्ट की गई समस्याओं के बारे में चिंता न करें।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



कमजोरियों से प्रभावित सिस्टम की पहचान करें
============================================

हम देखना चाहते हैं कि कौन से सिस्टम कमजोरियों (vulnerabilities) से प्रभावित हैं।

- अब, `Patches` ✈ `Patch List` ✈ `Relevant` पर नेविगेट करें

  यहाँ हम अपने सिस्टम के लिए उपलब्ध सभी प्रासंगिक पैच की सूची देख सकते हैं, आइए **Security Patches** (सुरक्षा पैच) देखें।

- **Advisory** (सलाहकार) नाम पर क्लिक करके, आप एक विस्तृत पृष्ठ देख सकते हैं जो दिखाता है कि यह किन पैकेजों और सिस्टम को प्रभावित करता है, साथ ही अन्य विवरण भी।

- सूची के दाईं ओर, **CVEs** कॉलम आधिकारिक कमजोरी रिपोर्ट (vulnerability reports) के सीधे लिंक प्रदान करता है।

  हम अपने स्वयं के पैच भी बना सकते हैं, लेकिन हम इस ट्रैक में इसे कवर नहीं करेंगे, अधिक जानकारी के लिए कृपया ट्रैक के अंत में दिए गए लिंक देखें।



## <b class="hovereffect">प्रभावित सिस्टम को पैच करें</b>

हमारे सिस्टम को पैच करना इन चरणों का पालन करने जितना आसान है:

- `Systems` ✈ `System Set Manager` पर जाएं
- `Patches` टैब पर नेविगेट करें ✈ ड्रॉप-डाउन सूची में **Security Advisory** चुनें, और `Show` पर क्लिक करें

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- `Select All` पर क्लिक करें ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] के लिए यह महत्वपूर्ण क्यों है?
=================================================================================


- तेजी से कार्य करने में सक्षम होकर, हम जोखिम (exposure) की खिड़की को कम कर रहे हैं। जब एक नई कमजोरी का पता चलता है, तो हमारे और इसे भुनाने की कोशिश करने वाले दुर्भावनापूर्ण अभिनेताओं के बीच एक दौड़ शुरू हो जाती है। एक जटिल, मैनुअल पैचिंग प्रक्रिया हमारे महत्वपूर्ण सिस्टम को बहुत लंबे समय तक असुरक्षित छोड़ देती है।

- <b class="smlmext">SUSE Multi-Linux Manager</b> हमारे पूरे बेड़े की सुरक्षा स्थिति का एक एकल, एकीकृत दृश्य प्रदान करता है और हमें एक सुसंगत, विश्वसनीय प्रक्रिया के साथ खतरों को दूर करने की अनुमति देता है।

- विभिन्न सुरक्षा ढांचे (security frameworks) के खिलाफ हमारे सिस्टम के अनुपालन की आसानी से जांच करने में सक्षम होने से हमें सुधारात्मक उपायों को तेजी से लागू करने और सख्त उद्योग नियमों का पालन करने की अनुमति मिलती है।


अधिक जानकारी
================


* [ऑडिटिंग (Auditing)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [SUSE सुरक्षा (SUSE Security)](https://www.suse.com/support/security/)
* [OpenSCAP के साथ सिस्टम सुरक्षा](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [पैच प्रबंधित करें (Manage Patches)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)