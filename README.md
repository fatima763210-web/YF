<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مفاجأة لك يا أغلى الناس</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #d4a373; /* درجات البيج الدافئة */
            --secondary-color: #faedcd;
            --accent-color: #bc6c25;
            --text-color: #582f0e;
        }
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #fefae0;
            overflow-x: hidden;
            color: var(--text-color);
        }
        .heart-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        .heart {
            position: absolute;
            color: #dda15e;
            animation: float 6s infinite linear;
            opacity: 0;
        }
        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0.8; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }
        .fade-in {
            animation: fadeIn 2s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .hidden-section {
            display: none;
        }
        .glass-card {
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(212, 163, 115, 0.3);
            box-shadow: 0 20px 40px 0 rgba(188, 108, 37, 0.1);
        }
        .btn-love {
            background: linear-gradient(45deg, #bc6c25, #dda15e);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        .btn-love:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 12px 25px rgba(188, 108, 37, 0.3);
        }
        .image-container {
            border: 10px solid white;
            box-shadow: 0 15px 30px rgba(0,0,0,0.08);
            transition: transform 0.5s ease;
        }
        .image-container:hover {
            transform: rotate(3deg);
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen p-4">

    <!-- خلفية القلوب الدافئة -->
    <div class="heart-bg" id="heartContainer"></div>

    <!-- شاشة البداية -->
    <div id="startScreen" class="text-center z-10 fade-in">
        <div class="mb-6">
            <svg class="w-24 h-24 mx-auto text-[#bc6c25] animate-bounce" fill="currentColor" viewBox="0 0 20 20">
                <path d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"></path>
            </svg>
        </div>
        <h1 class="text-4xl font-bold mb-4 tracking-tight">رسالة مخبأة لك.. ✨</h1>
        <p class="text-[#606c38] mb-10 text-xl">عندي لك شي بمناسبة السنة الجديدة..</p>
        <button onclick="revealSurprise()" class="btn-love text-white px-12 py-5 rounded-2xl text-2xl font-bold shadow-xl">
            ابي أشوف 
        </button>
    </div>

    <!-- المحتوى الرئيسي للمفاجأة -->
    <div id="mainContent" class="hidden-section max-w-xl w-full z-10">
        <div class="glass-card rounded-[3rem] p-10 text-center fade-in">
            
            <!-- الصورة الجديدة المطلوبة -->
            <div class="relative w-64 h-64 mx-auto mb-10">
                <div class="absolute inset-0 bg-[#bc6c25] rounded-full animate-ping opacity-10"></div>
                <img src="https://i.pinimg.com/736x/ca/ae/8c/caae8c2c153a234b40cf0e4325b9bde6.jpg" 
                     alt="صورة حب دافئة من بينتيريست" 
                     class="image-container rounded-full w-full h-full object-cover relative z-10"
                     onerror="this.src='https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=500&auto=format&fit=crop'">
            </div>

            <h2 class="text-4xl font-bold text-[#283618] mb-6">كل عام وأنت معي يا نور عيوني</h2>
            
            <div class="space-y-6 text-[#606c38] text-xl leading-relaxed">
                <p>
                    ممتنه للسنة لأني طلعت بأكبر انجازاتي انت يا حياتي.
                </p>
                <div class="py-6 px-8 bg-[#fefae0] rounded-[2rem] border-r-8 border-[#bc6c25] italic shadow-inner">
                    " أعدك بأن يكون قلبي هو منزلك، وضحكتك هي وجهتي، وحبك هو أعظم إنجازاتي."
                </div>
                <p class="font-bold text-[#bc6c25]">
                     نبدأ عامنا الجديد بوعود حب لا تنتهي..
                </p>
            </div>

            <!-- زر التفاعل السري -->
            <div class="mt-12 flex flex-col gap-4">
                <button onclick="showLoveNote()" class="bg-[#dda15e] text-white px-8 py-4 rounded-2xl hover:bg-[#bc6c25] transition-all font-bold text-lg shadow-md">
                     رسالة سرية💌
                </button>
            </div>

            <!-- الرسالة السرية -->
            <div id="secretNote" class="hidden mt-8 p-6 bg-white bg-opacity-60 rounded-3xl text-[#582f0e] border-2 border-dashed border-[#d4a373] text-lg leading-relaxed animate-fade-in">
                لو كانت النجوم تُهدى.. لأهديتك السماء، ولو كان العمر يُهدى.. لسجلت أيامي باسمك. أحبك اليوم، وبكرا، وللأبد.
            </div>
        </div>
        
        <p class="text-center text-[#bc6c25] text-sm mt-10 font-medium opacity-80">صُنع بكل حب من أجلك لعام 2026</p>
    </div>

    <!-- مودال الوعد -->
    <div id="loveModal" class="fixed inset-0 bg-[#283618] bg-opacity-50 hidden flex items-center justify-center z-50 p-6 backdrop-blur-md">
        <div class="bg-white p-12 rounded-[3rem] max-w-sm w-full text-center shadow-2xl border-b-8 border-[#bc6c25]">
            <div class="text-6xl mb-4">💍</div>
            <h3 class="text-3xl font-bold text-[#bc6c25] mb-4">وعد السنة؟</h3>
            <p class="text-gray-600 mb-10 text-lg">هل تعدني أن نبقى معاً في كل ثانية من عام 2026 وما بعدها؟</p>
            <div class="flex flex-col gap-4">
                <button onclick="closeModal('يا بعدي كلي، تم الوعد! ❤️')" class="w-full bg-[#bc6c25] text-white py-4 rounded-2xl font-bold text-xl hover:shadow-2xl active:scale-95 transition-all">أوعدك يا عمري!</button>
                <button onclick="closeModal('أحبك فوق ما تتخيل! 🌹')" class="w-full bg-[#fefae0] text-[#bc6c25] py-4 rounded-2xl font-bold border border-[#faedcd]">أكيد يا أغلى من يملكني</button>
            </div>
            <p id="modalResponse" class="mt-8 text-[#bc6c25] font-bold hidden text-xl"></p>
        </div>
    </div>

    <script>
        function createHeart() {
            const container = document.getElementById('heartContainer');
            const heart = document.createElement('div');
            heart.classList.add('heart');
            const icons = ['❤️', '✨', '🧸', '🌸', '🤍'];
            heart.innerHTML = icons[Math.floor(Math.random() * icons.length)];
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
            heart.style.animationDuration = (Math.random() * 5 + 4) + 's';
            container.appendChild(heart);

            setTimeout(() => { heart.remove(); }, 6000);
        }

        function revealSurprise() {
            document.getElementById('startScreen').style.display = 'none';
            const main = document.getElementById('mainContent');
            main.classList.remove('hidden-section');
            main.classList.add('fade-in');
            
            // تسريع إنتاج القلوب قليلاً لجو احتفالي
            setInterval(createHeart, 350);

            // إظهار المودال بعد وقت أطول قليلاً ليقرأ الكلام
            setTimeout(() => {
                document.getElementById('loveModal').classList.remove('hidden');
            }, 8000);
        }

        function showLoveNote() {
            const note = document.getElementById('secretNote');
            note.classList.toggle('hidden');
            if(!note.classList.contains('hidden')) {
                window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
            }
        }

        function closeModal(msg) {
            const res = document.getElementById('modalResponse');
            res.innerText = msg;
            res.classList.remove('hidden');
            setTimeout(() => {
                document.getElementById('loveModal').classList.add('hidden');
            }, 2500);
        }
    </script>
</body>
</html>
