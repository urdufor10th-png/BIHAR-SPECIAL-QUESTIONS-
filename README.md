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

    /* REAL IN-PAGE POPUP MODAL (100% Browser/GitHub Compatible) */
    .modal-overlay {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.7);
      z-index: 10000;
      justify-content: center;
      align-items: center;
    }

    .modal-content {
      background: #ffffff;
      padding: 35px;
      border-radius: 15px;
      max-width: 600px;
      width: 90%;
      text-align: center;
      border: 4px solid #2e7d32;
      box-shadow: 0 10px 30px rgba(0,0,0,0.4);
      animation: popIn 0.3s ease-out;
    }

    @keyframes popIn {
      from { transform: scale(0.7); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    .otp-code-highlight {
      font-size: 55px;
      color: #b71c1c;
      font-weight: bold;
      letter-spacing: 5px;
      margin: 20px 0;
      padding: 10px;
      background: #ffebee;
      border: 2px dashed #b71c1c;
      border-radius: 8px;
      display: inline-block;
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

    /* Option Highlighting */
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

<!-- REAL POP-UP WINDOW (Modal) -->
<div class="modal-overlay" id="otpModal">
  <div class="modal-content">
    <h3 style="color: #2e7d32; margin-top: 0;">📱 सत्यापन कोड (OTP)</h3>
    <p style="font-size: 30px; margin: 10px 0;">आपका 4 अंकों का सुरक्षा कोड:</p>
    <div class="otp-code-highlight" id="modalOtpValue">----</div>
    <p style="font-size: 26px; color: #555;">कृपया यह कोड नीचे दिए गए OTP बॉक्स में दर्ज करें।</p>
    <button type="button" class="btn" style="background-color: #2e7d32; font-size: 30px; padding: 10px 30px;" onclick="closeOtpModal()">कोड समझ गया / ठीक है</button>
  </div>
</div>

<div class="container">
  <!-- Motivation Quote -->
  <div class="motivation">
    "मेहनत इतनी खामोशी से करो कि सफलता शोर मचा दे। अपने लक्ष्य पर अडिग रहो, जीत निश्चित है!"
  </div>

  <!-- Registration Form -->
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
        <button type="button" class="btn" style="font-size: 30px; padding: 10px 22px; background-color: #1565c0;" onclick="openOtpModal()">OTP प्राप्त करें</button>
      </div>

      <div class="form-group" id="otp-group" style="display: none;">
        <label for="otp" style="color: #b71c1c;">पॉप-अप में दिखाया गया OTP यहाँ दर्ज करें:</label>
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

  // Real In-Page Popup Window Trigger
  function openOtpModal() {
    const mobile = document.getElementById("mobile").value.trim();
    const errorDisplay = document.getElementById("form-error");

    errorDisplay.style.display = "none";

    if (mobile.length !== 10 || isNaN(mobile)) {
      errorDisplay.style.display = "block";
      errorDisplay.innerText = "❌ कृपया पहले सही 10 अंकों का मोबाइल नंबर दर्ज करें!";
      return;
    }

    // 4-Digit Unique Code Generate
    generatedOtp = Math.floor(1000 + Math.random() * 9000).toString();

    // Modal ke andar OTP daalna
    document.getElementById("modalOtpValue").innerText = generatedOtp;

    // In-page Popup Window Show
    document.getElementById("otpModal").style.display = "flex";

    // Neeche ka input box open
    document.getElementById("otp-group").style.display = "block";
  }

  function closeOtpModal() {
    document.getElementById("otpModal").style.display = "none";
    document.getElementById("otp").focus();
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
      errorDisplay.innerText = "❌ गलत OTP! पॉप-अप में दिखाया गया सही 4 अंकों का कोड दर्ज करें।";
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
      exp: "व्याख्या: 24वें तीर्थंकर भगवान महावीर का जन्म 540 ईसा पूर्व में वैशाली के निकट कुण्डग्राम के ज्ञातृक कुल में हुआ था।"
    },
    {
      q: "37. भगवान महावीर को निर्वाण (मोक्ष) कहाँ प्राप्त हुआ था?",
      options: ["कुशीनगर", "पावापुरी", "राजगृह", "चंपा"],
      correct: 1,
      exp: "व्याख्या: नालंदा जिले के पावापुरी में 72 वर्ष की आयु में महावीर स्वामी को कैवल्य/निर्वाण की प्राप्ति हुई जहां जलमंदिर स्थित है।"
    },
    {
      q: "38. गौतम बुद्ध को ज्ञान की प्राप्ति किस नदी के तट पर हुई थी?",
      options: ["गंगा", "सोन", "निरंजना (फल्गु)", "गंडक"],
      correct: 2,
      exp: "व्याख्या: बोधगया में निरंजना नदी के तट पर एक पीपल वृक्ष के नीचे 35 वर्ष की अवस्था में सिद्धार्थ को बुद्धत्व प्राप्त हुआ।"
    },
    {
      q: "39. प्राचीन महाजनपद 'मगध' की प्रथम राजधानी कौन सी थी?",
      options: ["पाटलिपुत्र", "वैशाली", "गिरिव्रज (राजगृह)", "चंपा"],
      correct: 2,
      exp: "व्याख्या: मगध साम्राज्य की प्रारंभिक राजधानी पाँच पहाड़ियों से घिरी गिरिव्रज (राजगृह) थी।"
    },
    {
      q: "40. अंग महाजनपद की राजधानी कहाँ स्थित थी?",
      options: ["चंपा", "वाराणसी", "कौशांबी", "श्रावस्ती"],
      correct: 0,
      exp: "व्याख्या: वर्तमान भागलपुर और मुंगेर जिलों के क्षेत्र पर विस्तृत अंग राज्य की राजधानी चंपा (मालिनी) थी।"
    },
    {
      q: "41. विश्व का पहला गणतंत्र (Republic) कहाँ स्थापित हुआ था?",
      options: ["एथेंस", "स्पार्टा", "वैशाली", "पाटलिपुत्र"],
      correct: 2,
      exp: "व्याख्या: ईसा पूर्व छठी शताब्दी में वैशाली के लिच्छवियों ने विश्व का प्रथम लोकतांत्रिक/गणतंत्रात्मक संघ स्थापित किया था।"
    },
    {
      q: "42. कौटिल्य (चाणक्य) किसके प्रधानमंत्री थे?",
      options: ["चन्द्रगुप्त मौर्य", "बिन्दुसार", "अशोक", "हर्षवर्धन"],
      correct: 0,
      exp: "व्याख्या: चाणक्य ने नंद वंश को उखाड़ फेंकने में चन्द्रगुप्त मौर्य की सहायता की और उनके प्रधानमंत्री एवं प्रधान सलाहकार बने।"
    },
    {
      q: "43. 'अर्थशास्त्र' पुस्तक के लेखक कौटिल्य का संबंध किस प्राचीन विश्वविद्यालय से था?",
      options: ["नालंदा", "तक्षशिला", "विक्रमशिला", "वल्लभी"],
      correct: 1,
      exp: "व्याख्या: चाणक्य गांधार स्थित प्राचीन तक्षशिला विश्वविद्यालय में राजनीति और अर्थशास्त्र के आचार्य थे।"
    },
    {
      q: "44. मौर्य साम्राज्य के दरबार में यूनानी राजदूत मेगस्थनीज को किसने भेजा था?",
      options: ["सिकंदर", "सेल्युकस निकेटर", "डेमेट्रियस", "टॉलेमी"],
      correct: 1,
      exp: "व्याख्या: सेल्युकस ने 305 ई.पू. संधि के पश्चात मेगस्थनीज को पाटलिपुत्र में चन्द्रगुप्त मौर्य के दरबार में भेजा था।"
    },
    {
      q: "45. पाटलिपुत्र के नगर प्रशासन का वर्णन मेगस्थनीज की किस पुस्तक में मिलता है?",
      options: ["इंडिका", "मुद्राराक्षस", "अर्थशास्त्र", "राजतरंगिणी"],
      correct: 0,
      exp: "व्याख्या: मेगस्थनीज की पुस्तक 'इंडिका' में पाटलिपुत्र के नगर प्रशासन के लिए 6 समितियों (प्रत्येक में 5 सदस्य) का उल्लेख है।"
    },
    {
      q: "46. सम्राट अशोक के शिलालेखों में मुख्य रूप से किस भाषा और लिपि का प्रयोग हुआ है?",
      options: ["संस्कृत व देवनागरी", "प्राकृत व ब्राह्मी", "पाली व खरोष्ठी", "अर्धमागधी"],
      correct: 1,
      exp: "व्याख्या: अशोक के अधिकांश भारतीय शिलालेख प्राकृत भाषा और ब्राह्मी लिपि में उत्कीर्ण हैं।"
    },
    {
      q: "47. शेरशाह सूरी का प्रसिद्ध मकबरा बिहार में कहाँ स्थित है?",
      options: ["पटना", "सासाराम", "रोहतासगढ़", "मनेर"],
      correct: 1,
      exp: "व्याख्या: सासाराम (रोहतास) में एक कृत्रिम झील के बीचो-बीच अष्टकोणीय लाल बलुआ पत्थर से बना शेरशाह का मकबरा स्थित है।"
    },
    {
      q: "48. पटना शहर को 'अजीमाबाद' नाम किसने दिया था?",
      options: ["औरंगजेब", "राजकुमार अजीम-उस-शान", "शाह आलम द्वितीय", "फर्रुखसियर"],
      correct: 1,
      exp: "व्याख्या: 1704 में मुगल सूबेदार एवं औरंगजेब के पोते शहजादा अजीम-उस-शान ने पटना का नाम बदलकर अजीमाबाद किया था।"
    },
    {
      q: "49. 1764 में ऐतिहासिक बक्सर का युद्ध किसके-किसके बीच लड़ा गया था?",
      options: ["मीर कासिम की संयुक्त सेना और हेक्टर मुनरो", "सिराजुद्दौला और रॉबर्ट क्लाइव", "टीपू सुल्तान और वारेन हेस्टिंग्स", "मराठा और अहमद शाह अब्दाली"],
      correct: 0,
      exp: "व्याख्या: 22 अक्टूबर 1764 को मीर कासिम, शुजाउद्दौला और शाह आलम द्वितीय की संयुक्त सेना को मेजर हेक्टर मुनरो के नेतृत्व वाली ब्रिटिश सेना ने हराया।"
    },
    {
      q: "50. 'इलाहाबाद की संधि' (1765) के तहत अंग्रेजों को बिहार, बंगाल और उड़ीसा की क्या प्राप्त हुई?",
      options: ["सैन्य कमान", "दीवानी अधिकार", "न्यायिक पद", "सूबेदारी"],
      correct: 1,
      exp: "व्याख्या: शाह आलम द्वितीय ने ईस्ट इंडिया कंपनी को 26 लाख रुपये वार्षिक पेंशन के बदले बिहार, बंगाल व उड़ीसा की दीवानी (राजस्व वसूली) सौंप दी।"
    },
    {
      q: "51. बिहार में 'वहाबी आंदोलन' का प्रमुख केंद्र कौन सा शहर था?",
      options: ["मुंगेर", "पटना", "भागलपुर", "गया"],
      correct: 1,
      exp: "व्याख्या: 19वीं सदी में सैयद अहमद बरेलवी द्वारा शुरू किए गए वहाबी आंदोलन का सबसे प्रमुख संगठनात्मक केंद्र पटना था।"
    },
    {
      q: "52. 1857 के विद्रोह के समय पटना में क्रांति का नेतृत्व किसने किया था?",
      options: ["पीर अली", "अमर सिंह", "विलायत अली", "इनायत अली"],
      correct: 0,
      exp: "व्याख्या: 3 जुलाई 1857 को पटना के पुस्तक विक्रेता पीर अली ने अंग्रेजों के विरुद्ध विद्रोह का झंडा बुलंद किया था।"
    },
    {
      q: "53. बिहार में 'होम रूल लीग' की स्थापना दिसंबर 1916 में किसकी अध्यक्षता में हुई थी?",
      options: ["मौलाना मजहरुल हक", "सरफराज हुसैन खां", "पूर्णेंदु नारायण सिन्हा", "चंद्रवंशी सहाय"],
      correct: 0,
      exp: "व्याख्या: 16 दिसंबर 1916 को बांकीपुर (पटना) में मौलाना मजहरुल हक की अध्यक्षता में बिहार होमरूल लीग गठित हुई।"
    },
    {
      q: "54. भारतीय राष्ट्रीय कांग्रेस का 27वां अधिवेशन (1912) बिहार में कहाँ हुआ था?",
      options: ["गया", "बांकीपुर (पटना)", "रामगढ़", "भागलपुर"],
      correct: 1,
      exp: "व्याख्या: 1912 में बांकीपुर (पटना) में कांग्रेस का पहला बिहार अधिवेशन हुआ, जिसके अध्यक्ष आर.एन. माधोलकर थे।"
    },
    {
      q: "55. वर्ष 1922 का कांग्रेस का गया अधिवेशन किसकी अध्यक्षता में आयोजित हुआ था?",
      options: ["चितरंजन दास", "मोतीलाल नेहरू", "हकीम अजमल खां", "लाला लाजपत राय"],
      correct: 0,
      exp: "व्याख्या: देशबंधु चितरंजन दास ने गया कांग्रेस अधिवेशन (1922) की अध्यक्षता की थी, जहां परिषदों में प्रवेश के मुद्दे पर विवाद हुआ।"
    },
    {
      q: "56. बिहार में 'नमक सत्याग्रह' सर्वप्रथम किन जिलों में शुरू हुआ था?",
      options: ["पटना व गया", "चंपारण व सारण", "मुंगेर व भागलपुर", "दरभंगा व मधुबनी"],
      correct: 1,
      exp: "व्याख्या: 15 अप्रैल 1930 को चंपारण और सारण जिलों में नमकीन मिट्टी से नमक बनाकर नमक कानून तोड़ा गया।"
    },
    {
      q: "57. सविनय अवज्ञा आंदोलन के दौरान बिहार में कौन सा प्रमुख कर न देने का आंदोलन चला?",
      options: ["भू-राजस्व कर", "चौकीदारी कर", "आयकर", "सीमा शुल्क"],
      correct: 1,
      exp: "व्याख्या: समुद्र तट न होने के कारण बिहार में सविनय अवज्ञा आंदोलन का मुख्य जोर चौकीदारी टैक्स बंदी पर केंद्रित था।"
    },
    {
      q: "58. बिहार सोशलिस्ट पार्टी की औपचारिक स्थापना 1934 में कहाँ हुई थी?",
      options: ["सदाकत आश्रम", "अंजुमन इस्लामिया हॉल, पटना", "टाउन हॉल मुजफ्फरपुर", "गांधी मैदान"],
      correct: 1,
      exp: "व्याख्या: पटना के अंजुमन इस्लामिया हॉल में नरेंद्र देव की अध्यक्षता और जयप्रकाश नारायण के सचिवत्व में यह पार्टी बनी।"
    },
    {
      q: "59. 'भारत छोड़ो आंदोलन' (1942) के दौरान हजारीबाग जेल से भागकर भूमिगत आंदोलन किसने चलाया?",
      options: ["डॉ. राजेंद्र प्रसाद", "जयप्रकाश नारायण", "रामवृक्ष बेनीपुरी", "योगेंद्र शुक्ल"],
      correct: 1,
      exp: "व्याख्या: दीवाली की रात जयप्रकाश नारायण साथियों सहित हजारीबाग जेल फांदकर नेपाल पहुंचे और वहां 'आजाद दस्ता' संगठित किया।"
    },
    {
      q: "60. 11 अगस्त 1942 को पटना सचिवालय गोलीकांड में कितने छात्र शहीद हुए थे?",
      options: ["5", "7", "9", "11"],
      correct: 1,
      exp: "व्याख्या: पटना सचिवालय पर तिरंगा फहराते समय जिलाधिकारी डब्ल्यू. जी. आर्चर के आदेश पर पुलिस फायरिंग में 7 छात्र शहीद हुए।"
    },
    {
      q: "61. बिहार के किस जिले को स्वतंत्रता आंदोलन के दौरान 'अपराधी जिला' घोषित किया गया था?",
      options: ["सारण", "मुंगेर", "भोजपुर", "गया"],
      correct: 0,
      exp: "व्याख्या: 1942 के भारत छोड़ो आंदोलन के उग्र विरोध प्रदर्शनों के कारण अंग्रेजों ने सारण जिले को 'अपराधी जिला' घोषित किया था।"
    },
    {
      q: "62. भारत के प्रथम राष्ट्रपति डॉ. राजेंद्र प्रसाद का जन्म बिहार के किस गाँव में हुआ था?",
      options: ["जीरादेई", "सिताब दियारा", "मुरली भरहवा", "हथुआ"],
      correct: 0,
      exp: "व्याख्या: डॉ. राजेंद्र प्रसाद का जन्म 3 दिसंबर 1884 को सीवान जिले के जीरादेई गांव में हुआ था।"
    },
    {
      q: "63. 'लोकनायक' की उपाधि किसे दी गई है?",
      options: ["कर्पूरी ठाकुर", "जयप्रकाश नारायण", "अनुग्रह नारायण सिंह", "स्वामी सहजानंद"],
      correct: 1,
      exp: "व्याख्या: 1974 के संपूर्ण क्रांति आंदोलन के प्रणेता जयप्रकाश नारायण को जनता ने 'लोकनायक' की उपाधि दी।"
    },
    {
      q: "64. 'जननायक' के नाम से किन्हें जाना जाता है?",
      options: ["कर्पूरी ठाकुर", "श्रीकृष्ण सिंह", "सच्चिदानंद सिन्हा", "भोला पासवान शास्त्री"],
      correct: 0,
      exp: "व्याख्या: गरीबों और वंचितों के उत्थान के लिए समर्पित बिहार के पूर्व मुख्यमंत्री कर्पूरी ठाकुर को 'जननायक' कहा जाता है।"
    },
    {
      q: "65. संविधान सभा के प्रथम अस्थायी अध्यक्ष डॉ. सच्चिदानंद सिन्हा बिहार के किस जिले से थे?",
      options: ["भोजपुर (आरा)", "पटना", "बक्सर", "नालंदा"],
      correct: 0,
      exp: "व्याख्या: 9 दिसंबर 1946 को संविधान सभा के सबसे वरिष्ठ सदस्य डॉ. सच्चिदानंद सिन्हा (मूल निवासी आरा, भोजपुर) अस्थायी अध्यक्ष चुने गए थे।"
    },
    {
      q: "66. बिहार में गंगा नदी की कुल लंबाई कितनी है?",
      options: ["2525 किमी", "445 किमी", "512 किमी", "380 किमी"],
      correct: 1,
      exp: "व्याख्या: गंगा नदी बिहार में बक्सर जिले के चौसा से प्रवेश करती है और कटिहार से निकलती है; बिहार में इसकी लंबाई 445 किमी है।"
    },
    {
      q: "67. गंगा नदी बिहार के कितने जिलों से होकर प्रवाहित होती है?",
      options: ["10", "12", "14", "16"],
      correct: 1,
      exp: "व्याख्या: गंगा नदी बिहार के कुल 12 जिलों (बक्सर, भोजपुर, सारण, पटना, वैशाली, समस्तीपुर, बेगूसराय, लखीसराय, मुंगेर, खगड़िया, भागलपुर, कटिहार) से गुजरती है।"
    },
    {
      q: "68. गंगा नदी की बिहार में सबसे लंबी सीमा किस जिले में है?",
      options: ["भागलपुर", "पटना", "कटिहार", "बेगूसराय"],
      correct: 1,
      exp: "व्याख्या: पटना जिले में गंगा नदी की लंबाई सबसे अधिक (लगभग 99 किमी) है।"
    },
    {
      q: "69. 'कांवर झील' पक्षी अभयारण्य (Ramsar Site) बिहार के किस जिले में स्थित है?",
      options: ["दरभंगा", "बेगूसराय", "कटिहार", "सहरसा"],
      correct: 1,
      exp: "व्याख्या: बेगूसराय की कांवर झील एशिया की सबसे बड़ी गोखुर (Ox-bow) मीठे पानी की झील है और यह बिहार का पहला रामसर स्थल है।"
    }
  ];

  function loadQuestions() {
    const container = document.getElementById("questions-container");
    container.innerHTML = "";

    quizData.forEach((item, qIndex) => {
      const qDiv = document.createElement("div");
      qDiv.className = "question-block";

      const qTitle = document.createElement("div");
      qTitle.className = "question-text";
      qTitle.innerText = item.q;
      qDiv.appendChild(qTitle);

      item.options.forEach((opt, optIndex) => {
        const label = document.createElement("label");
        label.className = "option-label";
        label.id = `opt-label-${qIndex}-${optIndex}`;
        label.innerHTML = `
          <input type="radio" name="q${qIndex}" value="${optIndex}" onchange="checkAnswerInstantly(${qIndex}, ${optIndex})">
          ${String.fromCharCode(65 + optIndex)}. ${opt}
        `;
        qDiv.appendChild(label);
      });

      const expBox = document.createElement("div");
      expBox.id = `exp-box-${qIndex}`;
      expBox.className = "explanation-box";
      qDiv.appendChild(expBox);

      container.appendChild(qDiv);
    });
  }

  function checkAnswerInstantly(qIndex, selectedOptIndex) {
    if (isQuizSubmitted) return;

    const currentQ = quizData[qIndex];
    const expBox = document.getElementById(`exp-box-${qIndex}`);
    const correctIndex = currentQ.correct;

    const radios = document.querySelectorAll(`input[name="q${qIndex}"]`);
    radios.forEach(r => r.disabled = true);

    const isCorrect = (selectedOptIndex === correctIndex);

    const selectedLabel = document.getElementById(`opt-label-${qIndex}-${selectedOptIndex}`);
    const correctLabel = document.getElementById(`opt-label-${qIndex}-${correctIndex}`);

    if (isCorrect) {
      selectedLabel.classList.add("correct-opt");
      expBox.className = "explanation-box show success";
      expBox.innerHTML = `
        <div class="exp-title">✓ आपका उत्तर सही है!</div>
        <div>${currentQ.exp}</div>
      `;
    } else {
      selectedLabel.classList.add("wrong-opt");
      correctLabel.classList.add("correct-opt");
      expBox.className = "explanation-box show fail";
      expBox.innerHTML = `
        <div class="exp-title">✗ आपका उत्तर गलत है! (सही उत्तर: विकल्प ${String.fromCharCode(65 + correctIndex)} - ${currentQ.options[correctIndex]})</div>
        <div>${currentQ.exp}</div>
      `;
    }
  }

  function finishQuiz(isAutoSubmit) {
    if (isQuizSubmitted) return;
    isQuizSubmitted = true;

    clearInterval(timerInterval);

    let score = 0;
    quizData.forEach((item, qIndex) => {
      const selected = document.querySelector(`input[name="q${qIndex}"]:checked`);
      if (selected && parseInt(selected.value) === item.correct) {
        score++;
      }
      if (!selected) {
        const expBox = document.getElementById(`exp-box-${qIndex}`);
        const correctLabel = document.getElementById(`opt-label-${qIndex}-${item.correct}`);
        correctLabel.classList.add("correct-opt");
        expBox.className = "explanation-box show fail";
        expBox.innerHTML = `
          <div class="exp-title">⚠️ अनुत्तरित (सही उत्तर: विकल्प ${String.fromCharCode(65 + item.correct)} - ${item.options[item.correct]})</div>
          <div>${item.exp}</div>
        `;
      }
    });

    document.querySelectorAll("input[type=radio]").forEach(r => r.disabled = true);
    document.getElementById("manualSubmitBtn").style.display = "none";

    const resultDiv = document.getElementById("result");
    resultDiv.style.display = "block";
    resultDiv.innerHTML = `
      <div>${isAutoSubmit ? "⏰ समय समाप्त!" : "🎉 टेस्ट सफलतापूर्व समाप्त!"}</div>
      <div style="margin-top: 10px;">आपका कुल प्राप्तांक: ${score} / ${quizData.length}</div>
    `;

    resultDiv.scrollIntoView({ behavior: 'smooth' });
  }
</script>

</body>
</html>
