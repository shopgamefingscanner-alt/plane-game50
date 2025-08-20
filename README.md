<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Planet Hack Pro - هاك الطائرة المحترف</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --main-blue: #0a2463;
            --neon-blue: #00b4d8;
            --neon-pink: #ff0a78;
            --neon-green: #39ff14;
            --dark-bg: #0d0221;
            --card-bg: #1b0536;
            --text-light: #ffffff;
            --text-dim: #a3a3c2;
            --error-color: #ff3860;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--dark-bg), #16043a, #0d0221);
            color: var(--text-light);
            min-height: 100vh;
            overflow-x: hidden;
            line-height: 1.6;
        }
        
        /* Matrix rain effect */
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.15;
            pointer-events: none;
        }
        
        /* Flying plane animation */
        .flying-plane {
            position: fixed;
            bottom: -100px;
            left: 10%;
            font-size: 3rem;
            color: var(--neon-blue);
            z-index: 100;
            animation: flyUp 8s ease-in forwards;
            text-shadow: 0 0 15px var(--neon-blue);
        }
        
        @keyframes flyUp {
            0% {
                transform: translateY(0) rotate(10deg);
                opacity: 0;
            }
            20% {
                opacity: 1;
            }
            80% {
                opacity: 1;
            }
            100% {
                transform: translateY(-120vh) rotate(0deg);
                opacity: 0;
            }
        }
        
        /* Login Page */
        .login-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 20px;
        }
        
        .login-box {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            width: 100%;
            max-width: 450px;
            box-shadow: 0 0 30px rgba(0, 180, 216, 0.3);
            border: 1px solid var(--neon-blue);
            text-align: center;
        }
        
        .login-logo {
            margin-bottom: 25px;
        }
        
        .login-logo i {
            font-size: 4rem;
            color: var(--neon-blue);
            text-shadow: 0 0 20px rgba(0, 180, 216, 0.7);
            animation: pulse 2s infinite;
        }
        
        .login-logo h1 {
            font-size: 2rem;
            margin-top: 15px;
            background: linear-gradient(to right, var(--neon-blue), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .form-group {
            margin-bottom: 20px;
            text-align: right;
            width: 100%;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: var(--text-light);
            font-weight: 500;
        }
        
        .form-group input {
            width: 100%;
            padding: 12px 15px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 8px;
            color: var(--text-light);
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .form-group input:focus {
            outline: none;
            border-color: var(--neon-blue);
            box-shadow: 0 0 10px rgba(0, 180, 216, 0.5);
        }
        
        .login-btn {
            width: 100%;
            padding: 14px;
            background: linear-gradient(to right, var(--neon-blue), var(--neon-pink));
            color: white;
            border: none;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 10px;
            font-size: 1.1rem;
        }
        
        .login-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        /* Packages Page */
        .packages-page {
            display: none;
            padding: 40px 20px;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 30px;
            font-size: 2rem;
            background: linear-gradient(to right, var(--neon-blue), var(--neon-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .packages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .package-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 180, 216, 0.3);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .package-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, var(--neon-blue), var(--neon-pink));
        }
        
        .package-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
            border-color: var(--neon-blue);
        }
        
        .package-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--neon-blue);
        }
        
        .package-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--text-light);
        }
        
        .package-price {
            font-size: 2rem;
            font-weight: 700;
            margin: 15px 0;
            background: linear-gradient(to right, var(--neon-blue), var(--neon-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .package-features {
            list-style: none;
            margin: 20px 0;
            text-align: right;
        }
        
        .package-features li {
            padding: 8px 0;
            color: var(--text-dim);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .package-features li:last-child {
            border-bottom: none;
        }
        
        .code-input {
            width: 100%;
            padding: 12px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 8px;
            color: var(--text-light);
            font-size: 1rem;
            margin-bottom: 15px;
            text-align: center;
            transition: all 0.3s ease;
        }
        
        .code-input.error {
            border-color: var(--error-color);
            box-shadow: 0 0 10px rgba(255, 56, 96, 0.5);
        }
        
        .error-message {
            color: var(--error-color);
            font-size: 0.9rem;
            margin-bottom: 10px;
            display: none;
        }
        
        .buy-btn {
            width: 100%;
            padding: 12px;
            background: linear-gradient(to right, var(--neon-blue), var(--neon-pink));
            color: white;
            border: none;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 5px;
        }
        
        .buy-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        /* Payment Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(5px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
        }
        
        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }
        
        .payment-modal {
            background: var(--card-bg);
            border-radius: 15px;
            width: 90%;
            max-width: 500px;
            padding: 30px;
            box-shadow: 0 0 50px rgba(0, 180, 216, 0.3);
            border: 1px solid var(--neon-blue);
            position: relative;
            transform: scale(0.9);
            transition: transform 0.3s ease;
        }
        
        .modal-overlay.active .payment-modal {
            transform: scale(1);
        }
        
        .modal-close {
            position: absolute;
            top: 15px;
            left: 15px;
            background: none;
            border: none;
            color: var(--text-dim);
            font-size: 1.5rem;
            cursor: pointer;
            transition: color 0.3s ease;
        }
        
        .modal-close:hover {
            color: var(--neon-pink);
        }
        
        .modal-header {
            text-align: center;
            margin-bottom: 25px;
        }
        
        .modal-header i {
            font-size: 2.5rem;
            color: var(--neon-blue);
            margin-bottom: 15px;
        }
        
        .modal-header h2 {
            font-size: 1.8rem;
            background: linear-gradient(to right, var(--neon-blue), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .payment-info {
            background: rgba(0, 0, 0, 0.2);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            text-align: center;
        }
        
        .payment-info p {
            margin: 10px 0;
            font-size: 1.1rem;
        }
        
        .transfer-number {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--neon-green);
            direction: ltr;
            display: block;
            margin: 15px 0;
        }
        
        .upload-section {
            text-align: center;
            margin: 20px 0;
            padding: 20px;
            border: 2px dashed var(--neon-blue);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .upload-section:hover {
            background: rgba(0, 180, 216, 0.1);
        }
        
        .upload-section i {
            font-size: 2.5rem;
            color: var(--neon-blue);
            margin-bottom: 10px;
        }
        
        .file-name {
            margin-top: 10px;
            font-size: 0.9rem;
            color: var(--neon-green);
            display: none;
        }
        
        .file-error {
            color: var(--error-color);
            margin-top: 5px;
            font-size: 0.9rem;
            display: none;
        }
        
        .confirm-btn {
            width: 100%;
            padding: 14px;
            background: linear-gradient(to right, var(--neon-green), #2a9d8f);
            color: white;
            border: none;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 15px;
            font-size: 1.1rem;
        }
        
        .confirm-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        /* Confirmation Message */
        .confirmation-message {
            text-align: center;
            padding: 30px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            margin-top: 20px;
            display: none;
        }
        
        .confirmation-message i {
            font-size: 3rem;
            color: var(--neon-green);
            margin-bottom: 15px;
            animation: pulse 2s infinite;
        }
        
        .confirmation-message h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--neon-green);
        }
        
        .confirmation-message p {
            margin: 10px 0;
            line-height: 1.6;
        }
        
        /* Predictions Page */
        .predictions-page {
            display: none;
            padding: 40px 20px;
            text-align: center;
        }
        
        .prediction-container {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 40px;
            max-width: 600px;
            margin: 0 auto;
            box-shadow: 0 0 30px rgba(0, 180, 216, 0.3);
            border: 1px solid var(--neon-blue);
            position: relative;
        }
        
        .prediction-title {
            font-size: 2rem;
            margin-bottom: 30px;
            background: linear-gradient(to right, var(--neon-blue), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .prediction-value {
            font-size: 4rem;
            font-weight: 800;
            margin: 30px 0;
            background: linear-gradient(to right, var(--neon-green), var(--neon-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 20px rgba(57, 255, 20, 0.5);
            transition: all 0.5s ease;
        }
        
        .countdown {
            font-size: 1.2rem;
            color: var(--text-dim);
            margin-top: 20px;
        }
        
        .countdown-value {
            color: var(--neon-pink);
            font-weight: 700;
        }
        
        /* Animations */
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }
        
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            10%, 30%, 50%, 70%, 90% { transform: translateX(-10px); }
            20%, 40%, 60%, 80% { transform: translateX(10px); }
        }
        
        .shake {
            animation: shake 0.5s;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .packages-grid {
                grid-template-columns: 1fr;
            }
            
            .prediction-value {
                font-size: 3rem;
            }
            
            .login-box, .payment-modal, .prediction-container {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Matrix Rain Background -->
    <div class="matrix-bg" id="matrixRain"></div>
    
    <!-- Flying Plane -->
    <div class="flying-plane">
        <i class="fas fa-plane"></i>
    </div>
    
    <!-- Login Page -->
    <div class="login-container" id="loginPage">
        <div class="login-box">
            <div class="login-logo">
                <i class="fas fa-plane-departure"></i>
                <h1>Planet Hack Pro</h1>
            </div>
            
            <form id="loginForm">
                <div class="form-group">
                    <label for="email">البريد الإلكتروني</label>
                    <input type="email" id="email" required>
                </div>
                
                <div class="form-group">
                    <label for="password">كلمة المرور</label>
                    <input type="password" id="password" required>
                </div>
                
                <div class="form-group">
                    <label for="userId">ID حسابك</label>
                    <input type="text" id="userId" required>
                </div>
                
                <button type="submit" class="login-btn">تسجيل الدخول</button>
            </form>
        </div>
    </div>
    
    <!-- Packages Page -->
    <div class="packages-page" id="packagesPage">
        <h2 class="section-title">باقات هاك الطائرة</h2>
        
        <div class="packages-grid">
            <div class="package-card">
                <i class="fas fa-star package-icon"></i>
                <h3>الباقة الأساسية</h3>
                <div class="package-price">100 جنيه</div>
                
                <ul class="package-features">
                    <li>هاك لمدة 3 أيام</li>
                    <li>توقعات دقيقة بنسبة 70%</li>
                    <li>دعم فني أساسي</li>
                </ul>
                
                <input type="text" class="code-input" id="code1" placeholder="أدخل كود الهاك">
                <div class="error-message" id="error1">❌ تأكد من الكود</div>
                <button class="buy-btn" onclick="validateCode('code1', 'error1', 'basic')">اشتري الآن</button>
            </div>
            
            <div class="package-card">
                <i class="fas fa-gem package-icon"></i>
                <h3>الباقة المميزة</h3>
                <div class="package-price">180 جنيه</div>
                
                <ul class="package-features">
                    <li>هاك لمدة أسبوع</li>
                    <li>توقعات دقيقة بنسبة 80%</li>
                    <li>دعم فني مميز</li>
                    <li>تحديثات مستمرة</li>
                </ul>
                
                <input type="text" class="code-input" id="code2" placeholder="أدخل كود الهاك">
                <div class="error-message" id="error2">❌ تأكد من الكود</div>
                <button class="buy-btn" onclick="validateCode('code2', 'error2', 'premium')">اشتري الآن</button>
            </div>
            
            <div class="package-card">
                <i class="fas fa-crown package-icon"></i>
                <h3>الباقة الذهبية</h3>
                <div class="package-price">250 جنيه</div>
                
                <ul class="package-features">
                    <li>هاك لمدة شهر</li>
                    <li>توقعات دقيقة بنسبة 90%</li>
                    <li>دعم فني على مدار الساعة</li>
                    <li>تحديثات فورية</li>
                    <li>وصول مدى الحياة</li>
                </ul>
                
                <input type="text" class="code-input" id="code3" placeholder="أدخل كود الهاك">
                <div class="error-message" id="error3">❌ تأكد من الكود</div>
                <button class="buy-btn" onclick="validateCode('code3', 'error3', 'golden')">اشتري الآن</button>
            </div>
        </div>
    </div>
    
    <!-- Payment Modal -->
    <div class="modal-overlay" id="paymentModal">
        <div class="payment-modal">
            <button class="modal-close" onclick="closePayment()">&times;</button>
            
            <div class="modal-header">
                <i class="fas fa-credit-card"></i>
                <h2>إتمام عملية الدفع</h2>
            </div>
            
            <div class="payment-info">
                <p>برجاء التحويل إلى الرقم التالي:</p>
                <span class="transfer-number">01203294156</span>
                
                <p>سيتم إرسال كود التفعيل إلى بريدك الإلكتروني بعد التحقق من الدفع</p>
            </div>
            
            <div class="upload-section" id="uploadSection">
                <i class="fas fa-cloud-upload-alt"></i>
                <p>ارفع صورة إيصال التحويل (PNG, JPG - بحد أقصى 2MB)</p>
                <p class="file-name" id="fileName"></p>
                <p class="file-error" id="fileError"></p>
                <input type="file" id="fileInput" style="display: none;" accept="image/png, image/jpeg">
            </div>
            
            <div class="confirmation-message" id="confirmationMessage">
                <i class="fas fa-check-circle"></i>
                <h3>تم الارسال بنجاح!</h3>
                <p>سيتم التحقق من الدفع خلال 10 دقائق</p>
                <p>سيتم إرسال كود التفعيل إلى الإيميل</p>
                <p>شكراً لثقتك بنا</p>
            </div>
            
            <button class="confirm-btn" id="confirmBtn" onclick="confirmPayment()">تأكيد الإرسال</button>
        </div>
    </div>
    
    <!-- Predictions Page -->
    <div class="predictions-page" id="predictionsPage">
        <div class="prediction-container">
            <h2 class="prediction-title">توقعات هاك الطائرة</h2>
            <p>يتم تحديث التوقعات كل 20 ثانية</p>
            
            <div class="prediction-value" id="predictionValue">1.50</div>
            
            <div class="countdown">التحديث بعد: <span class="countdown-value" id="countdown">20</span> ثانية</div>
        </div>
    </div>

    <script>
        // Matrix rain effect
        function createMatrixRain() {
            const container = document.getElementById('matrixRain');
            const canvas = document.createElement('canvas');
            container.appendChild(canvas);
            
            const ctx = canvas.getContext('2d');
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            
            const letters = '01010101010101010101010101010101010101010101010101010101010101010101';
            const fontSize = 14;
            const columns = canvas.width / fontSize;
            
            const drops = [];
            for (let i = 0; i < columns; i++) {
                drops[i] = 1;
            }
            
            function draw() {
                ctx.fillStyle = 'rgba(13, 2, 33, 0.05)';
                ctx.fillRect(0, 0, canvas.width, canvas.height);
                
                ctx.fillStyle = '#0af';
                ctx.font = `${fontSize}px monospace`;
                
                for (let i = 0; i < drops.length; i++) {
                    const text = letters[Math.floor(Math.random() * letters.length)];
                    ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                    
                    if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                        drops[i] = 0;
                    }
                    
                    drops[i]++;
                }
            }
            
            setInterval(draw, 33);
            
            window.addEventListener('resize', () => {
                canvas.width = window.innerWidth;
                canvas.height = window.innerHeight;
            });
        }
        
        createMatrixRain();
        
        // Login form submission
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            const userId = document.getElementById('userId').value;
            
            // تخزين بيانات المستخدم محلياً
            localStorage.setItem('userEmail', email);
            localStorage.setItem('userId', userId);
            
            document.getElementById('loginPage').style.display = 'none';
            document.getElementById('packagesPage').style.display = 'block';
        });
        
        // Validate code function
        function validateCode(inputId, errorId, packageType) {
            const codeInput = document.getElementById(inputId);
            const errorMessage = document.getElementById(errorId);
            
            // أكواد مختلفة لكل باقة
            const correctCodes = {
                'basic': 'BASIC2024',
                'premium': 'PREMIUM24',
                'golden': 'GOLDENKEY'
            };
            
            const correctCode = correctCodes[packageType];
            
            if (codeInput.value.toUpperCase() === correctCode) {
                // تخزين نوع الباقة المختارة
                localStorage.setItem('selectedPackage', packageType);
                
                // Code is correct, show payment modal
                showPayment();
            } else {
                // Code is incorrect, show error
                codeInput.classList.add('error');
                codeInput.classList.add('shake');
                errorMessage.style.display = 'block';
                
                // Remove shake animation after it completes
                setTimeout(() => {
                    codeInput.classList.remove('shake');
                }, 500);
            }
        }
        
        // Reset code input on focus
        document.querySelectorAll('.code-input').forEach(input => {
            input.addEventListener('focus', function() {
                this.classList.remove('error');
                const errorId = 'error' + this.id.slice(-1);
                document.getElementById(errorId).style.display = 'none';
            });
        });
        
        // Show payment modal
        function showPayment() {
            document.getElementById('paymentModal').classList.add('active');
        }
        
        // Close payment modal
        function closePayment() {
            document.getElementById('paymentModal').classList.remove('active');
            // Reset confirmation message
            document.getElementById('confirmationMessage').style.display = 'none';
            document.getElementById('confirmBtn').style.display = 'block';
            document.getElementById('fileError').style.display = 'none';
        }
        
        // File upload handling
        document.getElementById('uploadSection').addEventListener('click', function() {
            document.getElementById('fileInput').click();
        });
        
        document.getElementById('fileInput').addEventListener('change', function(e) {
            const fileError = document.getElementById('fileError');
            if (e.target.files.length > 0) {
                const file = e.target.files[0];
                
                // التحقق من نوع الملف
                const validTypes = ['image/jpeg', 'image/png'];
                if (!validTypes.includes(file.type)) {
                    fileError.textContent = 'نوع الملف غير مدعوم. يرجى رفع صورة بصيغة JPG أو PNG.';
                    fileError.style.display = 'block';
                    this.value = '';
                    return;
                }
                
                // التحقق من حجم الملف (2MB كحد أقصى)
                if (file.size > 2 * 1024 * 1024) {
                    fileError.textContent = 'حجم الملف كبير جداً. الحد الأقصى هو 2MB.';
                    fileError.style.display = 'block';
                    this.value = '';
                    return;
                }
                
                // إذا اجتاز الملف جميع الشروط
                fileError.style.display = 'none';
                const fileName = file.name;
                document.getElementById('fileName').textContent = fileName;
                document.getElementById('fileName').style.display = 'block';
            }
        });
        
        // Confirm payment
        function confirmPayment() {
            const fileInput = document.getElementById('fileInput');
            const fileError = document.getElementById('fileError');
            
            if (fileInput.files.length === 0) {
                fileError.textContent = 'برجاء رفع صورة إيصال التحويل أولاً';
                fileError.style.display = 'block';
                return;
            }
            
            // Show confirmation message
            document.getElementById('confirmationMessage').style.display = 'block';
            document.getElementById('confirmBtn').style.display = 'none';
            
            // تخزين معلومات الدفع محلياً (في تطبيق حقيقي، يجب إرسالها إلى الخادم)
            const paymentData = {
                package: localStorage.getItem('selectedPackage'),
                email: localStorage.getItem('userEmail'),
                userId: localStorage.getItem('userId'),
                timestamp: new Date().toISOString()
            };
            
            localStorage.setItem('paymentData', JSON.stringify(paymentData));
            
            // Automatically redirect to predictions after 5 seconds
            setTimeout(function() {
                document.getElementById('paymentModal').classList.remove('active');
                document.getElementById('packagesPage').style.display = 'none';
                document.getElementById('predictionsPage').style.display = 'block';
                startPredictions();
            }, 5000);
        }
        
        // Predictions system
        let countdown = 20;
        let countdownInterval;
        
        function startPredictions() {
            // Initial prediction
            generatePrediction();
            
            // Set up countdown
            countdownInterval = setInterval(function() {
                countdown--;
                document.getElementById('countdown').textContent = countdown;
                
                if (countdown <= 0) {
                    generatePrediction();
                    countdown = 20;
                }
            }, 1000);
        }
        
        function generatePrediction() {
            // إنشاء توقعات أكثر واقعية بدلاً من 3 قيم ثابتة
            const baseValue = 1.0 + Math.random() * 1.5; // قيمة بين 1.0 و 2.5
            const randomPrediction = Math.round(baseValue * 100) / 100; // تقريب إلى منزلتين عشريتين
            
            const predictionElement = document.getElementById('predictionValue');
            
            // Add animation
            predictionElement.style.opacity = 0;
            predictionElement.style.transform = 'scale(0.5)';
            
            setTimeout(function() {
                predictionElement.textContent = randomPrediction.toFixed(2);
                predictionElement.style.opacity = 1;
                predictionElement.style.transform = 'scale(1)';
            }, 500);
        }
        
        // Add flying planes periodically
        function addFlyingPlane() {
            const plane = document.createElement('div');
            plane.className = 'flying-plane';
            plane.innerHTML = '<i class="fas fa-plane"></i>';
            
            // Random horizontal position
            const leftPosition = Math.random() * 80 + 10;
            plane.style.left = leftPosition + '%';
            
            // Random delay
            const randomDelay = Math.random() * 3;
            plane.style.animationDelay = randomDelay + 's';
            
            document.body.appendChild(plane);
            
            // Remove plane after animation completes
            setTimeout(function() {
                if (plane.parentNode) {
                    document.body.removeChild(plane);
                }
            }, 8000 + randomDelay * 1000);
        }
        
        // Add a plane every 10 seconds
        setInterval(addFlyingPlane, 10000);
        
        // Add initial plane
        setTimeout(addFlyingPlane, 1000);
    </script>
</body>
</html>
