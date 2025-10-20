
<html lang="fa" dir="rtl">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <link href="https://fonts.googleapis.com/css2?family=Shabnam:wght@400;600;700&display=swap" rel="stylesheet">
    <title>فرم راننده</title>
        <style>
        /* ===== پایه ===== */
        body {
            font-family: "Shabnam", sans-serif;
            margin:0;
            line-height:1.8;
            scroll-behavior:smooth;
            background: linear-gradient(-45deg, #121212, #1b5e20, #0d0d0d, #2e7d32);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color:#e0e0e0;
        }
        a { text-decoration:none; color:inherit; transition:.3s; }
        a:hover { color:#fff; text-decoration:underline; }

        /* ===== نوار ناوبری ===== */
        nav {
            position:sticky;
            top:0;
            background:rgba(27,94,32,0.9);
            padding:1rem 2rem;
            display:flex;
            justify-content:flex-end;
            gap:1.5rem;
            z-index:1000;
            backdrop-filter: blur(5px);
            box-shadow:0 2px 12px rgba(0,0,0,.6);
        }
        nav a { color:#fff; font-weight:600; }
        nav a:hover { color:#c8e6c9; }

        /* ===== هدر ===== */
        header { text-align:center; padding:4rem 1rem 2rem; }
        header h1 { color:#a5d6a7; font-size:2.4rem; margin-bottom:.5rem; text-shadow:0 0 20px #66bb6a88; }
        header p.subtitle { color:#bdbdbd; font-size:1.2rem; }

        /* ===== بخش‌ها ===== */
        section { padding:2rem 1rem; max-width:900px; margin:auto; }
        h2 { color:#81c784; border-right:4px solid #66bb6a; padding-right:10px; margin-bottom:1rem; }

        /* ===== کارت‌ها ===== */
        .grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); gap:1rem; }
        .card {
            background:rgba(30,30,30,0.9);
            border-radius:12px;
            padding:1rem;
            box-shadow:0 6px 18px rgba(0,0,0,.6);
            border:1px solid #66bb6a;
            transition:.3s;
            backdrop-filter: blur(5px);
        }
        .card:hover { transform:translateY(-7px) scale(1.03); border-color:#a5d6a7; box-shadow:0 10px 25px rgba(0,0,0,.8); }
        .card h3 { margin-top:0; color:#a5d6a7; }

        /* ===== فرم داخل کارت ===== */
        .container { max-width:900px; margin:0 auto; }
        .card-form {
            background:rgba(30,30,30,0.9);
            border-radius:12px;
            padding:1.4rem;
            box-shadow:0 6px 18px rgba(0,0,0,.6);
            border:1px solid #66bb6a;
            transition:.3s;
            backdrop-filter: blur(5px);
            color: #e9f5ee;
        }
        .card-form h2 { margin-top:0; color:#a5d6a7; }
        label { display:block; margin-bottom:.4rem; font-weight:600; color:#a5d6a7; }
        .form-row { margin-bottom:1rem; }
        input[type="text"], input[type="tel"], input[type="email"], input[list], textarea {
            width:100%; padding:10px; border:2px solid #ddd; border-radius:8px; font-size:16px; box-sizing:border-box; background:rgba(255,255,255,0.03); color:inherit;
        }
        textarea { min-height:80px; resize:vertical; }

        .file-wrapper { display:flex; flex-direction:column; gap:8px; }
        .file-label { display:inline-block; padding:10px 12px; background:linear-gradient(90deg,#2e7d32,#1b5e20); color:#fff; border-radius:8px; cursor:pointer; width:max-content; }
        .file-input { display:inline-block; opacity:0; width:160px; height:38px; cursor:pointer; vertical-align:middle; }

        .icon { margin-left:.5rem; font-size:1.05rem; }
        .radio-group { display:flex; gap:1.25rem; align-items:center; }

        .actions { display:flex; gap:12px; justify-content:center; margin-top:1rem; }
        .btn { padding:10px 18px; border:none; border-radius:8px; font-size:16px; cursor:pointer; background:#3498db; color:white; }
        .btn.secondary { background:#95a5a6; }

        /* ===== فوتر ===== */
        footer { background:#1b5e20; color:#fff; text-align:center; padding:1rem; font-size:.9rem; margin-top:2rem; text-shadow:0 0 10px #66bb6a55; }

        /* ===== انیمیشن‌ها ===== */
        .fade { opacity:0; transform:translateY(25px); animation:fadeUp 1s forwards; }
        .fade.delay-1{ animation-delay:.2s; }
        .fade.delay-2{ animation-delay:.4s; }
        .fade.delay-3{ animation-delay:.6s; }

        @keyframes fadeUp { to { opacity:1; transform:translateY(0); } }
        @keyframes gradientBG { 0%{background-position:0% 50%;} 50%{background-position:100% 50%;} 100%{background-position:0% 50%;} }
    </style>
</head>
<body>
    <div class="container">
        <section class="card-form fade">
            <h2> فرم ثبت نام آموزشگاه رانندگی رفاه</h2>
            <form id="driverForm" novalidate>
                <div class="form-row">
                    <label for="firstName">نام <span class="icon">👤</span></label>
                    <input type="text" id="firstName" name="firstName" placeholder="نام خود را وارد کنید" required>
                </div>

                <div class="form-row">
                    <label for="lastName">نام خانوادگی <span class="icon">🧾</span></label>
                    <input type="text" id="lastName" name="lastName" placeholder="نام خانوادگی خود را وارد کنید" required>
                </div>

                <div class="form-row">
                    <label>جنسیت <span class="icon">⚧️</span></label>
                    <div class="radio-group" role="radiogroup" aria-label="جنسیت">
                        <label for="male"><input type="radio" id="male" name="gender" value="male"> مرد</label>
                        <label for="female"><input type="radio" id="female" name="gender" value="female"> زن</label>
                    </div>
                </div>

                <div class="form-row">
                    <label for="dob">تاریخ تولد <span class="icon">🎂</span></label>
                    <input type="text" id="dob" name="dob" placeholder="YYYY-MM-DD">
                </div>

                <div class="form-row">
                    <label for="phone">تلفن همراه <span class="icon">📞</span></label>
                    <input type="tel" id="phone" name="phone" placeholder="09xxxxxxxxx">
                </div>

                <div class="form-row">
                    <label for="email">ایمیل <span class="icon">✉️</span></label>
                    <input type="email" id="email" name="email" placeholder="example@domain.com">
                </div>

                <div class="form-row">
                    <label for="education">سطح تحصیلات <span class="icon" aria-hidden="true">🎓</span></label>
                    <input list="education-list" id="education" name="education" aria-labelledby="education" placeholder="یک سطح انتخاب یا تایپ کنید">
                    <datalist id="education-list">
                        <option value="دیپلم"></option>
                        <option value="فوق دیپلم"></option>
                        <option value="کارشناسی"></option>
                        <option value="کارشناسی ارشد"></option>
                        <option value="دکتری"></option>
                    </datalist>
                </div>

                <div class="form-row">
                    <label for="address">آدرس <span class="icon">📍</span></label>
                    <textarea id="address" name="address" placeholder="نشانی محل سکونت"></textarea>
                </div>

                <div class="form-row">
                    <label for="emergency">تماس اضطراری <span class="icon">🚨</span></label>
                    <input type="tel" id="emergency" name="emergency" placeholder="شماره تماس اضطراری">
                </div>

                <div class="form-row file-wrapper">
                    <label class="file-label" for="nationalCard" id="nationalCardLabel" tabindex="0">📎 انتخاب عکس کارت ملی</label>
                    <input class="file-input" type="file" id="nationalCard" name="nationalCard" accept="image/*" aria-labelledby="nationalCardLabel">
                </div>

                <div class="actions">
                    <button type="submit" class="btn">ثبت اطلاعات</button>
                    <button type="button" class="btn secondary" id="resetBtn">ثبت نام فرد دیگر</button>
                </div>
            </form>
        </section>
    </div>

    <footer>✨ ساخته شده توسط محمد جواد تجدد ✨</footer>

    <!-- این صفحه اکنون فقط HTML/CSS است تا برای قرار دادن در GitHub به‌عنوان صفحهٔ استاتیک مناسب باشد -->

</body>
</html>
