# BIHAR-SPECIAL-QUESTIONS-
<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bihar Special Online Test</title>

  <style>
    body {
      font-family: 'Times New Roman', Times, serif;
      font-size: 36px;
      line-height: 1.6;
      background-color: #f4f7f6;
      color: #000000;
      margin: 15px;
    }

    .container {
      max-width: 1100px;
      margin: 0 auto;
      background: #ffffff;
      padding: 35px;
      border: 3px solid #1a237e;
      border-radius: 12px;
      box-shadow: 0 5px 20px rgba(0,0,0,0.15);
    }

    /* Motivation Quote */
    .motivation {
      text-align: center;
      color: #0d47a1;
      font-weight: bold;
      font-style: italic;
      margin-bottom: 30px;
      border-bottom: 3px dashed #0d47a1;
      padding-bottom: 15px;
    }

    /* Fixed Floating Timer */
    #timer-bar {
      display: none;
      position: sticky;
      top: 10px;
      z-index: 999;
      background-color: #d32f2f;
      color: #ffffff;
      text-align: center;
      padding: 12px;
      font-size: 38px;
      font-weight: bold;
      border-radius: 8px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
      margin-bottom: 25px;
    }

    .form-group {
      margin-bottom: 25px;
    }

    label {
      display: block;
      font-weight: bold;
      margin-bottom: 8px;
    }

    input, select {
      width: 100%;
      padding: 12px;
      font-family: 'Times New Roman', Times, serif;
      font-size: 32px;
      border: 2px solid #333333;
      border-radius: 8px;
      box-sizing: border-box;
    }

    .btn {
      background-color: #b71c1c;
      color: #ffffff;
      padding: 14px 28px;
      border: none;
      font-family: 'Times New Roman', Times, serif;
      font-size: 36px;
      font-weight: bold;
      cursor: pointer;
      border-radius: 8px;
      margin-top: 15px;
      transition: background 0.2s;
    }

    .btn:hover {
      background-color: #e53935;
    }

    /* Screen par OTP dikhane wala box */
    #otp-screen-display {
      display: none;
      margin-top: 15px;
      padding: 15px;
      background-color: #e8f5e9;
      border: 3px solid #2e7d32;
      border-radius: 8px;
      color: #1b5e20;
      font-weight: bold;
      text-align: center;
    }

    #form-error {
      display: none;
      color: #b71c1c;
      font-weight: bold;
      margin-top: 10px;
    }

    #quiz-section {
      display: none;
    }

    .question-block {
      margin-bottom: 50px;
      border-bottom: 2px solid #e0e0e0;
      padding-bottom: 30px;
    }

    /* Question: Bold & Red */
    .question-text {
      color: #d32f2f;
      font-weight: bold;
      margin-bottom: 20px;
    }

    /* Option: Bold & Black */
    .option-label {
      display: block;
      color: #000000;
      font-weight: bold;
      margin-bottom: 12px;
      cursor: pointer;
      padding: 8px 12px;
      border-radius: 6px;
      border: 2px solid transparent;
    }

    .option-label:hover {
      background-color: #f5f5f5;
    }

    .option-label input {
      width: 30px;
      height: 30px;
      margin-right: 15px;
      vertical-align: middle;
    }

    /* Sahi / Galat Option Highlights */
    .option-label.correct-opt {
      background-color: #c8e6c9 !important;
      border-color: #2e7d32 !important;
      color: #1b5e20 !important;
    }

    .option-label.wrong-opt {
      background-color: #ffcdd2 !important;
      border-color: #c62828 !important;
      color: #b71c1c !important;
    }

    /* Real-Time Explanation Box */
    .explanation-box {
      display: none;
      margin-top: 18px;
      padding: 18px;
      border-radius: 8px;
      font-size: 34px;
      line-height: 1.5;
    }

    .explanation-box.show {
      display: block;
    }

    .explanation-box.success {
      background-color: #e8f5e9;
      border-left: 8px solid #2e7d32;
      color: #1b5e20;
    }

    .explanation-box.fail {
      background-color: #ffebee;
      border-left: 8px solid #c62828;
      color: #b71c1c;
    }

    .exp-title {
      font-weight: bold;
      margin-bottom: 8px;
    }

    #result {
      display: none;
      text-align: center;
      font-weight: bold;
      font-size: 42px;
      color: #0d47a1;
      margin: 30px 0;
      padding: 25px;
      background-color: #e3f2fd;
      border: 3px solid #1565c0;
      border-radius: 10px;
    }
  </style>
</head>
<body>

<div class="container">
  <!-- Motivation Quote -->
  <div class="motivation">
    "मेहनत इतनी खामोशी से करो कि सफलता शोर मचा दे। अपने लक्ष्य पर अडिग रहो, जीत निश्चित है!"
  </div>

  <!-- Registration Form (Bina Email ke) -->
  <div id="registration-section">
    <h2 style="text-align: center; color: #b71c1c; margin-top: 0;">परीक्षार्थी पंजीकरण (Student Registration)</h2>
    <form id="regForm" onsubmit="handleRegistration(event)">
      <div class="form-group">
        <label for="name">विद्यार्थी का नाम (Full Name):</label>
        <input type="text" id="name" required placeholder="अपना पूरा नाम लिखें">
      </div>

      <div class="form-group">
        <label for="mobile">मोबाइल नंबर (Mobile Number):</label>
        <input type="tel" id="mobile" pattern="[0-9]{10}" required placeholder="10 अंकों का मोबाइल नंबर डालें">
      </div>

      <div class="form-group">
        <button type="button" class="btn" style="font-size: 30px; padding: 10px 22px; background-color: #1565c0;" onclick="sendDynamicOTP()">OTP प्राप्त करें</button>
        <!-- On-Screen OTP Box -->
        <div id="otp-screen-display"></div>
      </div>

      <div class="form-group" id="otp-group" style="display: none;">
        <label for="otp" style="color: #b71c1c;">ऊपर दिखाया गया OTP यहाँ दर्ज करें:</label>
        <input type="text" id="otp" placeholder="4 अंकों का OTP डालें">
      </div>

      <div class="form-group">
        <label for="state">राज्य (State):</label>
        <input type="text" id="state" value="बिहार" required>
      </div>

      <div class="form-group">
        <label for="district">जिला (District):</label>
        <input type="text" id="district" required placeholder="उदा. पटना, समस्तीपुर, मुजफ्फरपुर">
      </div>

      <div id="form-error"></div>

      <button type="submit" class="btn">सत्यापित करें और 60 मिनट का टेस्ट शुरू करें</button>
    </form>
  </div>

  <!-- Live 60-Minute Countdown Timer -->
  <div id="timer-bar">⏱ शेष समय (Time Left): <span id="time-display">60:00</span></div>

  <!-- Quiz Section -->
  <div id="quiz-section">
    <div id="questions-container"></div>
    <button class="btn" id="manualSubmitBtn" onclick="finishQuiz(false)">टेस्ट समाप्त करें (Submit Test)</button>
    <div id="result"></div>
  </div>
</div>

<script>
  let generatedOtp = "";
  let totalTimeInSeconds = 60 * 60; // 60 Minute
  let timerInterval = null;
  let isQuizSubmitted = false;

  // On-Screen Live OTP Function
  function sendDynamicOTP() {
    const mobile = document.getElementById("mobile").value.trim();
    const otpDisplay = document.getElementById("otp-screen-display");
    const errorDisplay = document.getElementById("form-error");

    errorDisplay.style.display = "none";

    if (mobile.length !== 10 || isNaN(mobile)) {
      otpDisplay.style.display = "block";
      otpDisplay.style.backgroundColor = "#ffebee";
      otpDisplay.style.borderColor = "#c62828";
      otpDisplay.style.color = "#b71c1c";
      otpDisplay.innerText = "कृपया पहले सही 10 अंकों का मोबाइल नंबर ऊपर दर्ज करें!";
      return;
    }

    // 4-Digit Unique Random OTP
    generatedOtp = Math.floor(1000 + Math.random() * 9000).toString();
    
    document.getElementById("otp-group").style.display = "block";

    otpDisplay.style.display = "block";
    otpDisplay.style.backgroundColor = "#e8f5e9";
    otpDisplay.style.borderColor = "#2e7d32";
    otpDisplay.style.color = "#1b5e20";
    otpDisplay.innerHTML = `सत्यापन कोड (OTP): <span style="font-size: 42px; text-decoration: underline;">${generatedOtp}</span><br><span style="font-size: 26px;">कृपया इस 4 अंकों के कोड को नीचे वाले बॉक्स में लिखें।</span>`;
  }

  function handleRegistration(e) {
    e.preventDefault();

    const enteredOtp = document.getElementById("otp").value.trim();
    const errorDisplay = document.getElementById("form-error");

    if (!generatedOtp) {
      errorDisplay.style.display = "block";
      errorDisplay.innerText = "कृपया पहले 'OTP प्राप्त करें' बटन दबाएं!";
      return;
    }

    if (enteredOtp !== generatedOtp) {
      errorDisplay.style.display = "block";
      errorDisplay.innerText = "❌ गलत OTP! स्क्रीन पर दिखाया गया सही 4 अंकों का कोड दर्ज करें।";
      return;
    }

    document.getElementById("registration-section").style.display = "none";
    document.getElementById("quiz-section").style.display = "block";
    document.getElementById("timer-bar").style.display = "block";

    loadQuestions();
    startCountdown();
  }

  function startCountdown() {
    timerInterval = setInterval(() => {
      totalTimeInSeconds--;

      let minutes = Math.floor(totalTimeInSeconds / 60);
      let seconds = totalTimeInSeconds % 60;

      let displayMinutes = minutes < 10 ? "0" + minutes : minutes;
      let displaySeconds = seconds < 10 ? "0" + seconds : seconds;

      document.getElementById("time-display").innerText = `${displayMinutes}:${displaySeconds}`;

      if (totalTimeInSeconds <= 0) {
        clearInterval(timerInterval);
        finishQuiz(true);
      }
    }, 1000);
  }

  // Question Bank
  const quizData = [
    {
      q: "1. पाटलिपुत्र को किस शासक ने सर्वप्रथम अपनी राजधानी बनाया था?",
      options: ["चन्द्रगुप्त मौर्य", "अशोक", "चन्द्रगुप्त विक्रमादित्य", "उदयिन"],
      correct: 3,
      exp: "व्याख्या: हर्यक वंश के शासक अजातशत्रु के पुत्र 'उदयिन' ने गंगा और सोन नदी के संगम पर पाटलिपुत्र नगर की नींव रखी और राजगृह से राजधानी स्थानांतरित की।"
    },
    {
      q: "2. 1857 के विद्रोह का बिहार में मुख्य केंद्र जगदीशपुर था, इसके नेता कौन थे?",
      options: ["नाना साहेब", "कुंवर सिंह", "तात्या टोपे", "अमर सिंह"],
      correct: 1,
      exp: "व्याख्या: 80 वर्ष की उम्र में बाबू वीर कुंवर सिंह ने जगदीशपुर (भोजपुर) से अंग्रेजों के खिलाफ 1857 की क्रांति का ऐतिहासिक नेतृत्व किया था।"
    },
    {
      q: "3. बिहार का प्रथम मुस्लिम विजेता कौन था?",
      options: ["मलिक इब्राहिम", "इल्तुतमिश", "बख्तियार खिलजी", "अली मर्दान खिलजी"],
      correct: 2,
      exp: "व्याख्या: इख्तियारुद्दीन मुहम्मद बिन बख्तियार खिलजी ने 12वीं शताब्दी के अंत (1198 ई.) में बिहार पर आक्रमण कर नालंदा और ओदंतपुरी को नष्ट किया था।"
    },
    {
      q: "4. चंपारण सत्याग्रह (1917) में गांधीजी को चंपारण आने का निमंत्रण किसने दिया था?",
      options: ["राजकुमार शुक्ल", "राजेंद्र प्रसाद", "ब्रजकिशोर प्रसाद", "धरणीधर"],
      correct: 0,
      exp: "व्याख्या: 1916 के लखनऊ कांग्रेस अधिवेशन में किसान नेता राजकुमार शुक्ल ने गांधीजी को चंपारण के किसानों की दुर्दशा (तिनकठिया प्रथा) देखने का आमंत्रण दिया था।"
    },
    {
      q: "5. बिहार प्रांतीय किसान सभा का गठन किसने किया था?",
      options: ["स्वामी सहजानंद सरस्वती", "रामनंदन मिश्र", "गंगा शरण सिंह", "रामानंद शर्मा"],
      correct: 0,
      exp: "व्याख्या: स्वामी सहजानंद सरस्वती ने वर्ष 1929 में सोनपुर मेले के अवसर पर बिहार प्रांतीय किसान सभा की स्थापना की थी।"
    },
    {
      q: "6. 'सदाकत आश्रम' की स्थापना पटना में किसके द्वारा की गई थी?",
      options: ["डॉ. राजेंद्र प्रसाद", "मौलाना मजहरुल हक", "अनुग्रह नारायण सिंह", "सच्चिदानंद सिन्हा"],
      correct: 1,
      exp: "व्याख्या: असहयोग आंदोलन के समय मौलाना मजहरुल हक ने पटना में खैरू मियां द्वारा दान दी गई भूमि पर सदाकत आश्रम की स्थापना की थी।"
    },
    {
      q: "7. बिहार का शोक (Sorrow of Bihar) किस नदी को कहा जाता है?",
      options: ["सोन नदी", "गंडक नदी", "कोसी नदी", "बागमती नदी"],
      correct: 2,
      exp: "व्याख्या: कोसी नदी अपने मार्ग परिवर्तन और भयंकर बाढ़ लाने की प्रवृत्ति के कारण बिहार का शोक कहलाती है।"
    },
    {
      q: "8. बिहार की सबसे ऊंची चोटी 'सोमेश्वर की पहाड़ी' किस जिले में स्थित है?",
      options: ["पश्चिम चंपारण", "गया", "रोहतास", "कैमूर"],
      correct: 0,
      exp: "व्याख्या: सोमेश्वर श्रेणी शिवालिक हिमालय का हिस्सा है और यह पश्चिम चंपारण जिले में नेपाल सीमा पर 874 मीटर ऊंची है।"
    },
    {
      q: "9. बिहार में सर्वाधिक लिंगानुपात वाला जिला कौन सा है?",
      options: ["सीवान", "गोपालगंज", "सारण", "किशनगंज"],
      correct: 1,
      exp: "व्याख्या: 2011 की जनगणना के अनुसार गोपालगंज का लिंगानुपात 1021 महिला प्रति 1000 पुरुष है, जो राज्य में सर्वाधिक है।"
    },
    {
      q: "10. बिहार का एकमात्र राष्ट्रीय उद्यान (National Park) कौन सा है?",
      options: ["वाल्मीकि राष्ट्रीय उद्यान", "भीमबांध अभयारण्य", "कैमूर अभयारण्य", "गौतम बुद्ध अभयारण्य"],
      correct: 0,
      exp: "व्याख्या: वाल्मीकि राष्ट्रीय उद्यान पश्चिम चंपारण जिले में स्थित एकमात्र टाइगर रिजर्व और नेशनल पार्क है।"
    },
    {
      q: "11. 'मधुबनी चित्रकला' को अंतरराष्ट्रीय स्तर पर पहली बार पद्मश्री पाने वाली कलाकार कौन थीं?",
      options: ["सीता देवी", "गंगा देवी", "जगदंबा देवी", "महासुंदरी देवी"],
      correct: 2,
      exp: "व्याख्या: जगदंबा देवी को वर्ष 1975 में भारत सरकार द्वारा पद्मश्री से सम्मानित किया गया था।"
    },
    {
      q: "12. बिहार में स्वराज दल का गठन 1923 में किसकी अध्यक्षता में हुआ था?",
      options: ["श्रीकृष्ण सिंह", "नारायण प्रसाद", "अब्दुल बारी", "हरिहर प्रसाद"],
      correct: 1,
      exp: "व्याख्या: फरवरी 1923 में बिहार स्वराज दल का गठन हुआ, जिसके अध्यक्ष नारायण प्रसाद और सचिव प्रो. अब्दुल बारी बनाए गए थे।"
    },
    {
      q: "13. नालंदा विश्वविद्यालय के संस्थापक कौन थे?",
      options: ["समुद्रगुप्त", "कुमारगुप्त प्रथम", "स्कंदगुप्त", "धर्मपाल"],
      correct: 1,
      exp: "व्याख्या: गुप्त वंश के सम्राट कुमारगुप्त प्रथम (महेंद्रादित्य) ने 5वीं शताब्दी में नालंदा महाविहार की नींव रखी थी।"
    },
    {
      q: "14. विक्रमशिला विश्वविद्यालय की स्थापना किस पाल शासक ने की थी?",
      options: ["गोपाल", "देवपाल", "धर्मपाल", "महिपाल"],
      correct: 2,
      exp: "व्याख्या: पालवंशीय शासक धर्मपाल ने 8वीं शताब्दी में भागलपुर के कहलगांव के समीप विक्रमशिला विश्वविद्यालय बनवाया था।"
    },
    {
      q: "15. बिहार में 'त्रिवेणी नहर' किस नदी से निकाली गई है?",
      options: ["सोन नदी", "कमला नदी", "गंडक नदी", "मयूराक्षी नदी"],
      correct: 2,
      exp: "व्याख्या: त्रिवेणी नहर गंडक नदी से पश्चिम चंपारण जिले में निकाली गई है जो उत्तर-पश्चिम बिहार को सिंचित करती है।"
    },
    {
      q: "16. बिहार का क्षेत्रफल भारत के कुल भौगोलिक क्षेत्रफल का कितना प्रतिशत है?",
      options: ["2.42%", "2.86%", "3.16%", "1.86%"],
      correct: 1,
      exp: "व्याख्या: बिहार का कुल क्षेत्रफल 94,163 वर्ग किमी है, जो भारत के कुल क्षेत्रफल का लगभग 2.86% है।"
    },
    {
      q: "17. बिहार राज्य का गठन आधिकारिक रूप से कब किया गया था?",
      options: ["22 मार्च 1912", "1 अप्रैल 1936", "15 नवंबर 2000", "26 जनवरी 1950"],
      correct: 0,
      exp: "व्याख्या: 22 मार्च 1912 को बंगाल प्रेसीडेंसी से अलग होकर बिहार-ओडिशा संयुक्त प्रांत बना, इसीलिए 22 मार्च को बिहार दिवस मनाया जाता है।"
    },
    {
      q: "18. बिहार से अलग होकर उड़ीसा एक नया राज्य कब बना?",
      options: ["1912", "1936", "1947", "1956"],
      correct: 1,
      exp: "व्याख्या: 1 अप्रैल 1936 को भारत सरकार अधिनियम 1935 के तहत उड़ीसा को बिहार से अलग प्रांत बनाया गया।"
    },
    {
      q: "19. बिहार से अलग करके झारखंड राज्य की स्थापना कब की गई?",
      options: ["1 नवंबर 2000", "9 नवंबर 2000", "15 नवंबर 2000", "1 जनवरी 2001"],
      correct: 2,
      exp: "व्याख्या: भगवान बिरसा मुंडा की जयंती पर 15 नवंबर 2000 को बिहार के 46% भूभाग को अलग करके झारखंड राज्य बना।"
    },
    {
      q: "20. बिहार के प्रथम मुख्यमंत्री कौन थे?",
      options: ["डॉ. अनुग्रह नारायण सिंह", "डॉ. श्रीकृष्ण सिंह", "कर्पूरी ठाकुर", "भोला पासवान शास्त्री"],
      correct: 1,
      exp: "व्याख्या: 'बिहार केसरी' के नाम से विख्यात डॉ. श्रीकृष्ण सिंह बिहार के प्रथम मुख्यमंत्री थे।"
    },
    {
      q: "21. बिहार के प्रथम राज्यपाल (आजादी के बाद) कौन बने थे?",
      options: ["जयरामदास दौलतराम", "आर.आर. दिवाकर", "माधव श्रीहरि अणे", "जाकिर हुसैन"],
      correct: 0,
      exp: "व्याख्या: 15 अगस्त 1947 को स्वतंत्रता के पश्चात जयरामदास दौलतराम बिहार के पहले राज्यपाल बने।"
    },
    {
      q: "22. बिहार विधान परिषद (Legislative Council) की कुल सीटों की संख्या कितनी है?",
      options: ["75", "243", "40", "16"],
      correct: 0,
      exp: "व्याख्या: बिहार द्विसदनीय व्यवस्था वाला राज्य है जहां विधानसभा में 243 और विधान परिषद में 75 सीटें हैं।"
    },
    {
      q: "23. बिहार से लोकसभा के लिए कितने सदस्य चुने जाते हैं?",
      options: ["38", "40", "54", "16"],
      correct: 1,
      exp: "व्याख्या: बिहार से लोकसभा की 40 और राज्यसभा की 16 सीटें निर्धारित हैं।"
    },
    {
      q: "24. बिहार में लोकसभा की कुल कितनी सीटें अनुसूचित जाति (SC) के लिए आरक्षित हैं?",
      options: ["4", "6", "8", "2"],
      correct: 1,
      exp: "व्याख्या: बिहार में 6 लोकसभा सीटें SC वर्ग के लिए आरक्षित हैं: गोपालगंज, हाजीपुर, समस्तीपुर, सासाराम, गया और जमुई।"
    },
    {
      q: "25. बिहार का राजकीय वृक्ष कौन सा है?",
      options: ["बरगद", "पीपल", "नीम", "आम"],
      correct: 1,
      exp: "व्याख्या: बिहार का राजकीय वृक्ष पीपल (बोधिवृक्ष का प्रतीक) है।"
    },
    {
      q: "26. बिहार का राजकीय पुष्प (फूल) कौन सा है?",
      options: ["कमल", "गेंदा", "गुलाब", "चमेली"],
      correct: 1,
      exp: "व्याख्या: बिहार का आधिकारिक राजकीय पुष्प गेंदा (Marigold) है।"
    },
    {
      q: "27. बिहार का राजकीय पशु किसे घोषित किया गया है?",
      options: ["बाघ", "बैल", "हाथी", "एक सींग वाला गैंडा"],
      correct: 1,
      exp: "व्याख्या: 2013 के बाद बिहार का नया राजकीय पशु 'बैल' (Gaur/Bull) घोषित किया गया, पहले यह रीछ था।"
    },
    {
      q: "28. बिहार में सर्वाधिक साक्षरता दर (Literacy Rate) वाला जिला कौन सा है?",
      options: ["पटना", "रोहतास", "मुंगेर", "भोजपुर"],
      correct: 1,
      exp: "व्याख्या: 2011 जनगणना के अनुसार रोहतास 73.37% साक्षरता दर के साथ शीर्ष स्थान पर है।"
    },
    {
      q: "29. बिहार में सबसे कम साक्षरता दर वाला जिला कौन सा है?",
      options: ["पूर्णिया", "कटिहार", "मधेपुरा", "शिवहर"],
      correct: 0,
      exp: "व्याख्या: पूर्णिया जिला 51.08% साक्षरता दर के साथ राज्य में सबसे निचले पायदान पर है।"
    },
    {
      q: "30. बिहार में सबसे कम वर्षा किस जिले में दर्ज की जाती है?",
      options: ["औरंगाबाद", "गया", "कैमूर", "नवादा"],
      correct: 0,
      exp: "व्याख्या: दक्षिण-पश्चिम बिहार का औरंगाबाद जिला सबसे कम वर्षा प्राप्त करने वाला सूखा जिला है।"
    },
    {
      q: "31. बिहार में सर्वाधिक वर्षा किस जिले में होती है?",
      options: ["किशनगंज", "पूर्णिया", "अररिया", "सुपौल"],
      correct: 0,
      exp: "व्याख्या: पूर्वोत्तर में स्थित किशनगंज जिला बंगाल की खाड़ी शाखा के मानसून के सबसे निकट होने के कारण सर्वाधिक वर्षा प्राप्त करता है।"
    },
    {
      q: "32. बिहार का सबसे गर्म और सबसे ठंडा जिला कौन सा है?",
      options: ["पटना", "गया", "मुजफ्फरपुर", "भागलपुर"],
      correct: 1,
      exp: "व्याख्या: अपनी चरम स्थलाकृति और पठारी प्रभाव के कारण गया जिला बिहार का सबसे गर्म और सबसे ठंडा दोनों जिला है।"
    },
    {
      q: "33. प्रथम बौद्ध संगीति का आयोजन कहाँ हुआ था?",
      options: ["वैशाली", "पाटलिपुत्र", "राजगृह", "कुंडलवन"],
      correct: 2,
      exp: "व्याख्या: 483 ईसा पूर्व में बुद्ध के महापरिनिर्वाण के तुरंत बाद राजगृह की सप्तपर्णी गुफा में अजातशत्रु के शासनकाल में प्रथम संगीति हुई।"
    },
    {
      q: "34. द्वितीय बौद्ध संगीति किसके शासनकाल में आयोजित की गई थी?",
      options: ["अशोक", "कालाशोक", "अजातशत्रु", "कनिष्क"],
      correct: 1,
      exp: "व्याख्या: 383 ईसा पूर्व में शिशुनाग वंश के शासक कालाशोक (काकवर्ण) के संरक्षण में वैशाली में द्वितीय बौद्ध संगीति हुई।"
    },
    {
      q: "35. तृतीय बौद्ध संगीति की अध्यक्षता किसने की थी?",
      options: ["महाकस्सप", "सब्बकामी", "मोग्गलिपुत्त तिस्स", "वसुमित्र"],
      correct: 2,
      exp: "व्याख्या: सम्राट अशोक के शासनकाल में 250 ई.पू. पाटलिपुत्र में आयोजित तृतीय संगीति की अध्यक्षता मोग्गलिपुत्त तिस्स ने की थी।"
    },
    {
      q: "36. भगवान महावीर का जन्म बिहार में कहाँ हुआ था?",
      options: ["पावापुरी", "कुण्डग्राम (वैशाली)", "लुंबिनी", "बोधगया"],
      correct: 1,
      exp: "व्याख्या: 24वें तीर्थंकर भगवान महावीर का जन्म 540 ईसा पूर्व में वैशाली के निकट कुण्डग्राम
