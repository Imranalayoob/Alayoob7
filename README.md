
<html lang="ar" dir="rtl"><head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>الايوب</title>
    <link href="https://fonts.googleapis.com/css2?family=Baloo+Bhaijaan+2:wght@400;700&amp;family=Tajawal:wght@400;700&amp;family=Rubik:wght@400;700&amp;family=Almarai:wght@400;700&amp;family=Noto+Naskh+Arabic:wght@400;700&amp;family=Vazirmatn:wght@400;700&amp;display=swap" rel="stylesheet">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" rel="stylesheet">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="">
    <link href="https://fonts.googleapis.com/css2?family=Baloo+Bhaijaan+2:wght@400..800&amp;display=swap" rel="stylesheet">
    <style>
    body {
      font-family: 'Vazirmatn', cursive;
      margin: 0;
      padding: 20px;
      background-color: #ffffff;
      color: black;
      text-align: center;
      transition: background-color 0.4s, color 0.4s;
    }
    .prayer-container {
      cursor: pointer;
      background-color: #f9f9f9;
      margin-bottom: 20px;
      padding: 15px;
      border-radius: 37px;
      position: relative;
      transition: background-color 0.4s, color 0.1s;
    }
    .prayer-container:hover {
      background-color: #e0e0e0;
    }
    .theme-switcher {
      position: fixed;
      top: 20px;
      left: 22px;
      width: 80px; 
      height: 40px;
      background-color: #ff7373;
      border-radius: 20px;
      cursor: pointer;
      border: none;
      transition: background-color 0.4s ease;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 5px;
      z-index: 1000;
      color: white;
      font-size: 15px;
    }
    .theme-switcher:hover {
      background-color: #fe5e5e;
    }
    .theme-switcher:before,
    .theme-switcher:after {
      content: '';
      display: block;
    }
    .theme-switcher .icon { 
      font-size: 20px;
      color: #fff;
    }
    .dark-mode {
      background-color: #333;
      color: white;
    }
    .dark-mode .theme-switcher {
      background-color: #5eb1db;
    }
    .dark-mode .theme-switcher:hover {
      background-color: #4aa9d9;
    }
    .dark-mode .prayer-container {
      background-color: #444;
      color: #ddd;
    }
    .dark-mode .prayer-container:hover {
      background-color: #363636;
    }
    #prayers {
      margin-top: 70px;
    }
    .prayer-container p {
      font-size: 20px;
    }
    @keyframes slideUp {
      0% {
        transform: translateY(100%);
        opacity: 0;
      }
      10%, 90% {
        transform: translateY(-20px);
        opacity: 1;
      }
      100% {
        transform: translateY(100%);
        opacity: 0;
      }
    }
    #copy-message {
      position: fixed;
      bottom: 0;
      left: 50%;
      transform: translate(-50%, 0);
      background-color: #72a0f0;
      color: #fff;
      border-radius: 50px;
      padding: 5px;
      width: auto;
      min-width: 100px;
      text-align: center;
      z-index: 1001;
      font-size: 16px;
      display: none;
    }
    .dark-mode #copy-message {
      background-color: #ffffff;
      color: #444;
      border-radius: 50px;
      font-weight: 500;
    }
    .show-notification {
      display: block;
      animation: slideUp 2s ease forwards;
    }
    .font-size-controls {
      position: fixed;
      top: 20px;
      right: 20px;
      display: flex;
      z-index: 1002;
    }
    .font-size-changer,
    .font-changer {
      background-color: #cccccc;
      border: none;
      border-radius: 50%;
      width: 40px;
      height: 40px;
      cursor: pointer;
      margin-left: 10px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .font-size-changer i,
    .font-changer i {
      font-size: 15px;
      color: #fff;
      transition: 0.4s;
    }
    .dark-mode .font-size-changer,
    .dark-mode .font-changer {
      transition: 0.4s;
      background-color: #ffffff;
    }
    .dark-mode .font-size-changer i,
    .dark-mode .font-changer i {
      font-size: 15px;
      color: #333;
    }
    @media (max-width: 768px) {
      .font-size-controls {
        display: flex;
      }
      #copy-message {
      position: fixed;
      bottom: 0;
      left: 36%;
      transform: translate(-50%, 0);
      background-color: #72a0f0;
      color: #fff;
      border-radius: 50px;
      padding: 5px;
      width: auto;
      min-width: 100px;
      text-align: center;
      z-index: 1001;
      font-size: 16px;
      display: none;
    }
    }
    #info-window {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: white;
      padding: 20px;
      border-radius: 28px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      z-index: 1050;
      width: 80%;
      max-width: 406px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    #close-info {
      margin-top: 20px;
      padding: 10px 20px;
      border-radius: 23px;
      border: none;
      background-color: #ccc;
      cursor: pointer;
      font-family: 'Vazirmatn', cursive;
      transition: 0.4s;
      color: black;
    }
    #close-info:hover {
      margin-top: 20px;
      padding: 10px 20px;
      border-radius: 23px;
      border: none;
      background-color: rgb(213, 211, 211);
      cursor: pointer;
      font-family: 'Vazirmatn', cursive;
      transition: 0.4s;
    }
    #info-window a {
      color: black;
    }
    .dark-mode #info-window a {
      color: white;
    }
    .dark-mode #info-window {
      background-color: #333;
      color: white;
    }
    .dark-mode #close-info {
      background-color: #555;
      font-family: 'Vazirmatn', cursive;
      color: white;
      transition: 0.4s;
    }
    .dark-mode #close-info:hover {
      background-color: #4e4e4e;
      font-family: 'Vazirmatn', cursive;
      color: white;
      transition: 0.4s;
    }
    #overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      z-index: 1040;
    }
    a {
      text-decoration: none;
      color: while;
    }
    </style>
    </head>
    <body>
      <div class="font-size-controls">
        <button class="font-changer"><i class="fa fa-font" aria-hidden="true"></i>    </button> 
        <button id="increase-font" class="font-size-changer"><i class="fas fa-plus"></i></button>
        <button id="toggle-diacritics" class="font-size-changer"><i class="fas fa-strikethrough"></i></button>
        <button id="decrease-font" class="font-size-changer"><i class="fas fa-minus"></i></button>
    <button id="info-btn" class="font-size-changer"><i class="fas fa-info"></i></button>
      </div>
      <div id="info-window" style="display:none;">
        <div id="info-content">
    
            <p>هذا الموقع يسهل عليك قراءة الادعية والاذكار بفضل الميزات التي نوفرها من تكبير وتصغير الخط مع ميزة تغير نوع الكتابة</p>
    
    <p>هذا الموقع صدقة جارية لروح المرحوم </p>
    <p>الاستاذ<strong  style="color:#aa0">  ايوب عبد دبيس</strong></p>
            
            
            
          <p>للتواصل والاقتراحات <a href="mailto:IMRAN@ALAYOOB.COM" target="_blank">IMRAN@ALAYOOB.COM</a></p>
          <button id="close-info">إغلاق</button>
        </div>
      </div>
      <div id="overlay" style="display:none;"></div>
      <button class="theme-switcher" onclick="toggleTheme()">
        <i class="fas fa-sun" aria-hidden="true"></i> 
        <i class="fas fa-moon" aria-hidden="true"></i> 
      </button>
        <div id="prayers"><div class="prayer-container"><p data-original-text="رَبَّنَا آتِنَا فِي الدُّنْيَا حَسَنَةً، وَفِي الْآخِرَةِ حَسَنَةً، وَقِنَا عَذَابَ النَّارِ.">رَبَّنَا آتِنَا فِي الدُّنْيَا حَسَنَةً، وَفِي الْآخِرَةِ حَسَنَةً، وَقِنَا عَذَابَ النَّارِ.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِنَّكَ عَفُوٌّ كَرِيمٌ تُحِبُّ العّفْوَ فَاعْفُ عَنِّي.">اللَّهُمَّ إِنَّكَ عَفُوٌّ كَرِيمٌ تُحِبُّ العّفْوَ فَاعْفُ عَنِّي.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ خُذْ بِنَوَاصِينَا لِِلْبِرِّ وَالتَّقْوَى، وَلِمَا تُحِبُّ مِنَ العَمَلِ وَتَرْضَى.">اللَّهُمَّ خُذْ بِنَوَاصِينَا لِِلْبِرِّ وَالتَّقْوَى، وَلِمَا تُحِبُّ مِنَ العَمَلِ وَتَرْضَى.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِنِّي أَعُوذُ بِرِضَاكَ مِنْ سَخَطِكَ، وَبِمُعَافَاتِكَ مِنْ عُقُوبَتِكَ، وَأَعُوذُ بِكَ مِنْكَ، لَا أُحْصِي ثَنَاءً عَلَيْكَ، أَنْتَ كَمَا أَثْنَيْتَ عَلَى نَفْسِكَ. ">اللَّهُمَّ إِنِّي أَعُوذُ بِرِضَاكَ مِنْ سَخَطِكَ، وَبِمُعَافَاتِكَ مِنْ عُقُوبَتِكَ، وَأَعُوذُ بِكَ مِنْكَ، لَا أُحْصِي ثَنَاءً عَلَيْكَ، أَنْتَ كَمَا أَثْنَيْتَ عَلَى نَفْسِكَ. </p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ أَصْلِحْ لِي دِينِي الَّذِي هُوَ عِصْمَةُ أَمْرِي، وَأَصْلِحْ لِي دُنْيَايَ الَّتِي فِيهَا مَعَاشِي، وَأَصْلِحْ لِي آخِرَتِي الَّتِي فِيهَا مَعَادِي وَاجْعَلِ الْحَيَاةَ زِيَادَةً لِي فِي كُلِّ خَيْرٍ، وَاجْعَلِ الْمَوْتَ رَاحَةً لِي مِنْ كُلِّ شَرٍّ. ">اللَّهُمَّ أَصْلِحْ لِي دِينِي الَّذِي هُوَ عِصْمَةُ أَمْرِي، وَأَصْلِحْ لِي دُنْيَايَ الَّتِي فِيهَا مَعَاشِي، وَأَصْلِحْ لِي آخِرَتِي الَّتِي فِيهَا مَعَادِي وَاجْعَلِ الْحَيَاةَ زِيَادَةً لِي فِي كُلِّ خَيْرٍ، وَاجْعَلِ الْمَوْتَ رَاحَةً لِي مِنْ كُلِّ شَرٍّ. </p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِنِّي أَسْأَلُكَ الْهُدَى وَالتُّقَى وَالْعَفَافَ وَالْغِنَى. ">اللَّهُمَّ إِنِّي أَسْأَلُكَ الْهُدَى وَالتُّقَى وَالْعَفَافَ وَالْغِنَى. </p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْكَسَلِ وَالْهَرَمِ وَالْمَأْثَمِ وَالْمَغْرَمِ، وَمِنْ فِتْنَةِ الْقَبْرِ وَعَذَابِ الْقَبْرِ، وَمِنْ فِتْنَةِ النَّارِ وَعَذَابِ النَّارِ، وَمِنْ شَرِّ فِتْنَةِ الْغِنَى، وَأَعُوذُ بِكَ مِنْ فِتْنَةِ الْفَقْرِ، وَأَعُوذُ بِكَ مِنْ فِتْنَةِ الْمَسِيحِ الدَّجَّالِ، اللَّهُمَّ اغْسِلْ عَنِّي خَطَايَايَ بِمَاءِ الثَّلْجِ وَالْبَرَدِ، وَنَقِّ قَلْبِي مِنَ الْخَطَايَا كَمَا نَقَّيْتَ الثَّوْبَ الْأَبْيَضَ مِنَ الدَّنَسِ، وَبَاعِدْ بَيْنِي وَبَيْنَ خَطَايَايَ كَمَا بَاعَدْتَ بَيْنَ الْمَشْرِقِ وَالْمَغْرِبِ. ">اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْكَسَلِ وَالْهَرَمِ وَالْمَأْثَمِ وَالْمَغْرَمِ، وَمِنْ فِتْنَةِ الْقَبْرِ وَعَذَابِ الْقَبْرِ، وَمِنْ فِتْنَةِ النَّارِ وَعَذَابِ النَّارِ، وَمِنْ شَرِّ فِتْنَةِ الْغِنَى، وَأَعُوذُ بِكَ مِنْ فِتْنَةِ الْفَقْرِ، وَأَعُوذُ بِكَ مِنْ فِتْنَةِ الْمَسِيحِ الدَّجَّالِ، اللَّهُمَّ اغْسِلْ عَنِّي خَطَايَايَ بِمَاءِ الثَّلْجِ وَالْبَرَدِ، وَنَقِّ قَلْبِي مِنَ الْخَطَايَا كَمَا نَقَّيْتَ الثَّوْبَ الْأَبْيَضَ مِنَ الدَّنَسِ، وَبَاعِدْ بَيْنِي وَبَيْنَ خَطَايَايَ كَمَا بَاعَدْتَ بَيْنَ الْمَشْرِقِ وَالْمَغْرِبِ. </p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ يَا سَمِيعَ الدَّعَوَاتِ، يَا مُقِيلَ العَثَرَاتِ، يَاقَاضِيَ الحَاجَاتِ، يَا كَاشِفَ الكَرُبَاتِ، يَا رَفِيعَ الدَّرَجَاتِ، وَيَا غَافِرَ الزَّلاَّتِ، اغْفِرْ لِلْمُسْلِمِينَ وَالمُسْلِمَاتِ، وَالمُؤْمِنِينَ وَالمُؤْمِنَاتِ، الأحْيَاءِ مِنْهُم وَالأمْوَاتِ، إِنَّكَ سَمِيعٌ قَرِيبٌ مُجِيبُ الدَّعَوَاتِ.">اللَّهُمَّ يَا سَمِيعَ الدَّعَوَاتِ، يَا مُقِيلَ العَثَرَاتِ، يَاقَاضِيَ الحَاجَاتِ، يَا كَاشِفَ الكَرُبَاتِ، يَا رَفِيعَ الدَّرَجَاتِ، وَيَا غَافِرَ الزَّلاَّتِ، اغْفِرْ لِلْمُسْلِمِينَ وَالمُسْلِمَاتِ، وَالمُؤْمِنِينَ وَالمُؤْمِنَاتِ، الأحْيَاءِ مِنْهُم وَالأمْوَاتِ، إِنَّكَ سَمِيعٌ قَرِيبٌ مُجِيبُ الدَّعَوَاتِ.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ أَغْنِنِي بِالعِلْمِ، وَزَيِّنِّي بِالحِلْمِ، وَأَكْرِمْنِي بِالتَّقْوَى، وَجَمِّلْنِي بِالعَافِيَةِ.">اللَّهُمَّ أَغْنِنِي بِالعِلْمِ، وَزَيِّنِّي بِالحِلْمِ، وَأَكْرِمْنِي بِالتَّقْوَى، وَجَمِّلْنِي بِالعَافِيَةِ.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِنِّي عَبْدُكَ ابْنُ عَبْدِكَ ابْنُ أَمَتِكَ، نَاصِيَتِي بِيَدِكَ، مَاضٍ فِيَّ حُكْمُكَ، عَدْلٌ فِيَّ قَضَاؤكَ، أَسْأَلُكَ بِكُلِّ اسْمٍ هُوَ لَكَ، سَمَّيتَ بِهِ نَفْسَكَ، أَوْ أَنْزَلْتَهُ فِي كِتَابِكَ، أَوْ عَلَّمْتَهُ أَحَداً مِنْ خَلْقِكَ، أَوْ اسْتَأْثَرْتَ بِهِ فِي عِلْمِ الغَيبِ عِنْدَكَ، أَنْ تَجْعَلَ القُرْآنَ رَبِيعَ قَلْبِي، وَنُورَ صَدْرِي، وَجَلاءَ حَزَنِي، وَذَهَابَ هَمِّي.">اللَّهُمَّ إِنِّي عَبْدُكَ ابْنُ عَبْدِكَ ابْنُ أَمَتِكَ، نَاصِيَتِي بِيَدِكَ، مَاضٍ فِيَّ حُكْمُكَ، عَدْلٌ فِيَّ قَضَاؤكَ، أَسْأَلُكَ بِكُلِّ اسْمٍ هُوَ لَكَ، سَمَّيتَ بِهِ نَفْسَكَ، أَوْ أَنْزَلْتَهُ فِي كِتَابِكَ، أَوْ عَلَّمْتَهُ أَحَداً مِنْ خَلْقِكَ، أَوْ اسْتَأْثَرْتَ بِهِ فِي عِلْمِ الغَيبِ عِنْدَكَ، أَنْ تَجْعَلَ القُرْآنَ رَبِيعَ قَلْبِي، وَنُورَ صَدْرِي، وَجَلاءَ حَزَنِي، وَذَهَابَ هَمِّي.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ رَبَّنَا أَتْمِمْ لَنَا نُورَنَا وَاغْفِرْ لَنَا إِنَّكَ عَلَى كُلّ شَيءٍ قَدِيرٌ.">اللَّهُمَّ رَبَّنَا أَتْمِمْ لَنَا نُورَنَا وَاغْفِرْ لَنَا إِنَّكَ عَلَى كُلّ شَيءٍ قَدِيرٌ.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ رَبَّ السَّمَوَاتِ وَرَبَّ الْأَرْضِ وَرَبَّ الْعَرْشِ الْعَظِيمِ، رَبَّنَا وَرَبَّ كُلِّ شَيْءٍ، فَالِقَ الْحَبِّ وَالنَّوَى وَمُنْزِلَ التَّوْرَاةِ وَالْإِنْجِيلِ وَالْفُرْقَانِ، أَعُوذُ بِكَ مِنْ شَرِّ كُلِّ شَيْءٍ أَنْتَ آخِذٌ بِنَاصِيَتهِِ، اللَّهُمَّ أَنْتَ الْأوََّلُ فَلَيْسَ قَبْلَكَ شَيْءٌ، وَأَنْتَ الْآخِرُ فَلَيْسَ بَعْدَكَ شَيْءٌ، وَأَنْتَ الظَّاهِرُ فَلَيْسَ فَوْقَكَ شَيْءٌ، وَأَنْتَ الْبَاطِنُ فَلَيْسَ دُونَكَ شَيْءٌ، اقْضِ عَنَّا الدَّيْنَ وَأَغْنِنَا مِنَ الْفَقْرِ. ">اللَّهُمَّ رَبَّ السَّمَوَاتِ وَرَبَّ الْأَرْضِ وَرَبَّ الْعَرْشِ الْعَظِيمِ، رَبَّنَا وَرَبَّ كُلِّ شَيْءٍ، فَالِقَ الْحَبِّ وَالنَّوَى وَمُنْزِلَ التَّوْرَاةِ وَالْإِنْجِيلِ وَالْفُرْقَانِ، أَعُوذُ بِكَ مِنْ شَرِّ كُلِّ شَيْءٍ أَنْتَ آخِذٌ بِنَاصِيَتهِِ، اللَّهُمَّ أَنْتَ الْأوََّلُ فَلَيْسَ قَبْلَكَ شَيْءٌ، وَأَنْتَ الْآخِرُ فَلَيْسَ بَعْدَكَ شَيْءٌ، وَأَنْتَ الظَّاهِرُ فَلَيْسَ فَوْقَكَ شَيْءٌ، وَأَنْتَ الْبَاطِنُ فَلَيْسَ دُونَكَ شَيْءٌ، اقْضِ عَنَّا الدَّيْنَ وَأَغْنِنَا مِنَ الْفَقْرِ. </p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ ثَبِّتْنِي وَاجْعَلْنِي هَادِياً مَهْدِيّاً.">اللَّهُمَّ ثَبِّتْنِي وَاجْعَلْنِي هَادِياً مَهْدِيّاً.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِنِّي ظَلَمْتُ نَفْسِي ظُلْمًا كَثِيرًا، وَلَا يَغْفِرُ الذُّنُوبَ إِلَّا أَنْتَ، فَاغْفِرْ لِي مَغْفِرَةً مِنْ عِنْدِكَ وَارْحَمْنِي إِنَّك أَنْتَ الْغَفُورُ الرَّحِيمُ. ">اللَّهُمَّ إِنِّي ظَلَمْتُ نَفْسِي ظُلْمًا كَثِيرًا، وَلَا يَغْفِرُ الذُّنُوبَ إِلَّا أَنْتَ، فَاغْفِرْ لِي مَغْفِرَةً مِنْ عِنْدِكَ وَارْحَمْنِي إِنَّك أَنْتَ الْغَفُورُ الرَّحِيمُ. </p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ اغْفِرْ لِي ذَنْبِي، وَوَسِّعْ لِي فِي دَارِي، وَبَارِكْ لِي فِي رِزْقِي.">اللَّهُمَّ اغْفِرْ لِي ذَنْبِي، وَوَسِّعْ لِي فِي دَارِي، وَبَارِكْ لِي فِي رِزْقِي.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِلَهِي حُجَّتِي حَاجَتِي، وَعُدَّتِي فَاقَتِي، فَارْحَمْنِي.">اللَّهُمَّ إِلَهِي حُجَّتِي حَاجَتِي، وَعُدَّتِي فَاقَتِي، فَارْحَمْنِي.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ أَلْهِمْنِي رُشْدِي، وَأَعِذْنِي مِنْ شَرِّ نَفْسِي.">اللَّهُمَّ أَلْهِمْنِي رُشْدِي، وَأَعِذْنِي مِنْ شَرِّ نَفْسِي.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ رَبَّنَا لا تُؤَاخِذْنَا إِنْ نَسِينَا أَوْ أَخْطَأْنَا، رَبَّنَا وَلا تَحْمِلْ عَلَينَا إِصْرَاً كَمَا حَمَلْتَهَ عَلَى الَّذِينَ مِنْ قَبْلِنَا، رَبَّنَا وَلا تُحَمِّلْنَا مَا لا طَاقَةَ لَنَا بِهِ، وَاعْفُ عَنَّا وّاغْفِرْ لَنَا وَارْحَمْنَا أَنْتَ مَوْلانَا فَانْصُرْنَا عَلَى القَوْمِ الكَافِرِينَ.">اللَّهُمَّ رَبَّنَا لا تُؤَاخِذْنَا إِنْ نَسِينَا أَوْ أَخْطَأْنَا، رَبَّنَا وَلا تَحْمِلْ عَلَينَا إِصْرَاً كَمَا حَمَلْتَهَ عَلَى الَّذِينَ مِنْ قَبْلِنَا، رَبَّنَا وَلا تُحَمِّلْنَا مَا لا طَاقَةَ لَنَا بِهِ، وَاعْفُ عَنَّا وّاغْفِرْ لَنَا وَارْحَمْنَا أَنْتَ مَوْلانَا فَانْصُرْنَا عَلَى القَوْمِ الكَافِرِينَ.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ انْفَعْنِي بِمَا عَلَّمْتَنِي، وَعَلِّمْنِي مَا يَنْفَعُنِي، وَزِدْنِي عِلْماً.">اللَّهُمَّ انْفَعْنِي بِمَا عَلَّمْتَنِي، وَعَلِّمْنِي مَا يَنْفَعُنِي، وَزِدْنِي عِلْماً.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ مُصَرِّفَ القُلُوبِ صَرِّفْ قُلُوبَنَا عَلَى طَاعَتِكَ.">اللَّهُمَّ مُصَرِّفَ القُلُوبِ صَرِّفْ قُلُوبَنَا عَلَى طَاعَتِكَ.</p></div><div class="prayer-container"><p data-original-text="رَبِّ اغْفِرْ لِي خَطِيئَتِي وَجَهْلِي وَإِسْرَافِي فِي أَمْرِي كُلِّهِ وَمَا أَنْتَ أَعْلَمُ بِهِ مِنِّي، اللَّهُمَّ اغْفِرْ لِي خَطَايَايَ وَعَمْدِي وَجَهْلِي وَهَزْلِي، وَكُلُّ ذَلِكَ عِنْدِي، اللَّهُمَّ اغْفِرْ لِي مَا قَدَّمْتُ وَمَا أَخَّرْتُ وَمَا أَسْرَرْتُ وَمَا أَعْلَنْتُ أَنْتَ الْمُقَدِّمُ وَأَنْتَ الْمُؤَخِّرُ وَأَنْتَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ. ">رَبِّ اغْفِرْ لِي خَطِيئَتِي وَجَهْلِي وَإِسْرَافِي فِي أَمْرِي كُلِّهِ وَمَا أَنْتَ أَعْلَمُ بِهِ مِنِّي، اللَّهُمَّ اغْفِرْ لِي خَطَايَايَ وَعَمْدِي وَجَهْلِي وَهَزْلِي، وَكُلُّ ذَلِكَ عِنْدِي، اللَّهُمَّ اغْفِرْ لِي مَا قَدَّمْتُ وَمَا أَخَّرْتُ وَمَا أَسْرَرْتُ وَمَا أَعْلَنْتُ أَنْتَ الْمُقَدِّمُ وَأَنْتَ الْمُؤَخِّرُ وَأَنْتَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ. </p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ أَقِلْ عَثَرَاتِنَا، وَاغْفِرْ زَلاَّتِنَا، وَكَفِّرْ عَنَّا سَيِّئَاتِنَا، وَتَوَفَّنَا مَعَ الأَبْرَارِ.">اللَّهُمَّ أَقِلْ عَثَرَاتِنَا، وَاغْفِرْ زَلاَّتِنَا، وَكَفِّرْ عَنَّا سَيِّئَاتِنَا، وَتَوَفَّنَا مَعَ الأَبْرَارِ.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِنَّ ذُنُوبِي عِظَامٌ وَهِي صِغَارٌ فِي جَنْبِ عَفْوِكَ يَا كَرِيمُ، فَاغْفِرْهَا لِي.">اللَّهُمَّ إِنَّ ذُنُوبِي عِظَامٌ وَهِي صِغَارٌ فِي جَنْبِ عَفْوِكَ يَا كَرِيمُ، فَاغْفِرْهَا لِي.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ يَا بَارِئَ البَرِيَّاتِ، وَغَافِرَ الخَـطِيَّاتِ، وَعَالِمَ الخَفِيَّاتِ، المُطَّلِعُ عَلَى الضَّمَائِرِ وَالنِّيَّاتِ، يَا مَنْ أَحَاطَ بِكُلِّ شَيءٍ عِلْماً، وَوَسِعَ كُلّ شَيْءٍ رَحْمَةً، وَقَهَرَ كُلّ مَخْلُوقٍ عِزَّةً وَحُكْماً، اغْفِرْ لِي ذُنُوبِي، وَاسْتُرْ عُيُوبِيَ، وَتَجَاوَزْ عَنْ سَيِّئَاتِيَ إِنَّكَ أَنْتَ الْغَفُورُ الرَّحِيمُ.">اللَّهُمَّ يَا بَارِئَ البَرِيَّاتِ، وَغَافِرَ الخَـطِيَّاتِ، وَعَالِمَ الخَفِيَّاتِ، المُطَّلِعُ عَلَى الضَّمَائِرِ وَالنِّيَّاتِ، يَا مَنْ أَحَاطَ بِكُلِّ شَيءٍ عِلْماً، وَوَسِعَ كُلّ شَيْءٍ رَحْمَةً، وَقَهَرَ كُلّ مَخْلُوقٍ عِزَّةً وَحُكْماً، اغْفِرْ لِي ذُنُوبِي، وَاسْتُرْ عُيُوبِيَ، وَتَجَاوَزْ عَنْ سَيِّئَاتِيَ إِنَّكَ أَنْتَ الْغَفُورُ الرَّحِيمُ.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ عَالِمَ الْغَيْبِ وَالشَّهَادَةِ، فَاطِرَ السَّمَوَاتِ وَالْأَرْضِ، رَبَّ كُلِّ شَيْءٍ وَمَلِيكَهُ، أَشْهَدُ أَنْ لَا إِلَهَ إِلَّا أَنْتَ، أَعُوذُ بِكَ مِنْ شَرِّ نَفْسِي وَشَرِّ الشَّيْطَانِ وَشِرْكِهِ. ">اللَّهُمَّ عَالِمَ الْغَيْبِ وَالشَّهَادَةِ، فَاطِرَ السَّمَوَاتِ وَالْأَرْضِ، رَبَّ كُلِّ شَيْءٍ وَمَلِيكَهُ، أَشْهَدُ أَنْ لَا إِلَهَ إِلَّا أَنْتَ، أَعُوذُ بِكَ مِنْ شَرِّ نَفْسِي وَشَرِّ الشَّيْطَانِ وَشِرْكِهِ. </p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِلَهِي كَيْفَ أمْتَنِعُ بِالذَّنْبِ مِنَ الدُّعَاءِ، وَلا أَرَاكَ تَمْنَعُ مَعَ الذَّنْبِ مِنَ العَطَاءِ، فَإِنْ غَفَرْتَ فَخَيرُ رَاحِمٍ أَنْتَ، وَإِنْ عَذَّبْتَ فَغَيْرُ ظَالِمٍ أَنْتَ.">اللَّهُمَّ إِلَهِي كَيْفَ أمْتَنِعُ بِالذَّنْبِ مِنَ الدُّعَاءِ، وَلا أَرَاكَ تَمْنَعُ مَعَ الذَّنْبِ مِنَ العَطَاءِ، فَإِنْ غَفَرْتَ فَخَيرُ رَاحِمٍ أَنْتَ، وَإِنْ عَذَّبْتَ فَغَيْرُ ظَالِمٍ أَنْتَ.</p></div><div class="prayer-container"><p data-original-text="اللَّهُمَّ إِنِّي أَسْأَلُكَ مِنَ الْخَيْرِ كُلِّهِ عَاجِلِهِ وَآجِلِهِ مَا عَلِمْتُ مِنْهُ وَمَا لَمْ أَعْلَم،ْ وَأَعُوذُ بِكَ مِنَ الشَّرِّ كُلِّهِ عَاجِلِهِ وَآجِلِهِ مَا عَلِمْتُ مِنْهُ وَمَا لَمْ أَعْلَمْ، اللَّهُمَّ إِنِّي أَسْأَلُكَ مِنْ خَيْرِ مَا سَأَلَكَ عَبْدُكَ وَنَبِيُّكَ، وَأَعُوذُ بِكَ مِنْ شَرِّ مَا عَاذَ بِهِ عَبْدُكَ وَنَبِيُّكَ، اللَّهُمَّ إِنِّي أَسْأَلُكَ الْجَنَّةَ وَمَا قَرَّبَ إِلَيْهَا مِنْ قَوْلٍ أَوْ عَمَلٍ، وَأَعُوذُ بِكَ مِنَ النَّارِ وَمَا قَرَّبَ إِلَيْهَا مِ
