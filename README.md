<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>نَفَس شبابي — مبادرة للشباب</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --main-green: #2aa07a;
      --accent: #3db08d;
      --dark: #15323b;
      --muted: #6b7b80;
      --card-bg: #ffffff;
      --glass: rgba(255,255,255,0.85);
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: "Cairo", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg,#f6f9f8 0%, #eef6f4 100%);
      color: var(--dark);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.6;
    }
    a{color:inherit; text-decoration:none}
    header{
      position:sticky;
      top:0;
      z-index:40;
      backdrop-filter: blur(6px);
      background: rgba(255,255,255,0.6);
      border-bottom: 1px solid rgba(0,0,0,0.05);
    }
    .container{max-width:1100px;margin:0 auto;padding:0 18px;}
    .nav{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      padding:10px 0;
    }
    .brand{display:flex;align-items:center;gap:12px}
    .brand img{width:64px;height:64px;object-fit:contain;border-radius:12px}
    .brand h1{margin:0;font-size:20px;font-weight:700}
    nav ul{display:flex;gap:12px;list-style:none;padding:0;margin:0}
    nav li a{padding:8px 12px;border-radius:8px;font-weight:600;color:var(--dark)}
    .cta{background:var(--main-green);color:white;padding:8px 14px;border-radius:10px;font-weight:700;box-shadow:0 6px 18px rgba(38,138,102,0.12)}
    /* Hero */
    .hero{
      padding:36px 0 10px;
      display:grid;
      grid-template-columns: 1fr;
      gap:20px;
      align-items:center;
    }
    .hero-inner{
      background: linear-gradient(135deg, rgba(45,160,122,0.06), rgba(61,176,141,0.02));
      border-radius:14px;padding:26px;
      display:flex;flex-direction:column;gap:16px;align-items:flex-start;
    }
    .hero h2{margin:0;font-size:28px}
    .hero p{margin:0;color:var(--muted)}
    .hero .buttons{display:flex;gap:10px;margin-top:6px}
    .btn{padding:10px 16px;border-radius:10px;font-weight:700;cursor:pointer;border:0}
    .btn-outline{background:transparent;border:2px solid var(--main-green);color:var(--main-green)}
    .btn-primary{background:var(--main-green);color:white}
    /* ticker */
    .ticker{
      display:flex;align-items:center;gap:12px;padding:6px 12px;border-radius:10px;background:var(--glass);border:1px solid rgba(0,0,0,0.03);
      overflow:hidden;
    }
    .tick-wrap{white-space:nowrap;display:inline-block;animation:scroll-left 20s linear infinite}
    @keyframes scroll-left{
      0%{transform:translateX(100%)}
      100%{transform:translateX(-100%)}
    }
    /* sections */
    section{padding:30px 0}
    .grid{display:grid;gap:16px}
    .two-col{grid-template-columns: 1fr 360px}
    .cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:14px}
    .card{background:var(--card-bg);padding:14px;border-radius:12px;box-shadow:0 8px 24px rgba(10,20,20,0.04);transition:transform .2s,box-shadow .2s}
    .card:hover{transform:translateY(-6px);box-shadow:0 18px 40px rgba(18,50,50,0.08)}
    .card h3{margin:0 0 6px;font-size:16px}
    .small{color:var(--muted);font-size:14px}
    /* team */
    .team{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:12px}
    .member{background:linear-gradient(180deg,rgba(255,255,255,0.9),#fff);padding:12px;border-radius:12px;text-align:center}
    .avatar{width:86px;height:86px;border-radius:50%;background:linear-gradient(135deg,var(--main-green),var(--accent));display:inline-flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:22px;margin-bottom:10px}
    footer{padding:20px 0;border-top:1px solid rgba(0,0,0,0.04);background:transparent}
    .contact-actions{display:flex;flex-direction:column;gap:10px}
    .socials{display:flex;gap:10px;flex-wrap:wrap}
    .socials a{display:inline-flex;align-items:center;gap:8px;padding:10px;border-radius:10px;background:var(--glass);border:1px solid rgba(0,0,0,0.04)}
    /* floating whatsapp */
    .whatsapp-float{
      position:fixed;left:18px;bottom:18px;background:#25d366;color:white;border-radius:999px;padding:14px 16px;font-weight:700;box-shadow:0 12px 36px rgba(37,211,102,0.18);z-index:60;display:flex;align-items:center;gap:10px
    }
    .whatsapp-float img{width:20px;height:20px}
    /* responsive */
    @media (min-width:860px){
      .hero{grid-template-columns: 1fr 360px}
      nav ul{gap:18px}
    }
    @media (max-width:520px){
      .brand h1{font-size:16px}
      .hero h2{font-size:22px}
    }
    /* subtle appear animation */
    .fade-in{opacity:0;transform:translateY(8px);animation:fadeUp .7s ease forwards}
    @keyframes fadeUp{to{opacity:1;transform:none}}
  </style>
</head>
<body>

<header>
  <div class="container nav">
    <div class="brand">
      <!-- ضع هنا ملف اللوجو باسم logo.png في نفس مجلد الصفحة -->
      <img src="logo.png" alt="لوغو نَفَس شبابي" onerror="this.style.display='none'">
      <div>
        <h1>نَفَس شَبَابي</h1>
        <div style="font-size:12px;color:var(--muted)">مساحة للتوعية، الدعم، والإبداع</div>
      </div>
    </div>

    <nav>
      <ul>
        <li><a href="#about">الرئيسية</a></li>
        <li><a href="#about">عنّا</a></li>
        <li><a href="#workshops">ورشاتنا</a></li>
        <li><a href="#team">الفريق</a></li>
        <li><a href="#contact">تواصل معنا</a></li>
        <li><a class="cta" href="#join">انضم الآن</a></li>
      </ul>
    </nav>
  </div>
</header>

<main class="container">
  <!-- Ticker -->
  <div style="margin-top:12px" class="ticker">
    <strong style="color:var(--main-green);margin-left:8px">إعلان:</strong>
    <div style="flex:1;overflow:hidden">
      <div class="tick-wrap">آخر ورشة: "التأثير النفسي للسوشال ميديا" — اشتركوا عبر رابط الواتساب • ورشات جديدة أونلاين عبر Google Meet وجاهية قريبًا</div>
    </div>
  </div>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-inner fade-in">
      <h2>نَفَس شبابي — من القلب للقلب</h2>
      <p>مبادرة شبابية أُطلقت عبر منصة "نَحن" لنشر الوعي النفسي وتعزيز الصحة النفسية بين الشباب الأردني. بنقدّم ورشات تفاعلية، لقاءات توعوية وأنشطة عملية أونلاين (Google Meet) ووجاهي.</p>

      <div class="buttons">
        <button class="btn btn-primary" onclick="scrollToId('workshops')">ورشاتنا</button>
        <button class="btn btn-outline" onclick="scrollToId('about')">تعرف علينا</button>
      </div>
    </div>

    <div class="hero-inner fade-in" style="align-self:center">
      <h3 style="margin-top:0">لماذا نَفَس شبابي؟</h3>
      <p class="small">منظومة دعم متكاملة تركز على الجوانب النفسية، الاجتماعية والصحية للشباب. نعمل بالشراكة مع مدربين ومتخصصين متطوعين لتقديم محتوى ذي قيمة.</p>

      <ul style="margin:12px 0;padding:0 12px;list-style:none">
        <li class="small">✔️ ورش تفاعلية عبر Google Meet</li>
        <li class="small">✔️ دعم مجتمعي ومساحات آمنة للنقاش</li>
        <li class="small">✔️ دورات وجاهية ومختبرات عملية قريباً</li>
      </ul>

      <div style="display:flex;gap:10px;flex-wrap:wrap">
        <a class="cta" href="https://chat.whatsapp.com/L55BbojXqZSDTSoKtJ9Dbc?mode=ems_copy_t" target="_blank" rel="noopener">انضم للواتساب</a>
        <a class="btn btn-outline" href="https://www.instagram.com/nafas.shababi?igsh=ano2bW56Nm41d3c3" target="_blank" rel="noopener">صفحتنا على إنستقرام</a>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about" class="fade-in">
    <div class="grid two-col">
      <div>
        <h2>عن نَفَس شبابي</h2>
        <p>نَفَس شبابي مبادرة شبابية أُطلقت عبر منصة <strong>نَحن</strong>، هدفها نشر الوعي النفسي وتعزيز الصحة النفسية بين الشباب الأردني. نقدم ورشات تفاعلية، لقاءات توعوية وأنشطة عملية لنمكّن الشباب ونخلق مساحات آمنة للتعبير والنقاش وتبادل الخبرات.</p>

        <h3>فكرتنا</h3>
        <p class="small">نؤمن أن التغيير يبدأ بوعي صغير ويتضخم بالمشاركة. نعمل على بناء جيل قادر على مواجهة ضغوط الحياة النفسية والاجتماعية من خلال مهارات عملية ودعم متواصل.</p>

        <h3>شراكاتنا</h3>
        <p class="small">نرحّب بتعاون المدربين والمتخصصين المتطوعين لتقديم ورشات تدريبية. هدفنا أن يستفيد الشباب ويترك كل مدرب أثرًا إيجابيًا عبر مجتمعاتنا.</p>
      </div>

      <aside style="padding:14px;background:var(--card-bg);border-radius:12px;box-shadow:0 8px 24px rgba(10,20,20,0.04)">
        <h4 style="margin-top:0">معلومات سريعة</h4>
        <p class="small">📞 هاتف: <a href="tel:0791036401">0791036401</a></p>
        <p class="small">📷 إنستغرام: <a href="https://www.instagram.com/nafas.shababi?igsh=ano2bW56Nm41d3c3" target="_blank">@nafas.shababi</a></p>
        <p class="small">🔗 انضم للواتساب: <a href="https://chat.whatsapp.com/L55BbojXqZSDTSoKtJ9Dbc?mode=ems_copy_t" target="_blank">اضغط هنا</a></p>
        <hr>
        <p class="small"><strong>ملاحظات تقنية:</strong><br>الورش أونلاين عبر Google Meet — نوفر تسجيل وروابط للحضور بعد التسجيل.</p>
      </aside>
    </div>
  </section>

  <!-- WORKSHOPS -->
  <section id="workshops" class="fade-in">
    <h2>ورشاتنا</h2>
    <p class="small">نظّمنا ورشات متنوعة عبر Google Meet وتسجيلات، وهذه بعض العناوين اللي قدمناها:</p>

    <div class="cards" style="margin-top:12px">
      <article class="card">
        <h3>الصحة النفسية</h3>
        <p class="small">أساسيات الصحة النفسية وكيفية طلب المساعدة.</p>
      </article>

      <article class="card">
        <h3>العلاقة بين الصحة النفسية والجسدية</h3>
        <p class="small">كيف يؤثر أسلوب الحياة على مزاجنا وصحتنا.</p>
      </article>

      <article class="card">
        <h3>تأثير السوشال ميديا على صحتنا النفسية</h3>
        <p class="small">آليات التعامل مع المحتوى وتقليل الضغوط الرقمية.</p>
      </article>

      <article class="card">
        <h3>رحلة لفهم التوحد</h3>
        <p class="small">مقدمة، مفاهيم، وكيفية دعم الأشخاص المتوحدين.</p>
      </article>

      <article class="card">
        <h3>الحيوانات الأليفة وصحتنا النفسية</h3>
        <p class="small">فائدة التفاعل مع الحيوانات ودوره العلاجي.</p>
      </article>

      <article class="card">
        <h3>الصدمات النفسية</h3>
        <p class="small">فهم الصدمة وطرق التدخل والدعم.</p>
      </article>

      <article class="card">
        <h3>رحلة مع نَفَس شبابي</h3>
        <p class="small">تعرف على مبادرتنا وخبرات الشباب معنا.</p>
      </article>

      <article class="card">
        <h3>الفرق بين الغَزَلة والتوحد</h3>
        <p class="small">فهم الفروق والسلوكيات وكيفية التأويل السليم.</p>
      </article>

      <article class="card">
        <h3>التغذية والصحة النفسية</h3>
        <p class="small">علاقة الأكل بالمزاج والطاقة اليومية.</p>
      </article>

      <article class="card">
        <h3>الذكاء العاطفي</h3>
        <p class="small">تنمية الوعي الذاتي والمهارات الاجتماعية.</p>
      </article>
    </div>

    <p class="small" style="margin-top:12px">قريبًا: المزيد من الموضوعات المدمجة بين الأونلاين والوجاهي.</p>
  </section>

  <!-- TEAM -->
  <section id="team" class="fade-in">
    <h2>فريق نَفَس شبابي</h2>
    <div class="team" style="margin-top:12px">
      <div class="member">
        <div class="avatar">أح</div>
        <strong>أحمد الصباغ</strong>
        <div class="small">مسؤول ومؤسس المبادرة</div>
      </div>

      <div class="member">
        <div class="avatar">نو</div>
        <strong>نورس المومني</strong>
        <div class="small">نائب رئيس</div>
      </div>

      <div class="member">
        <div class="avatar">أم</div>
        <strong>أماني بطوش</strong>
        <div class="small">عضو إداري / هندسة برمجيات</div>
      </div>

      <div class="member">
        <div class="avatar">مر</div>
        <strong>مرح القضاة</strong>
        <div class="small">عضو إداري / صيدلة</div>
      </div>

      <div class="member">
        <div class="avatar">فا</div>
        <strong>فاطمة القضاة</strong>
        <div class="small">عضو إداري / ناشطة شبابية</div>
      </div>

      <div class="member">
        <div class="avatar">يـس</div>
        <strong>ياسمين المومني</strong>
        <div class="small">عضو إداري / معلمة صف</div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact" class="fade-in">
    <div style="display:grid;grid-template-columns:1fr 320px;gap:18px;align-items:start">
      <div>
        <h2>تواصل معنا</h2>
        <p class="small">حابب تتعاون كمدرّب، تحضر ورشة، أو تحتاج استفسار؟ احنا جاهزين.</p>

        <div class="card" style="display:flex;gap:12px;align-items:center">
          <div style="flex:1">
            <p style="margin:0;font-weight:700">0791036401</p>
            <p class="small" style="margin:4px 0 0">متوفرين على الواتساب للتسجيل والاستفسار</p>
          </div>
          <div>
            <a href="tel:0791036401" class="btn btn-outline">اتصل الآن</a>
          </div>
        </div>

        <div style="margin-top:12px">
          <h4>حسابنا على إنستقرام</h4>
          <a href="https://www.instagram.com/nafas.shababi?igsh=ano2bW56Nm41d3c3" target="_blank" rel="noopener" class="small">@nafas.shababi</a>
        </div>

        <div style="margin-top:12px">
          <h4 id="join">انضم إلينا</h4>
          <p class="small">انضم لمجتمعنا عبر واتساب لتصلك روابط التسجيل وأحدث الإعلانات.</p>
          <a class="cta" href="https://chat.whatsapp.com/L55BbojXqZSDTSoKtJ9Dbc?mode=ems_copy_t" target="_blank">انضم للواتساب</a>
        </div>
      </div>

      <aside style="padding:14px;background:var(--card-bg);border-radius:12px;box-shadow:0 8px 24px rgba(10,20,20,0.04)">
        <h4 style="margin-top:0">ندعم التعاون التطوّعي</h4>
        <p class="small">إذا كنت مدربًا أو مختصًا وتحب تقدّم ورشة تطوّعية، تواصل معنا عبر الواتساب أو الهاتف — نحب نسمع منك!</p>

        <div style="margin-top:10px" class="socials">
          <a href="https://chat.whatsapp.com/L55BbojXqZSDTSoKtJ9Dbc?mode=ems_copy_t" target="_blank">واتساب</a>
          <a href="https://www.instagram.com/nafas.shababi?igsh=ano2bW56Nm41d3c3" target="_blank">إنستقرام</a>
        </div>
      </aside>
    </div>
  </section>
</main>

<!-- Footer -->
<footer>
  <div class="container" style="display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap">
    <div style="font-size:14px;color:var(--muted)">© 2025 نَفَس شبابي — كل الحقوق محفوظة</div>
    <div style="font-size:13px;color:var(--muted)">صمم بواسطة فريق نَفَس شبابي</div>
  </div>
</footer>

<!-- Floating WhatsApp -->
<a class="whatsapp-float" href="https://chat.whatsapp.com/L55BbojXqZSDTSoKtJ9Dbc?mode=ems_copy_t" target="_blank" rel="noopener">
  <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="whatsapp">
  تواصل معنا
</a>

<script>
  // smooth scroll helper
  function scrollToId(id){
    const el = document.getElementById(id);
    if(!el) return window.scrollTo({top:0, behavior:'smooth'});
    const offset = el.getBoundingClientRect().top + window.pageYOffset - 80;
    window.scrollTo({top: offset, behavior:'smooth'});
  }

  // add fade-in class on load with small delay for sections
  document.addEventListener('DOMContentLoaded', () => {
    document.querySelectorAll('.fade-in').forEach((el, i) => {
      el.style.animationDelay = (i * 80) + 'ms';
    });
  });

  // Replace avatars initials automatically if no images (simple)
  document.querySelectorAll('.avatar').forEach(a => {
    if(!a.dataset.initials){
      // keep existing text (already set)
    }
  });

  // Mobile: hide ticker animation for better perf
  if(window.innerWidth < 420){
    const tick = document.querySelector('.tick-wrap');
    if(tick) tick.style.animation = 'none';
  }
</script>

</body>
</html>
