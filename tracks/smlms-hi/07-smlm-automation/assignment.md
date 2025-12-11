---
slug: smlm-automation
id: qzesmywmx0yv
type: challenge
title: स्वचालन (वैकल्पिक)
tabs:
- id: 1feefxl32jni
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 स्वचालन और कॉन्फ़िगरेशन प्रबंधन (Automation and configuration management)
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

इस खंड में हम कार्यों को स्वचालित (automate) करने के लिए उपलब्ध कुछ विकल्पों पर नज़र डालेंगे।

इस लैब में, हम मैन्युअल कार्यों को करने से हटकर हमारे पास उपलब्ध कुछ विकल्पों का उपयोग करके कुछ स्वचालन (automation) बनाने की ओर बढ़ते हैं।
<b class="smlmext">SUSE Multi-Linux Manager</b> हमारे आईटी संचालन के लिए "ऑटोपायलट" के रूप में कार्य करता है, जिससे हमें कॉन्फ़िगरेशन मानकों को लागू करने और हमारे पूरे बेड़े में सटीकता और विश्वसनीयता के साथ नियमित कार्यों को स्वचालित करने की अनुमति मिलती है।

सैकड़ों सर्वरों को मैन्युअल रूप से कॉन्फ़िगर करने और यह उम्मीद करने के बजाय कि हम कोई कदम न चूकें, हम प्रक्रिया और स्थिति (state) को परिभाषित करते हैं और मानवीय संचालन को कम करके एक बार शेड्यूल (schedule) परिभाषित करते हैं।



## <b class="hovereffect">आपके उद्देश्य:</b>

- एक शेड्यूल (schedule) बनाएं जो आपके विकास (development) सिस्टम पर नियमित रूप से अपडेट करता है।

- सिस्टम के वातावरण (environment) के आधार पर एक अलग लॉगिन बैनर दिखाने के लिए एक स्क्रिप्ट बनाएं।

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


आवर्ती अपडेट सेटअप करें (Setup recurring updates)
=======================

हम चाहते हैं कि डेवलपर्स SUSE द्वारा प्रदान किए गए नवीनतम स्थिर अपडेट के साथ काम करें, लेकिन हम लोगों पर भरोसा नहीं कर सकते कि वे हर दिन अपने सिस्टम को अपडेट करना याद रखें, इसलिए हम एक आवर्ती शेड्यूल (recurring schedule) बनाने जा रहे हैं जो ठीक यही करता है।


हम इसे dev ग्रुप के सभी सिस्टम पर लागू करने जा रहे हैं ताकि इसे प्रत्येक सिस्टम पर न करना पड़े।

- चलिए `Systems` ✈ `System Groups` पर चलते हैं
- `dev` ग्रुप पर क्लिक करें।

हमने अभी देखा कि इसमें कोई सिस्टम असाइन नहीं है, चलिए एक जोड़ते हैं।

- `Target Systems` पर क्लिक करें और `sles15` चुनें
- फिर ![Add Systems](../assets/SMLM5.1/bottom-add_system.png) पर क्लिक करें

अब जब हमारे पास एक सिस्टम है, तो चलिए आवर्ती क्रिया (recurring action) बनाते हैं।

- `Recurring Actions` पर जाएं
- ![Create](../assets/SMLM5.1/bottom-create.png) पर क्लिक करें
- अब चलिए फ़ॉर्म को निम्नलिखित विवरणों के साथ भरते हैं:
	+ **Action Type:** 'Custom state'
 	+ **Schedule Name:** 'Update Dev systems'
	+ **Daily:** '03:00'
	+ **Configure states to execute:** सुनिश्चित करें कि **uptodate:** चयनित है
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- क्लिक करें

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



हमारी आवर्ती क्रियाओं की सूची देखने के लिए हम `Schedule` ✈ `Recurring Actions` पर जा सकते हैं।

अब सभी dev सिस्टम प्रतिदिन UTC समय अनुसार सुबह 3 बजे अपडेट हो जाएंगे।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




सुनिश्चित करें कि प्रत्येक सिस्टम में एक लॉगिन संदेश है
==========================================


हम यह सुनिश्चित करने के लिए एक कॉन्फ़िगरेशन चैनल बनाने जा रहे हैं कि हमारे द्वारा प्रबंधित प्रत्येक सिस्टम में एक उपयुक्त लॉगिन संदेश हो।



- चलिए `Configuration` ✈ `Channels` पर चलते हैं
- ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png) पर क्लिक करें
- फ़ॉर्म को निम्नलिखित विवरणों के साथ भरें:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png) पर क्लिक करें

अब जब हमने कॉन्फ़िग चैनल बना लिया है, तो चलिए इसे आबाद (populate) करते हैं।

- `Add Files` ✈ `Create File` पर जाएं
- निम्नलिखित विवरण भरें:
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


- ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png) पर क्लिक करें

अब चलिए संगठन (organization) के प्रत्येक सिस्टम को नए कॉन्फ़िगरेशन चैनल की सदस्यता (subscribe) दिलाते हैं।

- चलिए `Admin` ✈ `Organizations` पर चलते हैं
- संगठन **Organization** पर क्लिक करें (यह डिफ़ॉल्ट संगठन है)
- `States` पर जाएं और हमारे द्वारा अभी बनाए गए चैनल का चयन करें।
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- क्लिक करें


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


यह तुरंत नहीं होगा, चलिए सिस्टम की जाँच करते हैं। हम वेब UI के माध्यम से एक साधारण कमांड चलाने जा रहे हैं, यदि बहुत जल्दी चलाया गया, तो आप पुराने संदेश वाले सिस्टम और फ़ाइल अपडेट प्राप्त कर चुके सिस्टम देख सकते हैं।

- चलिए `Salt` ✈ `Remote Commands` पर चलते हैं
- निम्नलिखित टाइप करें:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- `Find targets` पर क्लिक करें
- आपको सिस्टम की एक सूची दिखाई देनी चाहिए, `Run command` पर क्लिक करें

अब आपको कुछ इस तरह दिखना चाहिए:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> इस प्रक्रिया में कुछ मिनट लग सकते हैं, यदि आपको MOTD दिखाई नहीं देता है, तो कृपया कुछ मिनटों के बाद कमांड फिर से चलाएं।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


यह [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] के लिए महत्वपूर्ण क्यों है?
=================================================================================



- हजारों सिस्टम का प्रबंधन करते समय हम सब कुछ एक-एक करके करने का जोखिम नहीं उठा सकते, कार्यों को स्वचालित (automated) करने की आवश्यकता है ताकि हम मवेशियों (cattle) का प्रबंधन करें, पालतू जानवरों (pets) का नहीं।



- "सही स्थिति" (correct state) को परिभाषित करके हम कॉन्फ़िगरेशन बहाव (configuration drift) को समाप्त करते हैं। बेड़े (fleet) का प्रत्येक सर्वर एक ही प्लेबुक से काम करता है, ठीक उसी तरह जैसे प्रत्येक पायलट एक ही चेकलिस्ट का उपयोग करता है।



- जिन कार्यों को सैकड़ों सर्वरों पर मैन्युअल रूप से करने में घंटों लगेंगे, वे मिनटों में पूरे हो जाते हैं। यह हमारे इंजीनियरों को नवाचार और सुधार पर काम करने के लिए मुक्त करता है, न कि दोहराए जाने वाले मैन्युअल श्रम के लिए।


- स्वचालन मानवीय भूल (human error) के खिलाफ अंतिम बचाव है। मैन्युअल कॉन्फ़िगरेशन के दौरान एक भूला हुआ कदम या एक टाइपो (typo) आउटेज (outage) का कारण बन सकता है। एक स्वचालित, परीक्षित प्रक्रिया हर बार पूरी तरह से निष्पादित होती है, जिससे हमारी पूरी एयरलाइन की विश्वसनीयता और सुरक्षा बढ़ती है।




अधिक जानकारी
================


* [SUSE Multi-Linux Manager उत्पाद पृष्ठ](https://www.suse.com/products/suse-manager/)

* [Ansible एकीकरण](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Salt गाइड](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)