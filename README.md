<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>دليل الأمن السيبراني ومكافحة الاحتيال</title>
    <!-- استيراد خط عربي مميز -->
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cairo', sans-serif;
        }
        body {
            background-color: #0f172a;
            color: #f8fafc;
            line-height: 1.6;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }
        header {
            background: linear-gradient(135deg, #1e293b, #0f172a);
            border-bottom: 1px solid #334155;
            padding: 20px;
            text-align: center;
        }
        header h1 {
            color: #38bdf8;
            font-size: 1.8rem;
            margin-bottom: 5px;
        }
        header p {
            color: #94a3b8;
            font-size: 0.95rem;
        }
        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 0 15px;
            flex: 1;
            width: 100%;
        }
        .card {
            background-color: #1e293b;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
            border: 1px solid #334155;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }
        .card h2 {
            color: #38bdf8;
            font-size: 1.3rem;
            margin-bottom: 10px;
        }
        .tips-list {
            list-style: none;
        }
        .tips-list li {
            margin-bottom: 10px;
            padding-right: 20px;
            position: relative;
        }
        .tips-list li::before {
            content: "🛡️";
            position: absolute;
            right: 0;
            top: 0;
        }
        /* تصميم الشات بوت */
        .chat-box {
            display: flex;
            flex-direction: column;
            height: 350px;
            background: #0f172a;
            border-radius: 8px;
            border: 1px solid #334155;
            overflow: hidden;
        }
        .chat-messages {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .message {
            max-width: 80%;
            padding: 10px 14px;
            border-radius: 8px;
            font-size: 0.9rem;
            word-wrap: break-word;
        }
        .message.bot {
            background-color: #1e293b;
            color: #f8fafc;
            align-self: flex-start;
            border-right: 3px solid #38bdf8;
        }
        .message.user {
            background-color: #0284c7;
            color: #fff;
            align-self: flex-end;
        }
        .chat-input-area {
            display: flex;
            border-top: 1px solid #334155;
            background: #1e293b;
            padding: 10px;
        }
        .chat-input-area input {
            flex: 1;
            background: #0f172a;
            border: 1px solid #334155;
            border-radius: 6px;
            padding: 10px;
            color: #fff;
            outline: none;
            font-size: 0.9rem;
        }
        .chat-input-area input:focus {
            border-color: #38bdf8;
        }
        .chat-input-area button {
            background-color: #0284c7;
            color: #white;
            border: none;
            border-radius: 6px;
            padding: 0 20px;
            margin-right: 10px;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.2s;
        }
        .chat-input-area button:hover {
            background-color: #0369a1;
        }
        footer {
            text-align: center;
            padding: 20px;
            background-color: #1e293b;
            border-top: 1px solid #334155;
            font-size: 0.9rem;
            color: #94a3b8;
        }
        footer span {
            color: #38bdf8;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <header>
        <h1>دليل الأمن السيبراني للطلاب</h1>
        <p>احمِ نفسك، بياناتك، وحساباتك من الهجمات الاحتيالية بطريقة ذكية</p>
    </header>

    <div class="container">
        <!-- قسم نصائح سريعة -->
        <div class="card">
            <h2>🚨 علامات تحذيرية تدل على وجود احتيال</h2>
            <ul class="tips-list">
                <li>الروابط الوهمية التي تحتوي على أحرف زائدة أو أخطاء إملائية طفيفة (مثل g00gle بدل google).</li>
                <li>الرسائل التي تطلب منك تحديث بياناتك المصرفية أو الشخصية بشكل عاجل.</li>
                <li>الوعود بمكافآت مالية ضخمة أو جوائز وهمية مقابل النقر على رابط مجهول.</li>
            </ul>
        </div>

        <!-- قسم المساعد الذكي -->
        <div class="card">
            <h2>💬 المساعد الذكي للأمان السيبراني</h2>
            <p style="font-size: 0.85rem; color: #94a3b8; margin-bottom: 10px;">اسأل المساعد عن أي استفسار يخص حماية الحسابات والروابط المشبوهة:</p>
            
            <div class="chat-box">
                <div class="chat-messages" id="chatMessages">
                    <div class="message bot">أهلاً بك! أنا مساعدك الأمني. كيف يمكنني مساعدتك في حماية حساباتك اليوم؟ (ملاحظة: أجيب فقط على أسئلة الأمن السيبراني وتجنب الاحتيال).</div>
                </div>
                <div class="chat-input-area">
                    <input type="text" id="userInput" placeholder="اكتب سؤالك هنا..." onkeypress="handleKeyPress(event)">
                    <button onclick="sendMessage()">إرسال</button>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>تم التصميم والتطوير بواسطة: <span>عبدالعزيز بن عبدالله بن حاكم الدويش</span></p>
        <p style="margin-top: 5px; font-size: 0.8rem;">لغة البرمجة: <span>HTML5, CSS3, JavaScript</span></p>
    </footer>

    <script>
        // محاكاة ذكية للمساعد (يمكنك لاحقاً ربطه بـ API حقيقي للذكاء الاصطناعي)
        function sendMessage() {
            const inputField = document.getElementById('userInput');
            const messageText = inputField.value.trim();
            if (!messageText) return;

            // إضافة رسالة المستخدم
            appendMessage(messageText, 'user');
            inputField.value = '';

            // محاكاة الرد الذكي
            setTimeout(() => {
                const botReply = generateSmartReply(messageText);
                appendMessage(botReply, 'bot');
            }, 600);
        }

        function handleKeyPress(event) {
            if (event.key === 'Enter') {
                sendMessage();
            }
        }

        function appendMessage(text, sender) {
            const chatMessages = document.getElementById('chatMessages');
            const messageDiv = document.createElement('div');
            messageDiv.className = `message ${sender}`;
            messageDiv.textContent = text;
            chatMessages.appendChild(messageDiv);
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }

        function generateSmartReply(question) {
            const q = question.toLowerCase();
            
            // فلترة المواضيع غير الأمنية
            if (q.includes('كورسات') || q.includes('لعب') || q.includes('رياضة') || q.includes('طبخ') || q.includes('شعر') || q.includes('فلوه')) {
                return "عذراً، اختصاصي يقتصر حصرياً على الأمن السيبراني، حماية الحسابات، وتجنب الاحتيال الإلكتروني. هل لديك استفسار يخص هذا المجال؟";
            }

            // ردود أمنية ذكية
            if (q.includes('رابط') || q.includes('موقع') || q.includes('كيف اعرف')) {
                return "لكشف الرابط الاحتيالي: تأكد دائماً من اسم النطاق (Domain) بدقة، وتجنب الضغط على الروابط المختصرة المجهولة أو التي ترسل عبر رسائل نصية وهمية.";
            } else if (q.includes('كلمة مرور') || q.includes('باسورد') || q.includes('سرية')) {
                return "أنصحك باستخدام كلمات مرور قوية تتكون من رموز وأرقام وحروف كبيرة وصغيرة، مع تفعيل خاصية التحقق بخطوتين (2FA) على جميع حساباتك.";
            } else if (q.includes('اختراق') || q.includes('انسرق') || q.includes('تهكير')) {
                return "إذا شعرت أن حسابك تعرض للاختراق، قم فوراً بتغيير كلمة المرور، تسجيل الخروج من جميع الأجهزة النشطة، ومراجعة البريد المرتبط بالحساب.";
            } else {
                return "سؤال مهم! احرص دائماً على عدم مشاركة معلوماتك الشخصية أو رموز التحقق (OTP) مع أي شخص، حتى لو ادعى أنه من جهة رسمية.";
            }
        }
    </script>
</body>
</html>
