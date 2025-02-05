<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, user-scalable=no">
    <title>8 חודשים יחד ❤️</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        body {
            font-family: Arial, sans-serif;
            background-color: #ffe4e1;
            direction: rtl;
        }
        .container {
            margin: 0 auto;
            padding: 20px;
            max-width: 600px;
            background: white;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            text-align: right;
            margin-top: 50px;
            margin-bottom: 50px;
            opacity: 0;
            animation: fadein 2s forwards;
        }
        @keyframes fadein {
            to {
                opacity: 1;
            }
        }
        h1, h2 {
            text-align: center;
        }
        p {
            margin: 10px 0;
        }
        button {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            background-color: #ff4d6d;
            color: white;
            font-size: 16px;
            cursor: pointer;
            margin-top: 20px;
            transition: transform 0.3s ease;
        }
        button:hover {
            background-color: #d63a56;
            transform: scale(1.1) rotate(-2deg);
        }
        .section {
            padding: 15px;
            border: 1px solid #ffccd5;
            border-radius: 5px;
            margin: 20px 0;
            transition: transform 0.3s ease;
        }
        .section:hover {
            transform: scale(1.02);
        }
        .hidden {
            display: none;
            margin-top: 15px;
        }
        .reveal {
            display: block !important;
        }
        .gallery {
            display: flex;
            overflow-x: auto;
            gap: 10px;
            scroll-snap-type: x mandatory;
            padding: 10px 0;
        }
        .gallery-item {
            flex: 0 0 auto;
            width: 150px;
            height: 200px;
            border-radius: 10px;
            background-size: cover;
            background-position: center;
            scroll-snap-align: center;
            transition: transform 0.3s ease;
        }
        .gallery-item:hover {
            transform: scale(1.1) rotate(3deg);
        }
        .countdown {
            font-size: 18px;
            font-weight: bold;
            margin-top: 10px;
            color: #ff4d6d;
            text-align: center;
        }
        .correctAnswer {
            color: green;
            font-weight: bold;
        }
        #memoryResult {
            margin-top: 10px;
            font-weight: bold;
        }
        .progress-bar {
            width: 100%;
            background-color: #ffccd5;
            height: 10px;
            border-radius: 5px;
            overflow: hidden;
            margin-bottom: 10px;
        }
        .progress-fill {
            background-color: #ff4d6d;
            height: 100%;
            width: 0;
            transition: width 0.3s ease;
        }
        @media (max-width: 600px) {
            .container {
                margin: 20px;
                width: auto;
                max-width: 100%;
            }
            .gallery-item {
                width: 40vw;
                height: calc(40vw * 1.333);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🎉 8 חודשים ! 🎉</h1>
        <p>ברוכה הבאה לאתר הסודי שלך! כאן תמצאי כמה הפתעות שיגרמו לך לחייך. תהני! ❤</p>
        <div class="section">
            <h2>1. שיר אישי שמבוצע עבורך על ידי AI 🎵</h2>
            <p>לחצי על הכפתור כדי לחשוף קישור לשיר שנכתב במיוחד עבורך.</p>
            <button onclick="showSongContainer()">גילוי השיר</button>
            <div id="songContainer" class="hidden">
                <div style="text-align:center; margin-top:15px;">
                    
                    <video controls style="width:100%;">
                        <source src="https://drive.usercontent.google.com/u/0/uc?id=1MVewf0v7pTvS5F3bMnWQA1W-jIx1293_&export=download" type="video/mp4">
                    </video>
                </div>
            </div>
        </div>
        <div class="section">
            <h2>2. אלבום קיצי של שנינו 📸</h2>
            <div class="gallery" id="nostalgiaGallery">
                <div class="gallery-item" style="background-image: url('https://picsum.photos/300/400?random=11');"></div>
                <div class="gallery-item" style="background-image: url('https://picsum.photos/300/400?random=12');"></div>
                <div class="gallery-item" style="background-image: url('https://picsum.photos/300/400?random=13');"></div>
                <div class="gallery-item" style="background-image: url('https://picsum.photos/300/400?random=14');"></div>
                <div class="gallery-item" style="background-image: url('https://picsum.photos/300/400?random=15');"></div>
                <div class="gallery-item" style="background-image: url('https://picsum.photos/300/400?random=16');"></div>
                <div class="gallery-item" style="background-image: url('https://picsum.photos/300/400?random=17');"></div>
                <div class="gallery-item" style="background-image: url('https://picsum.photos/300/400?random=18');"></div>
            </div>
        </div>
        <div class="section">
            <h2>3. משפטים שהצאט חושב שמצחיקים 😂</h2>
            <p>לחצי על הכפתור כדי לקבל משפט מצחיק (אולי) רנדומלי:</p>
            <button onclick="showFunnyLine()">הצג משפט מצחיק</button>
            <div id="funnyLine" class="hidden"></div>
        </div>
        <div class="section">
            <h2>4. משחק בקטנה – "האם את זוכרת את זה?" 🎮</h2>
            <div class="progress-bar"><div class="progress-fill" id="progressFill"></div></div>
            <p id="progressIndicator"></p>
            <p id="gameQuestion"><strong></strong></p>
            <div id="gameOptions"></div>
            <button id="checkAnswerBtn" onclick="checkMemory()" class="hidden">בדיקה</button>
            <button id="nextQuestionBtn" onclick="nextQuestion()" class="hidden">שאלה הבאה</button>
            <div id="memoryResult" class="hidden"></div>
        </div>
        <div class="section">
            <h2>5. פתק סודי שייפתח רק אחרי X זמן ⏳</h2>
            <p>ברגע שתתחילי את הטיימר, תצטרכי להמתין קצת עד שתוכלי לפתוח את ההודעה הסודית.</p>
            <button id="startTimerBtn" onclick="startTimer()">התחילי טיימר</button>
            <div id="timerInfo" class="countdown hidden"></div>
            <button id="secretNoteBtn" class="hidden" disabled onclick="showSecretNote()">פתחי את הפתק</button>
            <div id="secretNote" class="hidden">
                <p><em>ששש... זה סוד! אם את קוראת את זה, סימן שעבר מספיק זמן ויש לך סבלנות (או כישורי האקרית). אני מתגעגע אלייך כל יום! אוהב המון! ❤</em></p>
            </div>
        </div>
    </div>
    <script>
        function showSongContainer() {
            document.getElementById('songContainer').classList.add('reveal');
        }
        function showFunnyLine() {
            const lines = [
    "כשאני אומר 'עוד דקה ואני יוצא' – אני מתכוון לאותה דקה שפיזיקאים עדיין לא גילו.",
    "ניסיתי לספור קלוריות, אבל הן תמיד התחבאו במקומות שאי אפשר למצוא.",
    "כל בוקר אני חושב איך לכתוב ספר: '101 תירוצים למה אני עדיין במיטה'.",
    "רציתי להיכנס לכושר, אבל נראה שהכושר ברח למקום אחר.",
    "אל תדאגי, אני בחיטוב… של פיצה!",
    "אם הבנאדם שמכר לי שעון-מעורר היה חכם, הוא היה מוכר לי גם פטיש.",
    "מה הקטע עם צ'יפס – הוא לעולם לא שואל אם בא לי עליו, הוא פשוט קורה.",
    "תמיד אומרים לי: 'תהיה אתה'. אבל אני עדיין מנסה להבין מי זה אני.",
    "אם הייתי יכול לאכול את העוגה ולהשאיר אותה שלמה… זה היה חוסך לי הרבה רגשות אשמה.",
    "הכי קשה בשגרת בוקר זה להודות שהיא בכלל התחילה.",
    "כשהזמנתי סלט במסעדה, המלצר שאל אותי אם אני בסדר או שאני צריך חיבוק.",
    "רק אחרי שפספסתי את האוטובוס הבנתי שהוא בכלל לא עבר.",
    "רציתי לגדל שרירים, אבל יצאו לי דווקא טורטיות.",
    "אני לא באמת רואה סדרות ברצף – הן פשוט לא משחררות אותי.",
    "הבעיה בתכנון קדימה – מגיע הרגע הזה שבו צריך לבצע.",
    "החלום שלי זה להיות עציץ: לקבל שמש, מים, ולהישאר במקום בלי לזוז.",
    "החלטתי לעשות מדיטציה – נרדמתי באמצע. לא יודע אם זה הצלחה או כישלון.",
    "ניסיתי לשמור על דיאטה, אבל המקרר אמר: 'יש בורקס, בוא תבדוק מקרוב…'",
    "לפעמים אני תוהה אם הקפה זקוק לי יותר מאשר אני זקוק לו.",
    "אני תמיד במצב 'סוללה נמוכה' – רק מחכה לטעינה שלא מגיעה.",
    "מכירים את התחושה שאתם מגיעים לחדר ושוכחים מה רציתם? אז אני ככה בכל חדר.",
    "הרגע שבו אתה מבין שאתה מבוגר: כשחבילה של גומיות מתרגשת אותך.",
    "סוף שבוע הוא תקופה נהדרת, חבל שהוא עובר במהירות של הודעת ווטסאפ.",
    "הצבתי לעצמי יעד: לשתות יותר מים. בינתיים הצלחתי להוסיף קוביית קרח בקולה.",
    "ביקשו ממני לתת פידבק על המציאות. אמרתי: 'צריכה עדכון דחוף!'",
    "פעם רציתי להיות מינימליסט, אבל יש לי יותר מדי דברים חשובים.",
    "כל שבוע אני לומד מילה חדשה באנגלית, אבל שוכח איך אומרים 'מילה' בעברית.",
    "אני לא עצלן, אני באנרגיית חיסכון מתמשכת.",
    "כשניסיתי לפתוח עסק עצמאי, גיליתי שלאנשים אין הרבה ביקוש ל'ישיבות נמנום'.",
    "המצב הנוכחי של חשבון הבנק שלי מזכיר לי שאני פשוט גאון בלחיות על הקצה.",
    "אני במערכת יחסים ארוכה עם השעון המעורר שלי – הוא מצלצל, אני מתעלם, והוא לא מוותר.",
    "ניסיתי להתעמל הבוקר אז עשיתי מתיחות – יד אחת לקפה, יד שנייה לטלפון.",
    "אמרו לי להיות חיובי אז אני חיובי שהולך להיות לי יום ארוך.",
    "החורף הגיע זה הזמן להתחיל להסתתר מתחת לשמיכות כמו מקצוען.",
    "ניסיתי לאכול בריא אבל אז הקינוח קרץ לי ואמר תן לי צ'אנס!",
    "כל בוקר אני עושה החלטה חשובה – לקום או להמשיך לתרגל את השינה.",
    "התחלתי דיאטה אתמול אבל היא ביקשה להישאר בקשר מרחוק.",
    "אם כסף לא קונה אושר איך זה שבפיצה יש כל כך הרבה משמעות בחיים?",
    "ניסיתי להיות בן אדם בוגר אבל אז הבנתי שזה דורש יותר מדי אחריות.",
    "מבחינתי כושר זה לקום מהספה בלי לעשות קולות של קשיש.",
    "כל בוקר זה מרגיש כמו קרב בין אני שרוצה לישון ואני שצריך לקום.",
    "לפעמים אני מתלבט אם לשתות עוד קפה ואז הקפה עונה לי ברור שכן!",
    "להיות מבוגר זה להבין ששליח של אוכל זה החבר הכי קרוב שלך.",
    "הבנתי שאני מבוגר כשחשבתי ששואב אבק רובוטי זה מתנה מרגשת.",
    "ניסיתי לחסוך כסף אבל אז מצאתי את עצמי עם עוד משלוח מהאינטרנט.",
    "כשאני אומר אני בדרך אני מתכוון בדרך לעוד עשר דקות של בהייה בקיר.",
    "אמרו לי לחיות את הרגע אז אני יושב ומחכה שיעבור לבד.",
    "כל פעם שאני פותח את האימייל בעבודה אני מרגיש כמו אינדיאנה ג'ונס שפותח ארון מקולל.",
    "אני לא מבין איך בגדים מלוכלכים מצליחים להתרבות מהר יותר ממה שאני מספיק לכבס.",
    "התחייבתי לעשות הליכה יומית ואז גיליתי שחציית הסלון למקרר זה מספיק.",
    "כל בוקר אני מרגיש כמו אפליקציה שלא נטענת כמו שצריך.",
    "יש לי יחסים מסובכים עם האינטרנט – הוא מבטיח עבודה ואני מבטיח שאני עובד.",
    "אני לא יודע מי החליט ששמונה בבוקר זה שעה טובה להתחיל את היום אבל הוא בטח לא היה אנושי.",
    "העבודה שלי מרגישה כמו ריצה על הליכון – אני כל הזמן זז אבל לא מתקדם לשום מקום.",
    "התכוונתי לעשות ספורט אבל אז מצאתי תוכנית טלוויזיה חדשה נחשו מי ניצחה.",
    "ניסיתי לא לשתות קפה יום אחד החלטתי שזה היה ניסוי כושל.",
    "אני לא מתעצל אני פשוט שומר אנרגיה ליום שיהיה לי כוח להשתמש בה.",
    "אנשים אומרים לי תשקיע בעצמך אז קניתי לעצמי עוד חטיף.",
    "דיאטה זה כמו יחסים מסובכים – אני מנסה היא שוברת לי את הלב.",
    "רשימת המשימות שלי מחכה שאעשה משהו אבל גם אני מחכה למוטיבציה שלא מגיעה.",
    "כל בוקר אני בודק אם יש לי אנרגיה להתחיל את היום התשובה תמיד זהה לא.",
    "התכוונתי לעשות סדר בבית אבל במקום זה ישבתי וחשבתי איך הייתי עושה את זה אם היה לי כוח.",
    "מישהו אמר לי החיים קצרים אז אכלתי עוד פרוסת עוגה ליתר ביטחון.",
    "אני לא דוחה דברים – אני פשוט נותן להם זמן להבשיל.",
    "הלכתי לקנות מצרכים בריאים חזרתי עם חטיפים וגלידה.",
    "הדבר היחיד שעומד בין לבין כושר זה אני.",
    "בבוקר אני חצי בן אדם חצי פינגווין שמנסה לזחול למקלחת.",
    "החיים שלי הם כמו טלפון ישן – לפעמים הכל עובד אבל רוב הזמן צריך להטעין מחדש.",
    "אמרו לי שדברים טובים מגיעים לאלה שמחכים אבל המשלוח עדיין לא הגיע.",
    "אני מתכנן להתעורר מוקדם כל לילה ובכל בוקר מתכנן חזרה לישון.",
    "ניסיתי לחשוב על משהו חכם להגיד אבל המוח שלי פתח חלון חדש ונתקע.",
    "כשהייתי קטן חשבתי שכשאהיה גדול אבין הכל. עכשיו אני פשוט מבולבל יותר.",
    "תכננתי יום פרודוקטיבי אבל אז נזכרתי שיש סדרה חדשה בנטפליקס.",
    "אני לא מבזבז זמן – אני פשוט נותן לו ללכת בכיף שלו.",
    "קניתי שעון מעורר חזק בסוף אני סתם שונא את הבוקר יותר מתמיד.",
    "ניסיתי לצאת מוקדם מהבית אבל הכרית החזיקה אותי כבת ערובה.",
    "המקרר שלי הוא כמו חבר טוב – תמיד שם בשבילי בעיקר בלילה.",
    "שאלו אותי למה אני שותה כל כך הרבה קפה אמרתי שזה או זה או לישון בעבודה.",
    "אני מחכה לרגע שבו לישון מוקדם יתחיל לקרות באמת.",
    "רציתי לנקות את הבית אז הדלקתי נר ריחני וחשבתי שזה מספיק.",
    "להיות מבוגר זה להבין שארוחת ערב יכולה להיות קורנפלקס ולאף אחד לא אכפת.",
    "אני לא מבזבז כסף – אני פשוט עושה השקעות עתידיות בחוויות אוכל.",
    "כל שבוע אני מבטיח לעצמי שאהיה מסודר ואז נזכר שאני אני.",
    "כל שנה אני אומר השנה אני אהיה מסודר ואז ממשיך לדחות את זה לשנה הבאה.",
    "החיים הם מסע אז למה אני מרגיש שאני פשוט מחכה בתחנה?",
    "אני לא מאחר אני פשוט חי בזמן משלו.",
    "אם לקפה היה רגשות הוא בטח היה מתלונן על כמה שאני תלוי בו.",
    "אני אוהב לעשות תכניות גדולות ואז לגלות שאין לי כוח לבצע אותן.",
    "אם לנמנום היה מקצוע הייתי מקבל קידום כל שבוע.",
    "אין כמו התחושה של למצוא שטר כסף בכיס ואז לזכור שהוא היה שלך מלכתחילה.",
    "יש לי משימות חשובות לעשות אז אני כמובן מתמקד בבהייה במסך.",
    "כל בוקר אני מחפש את הכפתור של דלג על היום הזה.",
    "אני לא עצלן אני פשוט שומר כוחות למשהו חשוב שעדיין לא קרה.",
    "אני מבטיח לעצמי שאתחיל מחר אבל אף פעם לא מגדיר איזה תאריך זה מחר.",
    "אני רק אגיד שאני פותח יוטיוב לכמה דקות ואיכשהו נגמר היום.",
    "אם היה תואר בדחיינות הייתי לוקח קורסים בשנה הבאה.",
    "אמרו לי שצריך להיות חכמים עם הכסף אז אני חכם בזה שאני לא בודק את היתרה.",
    "התכנון שלי הוא לא לתכנן כלום וזה עובד מצוין.",
    "פעם הייתי ילד עם חלומות היום אני מבוגר עם נמנומים.",
    "אם הייתי מקבל שקל על כל פעם שדחיתי משהו הייתי דוחה גם את ההשקעה שלי.",
    "אני לא שונא בקרים אני פשוט לא מבין למה הם צריכים להתחיל כל כך מוקדם.",
    "פעם חשבתי שלהיות מבוגר זה מגניב עכשיו אני מבין שזה פשוט אומר לעשות כביסות כל הזמן.",
    "אני לא מאחר אני פשוט נותן לזמן לזרום בקצב שלו.",
    "הלכתי לרופא הוא אמר לי להיות יותר פעיל אז התחלתי להפעיל יותר סדרות בנטפליקס.",
    "אני לא בטלן אני פשוט חוקר את האמנות של לא לעשות כלום.",
    "ניסיתי להתעמל אבל אז נזכרתי שזה דורש תנועה וזה פשוט לא מתאים לי.",
    "לפעמים אני נכנס למטבח ושואל את עצמי – באתי לשתות מים או לנשנש משהו תמיד בוחר באפשרות השנייה.",
    "אני לא דוחה דברים אני פשוט נותן להם מרחב נשימה.",
    "כשראיתי סרטון על אנשים שמתעוררים ב-5 בבוקר כדי לרוץ נזכרתי כמה טוב לישון.",
    "פעם הייתי מנסה לתקן דברים עכשיו אני פשוט מחכה שהם יתקנו את עצמם.",
    "אני לא עצלן אני פשוט בפנסיה מוקדמת של החיים.",
    "אם היה ספורט אולימפי בדחיינות הייתי מתאמן מחר.",
    "הבוקר שלי מתחיל עם קפה ואז עוד קפה ואז עוד אחד ואז אולי מתחיל משהו.",
    "ניסיתי לעשות יוגה אבל במקום זה נרדמתי על המזרן.",
    "חשבתי להתחיל ריצה בסוף רדפתי אחרי שליח של אוכל וזה גם נחשב.",
    "מישהו שאל אותי מה הכישרון שלי עניתי 'למצוא תירוצים לכל דבר.'",
    "אם קניות באינטרנט היה מקצוע כבר הייתי מנכל.",
    "ניסיתי לתכנן שבוע מראש הגעתי ליום שני והתייאשתי.",
    "העבודה שלי דורשת ריכוז אז אני רואה סרטונים של חתולים כדי להירגע.",
    "קניתי רהיטים להרכבה עצמית גיליתי שזה פשוט חידה עם בורג מיותר בסוף.",
    "כל בוקר אני מחליט להיות פרודוקטיבי ואז מחכה ללילה כדי לעשות הכל בלחץ.",
    "חשבון הבנק שלי כל כך ריק שאפילו הג'וקים בורחים ממנו.",
    "אני לא יכול להתחיל את היום בלי קפה ולפעמים גם בלי עוד שעת שינה.",
    "אם היה תואר בבהייה בקיר הייתי מסיים אותו בהצטיינות.",
    "ניסיתי ללכת לישון מוקדם וביליתי שלוש שעות בסרטונים ביוטיוב.",
    "אני לא שונא חורף אני פשוט מעדיף לא לקום מהמיטה.",
    "הבוקר שלי הוא כמו מחשב ישן לוקח לו שעה להידלק.",
    "חשבתי להתחיל לחסוך כסף ואז היה מבצע שדרש את תשומת ליבי.",
    "רציתי להיות מינימליסט אבל יש לי יותר מדי דברים שאני לא יכול לזרוק.",
    "אם הייתי יכול לישון ולהרוויח כסף כבר הייתי מיליונר.",
    "אמרו לי שכושר זה חשוב אז אני מחפש אפליקציה שתעשה את זה בשבילי.",
    "הלכתי לסופר כדי לקנות חלב חזרתי עם עוגיות גלידה וחוב חדש.",
    "אני לא יכול להתחיל את היום בלי לשאול את עצמי למה התעוררתי.",
    "כל פעם שאני עושה רשימת משימות אני מסיים עם עוד רשימה של דברים שלא עשיתי.",
    "אני לא יכול לשבת רגוע אלא אם כן זה על הספה עם שלט ביד.",
    "החיים שלי הם כמו סוללה בטלפון תמיד על אחוז נמוך.",
    "כל פעם שאני מחפש משהו בבית אני מוצא דברים שאיבדתי לפני שנים.",
    "הייתי מתחיל דיאטה אבל העוגיות לא נותנות לי לעזוב אותן.",
    "רציתי לקרוא ספר אבל אז גיליתי שנטפליקס קיימת.",
    "אני לא שונא בקרים הם פשוט באים בזמן הלא נכון.",
    "כשאני אומר אני לא רעב אני מתכוון אני לא רעב עדיין.",
    "יש לי מיליון דברים לעשות אז בחרתי לא לעשות אף אחד מהם.",
    "הבנתי שאני מבוגר כשחשבתי שכיסא נוח זה מתנה טובה.",
    "אני לא עייף אני פשוט במצב חיסכון באנרגיה.",
    "כל פעם שאני שומע את השעון המעורר שלי אני מרגיש שהוא צורח עליי בלי סיבה.",
    "תכננתי לנקות את הבית ואז מצאתי את עצמי עושה שום דבר.",
    "ניסיתי לנהל זמן אבל הוא ברח לי בלי שאשים לב.",
    "אני לא מכור לקפה הוא פשוט היחיד שמבין אותי בבוקר.",
    "ניסיתי להבין את מס הכנסה ויתרתי אחרי עשר דקות.",
    "אני לא יכול להתחיל את היום בלי לתהות למה קמתי בכלל.",
    "אמרו לי שאם אתאמן כל יום ארגיש טוב יותר אני מחכה שזה יקרה.",
    "אני לא מאחר אני פשוט נהנה מהזמן שלי קצת יותר מדי.",
    "ניסיתי לקרוא ספר אבל העיניים שלי העדיפו להיסגר.",
    "אני לא נרדם בעבודה אני פשוט בודק אם החלומות שלי פרודוקטיביים.",
    "לפעמים אני שואל את עצמי מה אני עושה עם החיים שלי ואז נרדם.",
    "אני לא מכור לסמארטפון הוא פשוט החבר הכי טוב שלי.",
    "הלוואי שהייתי יכול להטעין את עצמי כמו שאני טוען את הטלפון שלי.",
    "העבודה שלי גורמת לי להרגיש כמו רובוט רק בלי היכולת לעבוד בלי הפסקות.",
    "אני לא שונא אנשים אני פשוט מעדיף לא להיות לידם מוקדם בבוקר.",
    "כל פעם שאני חושב אני חייב להתחיל לחסוך אני מוצא משהו חדש לקנות.",
    "ניסיתי לעשות מדיטציה ואז התעוררתי שעתיים אחרי.",
    "אני לא אוהב לדבר בטלפון כי אז אני צריך לחשוב על מה להגיד.",
    "לפעמים אני תוהה אם אני הבוס של חיי ואז אני רואה את חשבון הבנק שלי ומבין שלא.",
    "אני לא עצלן אני פשוט אוהב לחכות לזמן הנכון שהוא אף פעם לא עכשיו.",
    "ניסיתי להפסיק עם קפה אבל הקפה לא הסכים להפסיק איתי.",
    "כל בוקר אני מתלבט אם לקום ואז החיים בוחרים בשבילי.",
    "אני לא סתם מבזבז זמן אני פשוט בודק כמה זמן אפשר לבזבז.",
    "אמרו לי תהיה אתה אבל אני עדיין מנסה להבין מי זה אני.",
    "כל פעם שאני חושב על לעשות משהו מועיל אני מוצא משהו פחות מועיל לעשות.",
    "אני לא מכור לקניות אני פשוט משקיע בעתיד של החנות.",
    "החיים שלי הם כמו רשימת מטלות מלאה אבל שום דבר לא מסומן.",
    "אם החיים היו משחק וידאו הייתי תקוע בלבל הראשון.",
    "אני לא דוחה דברים אני פשוט נותן להם את הכבוד הראוי להם.",
    "כל בוקר אני אומר לעצמי היום יהיה היום שלי ואז מחכה למחר.",
    "ניסיתי להפסיק לאכול מתוקים אבל הם לא הפסיקו לקרוץ לי.",
    "כשאני שואל את עצמי מה אני עושה עם החיים שלי אני בדרך כלל אוכל תוך כדי.",
    "אם הייתה תחרות בלדחות דברים הייתי נרשם מחר.",
    "אני לא סתם יושב פה בלי לעשות כלום אני עושה את זה בכוונה.",
    "כל פעם שאני מחליט זהו אני משתנה אני מחליט להתחיל ממחר.",
    "החיים הם מסע ואני כנראה מחכה לרכבת שתיקח אותי."
            ];
            const randomLine = lines[Math.floor(Math.random() * lines.length)];
            const funnyLineDiv = document.getElementById('funnyLine');
            funnyLineDiv.textContent = randomLine;
            funnyLineDiv.classList.add('reveal');
        }
        const questions = [
            {
                q: "לאיזה מקום נסענו בפעם הראשונה ביחד?",
                options: ["לוצ׳נה גיאה", "להקפה ליד הנחל", "לחוף דוגית"],
                correct: 1,
                correctMsg: "נכון! לא נשכח את הדורה המוזרה הזאת",
                wrongMsg: "כנראה התבלבלת... אולי הגיע הזמן לשידור חוזר?"
            },
            {
                q: "מה הייתה ההודעה הראשונה שלנו?",
                options: ["היי מה קורה?", "היי הילה מה המצב?", "היי הילה אני אלעד מה המצב?"],
                correct: 1,
                correctMsg: "את האמת אני 99% חושב שזה מה שרשמתי",
                wrongMsg: "אז את כרגיל זוכרת חחחחחחחח"
            },
            {
                q: "איפה אלעד הכי אוהב נעים?",
                options: ["חיי בסרט", "ברגל", "בראש"],
                correct: 0,
                correctMsg: "ידעתי שתבחרי את זה אבל בכל מקום 😂",
                wrongMsg: "תנסי שוב בסיבוב הבא"
            },
            {
                q: "מה אלעד הכי אוהב להביא להילה בעולם?",
                options: ["חיבוקים ונשיקות", "שוקולדים", "כל התשובות נכונות"],
                correct: 2,
                correctMsg: "רק שתחייכי זה הכי כיף לי בעולם",
                wrongMsg: "תשובה חלקית"
            },
            {
                q: "מה המקום שאלעד הכי אוהב באשקלון?",
                options: ["חוף חופית", "המרינה", "אגמים"],
                correct: 2,
                correctMsg: "תכלס זה מקום מטורף",
                wrongMsg: "גם את זה אני אוהב פשוט לא הכי"
            }
        ];
        let currentQuestionIndex = 0;
        const gameQuestion = document.getElementById("gameQuestion");
        const gameOptions = document.getElementById("gameOptions");
        const checkAnswerBtn = document.getElementById("checkAnswerBtn");
        const nextQuestionBtn = document.getElementById("nextQuestionBtn");
        const memoryResult = document.getElementById("memoryResult");
        const progressIndicator = document.getElementById("progressIndicator");
        const progressFill = document.getElementById("progressFill");
        loadQuestion();
        function loadQuestion() {
            if (currentQuestionIndex >= questions.length) {
                gameQuestion.innerHTML = "סיימת את כל השאלות!";
                gameOptions.innerHTML = "";
                checkAnswerBtn.classList.add("hidden");
                nextQuestionBtn.classList.add("hidden");
                memoryResult.textContent = "קיבלת 100 מעלפת שלי ";
                memoryResult.classList.add("reveal");
                memoryResult.style.color = "#ff4d6d";
                progressIndicator.textContent = "";
                progressFill.style.width = "100%";
                return;
            }
            let progressPercentage = (currentQuestionIndex / questions.length) * 100;
            progressFill.style.width = progressPercentage + "%";
            progressIndicator.textContent = "ענית על " + currentQuestionIndex + " מתוך " + questions.length;
            const currentQ = questions[currentQuestionIndex];
            gameQuestion.innerHTML = "<strong>" + currentQ.q + "</strong>";
            let optionsHTML = "";
            currentQ.options.forEach(function(opt, index){
                optionsHTML += "<label><input type='radio' name='gameOption' value='" + index + "'> " + opt + "</label><br>";
            });
            gameOptions.innerHTML = optionsHTML;
            memoryResult.classList.add("hidden");
            memoryResult.textContent = "";
            memoryResult.style.color = "#ff4d6d";
            checkAnswerBtn.classList.remove("hidden");
            nextQuestionBtn.classList.add("hidden");
        }
        function checkMemory() {
            const currentQ = questions[currentQuestionIndex];
            const selectedOption = document.querySelector("input[name='gameOption']:checked");
            if (!selectedOption) {
                memoryResult.textContent = "נא לבחור תשובה קודם!";
                memoryResult.classList.remove("hidden");
                memoryResult.style.color = "#ff4d6d";
                return;
            }
            const userAnswer = parseInt(selectedOption.value);
            const correctRadio = document.querySelector("input[name='gameOption'][value='" + currentQ.correct + "']");
            if(correctRadio) {
                correctRadio.parentElement.classList.add("correctAnswer");
            }
            if (userAnswer === currentQ.correct) {
                memoryResult.textContent = currentQ.correctMsg;
                memoryResult.style.color = "green";
            } else {
                memoryResult.textContent = currentQ.wrongMsg;
                memoryResult.style.color = "#ff4d6d";
            }
            memoryResult.classList.remove("hidden");
            checkAnswerBtn.classList.add("hidden");
            nextQuestionBtn.classList.remove("hidden");
        }
        function nextQuestion() {
            currentQuestionIndex++;
            loadQuestion();
        }
        let countdownInterval;
        function startTimer() {
            const startTimerBtn = document.getElementById("startTimerBtn");
            const timerInfo = document.getElementById("timerInfo");
            const secretNoteBtn = document.getElementById("secretNoteBtn");
            let timeLeft = 15;
            timerInfo.textContent = "הסוד ייפתח בעוד " + timeLeft + " שניות...";
            timerInfo.classList.remove("hidden");
            startTimerBtn.disabled = true;
            countdownInterval = setInterval(function(){
                timeLeft--;
                if(timeLeft > 0){
                    timerInfo.textContent = "הסוד ייפתח בעוד " + timeLeft + " שניות...";
                } else {
                    clearInterval(countdownInterval);
                    timerInfo.textContent = "הזמן עבר! אפשר לפתוח את הפתק.";
                    secretNoteBtn.disabled = false;
                    secretNoteBtn.classList.remove("hidden");
                }
            },1000);
        }
        function showSecretNote() {
            document.getElementById("secretNote").classList.add("reveal");
        }
    </script>
</body>
</html>
