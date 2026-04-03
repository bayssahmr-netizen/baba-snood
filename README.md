<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
<title>منصة تجارية تجمع كل التجار والخدمات في تبسة</title>
<style>
:root{
  --pr:#1a73e8;--prd:#1557b0;--sec:#ff6b35;--suc:#28a745;
  --dan:#dc3545;--drk:#2c3e50;--rad:12px;
  --sh:0 2px 15px rgba(0,0,0,.1);
}
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Segoe UI',Tahoma,Arial,sans-serif;background:#f0f2f5;color:#333;min-height:100vh;line-height:1.6}

/* HEADER */
.hdr{background:linear-gradient(135deg,var(--pr),var(--prd));color:#fff;padding:10px 15px;position:sticky;top:0;z-index:1000;box-shadow:var(--sh)}
.hdr-row{display:flex;align-items:center;gap:10px;flex-wrap:wrap}
.logo{font-size:1.3em;font-weight:700;cursor:pointer;white-space:nowrap}
.logo b{color:var(--sec)}
.srch{flex:1;min-width:180px;max-width:500px}
.srch input{width:100%;padding:9px 16px;border:none;border-radius:25px;font-size:14px;outline:none}
.hdr-btns{display:flex;gap:4px;flex-wrap:wrap}
.hb{background:rgba(255,255,255,.18);color:#fff;border:none;padding:7px 12px;border-radius:18px;cursor:pointer;font-size:12px;transition:.3s;white-space:nowrap;font-family:inherit}
.hb:hover{background:rgba(255,255,255,.35)}
.hb.sh{opacity:.4;font-size:16px;padding:7px 8px}.hb.sh:hover{opacity:1}

/* CATEGORIES */
.cats{background:#fff;padding:12px 8px;overflow-x:auto;box-shadow:0 2px 5px rgba(0,0,0,.05)}
.cats-scroll{display:flex;gap:12px;padding:4px 8px;min-width:max-content}
.cat-item{display:flex;flex-direction:column;align-items:center;gap:5px;cursor:pointer;min-width:65px;transition:.3s}
.cat-item:hover{transform:translateY(-3px)}
.cat-ico{width:50px;height:50px;border-radius:50%;background:linear-gradient(135deg,#e3f2fd,#bbdefb);display:flex;align-items:center;justify-content:center;font-size:22px;box-shadow:0 2px 8px rgba(0,0,0,.1)}
.cat-nm{font-size:10px;text-align:center;color:#555;font-weight:500;max-width:70px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}

/* PRODUCTS */
.feed{padding:15px;max-width:1400px;margin:0 auto}
.stitle{font-size:1.2em;margin-bottom:15px;color:var(--drk);display:flex;align-items:center;gap:8px}
.pgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:12px}
.pcard{background:#fff;border-radius:var(--rad);overflow:hidden;box-shadow:var(--sh);transition:.3s;cursor:pointer}
.pcard:hover{transform:translateY(-4px);box-shadow:0 8px 25px rgba(0,0,0,.15)}
.pimg{width:100%;height:180px;background:#f5f5f5;display:flex;align-items:center;justify-content:center;color:#ccc;font-size:40px;overflow:hidden}
.pimg img{width:100%;height:100%;object-fit:cover}
.pinfo{padding:10px}
.pname{font-weight:600;font-size:13px;color:#333;height:36px;overflow:hidden;line-height:1.4}
.pprice{color:var(--sec);font-weight:700;font-size:15px;margin:4px 0 6px}
.pstore{display:flex;align-items:center;gap:5px;font-size:11px;color:#888;padding-top:6px;border-top:1px solid #eee}
.pstore .av{width:22px;height:22px;border-radius:50%;background:var(--pr);color:#fff;display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:700;flex-shrink:0}
.pacts{display:flex;gap:4px;margin-top:6px}
.abtn{flex:1;padding:5px 2px;border:none;border-radius:6px;font-size:11px;cursor:pointer;color:#fff;transition:.2s;text-align:center;font-family:inherit}
.abtn.msg{background:#0084ff}.abtn.cal{background:var(--suc)}.abtn.ord{background:var(--sec)}

/* MODALS */
.mov{display:none;position:fixed;inset:0;background:rgba(0,0,0,.55);z-index:2000;justify-content:center;align-items:flex-start;padding:15px;overflow-y:auto}
.mov.act{display:flex}
.mdl{background:#fff;border-radius:var(--rad);width:100%;max-width:560px;margin:20px auto;box-shadow:0 15px 50px rgba(0,0,0,.3);max-height:92vh;overflow-y:auto}
.mdl-h{padding:15px 18px;background:linear-gradient(135deg,var(--pr),var(--prd));color:#fff;border-radius:var(--rad) var(--rad) 0 0;display:flex;justify-content:space-between;align-items:center;position:sticky;top:0;z-index:5}
.mdl-h h2{font-size:1em;margin:0}
.mdl-x{background:rgba(255,255,255,.2);border:none;color:#fff;width:30px;height:30px;border-radius:50%;font-size:16px;cursor:pointer;display:flex;align-items:center;justify-content:center}
.mdl-b{padding:18px}

/* FORMS */
.fg{margin-bottom:14px}
.fg label{display:block;margin-bottom:5px;font-weight:600;font-size:13px;color:#444}
.fg input,.fg select,.fg textarea{width:100%;padding:9px 12px;border:2px solid #e0e0e0;border-radius:8px;font-size:13px;transition:.3s;font-family:inherit}
.fg input:focus,.fg select:focus,.fg textarea:focus{border-color:var(--pr);outline:none;box-shadow:0 0 0 3px rgba(26,115,232,.1)}
.fg textarea{min-height:70px;resize:vertical}
.fhint{font-size:10px;color:#aaa;margin-top:3px}
.sbtn{width:100%;padding:11px;background:linear-gradient(135deg,var(--pr),var(--prd));color:#fff;border:none;border-radius:8px;font-size:15px;font-weight:700;cursor:pointer;transition:.3s;font-family:inherit}
.sbtn:hover{transform:translateY(-2px);box-shadow:0 4px 12px rgba(26,115,232,.4)}
.sbtn.g{background:linear-gradient(135deg,var(--suc),#1e7e34)}
.sbtn.r{background:linear-gradient(135deg,var(--dan),#a71d2a)}
.sbtn:disabled{opacity:.5;cursor:not-allowed;transform:none}

/* IMAGE UPLOAD */
.uparea{border:3px dashed #ccc;border-radius:12px;padding:25px 10px;text-align:center;cursor:pointer;transition:.3s;background:#fafafa;position:relative;min-height:100px}
.uparea:hover,.uparea.dov{border-color:var(--pr);background:#e8f0fe}
.uparea .uico{font-size:36px;pointer-events:none}
.uparea .utxt{color:#666;font-size:13px;pointer-events:none}
.uparea .uhint{color:#aaa;font-size:11px;margin-top:4px;pointer-events:none}
.uparea input[type=file]{position:absolute;inset:0;opacity:0;cursor:pointer;z-index:5}
.previews{display:flex;flex-wrap:wrap;gap:8px;margin-top:8px}
.prev-item{position:relative;width:80px;height:80px;border-radius:8px;overflow:hidden;box-shadow:0 2px 6px rgba(0,0,0,.15)}
.prev-item img{width:100%;height:100%;object-fit:cover}
.prev-item .rm{position:absolute;top:2px;right:2px;background:rgba(220,53,69,.9);color:#fff;border:none;width:22px;height:22px;border-radius:50%;font-size:12px;cursor:pointer;display:flex;align-items:center;justify-content:center;z-index:5}

/* CSV */
.csv-area{border:3px dashed var(--suc);border-radius:12px;padding:25px 10px;text-align:center;cursor:pointer;transition:.3s;background:#f0fff0;position:relative;min-height:100px;margin-bottom:12px}
.csv-area:hover,.csv-area.dov{border-color:#1e7e34;background:#d4edda}
.csv-area input[type=file]{position:absolute;inset:0;opacity:0;cursor:pointer;z-index:5}
.csv-fn{margin-top:8px;padding:7px 12px;background:#d4edda;border-radius:8px;color:var(--suc);font-weight:700;display:none}
.csv-fn.show{display:block}
.csv-res{margin-top:12px;padding:12px;background:#f8f9fa;border-radius:8px;display:none;font-size:13px}
.csv-res.show{display:block}

/* DASHBOARD */
.dnav{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:15px;padding:8px;background:#fff;border-radius:var(--rad)}
.dtab{padding:7px 14px;border:2px solid #e0e0e0;border-radius:18px;background:#fff;cursor:pointer;font-size:12px;transition:.3s;font-family:inherit}
.dtab.act{background:var(--pr);color:#fff;border-color:var(--pr)}
.dsec{display:none;background:#fff;padding:18px;border-radius:var(--rad);box-shadow:var(--sh)}
.dsec.act{display:block}
.amnav{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:15px}
.ambtn{padding:8px 15px;background:#fff;border:2px solid #e0e0e0;border-radius:10px;cursor:pointer;font-size:12px;transition:.3s;font-family:inherit;display:flex;align-items:center;gap:5px}
.ambtn.act{background:var(--pr);color:#fff;border-color:var(--pr)}
.amsec{display:none;background:#fff;padding:18px;border-radius:var(--rad);box-shadow:var(--sh)}
.amsec.act{display:block}
.dtbl{width:100%;border-collapse:collapse;margin-top:12px}
.dtbl th,.dtbl td{padding:8px 6px;text-align:right;border-bottom:1px solid #eee;font-size:12px;word-break:break-word}
.dtbl th{background:#f8f9fa;font-weight:700;color:#555}
.dtbl tr:hover{background:#f5f8ff}

/* NOTIFICATIONS */
.notif{position:fixed;top:70px;left:50%;transform:translateX(-50%) translateY(-20px);padding:12px 24px;border-radius:10px;color:#fff;font-weight:700;z-index:9999;opacity:0;transition:.4s;text-align:center;min-width:260px;max-width:90%;box-shadow:0 4px 16px rgba(0,0,0,.2);font-size:14px}
.notif.show{opacity:1;transform:translateX(-50%) translateY(0)}
.notif.ok{background:linear-gradient(135deg,#28a745,#1e7e34)}
.notif.er{background:linear-gradient(135deg,#dc3545,#a71d2a)}
.notif.inf{background:linear-gradient(135deg,#17a2b8,#117a8b)}

/* TOGGLE */
.tgl{position:relative;width:46px;height:24px;display:inline-block}
.tgl input{display:none}
.tgl span{position:absolute;inset:0;background:#ccc;border-radius:24px;cursor:pointer;transition:.3s}
.tgl span::before{content:'';position:absolute;width:18px;height:18px;background:#fff;border-radius:50%;top:3px;right:3px;transition:.3s}
.tgl input:checked+span{background:var(--suc)}
.tgl input:checked+span::before{transform:translateX(-22px)}

/* MISC */
.back{display:inline-flex;align-items:center;gap:5px;padding:7px 14px;background:#fff;border:2px solid #e0e0e0;border-radius:8px;cursor:pointer;font-size:13px;margin-bottom:12px;transition:.3s;font-family:inherit}
.back:hover{border-color:var(--pr)}
.empty{text-align:center;padding:40px 15px;color:#aaa}
.empty .eico{font-size:50px;margin-bottom:10px}
.badge{padding:3px 8px;border-radius:10px;font-size:10px;font-weight:700;white-space:nowrap}
.badge.g{background:#d4edda;color:var(--suc)}.badge.r{background:#f8d7da;color:var(--dan)}
.page{display:none}.page.act{display:block}
.scard{display:flex;align-items:center;gap:12px;padding:12px;background:#f8f9fa;border-radius:10px;margin-bottom:8px;flex-wrap:wrap}
.scard .sav{width:45px;height:45px;border-radius:50%;background:var(--pr);color:#fff;display:flex;align-items:center;justify-content:center;font-size:18px;font-weight:700;flex-shrink:0}
.scard .sinf{flex:1;min-width:140px}
.scard .sinf h4{font-size:14px;margin-bottom:2px}
.scard .sinf p{font-size:11px;color:#888}
.cpg{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.cpg label{min-width:110px;font-weight:600;font-size:13px}
.cpg input[type=color]{width:45px;height:32px;border:2px solid #ddd;border-radius:8px;cursor:pointer;padding:1px}
.chkg{display:flex;gap:12px;flex-wrap:wrap}
.chkg label{display:flex;align-items:center;gap:5px;cursor:pointer;font-weight:normal;font-size:13px}
.jcard{background:#fff;padding:12px;border-radius:10px;box-shadow:var(--sh);margin-bottom:8px}
.jcard h3{color:var(--pr);margin-bottom:6px;font-size:14px}
.jmeta{display:flex;gap:12px;flex-wrap:wrap;font-size:12px;color:#888;margin-top:6px}
.jtabs{display:flex;gap:8px;margin-bottom:15px}
.jtab{flex:1;padding:10px;text-align:center;background:#fff;border:2px solid #e0e0e0;border-radius:10px;cursor:pointer;font-weight:700;transition:.3s;font-family:inherit;font-size:13px}
.jtab.act{background:var(--pr);color:#fff;border-color:var(--pr)}
.det-imgs{display:flex;gap:8px;overflow-x:auto;padding:8px 0}
.det-imgs img{width:280px;height:280px;object-fit:cover;border-radius:10px;flex-shrink:0}
.det-info{padding:18px}
.det-info h1{font-size:1.4em;margin-bottom:8px}
.det-info .dprice{font-size:1.6em;color:var(--sec);font-weight:700;margin-bottom:12px}
.det-info .ddesc{line-height:1.8;color:#555;margin-bottom:16px}
.det-acts{display:flex;gap:8px;flex-wrap:wrap}
.det-acts .abtn{padding:10px 20px;font-size:14px;border-radius:10px}
.stat-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:12px;margin-bottom:18px}
.stat-card{padding:18px 10px;border-radius:12px;color:#fff;text-align:center}
.stat-card .snum{font-size:26px;font-weight:700}
.stat-card .slbl{font-size:12px;margin-top:4px}

/* Contact Info Box */
.contact-box{background:linear-gradient(135deg,#e3f2fd,#fff);border:2px solid #bbdefb;border-radius:12px;padding:15px;margin-bottom:15px}
.contact-box h4{color:var(--pr);margin-bottom:8px}
.contact-box .ci{display:flex;align-items:center;gap:8px;padding:6px 0;font-size:13px;color:#555}
.contact-box .ci span{font-size:18px}

/* Complaint Card */
.comp-card{padding:12px;background:#f8f9fa;border-radius:10px;margin-bottom:8px;border-right:4px solid var(--pr)}
.comp-card.from-store{border-right-color:var(--sec)}
.comp-card.from-visitor{border-right-color:var(--suc)}
.comp-card .comp-meta{display:flex;justify-content:space-between;align-items:center;margin-bottom:6px;font-size:11px;color:#aaa}
.comp-card .comp-type{font-size:10px;padding:2px 8px;border-radius:10px;font-weight:700}
.comp-card .comp-type.t-store{background:#fff3e0;color:var(--sec)}
.comp-card .comp-type.t-visitor{background:#e8f5e9;color:var(--suc)}

/* Privacy checkbox */
.privacy-check{display:flex;align-items:flex-start;gap:8px;padding:12px;background:#f0f4ff;border-radius:8px;margin-bottom:14px;border:2px solid #e0e0e0}
.privacy-check input{margin-top:3px;width:18px;height:18px;flex-shrink:0}
.privacy-check .ptxt{font-size:12px;color:#555;line-height:1.5}
.privacy-check .ptxt a{color:var(--pr);cursor:pointer;text-decoration:underline}

/* Smart Category Badge */
.smart-cat-badge{display:inline-block;padding:2px 8px;background:#e3f2fd;color:var(--pr);border-radius:10px;font-size:10px;font-weight:600;margin-right:4px}

/* Footer */
.ftr{background:var(--drk);color:#fff;padding:25px 15px 12px;margin-top:30px}
.ftr-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:18px;max-width:1200px;margin:0 auto 15px}
.ftr-sec h4{margin-bottom:10px;color:var(--sec);font-size:14px}
.ftr-sec a{display:block;color:#bbb;font-size:12px;margin-bottom:5px;cursor:pointer}
.ftr-sec a:hover{color:#fff}
.ftr-bot{text-align:center;padding-top:12px;border-top:1px solid rgba(255,255,255,.1);font-size:12px;color:#888}

/* --- 1. القواعد العامة (للحاسوب وللجميع) --- */
.hdr-row {
  display: flex;
  align-items: center;
  gap: 15px;
  flex-wrap: nowrap; /* الحفاظ على استقامة العناصر في الحاسوب */
}

.srch {
  flex: 1; /* شريط البحث يأخذ المساحة المتاحة */
  min-width: 200px;
}

.hdr-btns {
  display: flex;
  gap: 8px;
}

/* --- 2. قواعد الهاتف (تطبق فقط إذا كان عرض الشاشة أقل من 768px) --- */
@media (max-width: 768px) {
  /* منع التمرير الجانبي نهائياً */
  html, body {
    overflow-x: hidden;
    width: 100%;
  }

  /* تحويل الهيدر إلى ترتيب عمودي في الهاتف */
  .hdr-row {
    flex-direction: column !important;
    gap: 12px !important;
    padding: 10px 5px;
  }

  /* شريط البحث يأخذ العرض الكامل في الهاتف */
  .srch {
    width: 100% !important;
    order: 2; /* يظهر تحت اللوجو */
  }
  .srch input {
    width: 100% !important;
  }

  /* ترتيب الأزرار بشكل شبكة (Grid) لكي لا تخرج عن الشاشة */
  .hdr-btns {
    width: 100%;
    display: grid !important;
    grid-template-columns: repeat(3, 1fr); /* 3 أزرار في كل صف */
    gap: 6px !important;
    order: 3;
  }

  /* ضبط حجم الأزرار ونصوصها في الهاتف */
  .hb {
    width: 100%;
    padding: 8px 2px !important;
    font-size: 11px !important;
    text-align: center;
    justify-content: center;
    white-space: nowrap; /* يمنع نزول النص لسطر جديد */
  }

  /* جعل زر الإدارة (الدرع) يأخذ عرضاً كاملاً في الأسفل */
  .hb.sh {
    grid-column: span 3;
    margin-top: 4px;
  }

  /* تحسين شبكة المنتجات لتظهر كعمودين في الهاتف */
  .pgrid {
    grid-template-columns: repeat(2, 1fr) !important;
    gap: 10px !important;
    padding: 5px;
  }

  /* جعل النوافذ المنبثقة (Modals) تتناسب مع حجم شاشة الهاتف */
  .mdl {
    width: 95% !important;
    margin: 10px auto !important;
    max-height: 90vh;
    overflow-y: auto;
  }
}

/* --- 3. قواعد الشاشات الصغيرة جداً (أقل من 480px) --- */
@media (max-width: 480px) {
  .hdr-btns {
    grid-template-columns: repeat(2, 1fr); /* زرين فقط في الصف الواحد لزيادة الوضوح */
  }
  .hb.sh {
    grid-column: span 2;
  }
  .pname { font-size: 11px; height: 30px; }
  .pprice { font-size: 13px; }
}
.ftr{background:var(--drk);color:#fff;padding:25px 15px 12px;margin-top:30px}
.ftr-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:18px;max-width:1200px;margin:0 auto 15px}
.ftr-sec h4{margin-bottom:10px;color:var(--sec);font-size:14px}
.ftr-sec a{display:block;color:#bbb;font-size:12px;margin-bottom:5px;cursor:pointer}
.ftr-sec a:hover{color:#fff}
.ftr-bot{text-align:center;padding-top:12px;border-top:1px solid rgba(255,255,255,.1);font-size:12px;color:#888}

/* Cloud Status */
.cloud-status{position:fixed;bottom:10px;left:10px;background:rgba(0,0,0,0.6);color:#fff;padding:4px 10px;border-radius:20px;font-size:10px;z-index:9999;display:flex;align-items:center;gap:5px}
.cloud-dot{width:8px;height:8px;border-radius:50%;background:#ccc}
.cloud-dot.online{background:#28a745}
.cloud-dot.syncing{background:#ffc107;animation:pulse 1s infinite}
@keyframes pulse{0%{opacity:1}50%{opacity:0.4}100%{opacity:1}}

/* Responsive Rules */
.hdr-row { display: flex; align-items: center; gap: 15px; flex-wrap: nowrap; }
.srch { flex: 1; min-width: 200px; }
.hdr-btns { display: flex; gap: 8px; }

@media (max-width: 768px) {
  html, body { overflow-x: hidden; width: 100%; }
  .hdr-row { flex-direction: column !important; gap: 12px !important; padding: 10px 5px; }
  .srch { width: 100% !important; order: 2; }
  .srch input { width: 100% !important; }
  .hdr-btns { width: 100%; display: grid !important; grid-template-columns: repeat(3, 1fr); gap: 6px !important; order: 3; }
  .hb { width: 100%; padding: 8px 2px !important; font-size: 11px !important; text-align: center; justify-content: center; white-space: nowrap; }
  .hb.sh { grid-column: span 3; margin-top: 4px; }
  .pgrid { grid-template-columns: repeat(2, 1fr) !important; gap: 10px !important; padding: 5px; }
  .mdl { width: 95% !important; margin: 10px auto !important; max-height: 90vh; overflow-y: auto; }
}

@media (max-width: 480px) {
  .hdr-btns { grid-template-columns: repeat(2, 1fr); }
  .hb.sh { grid-column: span 2; }
  .pname { font-size: 11px; height: 30px; }
  .pprice { font-size: 13px; }
}
</style>
</head>
<body>

<div id="ntf" class="notif"></div>

<!-- HEADER -->
<header class="hdr">
<div class="hdr-row">
  <div class="logo" onclick="nav('home')">🛒 <b id="pName">BABA SANOOD</b></div>
  <div class="srch"><input type="text" id="sInp" placeholder="🔍 ابحث عن منتجات، متاجر، وظائف..." oninput="doSearch(this.value)"></div>
  <div class="hdr-btns">
    <button class="hb" onclick="nav('home')">🏠 الرئيسية</button>
    <button class="hb" onclick="nav('jobs')">💼 وظائف</button>
    <button class="hb" onclick="oMod('regMod')">🏪 فتح متجر</button>
    <button class="hb" onclick="oMod('logMod')">🔑 دخول</button>
    <button class="hb" onclick="oMod('contactMod')">📞 تواصل معنا</button>
    <button class="hb sh" onclick="oMod('admMod')">🛡️</button>
  </div>
</div>
</header>

<!-- PAGES -->
<div id="pg_home" class="page act">
  <div class="cats"><div class="cats-scroll" id="catsBar"></div></div>
  <div class="feed">
    <h2 class="stitle">🔥 أحدث المنتجات</h2>
    <div class="pgrid" id="mainGrid"></div>
    <div id="emptyMsg" class="empty" style="display:none"><div class="eico">🛍️</div><p>لا توجد منتجات. كن أول من يفتح متجره!</p></div>
  </div>
</div>

<div id="pg_cat" class="page">
  <div class="feed"><button class="back" onclick="nav('home')">→ العودة</button><h2 class="stitle" id="catTitle"></h2><div class="pgrid" id="catGrid"></div></div>
</div>

<div id="pg_store" class="page">
  <div class="feed"><button class="back" onclick="nav('home')">→ العودة</button><div id="storeHdr" style="background:#fff;padding:18px;border-radius:12px;margin-bottom:15px;box-shadow:var(--sh)"></div><h2 class="stitle">📦 منتجات المتجر</h2><div class="pgrid" id="storeGrid"></div></div>
</div>

<div id="pg_det" class="page">
  <div class="feed"><button class="back" onclick="nav('home')">→ العودة</button><div id="detContent"></div></div>
</div>

<div id="pg_jobs" class="page">
  <div class="feed">
    <button class="back" onclick="nav('home')">→ العودة</button>
    <h2 class="stitle">💼 مركز التوظيف</h2>
    <div class="jtabs">
      <div class="jtab act" onclick="jTab(this,'browse')">📋 الوظائف</div>
      <div class="jtab" onclick="jTab(this,'post')">📝 نشر</div>
      <div class="jtab" onclick="jTab(this,'seek')">🔍 أبحث عن عمل</div>
    </div>
    <div id="jBrowse" class="dsec act"><div id="jobList"></div></div>
    <div id="jPost" class="dsec">
      <div class="fg"><label>المؤسسة</label><input id="jComp"></div>
      <div class="fg"><label>نوع الوظيفة</label><input id="jType"></div>
      <div class="fg"><label>المتطلبات</label><textarea id="jReq"></textarea></div>
      <div class="fg"><label>الراتب</label><input id="jSal"></div>
      <div class="fg"><label>الموقع</label><input id="jLoc"></div>
      <div class="fg"><label>الاتصال</label><input id="jCont"></div>
      <button class="sbtn" onclick="postJob()">✅ نشر</button>
    </div>
    <div id="jSeek" class="dsec">
      <div class="fg"><label>الاسم</label><input id="skName"></div>
      <div class="fg"><label>السن</label><input type="number" id="skAge"></div>
      <div class="fg"><label>التخصص</label><input id="skSkill"></div>
      <div class="fg"><label>الخبرات</label><textarea id="skExp"></textarea></div>
      <div class="fg"><label>الهاتف</label><input type="tel" id="skPhone"></div>
      <button class="sbtn" onclick="subSeeker()">✅ تسجيل</button>
    </div>
  </div>
</div>

<!-- MERCHANT DASHBOARD -->
<div id="pg_dash" class="page">
  <div class="feed">
    <button class="back" onclick="mLogout()">🚪 خروج</button>
    <h2 class="stitle" id="dName">📊 لوحة التحكم</h2>
    <div class="dnav" id="dNav">
      <div class="dtab act" onclick="dTab(this,'prods')">📦 المنتجات</div>
      <div class="dtab" onclick="dTab(this,'addP')">➕ إضافة</div>
      <div class="dtab" onclick="dTab(this,'ords')">📋 الطلبات</div>
      <div class="dtab" onclick="dTab(this,'sett')">⚙️ الإعدادات</div>
      <div class="dtab" onclick="dTab(this,'mComp')">📩 تواصل مع الإدارة</div>
    </div>
    <div id="dProds" class="dsec act"><div id="myProds"></div></div>
    <div id="dAddP" class="dsec">
      <h3 style="margin-bottom:12px">➕ إضافة منتج</h3>
      <div class="fg"><label>📸 الصور (حتى 5)</label>
        <div class="uparea" id="mUpArea"><div class="uico">📷</div><div class="utxt">اضغط أو اسحب الصور</div><div class="uhint">JPG, PNG, WebP</div><input type="file" id="mFileIn" accept="image/*" multiple></div>
        <div class="previews" id="mPrevs"></div>
      </div>
      <div class="fg"><label>اسم المنتج</label><input id="npName"></div>
      <div class="fg"><label>السعر (دج)</label><input type="number" id="npPrice"></div>
      <div class="fg"><label>القسم</label><select id="npCat"></select></div>
      <div class="fg"><label>الوصف</label><textarea id="npDesc"></textarea></div>
      <div class="fg"><label>التوصيل</label><select id="npDel"><option value="yes">✅ متاح</option><option value="no">❌ غير متاح</option></select></div>
      <div class="fg"><label>طرق الطلب</label><div class="chkg"><label><input type="checkbox" id="omMsg" checked> 📱 مسنجر</label><label><input type="checkbox" id="omPh"> 📞 اتصال</label><label><input type="checkbox" id="omIn"> 📋 داخلي</label></div></div>
      <button class="sbtn g" onclick="addProd()">✅ نشر</button>
    </div>
    <div id="dOrds" class="dsec"><div id="mOrds"></div></div>
    <div id="dSett" class="dsec">
      <h3 style="margin-bottom:12px">⚙️ الإعدادات</h3>
      <div class="fg"><label>اسم المتجر</label><input id="sName"></div>
      <div class="fg"><label>فيسبوك</label><input id="sFb"></div>
      <div class="fg"><label>الهاتف</label><input type="tel" id="sPh"></div>
      <div class="fg"><label>الوصف</label><textarea id="sDesc"></textarea></div>
      <button class="sbtn" onclick="saveSett()">💾 حفظ</button>
    </div>
    <div id="dMComp" class="dsec">
      <h3 style="margin-bottom:12px">📩 تواصل مع الإدارة</h3>
      <div id="adminContactInfo"></div>
      <div class="fg"><label>نوع الرسالة</label>
        <select id="mCompType"><option value="شكوى">📛 شكوى</option><option value="استفسار">❓ استفسار</option><option value="اقتراح">💡 اقتراح</option><option value="مشكلة تقنية">🔧 مشكلة تقنية</option></select>
      </div>
      <div class="fg"><label>الرسالة</label><textarea id="mCompTxt" placeholder="اكتب رسالتك للإدارة..."></textarea></div>
      <button class="sbtn" onclick="subMerchComp()">📨 إرسال</button>
      <div id="mCompHistory" style="margin-top:15px"></div>
    </div>
  </div>
</div>

<!-- ADMIN PANEL -->
<div id="pg_admin" class="page">
  <div class="feed">
    <button class="back" onclick="nav('home')">🚪 خروج</button>
    <h2 class="stitle">🛡️ لوحة الإدارة الكبرى</h2>
    <div class="amnav" id="amNav">
      <button class="ambtn act" onclick="aTab(this,'look')">🎨 المظهر</button>
      <button class="ambtn" onclick="aTab(this,'contact')">📞 معلومات الاتصال</button>
      <button class="ambtn" onclick="aTab(this,'merch')">🏪 التجار</button>
      <button class="ambtn" onclick="aTab(this,'stat')">📊 إحصائيات</button>
      <button class="ambtn" onclick="aTab(this,'comp')">📩 الشكاوى والرسائل</button>
      <button class="ambtn" onclick="aTab(this,'myS')">🛒 متجري</button>
    </div>
    <div id="amLook" class="amsec act">
      <h3 style="margin-bottom:12px">🎨 المظهر</h3>
      <div class="fg"><label>اسم المنصة</label><input id="apName" oninput="$('pName').textContent=this.value||'BABA SANOOD'"></div>
      <div class="cpg"><label>اللون الرئيسي</label><input type="color" id="apClr1" value="#1a73e8" onchange="document.documentElement.style.setProperty('--pr',this.value)"></div>
      <div class="cpg"><label>اللون الثانوي</label><input type="color" id="apClr2" value="#ff6b35" onchange="document.documentElement.style.setProperty('--sec',this.value)"></div>
      <button class="sbtn" onclick="saveApp()">💾 حفظ المظهر</button>
    </div>
    <div id="amContact" class="amsec">
      <h3 style="margin-bottom:12px">📞 معلومات الاتصال بالإدارة</h3>
      <div class="fg"><label>📱 رقم الهاتف</label><input id="adPh"></div>
      <div class="fg"><label>📱 واتساب</label><input id="adWa"></div>
      <div class="fg"><label>📧 البريد الإلكتروني</label><input type="email" id="adEmail"></div>
      <div class="fg"><label>📘 فيسبوك</label><input id="adFb"></div>
      <div class="fg"><label>📍 العنوان</label><input id="adAddr"></div>
      <div class="fg"><label>🕐 أوقات العمل</label><input id="adHours"></div>
      <button class="sbtn" onclick="saveContact()">💾 حفظ معلومات الاتصال</button>
    </div>
    <div id="amMerch" class="amsec"><h3 style="margin-bottom:12px">🏪 التجار</h3><div id="amStores"></div></div>
    <div id="amStat" class="amsec"><h3 style="margin-bottom:12px">📊 الإحصائيات</h3><div id="amStats"></div></div>
    <div id="amComp" class="amsec">
      <h3 style="margin-bottom:12px">📩 الشكاوى والرسائل الواردة</h3>
      <div style="display:flex;gap:8px;margin-bottom:12px;flex-wrap:wrap">
        <button class="dtab act" onclick="filterComp(this,'all')">📬 الكل</button>
        <button class="dtab" onclick="filterComp(this,'store')">🏪 من التجار</button>
        <button class="dtab" onclick="filterComp(this,'visitor')">👤 من الزوار</button>
      </div>
      <div id="compList"></div>
    </div>
    <div id="amMyS" class="amsec">
      <h3 style="margin-bottom:12px">🛒 متجري الخاص</h3>
      <div style="padding:15px;background:#f0fff0;border-radius:12px;margin-bottom:18px">
        <h4 style="margin-bottom:8px">📁 رفع CSV مع فرز ذكي</h4>
        <div class="csv-area" id="csvArea"><div style="font-size:36px;pointer-events:none">📄</div><input type="file" id="csvIn" accept=".csv,.txt"></div>
        <div class="csv-fn" id="csvFn"></div>
        <div class="csv-res" id="csvRes"></div>
      </div>
      <div style="padding:15px;background:#fff3e0;border-radius:12px;margin-bottom:18px">
        <h4 style="margin-bottom:8px">✏️ إضافة يدوية (+20%)</h4>
        <div class="fg"><label>📸 الصور</label>
          <div class="uparea" id="aUpArea"><div class="uico">📷</div><input type="file" id="aFileIn" accept="image/*" multiple></div>
          <div class="previews" id="aPrevs"></div>
        </div>
        <div class="fg"><label>الاسم</label><input id="apPName"></div>
        <div class="fg"><label>السعر (دج)</label><input type="number" id="apPPrice"></div>
        <div class="fg"><label>القسم</label><select id="apPCat"></select></div>
        <div class="fg"><label>الوصف</label><textarea id="apPDesc"></textarea></div>
        <button class="sbtn g" onclick="addAdmProd()">✅ نشر (+20%)</button>
      </div>
      <h4>📦 منتجاتي (<span id="admPCount">0</span>)</h4>
      <div id="amMyProds" style="margin-top:12px"></div>
    </div>
  </div>
</div>

<!-- MODALS -->
<div id="regMod" class="mov"><div class="mdl"><div class="mdl-h"><h2>🏪 فتح متجر جديد</h2><button class="mdl-x" onclick="cMod('regMod')">✕</button></div><div class="mdl-b">
  <div class="fg"><label>اسم المتجر *</label><input id="rName"></div>
  <div class="fg"><label>نوع النشاط *</label><select id="rType"><option value="">-- اختر --</option><option value="تاجر">🛒 تاجر</option><option value="حرفي">🔧 حرفي</option><option value="مهنة حرة">⚖️ مهنة حرة</option><option value="خدمات رقمية">💻 خدمات رقمية</option><option value="مطعم">🍽️ مطعم</option></select></div>
  <div class="fg"><label>إيميل</label><input type="email" id="rEmail"></div>
  <div class="fg"><label>هاتف</label><input type="tel" id="rPhone"></div>
  <div class="fg"><label>كلمة السر *</label><input type="password" id="rPass"></div>
  <div class="privacy-check"><input type="checkbox" id="privacyAgree"><div class="ptxt">أوافق على <a onclick="infoPage('priv')">سياسة الخصوصية</a> و<a onclick="infoPage('terms')">شروط الاستخدام</a>.</div></div>
  <button class="sbtn g" onclick="regStore()">🎉 إنشاء المتجر</button>
</div></div></div>

<div id="logMod" class="mov"><div class="mdl"><div class="mdl-h"><h2>🔑 دخول التاجر</h2><button class="mdl-x" onclick="cMod('logMod')">✕</button></div><div class="mdl-b">
  <div class="fg"><label>اسم المتجر</label><input id="lName"></div>
  <div class="fg"><label>كلمة السر</label><input type="password" id="lPass"></div>
  <div class="fg"><label style="font-weight:normal;display:flex;align-items:center;gap:5px"><input type="checkbox" id="lRem"> تذكرني</label></div>
  <button class="sbtn" onclick="mLogin()">🔓 دخول</button>
</div></div></div>

<div id="admMod" class="mov"><div class="mdl" style="max-width:380px"><div class="mdl-h" style="background:#2c3e50"><h2>🛡️ الإدارة</h2><button class="mdl-x" onclick="cMod('admMod')">✕</button></div><div class="mdl-b">
  <div class="fg"><label>الرقم السري</label><input type="password" id="admPass"></div>
  <button class="sbtn" style="background:#2c3e50" onclick="admLogin()">🔓 دخول</button>
</div></div></div>

<div id="contactMod" class="mov"><div class="mdl"><div class="mdl-h"><h2>📞 تواصل معنا</h2><button class="mdl-x" onclick="cMod('contactMod')">✕</button></div><div class="mdl-b">
  <div id="publicContactInfo"></div>
  <hr style="margin:12px 0;border:none;border-top:1px solid #eee">
  <h4 style="margin-bottom:10px">📨 أرسل رسالة للإدارة</h4>
  <div class="fg"><label>اسمك</label><input id="vName"></div>
  <div class="fg"><label>الهاتف أو الإيميل</label><input id="vContact"></div>
  <div class="fg"><label>نوع الرسالة</label><select id="vType"><option value="استفسار">❓ استفسار</option><option value="شكوى">📛 شكوى</option><option value="اقتراح">💡 اقتراح</option></select></div>
  <div class="fg"><label>الرسالة</label><textarea id="vMsg"></textarea></div>
  <button class="sbtn g" onclick="subVisitorMsg()">📨 إرسال</button>
</div></div></div>

<div id="ordMod" class="mov"><div class="mdl"><div class="mdl-h"><h2>📋 طلب منتج</h2><button class="mdl-x" onclick="cMod('ordMod')">✕</button></div><div class="mdl-b">
  <div class="fg"><label>اسمك *</label><input id="oName"></div>
  <div class="fg"><label>الهاتف *</label><input type="tel" id="oPhone"></div>
  <div class="fg"><label>الولاية</label><input id="oWil"></div>
  <div class="fg"><label>العنوان</label><textarea id="oAddr"></textarea></div>
  <div class="fg"><label>ملاحظات</label><textarea id="oNotes"></textarea></div>
  <input type="hidden" id="oPid"><input type="hidden" id="oSid">
  <button class="sbtn g" onclick="subOrd()">✅ تأكيد</button>
</div></div></div>

<footer class="ftr">
<div class="ftr-grid">
  <div class="ftr-sec"><h4>🛒 سوق تبسة العملاق</h4><p style="font-size:12px;color:#bbb">منصة تجارية تجمع كل التجار والخدمات في تبسة</p></div>
  <div class="ftr-sec"><h4>📌 روابط</h4><a onclick="infoPage('priv')">🔒 الخصوصية</a><a onclick="infoPage('terms')">📜 شروط الاستخدام</a><a onclick="infoPage('guide')">📖 الدليل</a><a onclick="infoPage('faq')">❓ أسئلة شائعة</a><a onclick="infoPage('copy')">©️ حقوق الملكية</a></div>
  <div class="ftr-sec"><h4>📞 تواصل</h4><a onclick="oMod('contactMod')">📩 أرسل رسالة</a><div id="footerContact"></div></div>
</div>
<div class="ftr-bot">© 2026 سوق تبسة العملاق - بابا سنود</div>
</footer>

<div class="cloud-status"><div id="cloudDot" class="cloud-dot"></div><span id="cloudTxt">جاري التحقق...</span></div>

<script>
// ★★★ CLOUD SYNC ENGINE ★★★
const CLOUD_API = "https://keyvalue.imfast.io/api/keyval";
const APP_ID = "BS_MARKET_TABESSA_PRO";

async function cloudSync(action, key, data = null) {
    const dot = document.getElementById('cloudDot');
    const txt = document.getElementById('cloudTxt');
    const fullKey = `${APP_ID}_${key}`;
    try {
        if (action === 'save') {
            dot.className = 'cloud-dot syncing';
            txt.textContent = 'جاري الحفظ...';
            await fetch(`${CLOUD_API}/${fullKey}`, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(data)
            });
            dot.className = 'cloud-dot online';
            txt.textContent = '✅ متصل (سحابي)';
            return true;
        } else if (action === 'load') {
            dot.className = 'cloud-dot syncing';
            txt.textContent = 'جاري المزامنة...';
            const res = await fetch(`${CLOUD_API}/${fullKey}`);
            if (res.ok) {
                const val = await res.json();
                dot.className = 'cloud-dot online';
                txt.textContent = '✅ متصل (سحابي)';
                return val;
            }
        }
    } catch (e) {
        dot.className = 'cloud-dot';
        txt.textContent = '⚠️ وضع محلي (أوفلاين)';
    }
    return null;
}

const $ = id => document.getElementById(id);
const D = {s:'bs_s',p:'bs_p',o:'bs_o',j:'bs_j',c:'bs_c',a:'bs_a',ap:'bs_ap',ct:'bs_ct'};

const gA = k => {try{return JSON.parse(localStorage.getItem(k))||[]}catch(e){return[]}};
const sA = async (k, v) => {
    try {
        localStorage.setItem(k, JSON.stringify(v));
        await cloudSync('save', k, v);
    } catch(e) { ntf('خطأ حفظ!','er'); }
};
const gO = k => {try{return JSON.parse(localStorage.getItem(k))||{}}catch(e){return{}}};
const sO = async (k, v) => {
    try {
        localStorage.setItem(k, JSON.stringify(v));
        await cloudSync('save', k, v);
    } catch(e) {}
};

// IndexedDB
let idb=null;
function initIDB(){return new Promise(r=>{try{const q=indexedDB.open('BS_IMG',1);q.onupgradeneeded=e=>{if(!e.target.result.objectStoreNames.contains('i'))e.target.result.createObjectStore('i',{keyPath:'id'})};q.onsuccess=e=>{idb=e.target.result;r()};q.onerror=()=>r()}catch(e){r()}})}
function sImg(id,d){return new Promise(r=>{if(!idb)return r();try{const t=idb.transaction('i','readwrite');t.objectStore('i').put({id,data:d});t.oncomplete=()=>r();t.onerror=()=>r()}catch(e){r()}})}
function gImg(id){return new Promise(r=>{if(!idb)return r(null);try{const t=idb.transaction('i','readonly');const q=t.objectStore('i').get(id);q.onsuccess=()=>r(q.result?q.result.data:null);q.onerror=()=>r(null)}catch(e){r(null)}})}

// ★★★ SMART CATEGORY DETECTION KEYWORDS ★★★
const CATS=[
  {id:'fruits',n:'خضر وفواكه',i:'🥬',kw:['خضر','فواكه','طماطم','بطاطا','تفاح','برتقال','بصل','فلفل','جزر','خيار','خس','موز','عنب','فراولة','ليمون','بطيخ','كوسة','باذنجان','ثوم','بازلاء','سبانخ','نعناع','بقدونس','fruits','vegetables','légumes']},
  {id:'butcher',n:'جزارة',i:'🥩',kw:['لحم','جزار','دجاج','كباب','مرقاز','ستيك','لحوم','بقر','غنم','خروف','meat','viande','poulet','butcher']},
  {id:'bakery',n:'مخابز',i:'🍞',kw:['خبز','مخبز','كرواسون','بيتزا','حلويات','كعك','بسكويت','فطائر','bread','bakery','boulangerie','gâteau','cake']},
  {id:'grocery',n:'بقالة',i:'🛒',kw:['بقالة','سكر','زيت','أرز','معكرونة','حليب','جبن','عصير','شاي','قهوة','grocery','épicerie']},
  {id:'homefood',n:'أكلات منزلية',i:'🍲',kw:['أكلات','منزلي','طبخ','كسكس','شوربة','طاجين','محاجب','بوراك','homefood']},
  {id:'restaurant',n:'مطاعم',i:'🍽️',kw:['مطعم','وجبات','سندويش','شاورما','برغر','بيتزا','restaurant','fast food']},
  {id:'phones',n:'هواتف',i:'📱',kw:['هاتف','موبايل','سامسونغ','آيفون','هواوي','شاومي','أوبو','ريدمي','phone','samsung','iphone','huawei','xiaomi','oppo','realme','infinix','tecno','smartphone','mobile','جوال','تلفون','غلاف','شاحن','سماعات','إكسسوارات هاتف']},
  {id:'computers',n:'كمبيوتر',i:'💻',kw:['كمبيوتر','لابتوب','حاسوب','شاشة','لوحة مفاتيح','ماوس','طابعة','computer','laptop','pc','clavier','écran','imprimante']},
  {id:'electronics',n:'إلكترونيات',i:'🔌',kw:['إلكتروني','تلفزيون','ريسيفر','كاميرا','بطارية','شاحن','سبيكر','سماعة','electronic','tv','camera','speaker']},
  {id:'cars',n:'سيارات',i:'🚗',kw:['سيارة','سيارات','رينو','بيجو','هيونداي','تويوتا','فولكسفاغن','car','voiture','auto','renault','peugeot','hyundai','toyota']},
  {id:'motorcycles',n:'دراجات نارية',i:'🏍️',kw:['دراجة نارية','موتو','سكوتر','moto','motorcycle','scooter']},
  {id:'bicycles',n:'دراجات هوائية',i:'🚲',kw:['دراجة هوائية','فيلو','vélo','bicycle']},
  {id:'parts',n:'قطع غيار',i:'🔧',kw:['قطع غيار','فلتر','زيت محرك','فرامل','إطارات','بطارية سيارة','pièces','spare parts']},
  {id:'furniture',n:'أثاث',i:'🛋️',kw:['أثاث','كنبة','سرير','طاولة','خزانة','كرسي','صالون','meuble','furniture','canapé','lit','table']},
  {id:'decor',n:'ديكور',i:'🖼️',kw:['ديكور','لوحة','ستائر','سجاد','مرآة','décor','rideau','tapis']},
  {id:'household',n:'أدوات منزلية',i:'🏠',kw:['منزل','مطبخ','قدر','صحون','ملعقة','غسالة','ثلاجة','مكنسة','ménage','cuisine','household']},
  {id:'menclothes',n:'ملابس رجالية',i:'👔',kw:['ملابس رجال','قميص','بنطلون','جاكيت','بدلة','كوستيم','رجالي','homme','men','chemise','pantalon','costume']},
  {id:'womenclothes',n:'ملابس نسائية',i:'👗',kw:['ملابس نساء','فستان','حجاب','عباية','جلابة','قفطان','نسائي','femme','women','robe','hijab']},
  {id:'kidclothes',n:'ملابس أطفال',i:'👶',kw:['أطفال','بيبي','طفل','ملابس أطفال','enfant','bébé','kids']},
  {id:'shoes',n:'أحذية',i:'👟',kw:['حذاء','أحذية','صندل','نعل','رياضي','كروكس','chaussure','shoes','baskets']},
  {id:'jewelry',n:'مجوهرات',i:'💎',kw:['مجوهرات','ذهب','فضة','خاتم','سلسلة','أقراط','bijoux','or','argent','jewelry']},
  {id:'watches',n:'ساعات',i:'⌚',kw:['ساعة','ساعات','montre','watch']},
  {id:'tailor',n:'خياطة',i:'✂️',kw:['خياطة','تفصيل','قماش','couture','tailor','tissu']},
  {id:'barber',n:'حلاقة رجالية',i:'💈',kw:['حلاقة','حلاق','coiffeur','barber']},
  {id:'salon',n:'حلاقة نسائية',i:'💇',kw:['صالون','تجميل','مكياج','salon','coiffeuse','beauté','makeup']},
  {id:'carpenter',n:'نجارة',i:'🪵',kw:['نجارة','نجار','خشب','menuiserie','bois']},
  {id:'blacksmith',n:'حدادة',i:'⚒️',kw:['حدادة','حديد','لحام','fer','soudure']},
  {id:'electrician',n:'كهربائي',i:'⚡',kw:['كهربائي','كهرباء','électricien','electrician']},
  {id:'plumber',n:'سباكة',i:'🔧',kw:['سباك','سباكة','حنفية','plombier','plumber']},
  {id:'painter',n:'دهان',i:'🎨',kw:['دهان','صباغة','طلاء','peinture','painter']},
  {id:'handcraft',n:'حرف يدوية',i:'🧶',kw:['حرف','يدوي','صناعة تقليدية','كروشيه','تريكو','artisanat','handcraft']},
  {id:'lawyer',n:'محامين',i:'⚖️',kw:['محامي','محاماة','قانون','avocat','lawyer']},
  {id:'notary',n:'كاتب عمومي',i:'📝',kw:['كاتب عمومي','وثائق','notaire']},
  {id:'accountant',n:'محاسبين',i:'🧮',kw:['محاسب','محاسبة','comptable']},
  {id:'translator',n:'ترجمة',i:'🌐',kw:['ترجمة','مترجم','traduction','translator']},
  {id:'internet',n:'قاعات إنترنت',i:'🌐',kw:['إنترنت','سايبر','cyber','internet']},
  {id:'design',n:'تصميم',i:'🎨',kw:['تصميم','جرافيك','فوتوشوب','design','graphic','photoshop']},
  {id:'digital',n:'خدمات رقمية',i:'💻',kw:['رقمي','خدمة رقمية','digital','numérique']},
  {id:'bookstore',n:'مكتبات',i:'📚',kw:['مكتبة','كتب','قرطاسية','librairie','books','papeterie']},
  {id:'school',n:'لوازم مدرسية',i:'🎒',kw:['مدرسة','مدرسي','محفظة','دفتر','أقلام','scolaire','école']},
  {id:'tutoring',n:'دروس خصوصية',i:'📖',kw:['دروس','خصوصي','تعليم','cours','tutoring']},
  {id:'pets',n:'حيوانات أليفة',i:'🐾',kw:['حيوان','قط','كلب','عصفور','أرنب','سمك','animal','chat','chien','oiseau','pet']},
  {id:'used',n:'سوق المستعمل',i:'🔄',kw:['مستعمل','occasion','used','للبيع']},
  {id:'sports',n:'رياضة',i:'🏋️',kw:['رياضة','رياضي','كرة','sport','fitness','gym']},
  {id:'misc',n:'متنوعات',i:'🛍️',kw:['متنوع','أخرى','divers','misc']}
];
let cMer=null,mImgs=[],aImgs=[],compFilter='all';

function ntf(m,t='ok'){const n=$('ntf');n.textContent=m;n.className='notif '+t+' show';setTimeout(()=>n.classList.remove('show'),3500)}
function nav(p){document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_'+p).classList.add('act');if(p==='home')renderProds();if(p==='jobs')renderJobs();scrollTo(0,0)}
function oMod(id){$(id).classList.add('act');if(id==='contactMod')loadPublicContact()}
function cMod(id){$(id).classList.remove('act')}
document.querySelectorAll('.mov').forEach(o=>o.addEventListener('click',e=>{if(e.target===o)o.classList.remove('act')}));

function renderCats(){$('catsBar').innerHTML=CATS.map(c=>`<div class="cat-item" onclick="openCat('${c.id}')"><div class="cat-ico">${c.i}</div><div class="cat-nm">${c.n}</div></div>`).join('')}
function fillCatSel(){const h='<option value="">-- القسم --</option>'+CATS.map(c=>`<option value="${c.id}">${c.i} ${c.n}</option>`).join('');['npCat','apPCat'].forEach(id=>{const s=$(id);if(s)s.innerHTML=h})}
function openCat(cid){const c=CATS.find(x=>x.id===cid);if(!c)return;document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_cat').classList.add('act');$('catTitle').textContent=c.i+' '+c.n;renderCards(allProds().filter(p=>p.category===cid),'catGrid');scrollTo(0,0)}

function detectCategory(name,desc=''){
  const text=(name+' '+desc).toLowerCase();
  let best=null,bestScore=0;
  for(const cat of CATS){
    if(cat.id==='misc')continue;
    let score=0;
    for(const kw of cat.kw){ if(text.includes(kw.toLowerCase())) score+=kw.length; }
    if(score>bestScore){bestScore=score;best=cat.id}
  }
  return best||'misc';
}

function allProds(){
  const stores=gA(D.s),prods=gA(D.p),admP=gA(D.ap);let v=[];
  prods.forEach(p=>{const s=stores.find(x=>x.id===p.sid);if(s&&s.on!==false)v.push({...p,sName:s.name,sType:s.type})});
  admP.forEach(p=>v.push({...p,sName:'BABA SANOOD',sType:'admin',sid:'admin'}));
  return v.sort((a,b)=>(b.ts||0)-(a.ts||0));
}

async function renderProds(){const p=allProds(),g=$('mainGrid'),e=$('emptyMsg');if(!p.length){g.innerHTML='';e.style.display='block';return}e.style.display='none';g.innerHTML='';for(const x of p)g.innerHTML+=await mkCard(x)}
async function renderCards(arr,gid){const g=$(gid);if(!arr.length){g.innerHTML='<div class="empty"><div class="eico">📭</div><p>لا توجد منتجات</p></div>';return}g.innerHTML='';for(const x of arr)g.innerHTML+=await mkCard(x)}

async function mkCard(p){
  let img='<div class="pimg">📷</div>';
  if(p.imgs&&p.imgs.length){
    const f=p.imgs[0];let src=f;
    if(!f.startsWith('data:')&&!f.startsWith('http'))src=await gImg(f);
    if(src)img=`<div class="pimg"><img src="${src}" onerror="this.parentElement.innerHTML='📷'"></div>`;
  }
  else if(p.imgUrl)img=`<div class="pimg"><img src="${p.imgUrl}" onerror="this.parentElement.innerHTML='📷'"></div>`;
  const ini=(p.sName||'?')[0],pr=p.price?Number(p.price).toLocaleString()+' دج':'السعر';
  const st=gA(D.s).find(s=>s.id===p.sid);
  let acts='';
  if(st&&st.fb)acts+=`<button class="abtn msg" onclick="event.stopPropagation();window.open('${st.fb}','_blank')">📱</button>`;
  if(st&&st.ph)acts+=`<button class="abtn cal" onclick="event.stopPropagation();location.href='tel:${st.ph}'">📞</button>`;
  acts+=`<button class="abtn ord" onclick="event.stopPropagation();oOrd('${p.id}','${p.sid}')">🛒</button>`;
  return`<div class="pcard" onclick="openDet('${p.id}')">${img}<div class="pinfo"><div class="pname">${p.name||''}</div><div class="pprice">${pr}</div><div class="pstore" onclick="event.stopPropagation();openSt('${p.sid}')"><div class="av">${ini}</div><span>${p.sName||''}</span></div><div class="pacts">${acts}</div></div></div>`;
}

async function openDet(pid){const p=allProds().find(x=>x.id===pid);if(!p)return;document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_det').classList.add('act');let imgs='';if(p.imgs&&p.imgs.length){for(const im of p.imgs){let s=im;if(!im.startsWith('data:')&&!im.startsWith('http'))s=await gImg(im);if(s)imgs+=`<img src="${s}" onerror="this.remove()">`}}else if(p.imgUrl)imgs=`<img src="${p.imgUrl}" onerror="this.remove()">`;if(!imgs)imgs='<div style="width:280px;height:280px;background:#f0f0f0;display:flex;align-items:center;justify-content:center;border-radius:10px;font-size:50px">📷</div>';const pr=p.price?Number(p.price).toLocaleString()+' دج':'السعر';const st=gA(D.s).find(s=>s.id===p.sid);let acts='';if(st&&st.fb)acts+=`<button class="abtn msg" onclick="window.open('${st.fb}','_blank')">📱 مسنجر</button>`;if(st&&st.ph)acts+=`<button class="abtn cal" onclick="location.href='tel:${st.ph}'">📞 اتصال</button>`;acts+=`<button class="abtn ord" onclick="oOrd('${p.id}','${p.sid}')">🛒 طلب</button>`;$('detContent').innerHTML=`<div style="background:#fff;border-radius:12px;overflow:hidden;box-shadow:var(--sh)"><div class="det-imgs">${imgs}</div><div class="det-info"><h1>${p.name}</h1><div class="dprice">${pr}</div><div class="ddesc">${p.description||''}</div><div style="margin-bottom:12px"><b>المتجر:</b> <span style="cursor:pointer;color:var(--pr)" onclick="openSt('${p.sid}')">${p.sName}</span></div>${p.delivery==='yes'?'<div style="color:var(--suc);margin-bottom:12px">✅ التوصيل متاح</div>':''}<div class="det-acts">${acts}</div></div></div>`;scrollTo(0,0)}

async function openSt(sid){document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_store').classList.add('act');if(sid==='admin'){$('storeHdr').innerHTML='<div style="display:flex;align-items:center;gap:12px"><div class="sav" style="width:55px;height:55px;font-size:22px">🛒</div><div><h2>BABA SANOOD</h2><p style="color:#888">المتجر الرسمي</p></div></div>';await renderCards(gA(D.ap).map(p=>({...p,sName:'BABA SANOOD',sid:'admin'})),'storeGrid')}else{const s=gA(D.s).find(x=>x.id===sid);if(!s)return;let ct='';if(s.fb)ct+=`<a href="${s.fb}" target="_blank" style="color:var(--pr)">📱 فيسبوك</a> `;if(s.ph)ct+=`<a href="tel:${s.ph}" style="color:var(--suc)">📞 ${s.ph}</a>`;$('storeHdr').innerHTML=`<div style="display:flex;align-items:center;gap:12px"><div class="sav" style="width:55px;height:55px;font-size:22px">${s.name[0]}</div><div><h2>${s.name}</h2><p style="color:#888">${s.type||''}</p><div style="margin-top:6px">${ct}</div></div></div>`;await renderCards(gA(D.p).filter(p=>p.sid===sid).map(p=>({...p,sName:s.name})),'storeGrid')}scrollTo(0,0)}

function regStore(){
  const nm=$('rName').value.trim(),tp=$('rType').value,em=$('rEmail').value.trim(),ph=$('rPhone').value.trim(),pw=$('rPass').value;
  if(!nm)return ntf('أدخل اسم المتجر','er');if(!tp)return ntf('اختر النوع','er');if(!pw)return ntf('أدخل كلمة السر','er');if(!em&&!ph)return ntf('أدخل إيميل أو هاتف','er');
  if(!$('privacyAgree').checked)return ntf('يجب الموافقة على سياسة الخصوصية وشروط الاستخدام','er');
  const ss=gA(D.s);if(ss.find(s=>s.name.toLowerCase()===nm.toLowerCase()))return ntf('الاسم موجود!','er');
  ss.push({id:'s_'+Date.now(),name:nm,type:tp,email:em,ph,password:pw,fb:'',desc:'',on:true,ts:Date.now(),agreedPrivacy:true});
  sA(D.s,ss);cMod('regMod');ntf('🎉 تم إنشاء "'+nm+'" بنجاح!');
  setTimeout(()=>{$('lName').value=nm;$('lPass').value=pw;oMod('logMod')},800);
}

function mLogin(){const nm=$('lName').value.trim(),pw=$('lPass').value;if(!nm||!pw)return ntf('أدخل البيانات','er');const s=gA(D.s).find(x=>x.name.toLowerCase()===nm.toLowerCase()&&x.password===pw);if(!s)return ntf('بيانات خاطئة','er');if(s.on===false)return ntf('متجرك معطّل','er');cMer=s;if($('lRem').checked)localStorage.setItem('bs_rem',JSON.stringify({n:nm,p:pw}));cMod('logMod');openDash();ntf('مرحباً في "'+s.name+'" ✅')}
function loadRem(){try{const r=localStorage.getItem('bs_rem');if(r){const{n,p}=JSON.parse(r);$('lName').value=n||'';$('lPass').value=p||'';$('lRem').checked=true}}catch(e){}}
function mLogout(){cMer=null;mImgs=[];nav('home')}

function openDash(){document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_dash').classList.add('act');$('dName').textContent='📊 '+cMer.name;$('sName').value=cMer.name;$('sFb').value=cMer.fb||'';$('sPh').value=cMer.ph||'';$('sDesc').value=cMer.desc||'';renderMyP();renderMyOrd();loadAdminContactForMerchant();document.querySelectorAll('#dNav .dtab').forEach(t=>t.classList.remove('act'));document.querySelectorAll('#pg_dash .dsec').forEach(s=>s.classList.remove('act'));document.querySelector('#dNav .dtab').classList.add('act');$('dProds').classList.add('act');scrollTo(0,0)}
function dTab(el,t){document.querySelectorAll('#dNav .dtab').forEach(x=>x.classList.remove('act'));document.querySelectorAll('#pg_dash .dsec').forEach(x=>x.classList.remove('act'));el.classList.add('act');$({prods:'dProds',addP:'dAddP',ords:'dOrds',sett:'dSett',mComp:'dMComp'}[t]).classList.add('act');if(t==='addP'){mImgs=[];$('mPrevs').innerHTML=''}if(t==='mComp')renderMerchCompHistory()}

function setupFiles(){
  $('mFileIn').onchange=function(){procImgs(this.files,'m');this.value=''};
  $('aFileIn').onchange=function(){procImgs(this.files,'a');this.value=''};
  $('csvIn').onchange=function(){if(this.files[0])procCSV(this.files[0]);this.value=''};
  ['mUpArea','aUpArea'].forEach(id=>{const a=$(id),t=id==='mUpArea'?'m':'a';a.ondragover=e=>{e.preventDefault();a.classList.add('dov')};a.ondragleave=()=>a.classList.remove('dov');a.ondrop=e=>{e.preventDefault();a.classList.remove('dov');if(e.dataTransfer.files.length)procImgs(e.dataTransfer.files,t)}});
  const ca=$('csvArea');ca.ondragover=e=>{e.preventDefault();ca.classList.add('dov')};ca.ondragleave=()=>ca.classList.remove('dov');ca.ondrop=e=>{e.preventDefault();ca.classList.remove('dov');if(e.dataTransfer.files.length)procCSV(e.dataTransfer.files[0])};
}

function procImgs(files,t){
  const arr=t==='m'?mImgs:aImgs,pid=t==='m'?'mPrevs':'aPrevs',mx=5;
  if(arr.length>=mx)return ntf('الحد '+mx+' صور','er');
  const rem=mx-arr.length,ok=Array.from(files).filter(f=>f.type.startsWith('image/')).slice(0,rem);
  if(!ok.length)return ntf('صور فقط','er');
  let done=0;
  ok.forEach((f,i)=>{if(f.size>15e6)return ntf('كبيرة جداً','er');const r=new FileReader();r.onload=async ev=>{const d=ev.target.result;const comp=await new Promise(res=>{const img=new Image();img.onload=()=>{try{const c=document.createElement('canvas');let w=img.width,h=img.height;if(w>800){h=800/w*h;w=800}c.width=w;c.height=h;c.getContext('2d').drawImage(img,0,0,w,h);res(c.toDataURL('image/jpeg',.7))}catch(e){res(d)}};img.onerror=()=>res(d);img.src=d});const id='im_'+Date.now()+'_'+i+'_'+Math.random().toString(36).slice(2,6);await sImg(id,comp);arr.push(id);done++;await showPrev(arr,pid,t);if(done===ok.length)ntf('✅ '+done+' صورة')};r.readAsDataURL(f)});
}
async function showPrev(arr,cid,t){const c=$(cid);c.innerHTML='';for(let i=0;i<arr.length;i++){const id=arr[i];let src=id.startsWith('data:')||id.startsWith('http')?id:await gImg(id);if(!src)continue;const d=document.createElement('div');d.className='prev-item';d.innerHTML=`<img src="${src}"><button class="rm" data-i="${i}" data-t="${t}">✕</button>`;d.querySelector('.rm').onclick=function(e){e.preventDefault();e.stopPropagation();const idx=+this.dataset.i,tp=this.dataset.t;if(tp==='m'){mImgs.splice(idx,1);showPrev(mImgs,'mPrevs','m')}else{aImgs.splice(idx,1);showPrev(aImgs,'aPrevs','a')}};c.appendChild(d)}}

function addProd(){if(!cMer)return ntf('سجل الدخول','er');const nm=$('npName').value.trim(),pr=$('npPrice').value,ct=$('npCat').value,ds=$('npDesc').value.trim(),dl=$('npDel').value;if(!nm)return ntf('الاسم','er');if(!pr)return ntf('السعر','er');if(!ct)return ntf('القسم','er');const mt=[];if($('omMsg').checked)mt.push('msg');if($('omPh').checked)mt.push('ph');if($('omIn').checked)mt.push('in');const ps=gA(D.p);ps.push({id:'p_'+Date.now(),sid:cMer.id,name:nm,price:+pr,category:ct,description:ds,delivery:dl,methods:mt,imgs:[...mImgs],ts:Date.now()});sA(D.p,ps);$('npName').value='';$('npPrice').value='';$('npCat').value='';$('npDesc').value='';mImgs=[];$('mPrevs').innerHTML='';ntf('✅ تم النشر!');renderMyP();renderProds()}
async function renderMyP(){if(!cMer)return;const ps=gA(D.p).filter(p=>p.sid===cMer.id),c=$('myProds');if(!ps.length){c.innerHTML='<div class="empty"><div class="eico">📦</div><p>لا منتجات</p></div>';return}let h='<table class="dtbl"><thead><tr><th>صورة</th><th>المنتج</th><th>السعر</th><th>حذف</th></tr></thead><tbody>';for(const p of ps){let img='📷';if(p.imgs&&p.imgs.length){const f=p.imgs[0];let s=f.startsWith('data:')||f.startsWith('http')?f:await gImg(f);if(s)img=`<img src="${s}" style="width:42px;height:42px;object-fit:cover;border-radius:5px" onerror="this.outerHTML='📷'">`}h+=`<tr><td>${img}</td><td>${p.name}</td><td>${(+p.price).toLocaleString()} دج</td><td><button onclick="delP('${p.id}')" style="background:var(--dan);color:#fff;border:none;padding:4px 10px;border-radius:6px;cursor:pointer">🗑️</button></td></tr>`}c.innerHTML=h+'</tbody></table>'}
function delP(id){if(!confirm('حذف؟'))return;sA(D.p,gA(D.p).filter(p=>p.id!==id));renderMyP();renderProds();ntf('حذف','inf')}
function saveSett(){if(!cMer)return;const ss=gA(D.s),i=ss.findIndex(s=>s.id===cMer.id);if(i<0)return;ss[i].name=$('sName').value.trim()||ss[i].name;ss[i].fb=$('sFb').value.trim();ss[i].ph=$('sPh').value.trim();ss[i].desc=$('sDesc').value.trim();sA(D.s,ss);cMer=ss[i];$('dName').textContent='📊 '+cMer.name;ntf('✅ حفظ')}

function oOrd(pid,sid){$('oPid').value=pid;$('oSid').value=sid;oMod('ordMod')}
function subOrd(){const nm=$('oName').value.trim(),ph=$('oPhone').value.trim();if(!nm)return ntf('اسمك','er');if(!ph)return ntf('الهاتف','er');const pid=$('oPid').value,sid=$('oSid').value,all=[...gA(D.p),...gA(D.ap)],pr=all.find(p=>p.id===pid);const os=gA(D.o);os.push({id:'o_'+Date.now(),sid,pid,pName:pr?pr.name:'?',cName:nm,cPh:ph,wil:$('oWil').value.trim(),addr:$('oAddr').value.trim(),notes:$('oNotes').value.trim(),st:'جديد',ts:Date.now()});sA(D.o,os);cMod('ordMod');['oName','oPhone','oWil','oAddr','oNotes'].forEach(id=>$(id).value='');ntf('✅ تم الطلب!')}
function renderMyOrd(){if(!cMer)return;const os=gA(D.o).filter(o=>o.sid===cMer.id),c=$('mOrds');if(!os.length){c.innerHTML='<div class="empty"><div class="eico">📋</div><p>لا طلبات</p></div>';return}c.innerHTML='<table class="dtbl"><thead><tr><th>المنتج</th><th>الزبون</th><th>الهاتف</th><th>الولاية</th></tr></thead><tbody>'+os.slice().reverse().map(o=>`<tr><td>${o.pName}</td><td>${o.cName}</td><td>${o.cPh}</td><td>${o.wil||'-'}</td></tr>`).join('')+'</tbody></table>'}

function procCSV(file){
  const ext=file.name.split('.').pop().toLowerCase();
  if(!['csv','txt'].includes(ext)&&!file.type.includes('csv')&&!file.type.includes('text'))return ntf('ارفع CSV','er');
  $('csvFn').textContent='📄 '+file.name;$('csvFn').classList.add('show');ntf('⏳ جاري القراءة...','inf');
  const r=new FileReader();r.onload=e=>{try{parseCSV(e.target.result)}catch(er){ntf('❌ '+er.message,'er')}};r.onerror=()=>ntf('❌ فشل','er');r.readAsText(file,'UTF-8');
}
function parseCSV(txt){
  txt=txt.replace(/^\uFEFF/,'');const fl=txt.split('\n')[0]||'';let dl=',';
  if((fl.match(/;/g)||[]).length>(fl.match(/,/g)||[]).length)dl=';';
  else if((fl.match(/\t/g)||[]).length>(fl.match(/,/g)||[]).length)dl='\t';
  const lines=txt.split(/\r?\n/).map(l=>l.trim()).filter(l=>l);
  if(lines.length<2)return ntf('❌ ملف فارغ','er');
  const hds=csvSplit(lines[0],dl).map(h=>h.toLowerCase().replace(/['"]/g,'').trim());
  const ni=fCol(hds,['name','product_name','اسم','title','اسم المنتج','nom']);
  const pi=fCol(hds,['price','original_price','سعر','السعر','prix','cost']);
  const ii=fCol(hds,['image','image_url','img','صورة','photo','url','الصورة','image_src']);
  const di=fCol(hds,['description','desc','الوصف','وصف','detail']);
  const ci=fCol(hds,['category','cat','القسم','الفئة','type','categorie']);
  let ok=0,fl2=0,catStats={};const ap=gA(D.ap);
  for(let i=1;i<lines.length;i++){
    try{
      const cols=csvSplit(lines[i],dl);if(cols.length<2){fl2++;continue}
      const nm=clean(ni>=0?cols[ni]:cols[0]||'');if(!nm){fl2++;continue}
      let pr=clean(pi>=0?cols[pi]:cols[1]||'0').replace(/[^\d.,]/g,'').replace(',','.');
      let num=Math.round((parseFloat(pr)||0)*1.2);
      const im=clean(ii>=0&&cols[ii]?cols[ii]:''), ds=clean(di>=0&&cols[di]?cols[di]:''), rawCat=clean(ci>=0&&cols[ci]?cols[ci]:'');
      let mc='misc';if(rawCat){const fc=CATS.find(c=>c.n.includes(rawCat)||c.id===rawCat.toLowerCase());if(fc)mc=fc.id;else mc=detectCategory(nm+' '+rawCat,ds);}else mc=detectCategory(nm,ds);
      catStats[mc]=(catStats[mc]||0)+1;
      ap.push({id:'ap_'+Date.now()+'_'+i,name:nm,price:num,imgUrl:im,imgs:im?[im]:[],description:ds,category:mc,delivery:'yes',sid:'admin',ts:Date.now()+i});
      ok++;
    }catch(e){fl2++;}
  }
  sA(D.ap,ap);
  let catHtml='<div style="margin-top:8px"><b>📊 التوزيع على الأقسام:</b><div style="display:flex;flex-wrap:wrap;gap:4px;margin-top:4px">';
  for(const[cid,cnt]of Object.entries(catStats)){const c=CATS.find(x=>x.id===cid);catHtml+=`<span class="smart-cat-badge">${c?c.i:''} ${c?c.n:cid}: ${cnt}</span>`}
  catHtml+='</div></div>';
  const rs=$('csvRes');rs.classList.add('show');rs.innerHTML=`<div style="color:var(--suc);font-weight:700">✅ ${ok} منتج (+20%)</div>${fl2?`<div style="color:var(--dan);font-size:12px">❌ فشل ${fl2}</div>`:''}${catHtml}`;
  ntf('✅ '+ok+' منتج!');$('admPCount').textContent=gA(D.ap).length;renderAdmP();renderProds();
}
function clean(s){return(s||'').replace(/^["'\s]+|["'\s]+$/g,'').trim()}
function csvSplit(l,d){const r=[];let c='',q=false;for(let i=0;i<l.length;i++){const ch=l[i];if(ch==='"'){if(q&&l[i+1]==='"'){c+='"';i++}else q=!q}else if(ch===d&&!q){r.push(c);c=''}else c+=ch}r.push(c);return r}
function fCol(h,ns){for(let i=0;i<h.length;i++){const x=h[i];for(const n of ns)if(x===n||x.includes(n))return i}return -1}

function addAdmProd(){const nm=$('apPName').value.trim(),pr=$('apPPrice').value;if(!nm||!pr)return ntf('أكمل البيانات','er');const fp=Math.round(+pr*1.2);const cat=$('apPCat').value||detectCategory(nm,$('apPDesc').value);const ap=gA(D.ap);ap.push({id:'ap_'+Date.now(),name:nm,price:fp,category:cat,description:$('apPDesc').value.trim(),imgs:[...aImgs],delivery:'yes',sid:'admin',ts:Date.now()});sA(D.ap,ap);$('apPName').value='';$('apPPrice').value='';$('apPDesc').value='';aImgs=[];$('aPrevs').innerHTML='';ntf('✅ '+fp.toLocaleString()+' دج');renderAdmP();renderProds()}
async function renderAdmP(){const ap=gA(D.ap),c=$('amMyProds');$('admPCount').textContent=ap.length;if(!ap.length){c.innerHTML='<div class="empty">📦 لا منتجات</div>';return}let h='<table class="dtbl"><thead><tr><th>صورة</th><th>المنتج</th><th>السعر</th><th>القسم</th><th>حذف</th></tr></thead><tbody>';for(const p of ap.slice(-50).reverse()){let img='📷';if(p.imgs&&p.imgs.length){const f=p.imgs[0];let s=(f.startsWith('data:')||f.startsWith('http'))?f:await gImg(f);if(s)img=`<img src="${s}" style="width:42px;height:42px;object-fit:cover;border-radius:5px">`}const cat=CATS.find(x=>x.id===p.category);h+=`<tr><td>${img}</td><td>${p.name}</td><td>${p.price.toLocaleString()}</td><td>${cat?cat.n:'?'}</td><td><button onclick="delAP('${p.id}')">🗑️</button></td></tr>`}c.innerHTML=h+'</tbody></table>'}
function delAP(id){if(!confirm('حذف؟'))return;sA(D.ap,gA(D.ap).filter(p=>p.id!==id));renderAdmP();renderProds();}

function saveContact(){sO(D.ct,{ph:$('adPh').value.trim(),wa:$('adWa').value.trim(),email:$('adEmail').value.trim(),fb:$('adFb').value.trim(),addr:$('adAddr').value.trim(),hours:$('adHours').value.trim()});ntf('✅ تم الحفظ');updateFooterContact();}
function loadAdminContact(){const c=gO(D.ct);$('adPh').value=c.ph||'';$('adWa').value=c.wa||'';$('adEmail').value=c.email||'';$('adFb').value=c.fb||'';$('adAddr').value=c.addr||'';$('adHours').value=c.hours||''}
function loadPublicContact(){const c=gO(D.ct);let h='<div class="contact-box"><h4>📞 معلومات الاتصال بالإدارة</h4>';if(c.ph)h+=`<div class="ci"><span>📱</span><a href="tel:${c.ph}">${c.ph}</a></div>`;if(c.wa)h+=`<div class="ci"><span>📱</span><a href="https://wa.me/${c.wa}" target="_blank">واتساب: ${c.wa}</a></div>`;if(c.email)h+=`<div class="ci"><span>📧</span><a href="mailto:${c.email}">${c.email}</a></div>`;h+='</div>';$('publicContactInfo').innerHTML=h}
function loadAdminContactForMerchant(){const c=gO(D.ct);let h='<div class="contact-box"><h4>📞 معلومات الإدارة</h4>';if(c.ph)h+=`<div class="ci"><span>📱</span>${c.ph}</div>`;if(c.email)h+=`<div class="ci"><span>📧</span>${c.email}</div>`;h+='</div>';$('adminContactInfo').innerHTML=h}
function updateFooterContact(){const c=gO(D.ct);let h='';if(c.ph)h+=`📱 ${c.ph}<br>`;if(c.email)h+=`📧 ${c.email}`;$('footerContact').innerHTML=h}

function subMerchComp(){if(!cMer)return;const txt=$('mCompTxt').value.trim(),tp=$('mCompType').value;if(!txt)return ntf('اكتب الرسالة','er');const cs=gA(D.c);cs.push({id:'c_'+Date.now(),txt,type:tp,from:'store',storeName:cMer.name,storeId:cMer.id,ts:Date.now()});sA(D.c,cs);$('mCompTxt').value='';ntf('✅ تم الإرسال');renderMerchCompHistory();}
function renderMerchCompHistory(){if(!cMer)return;const cs=gA(D.c).filter(c=>c.storeId===cMer.id);const c=$('mCompHistory');if(!cs.length){c.innerHTML='<p style="color:#aaa;font-size:12px">لا رسائل</p>';return}c.innerHTML='<h4>📬 رسائلي السابقة</h4>'+cs.slice().reverse().map(x=>`<div class="comp-card from-store"><div class="comp-meta"><span>${x.type}</span><span>${new Date(x.ts).toLocaleString('ar')}</span></div><p>${x.txt}</p></div>`).join('');}

function subVisitorMsg(){const nm=$('vName').value.trim(),ct=$('vContact').value.trim(),tp=$('vType').value,msg=$('vMsg').value.trim();if(!nm||!msg)return ntf('أكمل البيانات','er');const cs=gA(D.c);cs.push({id:'c_'+Date.now(),txt:msg,type:tp,from:'visitor',visitorName:nm,visitorContact:ct,ts:Date.now()});sA(D.c,cs);$('vName').value='';$('vContact').value='';$('vMsg').value='';cMod('contactMod');ntf('✅ تم الإرسال!');}

function filterComp(el,f){compFilter=f;document.querySelectorAll('#amComp .dtab').forEach(x=>x.classList.remove('act'));el.classList.add('act');renderComp()}
function renderComp(){let cs=gA(D.c);if(compFilter==='store')cs=cs.filter(c=>c.from==='store');else if(compFilter==='visitor')cs=cs.filter(c=>c.from==='visitor');const c=$('compList');if(!cs.length){c.innerHTML='<div class="empty">📭 لا رسائل</div>';return}c.innerHTML=cs.slice().reverse().map(x=>`<div class="comp-card ${x.from==='store'?'from-store':'from-visitor'}"><div class="comp-meta"><span>${x.from==='store'?x.storeName:x.visitorName}</span><span>${new Date(x.ts).toLocaleString('ar')}</span></div><p>${x.txt}</p></div>`).join('');}

function admLogin(){if($('admPass').value==='04081985HMR'){cMod('admMod');document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_admin').classList.add('act');const a=gO(D.a);$('apName').value=a.n||'BABA SANOOD';$('apClr1').value=a.c1||'#1a73e8';$('apClr2').value=a.c2||'#ff6b35';loadAdminContact();renderAmSt();renderStats();renderComp();renderAdmP();ntf('مرحباً 🛡️');}else ntf('❌','er');$('admPass').value=''}
function aTab(el,t){document.querySelectorAll('#amNav .ambtn').forEach(x=>x.classList.remove('act'));document.querySelectorAll('#pg_admin .amsec').forEach(x=>x.classList.remove('act'));el.classList.add('act');$({look:'amLook',contact:'amContact',merch:'amMerch',stat:'amStat',comp:'amComp',myS:'amMyS'}[t]).classList.add('act');if(t==='myS')renderAdmP();if(t==='comp')renderComp()}
function saveApp(){sO(D.a,{n:$('apName').value.trim(),c1:$('apClr1').value,c2:$('apClr2').value});ntf('✅ حفظ')}
function renderAmSt(){const ss=gA(D.s),c=$('amStores');if(!ss.length){c.innerHTML='<div class="empty">🏪 لا متاجر</div>';return}c.innerHTML=ss.map(s=>`<div class="scard"><div class="sav">${s.name[0]}</div><div class="sinf"><h4>${s.name}</h4><p>${s.type}</p></div><div><label class="tgl"><input type="checkbox" ${s.on!==false?'checked':''} onchange="tglSt('${s.id}',this.checked)"><span></span></label></div></div>`).join('')}
function tglSt(id,on){const ss=gA(D.s),i=ss.findIndex(s=>s.id===id);if(i>=0){ss[i].on=on;sA(D.s,ss);renderAmSt();renderProds();}}
function renderStats(){const ss=gA(D.s),ps=gA(D.p),ap=gA(D.ap),os=gA(D.o),js=gA(D.j),cs=gA(D.c);$('amStats').innerHTML=`<div class="stat-grid"><div class="stat-card" style="background:#4CAF50"><div class="snum">${ss.length}</div><div class="slbl">متجر</div></div><div class="stat-card" style="background:#2196F3"><div class="snum">${ps.length+ap.length}</div><div class="slbl">منتج</div></div><div class="stat-card" style="background:#FF9800"><div class="snum">${os.length}</div><div class="slbl">طلب</div></div><div class="stat-card" style="background:#9C27B0"><div class="snum">${cs.length}</div><div class="slbl">رسالة</div></div></div>`;}

function jTab(el,t){document.querySelectorAll('#pg_jobs .jtab').forEach(x=>x.classList.remove('act'));document.querySelectorAll('#pg_jobs .dsec').forEach(x=>x.classList.remove('act'));el.classList.add('act');$({browse:'jBrowse',post:'jPost',seek:'jSeek'}[t]).classList.add('act');if(t==='browse')renderJobs()}
function postJob(){const co=$('jComp').value.trim(),tp=$('jType').value.trim(),ct=$('jCont').value.trim();if(!co||!tp||!ct)return ntf('أكمل البيانات','er');const js=gA(D.j);js.push({id:'j_'+Date.now(),co,tp,req:$('jReq').value.trim(),sal:$('jSal').value.trim(),loc:$('jLoc').value.trim(),ct,jt:'offer',ts:Date.now()});sA(D.j,js);['jComp','jType','jReq','jSal','jLoc','jCont'].forEach(id=>$(id).value='');ntf('✅ نشر')}
function subSeeker(){const nm=$('skName').value.trim(),sk=$('skSkill').value.trim(),ph=$('skPhone').value.trim();if(!nm||!sk||!ph)return ntf('أكمل البيانات','er');const js=gA(D.j);js.push({id:'js_'+Date.now(),co:nm,tp:sk,req:$('skExp').value.trim(),ct:ph,jt:'seek',ts:Date.now()});sA(D.j,js);['skName','skAge','skSkill','skExp','skPhone'].forEach(id=>$(id).value='');ntf('✅ تسجيل')}
function renderJobs(){const js=gA(D.j),c=$('jobList');if(!js.length){c.innerHTML='<div class="empty">💼 لا وظائف</div>';return}c.innerHTML=js.slice().reverse().map(j=>`<div class="jcard"><h3>${j.tp}</h3><p><b>${j.co}</b></p><p>${j.req||''}</p><div class="jmeta"><span>📞 ${j.ct}</span></div></div>`).join('')}

function doSearch(q){if(!q.trim()){renderProds();return}const ql=q.toLowerCase(),f=allProds().filter(p=>(p.name&&p.name.toLowerCase().includes(ql))||(p.sName&&p.sName.toLowerCase().includes(ql)));renderCards(f,'mainGrid')}

function infoPage(t){
  const pg={
    priv:{t:'🔒 سياسة الخصوصية',c:'<h3>حماية البيانات</h3><ul><li>نحمي بياناتك الشخصية</li><li>كل تاجر مسؤول عن محتواه</li></ul>'},
    terms:{t:'📜 شروط الاستخدام',c:'<h3>شروط استخدام المنصة</h3><ul><li>يمنع نشر محتوى مخالف</li><li>كل تاجر مسؤول قانونياً</li></ul>'},
    guide:{t:'📖 الدليل',c:'<h4>🛒 للمتسوقين:</h4><ol><li>تصفح المنتجات</li><li>اطلب عبر مسنجر أو اتصال</li></ol>'},
    faq:{t:'❓ أسئلة شائعة',c:'<p><b>كيف أفتح متجر؟</b><br>اضغط فتح متجر وسجل بياناتك</p>'},
    copy:{t:'©️ حقوق الملكية',c:'<p>© 2026 سوق تبسة العملاق - بابا سنود</p>'}
  };
  const p=pg[t];if(!p)return;
  const o=document.createElement('div');o.className='mov act';o.onclick=e=>{if(e.target===o)o.remove()};
  o.innerHTML=`<div class="mdl" style="max-width:650px"><div class="mdl-h"><h2>${p.t}</h2><button class="mdl-x" onclick="this.closest('.mov').remove()">✕</button></div><div class="mdl-b">${p.c}</div></div>`;
  document.body.appendChild(o);<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
<title>ســــــوق تبــــــــسة العمـــــــــــلاق - بــــــــــا بــــــــــــا ســـــــنـــــودــ</title>
<style>
:root{
  --pr:#1a73e8;--prd:#1557b0;--sec:#ff6b35;--suc:#28a745;
  --dan:#dc3545;--drk:#2c3e50;--rad:12px;
  --sh:0 2px 15px rgba(0,0,0,.1);
}
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Segoe UI',Tahoma,Arial,sans-serif;background:#f0f2f5;color:#333;min-height:100vh;line-height:1.6}

/* HEADER */
.hdr{background:linear-gradient(135deg,var(--pr),var(--prd));color:#fff;padding:10px 15px;position:sticky;top:0;z-index:1000;box-shadow:var(--sh)}
.hdr-row{display:flex;align-items:center;gap:10px;flex-wrap:wrap}
.logo{font-size:1.3em;font-weight:700;cursor:pointer;white-space:nowrap}
.logo b{color:var(--sec)}
.srch{flex:1;min-width:180px;max-width:500px}
.srch input{width:100%;padding:9px 16px;border:none;border-radius:25px;font-size:14px;outline:none}
.hdr-btns{display:flex;gap:4px;flex-wrap:wrap}
.hb{background:rgba(255,255,255,.18);color:#fff;border:none;padding:7px 12px;border-radius:18px;cursor:pointer;font-size:12px;transition:.3s;white-space:nowrap;font-family:inherit}
.hb:hover{background:rgba(255,255,255,.35)}
.hb.sh{opacity:.4;font-size:16px;padding:7px 8px}.hb.sh:hover{opacity:1}

/* CATEGORIES */
.cats{background:#fff;padding:12px 8px;overflow-x:auto;box-shadow:0 2px 5px rgba(0,0,0,.05)}
.cats-scroll{display:flex;gap:12px;padding:4px 8px;min-width:max-content}
.cat-item{display:flex;flex-direction:column;align-items:center;gap:5px;cursor:pointer;min-width:65px;transition:.3s}
.cat-item:hover{transform:translateY(-3px)}
.cat-ico{width:50px;height:50px;border-radius:50%;background:linear-gradient(135deg,#e3f2fd,#bbdefb);display:flex;align-items:center;justify-content:center;font-size:22px;box-shadow:0 2px 8px rgba(0,0,0,.1)}
.cat-nm{font-size:10px;text-align:center;color:#555;font-weight:500;max-width:70px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}

/* PRODUCTS */
.feed{padding:15px;max-width:1400px;margin:0 auto}
.stitle{font-size:1.2em;margin-bottom:15px;color:var(--drk);display:flex;align-items:center;gap:8px}
.pgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:12px}
.pcard{background:#fff;border-radius:var(--rad);overflow:hidden;box-shadow:var(--sh);transition:.3s;cursor:pointer}
.pcard:hover{transform:translateY(-4px);box-shadow:0 8px 25px rgba(0,0,0,.15)}
.pimg{width:100%;height:180px;background:#f5f5f5;display:flex;align-items:center;justify-content:center;color:#ccc;font-size:40px;overflow:hidden}
.pimg img{width:100%;height:100%;object-fit:cover}
.pinfo{padding:10px}
.pname{font-weight:600;font-size:13px;color:#333;height:36px;overflow:hidden;line-height:1.4}
.pprice{color:var(--sec);font-weight:700;font-size:15px;margin:4px 0 6px}
.pstore{display:flex;align-items:center;gap:5px;font-size:11px;color:#888;padding-top:6px;border-top:1px solid #eee}
.pstore .av{width:22px;height:22px;border-radius:50%;background:var(--pr);color:#fff;display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:700;flex-shrink:0}
.pacts{display:flex;gap:4px;margin-top:6px}
.abtn{flex:1;padding:5px 2px;border:none;border-radius:6px;font-size:11px;cursor:pointer;color:#fff;transition:.2s;text-align:center;font-family:inherit}
.abtn.msg{background:#0084ff}.abtn.cal{background:var(--suc)}.abtn.ord{background:var(--sec)}

/* MODALS */
.mov{display:none;position:fixed;inset:0;background:rgba(0,0,0,.55);z-index:2000;justify-content:center;align-items:flex-start;padding:15px;overflow-y:auto}
.mov.act{display:flex}
.mdl{background:#fff;border-radius:var(--rad);width:100%;max-width:560px;margin:20px auto;box-shadow:0 15px 50px rgba(0,0,0,.3);max-height:92vh;overflow-y:auto}
.mdl-h{padding:15px 18px;background:linear-gradient(135deg,var(--pr),var(--prd));color:#fff;border-radius:var(--rad) var(--rad) 0 0;display:flex;justify-content:space-between;align-items:center;position:sticky;top:0;z-index:5}
.mdl-h h2{font-size:1em;margin:0}
.mdl-x{background:rgba(255,255,255,.2);border:none;color:#fff;width:30px;height:30px;border-radius:50%;font-size:16px;cursor:pointer;display:flex;align-items:center;justify-content:center}
.mdl-b{padding:18px}

/* FORMS */
.fg{margin-bottom:14px}
.fg label{display:block;margin-bottom:5px;font-weight:600;font-size:13px;color:#444}
.fg input,.fg select,.fg textarea{width:100%;padding:9px 12px;border:2px solid #e0e0e0;border-radius:8px;font-size:13px;transition:.3s;font-family:inherit}
.fg input:focus,.fg select:focus,.fg textarea:focus{border-color:var(--pr);outline:none;box-shadow:0 0 0 3px rgba(26,115,232,.1)}
.fg textarea{min-height:70px;resize:vertical}
.fhint{font-size:10px;color:#aaa;margin-top:3px}
.sbtn{width:100%;padding:11px;background:linear-gradient(135deg,var(--pr),var(--prd));color:#fff;border:none;border-radius:8px;font-size:15px;font-weight:700;cursor:pointer;transition:.3s;font-family:inherit}
.sbtn:hover{transform:translateY(-2px);box-shadow:0 4px 12px rgba(26,115,232,.4)}
.sbtn.g{background:linear-gradient(135deg,var(--suc),#1e7e34)}
.sbtn.r{background:linear-gradient(135deg,var(--dan),#a71d2a)}
.sbtn:disabled{opacity:.5;cursor:not-allowed;transform:none}

/* IMAGE UPLOAD */
.uparea{border:3px dashed #ccc;border-radius:12px;padding:25px 10px;text-align:center;cursor:pointer;transition:.3s;background:#fafafa;position:relative;min-height:100px}
.uparea:hover,.uparea.dov{border-color:var(--pr);background:#e8f0fe}
.uparea .uico{font-size:36px;pointer-events:none}
.uparea .utxt{color:#666;font-size:13px;pointer-events:none}
.uparea .uhint{color:#aaa;font-size:11px;margin-top:4px;pointer-events:none}
.uparea input[type=file]{position:absolute;inset:0;opacity:0;cursor:pointer;z-index:5}
.previews{display:flex;flex-wrap:wrap;gap:8px;margin-top:8px}
.prev-item{position:relative;width:80px;height:80px;border-radius:8px;overflow:hidden;box-shadow:0 2px 6px rgba(0,0,0,.15)}
.prev-item img{width:100%;height:100%;object-fit:cover}
.prev-item .rm{position:absolute;top:2px;right:2px;background:rgba(220,53,69,.9);color:#fff;border:none;width:22px;height:22px;border-radius:50%;font-size:12px;cursor:pointer;display:flex;align-items:center;justify-content:center;z-index:5}

/* CSV */
.csv-area{border:3px dashed var(--suc);border-radius:12px;padding:25px 10px;text-align:center;cursor:pointer;transition:.3s;background:#f0fff0;position:relative;min-height:100px;margin-bottom:12px}
.csv-area:hover,.csv-area.dov{border-color:#1e7e34;background:#d4edda}
.csv-area input[type=file]{position:absolute;inset:0;opacity:0;cursor:pointer;z-index:5}
.csv-fn{margin-top:8px;padding:7px 12px;background:#d4edda;border-radius:8px;color:var(--suc);font-weight:700;display:none}
.csv-fn.show{display:block}
.csv-res{margin-top:12px;padding:12px;background:#f8f9fa;border-radius:8px;display:none;font-size:13px}
.csv-res.show{display:block}

/* DASHBOARD */
.dnav{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:15px;padding:8px;background:#fff;border-radius:var(--rad)}
.dtab{padding:7px 14px;border:2px solid #e0e0e0;border-radius:18px;background:#fff;cursor:pointer;font-size:12px;transition:.3s;font-family:inherit}
.dtab.act{background:var(--pr);color:#fff;border-color:var(--pr)}
.dsec{display:none;background:#fff;padding:18px;border-radius:var(--rad);box-shadow:var(--sh)}
.dsec.act{display:block}
.amnav{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:15px}
.ambtn{padding:8px 15px;background:#fff;border:2px solid #e0e0e0;border-radius:10px;cursor:pointer;font-size:12px;transition:.3s;font-family:inherit;display:flex;align-items:center;gap:5px}
.ambtn.act{background:var(--pr);color:#fff;border-color:var(--pr)}
.amsec{display:none;background:#fff;padding:18px;border-radius:var(--rad);box-shadow:var(--sh)}
.amsec.act{display:block}
.dtbl{width:100%;border-collapse:collapse;margin-top:12px}
.dtbl th,.dtbl td{padding:8px 6px;text-align:right;border-bottom:1px solid #eee;font-size:12px;word-break:break-word}
.dtbl th{background:#f8f9fa;font-weight:700;color:#555}
.dtbl tr:hover{background:#f5f8ff}

/* NOTIFICATIONS */
.notif{position:fixed;top:70px;left:50%;transform:translateX(-50%) translateY(-20px);padding:12px 24px;border-radius:10px;color:#fff;font-weight:700;z-index:9999;opacity:0;transition:.4s;text-align:center;min-width:260px;max-width:90%;box-shadow:0 4px 16px rgba(0,0,0,.2);font-size:14px}
.notif.show{opacity:1;transform:translateX(-50%) translateY(0)}
.notif.ok{background:linear-gradient(135deg,#28a745,#1e7e34)}
.notif.er{background:linear-gradient(135deg,#dc3545,#a71d2a)}
.notif.inf{background:linear-gradient(135deg,#17a2b8,#117a8b)}

/* TOGGLE */
.tgl{position:relative;width:46px;height:24px;display:inline-block}
.tgl input{display:none}
.tgl span{position:absolute;inset:0;background:#ccc;border-radius:24px;cursor:pointer;transition:.3s}
.tgl span::before{content:'';position:absolute;width:18px;height:18px;background:#fff;border-radius:50%;top:3px;right:3px;transition:.3s}
.tgl input:checked+span{background:var(--suc)}
.tgl input:checked+span::before{transform:translateX(-22px)}

/* MISC */
.back{display:inline-flex;align-items:center;gap:5px;padding:7px 14px;background:#fff;border:2px solid #e0e0e0;border-radius:8px;cursor:pointer;font-size:13px;margin-bottom:12px;transition:.3s;font-family:inherit}
.back:hover{border-color:var(--pr)}
.empty{text-align:center;padding:40px 15px;color:#aaa}
.empty .eico{font-size:50px;margin-bottom:10px}
.badge{padding:3px 8px;border-radius:10px;font-size:10px;font-weight:700;white-space:nowrap}
.badge.g{background:#d4edda;color:var(--suc)}.badge.r{background:#f8d7da;color:var(--dan)}
.page{display:none}.page.act{display:block}
.scard{display:flex;align-items:center;gap:12px;padding:12px;background:#f8f9fa;border-radius:10px;margin-bottom:8px;flex-wrap:wrap}
.scard .sav{width:45px;height:45px;border-radius:50%;background:var(--pr);color:#fff;display:flex;align-items:center;justify-content:center;font-size:18px;font-weight:700;flex-shrink:0}
.scard .sinf{flex:1;min-width:140px}
.scard .sinf h4{font-size:14px;margin-bottom:2px}
.scard .sinf p{font-size:11px;color:#888}
.cpg{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.cpg label{min-width:110px;font-weight:600;font-size:13px}
.cpg input[type=color]{width:45px;height:32px;border:2px solid #ddd;border-radius:8px;cursor:pointer;padding:1px}
.chkg{display:flex;gap:12px;flex-wrap:wrap}
.chkg label{display:flex;align-items:center;gap:5px;cursor:pointer;font-weight:normal;font-size:13px}
.jcard{background:#fff;padding:12px;border-radius:10px;box-shadow:var(--sh);margin-bottom:8px}
.jcard h3{color:var(--pr);margin-bottom:6px;font-size:14px}
.jmeta{display:flex;gap:12px;flex-wrap:wrap;font-size:12px;color:#888;margin-top:6px}
.jtabs{display:flex;gap:8px;margin-bottom:15px}
.jtab{flex:1;padding:10px;text-align:center;background:#fff;border:2px solid #e0e0e0;border-radius:10px;cursor:pointer;font-weight:700;transition:.3s;font-family:inherit;font-size:13px}
.jtab.act{background:var(--pr);color:#fff;border-color:var(--pr)}
.det-imgs{display:flex;gap:8px;overflow-x:auto;padding:8px 0}
.det-imgs img{width:280px;height:280px;object-fit:cover;border-radius:10px;flex-shrink:0}
.det-info{padding:18px}
.det-info h1{font-size:1.4em;margin-bottom:8px}
.det-info .dprice{font-size:1.6em;color:var(--sec);font-weight:700;margin-bottom:12px}
.det-info .ddesc{line-height:1.8;color:#555;margin-bottom:16px}
.det-acts{display:flex;gap:8px;flex-wrap:wrap}
.det-acts .abtn{padding:10px 20px;font-size:14px;border-radius:10px}
.stat-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:12px;margin-bottom:18px}
.stat-card{padding:18px 10px;border-radius:12px;color:#fff;text-align:center}
.stat-card .snum{font-size:26px;font-weight:700}
.stat-card .slbl{font-size:12px;margin-top:4px}

/* Contact Info Box */
.contact-box{background:linear-gradient(135deg,#e3f2fd,#fff);border:2px solid #bbdefb;border-radius:12px;padding:15px;margin-bottom:15px}
.contact-box h4{color:var(--pr);margin-bottom:8px}
.contact-box .ci{display:flex;align-items:center;gap:8px;padding:6px 0;font-size:13px;color:#555}
.contact-box .ci span{font-size:18px}

/* Complaint Card */
.comp-card{padding:12px;background:#f8f9fa;border-radius:10px;margin-bottom:8px;border-right:4px solid var(--pr)}
.comp-card.from-store{border-right-color:var(--sec)}
.comp-card.from-visitor{border-right-color:var(--suc)}
.comp-card .comp-meta{display:flex;justify-content:space-between;align-items:center;margin-bottom:6px;font-size:11px;color:#aaa}
.comp-card .comp-type{font-size:10px;padding:2px 8px;border-radius:10px;font-weight:700}
.comp-card .comp-type.t-store{background:#fff3e0;color:var(--sec)}
.comp-card .comp-type.t-visitor{background:#e8f5e9;color:var(--suc)}

/* Privacy checkbox */
.privacy-check{display:flex;align-items:flex-start;gap:8px;padding:12px;background:#f0f4ff;border-radius:8px;margin-bottom:14px;border:2px solid #e0e0e0}
.privacy-check input{margin-top:3px;width:18px;height:18px;flex-shrink:0}
.privacy-check .ptxt{font-size:12px;color:#555;line-height:1.5}
.privacy-check .ptxt a{color:var(--pr);cursor:pointer;text-decoration:underline}

/* Smart Category Badge */
.smart-cat-badge{display:inline-block;padding:2px 8px;background:#e3f2fd;color:var(--pr);border-radius:10px;font-size:10px;font-weight:600;margin-right:4px}

/* Footer */
.ftr{background:var(--drk);color:#fff;padding:25px 15px 12px;margin-top:30px}
.ftr-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:18px;max-width:1200px;margin:0 auto 15px}
.ftr-sec h4{margin-bottom:10px;color:var(--sec);font-size:14px}
.ftr-sec a{display:block;color:#bbb;font-size:12px;margin-bottom:5px;cursor:pointer}
.ftr-sec a:hover{color:#fff}
.ftr-bot{text-align:center;padding-top:12px;border-top:1px solid rgba(255,255,255,.1);font-size:12px;color:#888}

/* --- 1. القواعد العامة (للحاسوب وللجميع) --- */
.hdr-row {
  display: flex;
  align-items: center;
  gap: 15px;
  flex-wrap: nowrap; /* الحفاظ على استقامة العناصر في الحاسوب */
}

.srch {
  flex: 1; /* شريط البحث يأخذ المساحة المتاحة */
  min-width: 200px;
}

.hdr-btns {
  display: flex;
  gap: 8px;
}

/* --- 2. قواعد الهاتف (تطبق فقط إذا كان عرض الشاشة أقل من 768px) --- */
@media (max-width: 768px) {
  /* منع التمرير الجانبي نهائياً */
  html, body {
    overflow-x: hidden;
    width: 100%;
  }

  /* تحويل الهيدر إلى ترتيب عمودي في الهاتف */
  .hdr-row {
    flex-direction: column !important;
    gap: 12px !important;
    padding: 10px 5px;
  }

  /* شريط البحث يأخذ العرض الكامل في الهاتف */
  .srch {
    width: 100% !important;
    order: 2; /* يظهر تحت اللوجو */
  }
  .srch input {
    width: 100% !important;
  }

  /* ترتيب الأزرار بشكل شبكة (Grid) لكي لا تخرج عن الشاشة */
  .hdr-btns {
    width: 100%;
    display: grid !important;
    grid-template-columns: repeat(3, 1fr); /* 3 أزرار في كل صف */
    gap: 6px !important;
    order: 3;
  }

  /* ضبط حجم الأزرار ونصوصها في الهاتف */
  .hb {
    width: 100%;
    padding: 8px 2px !important;
    font-size: 11px !important;
    text-align: center;
    justify-content: center;
    white-space: nowrap; /* يمنع نزول النص لسطر جديد */
  }

  /* جعل زر الإدارة (الدرع) يأخذ عرضاً كاملاً في الأسفل */
  .hb.sh {
    grid-column: span 3;
    margin-top: 4px;
  }

  /* تحسين شبكة المنتجات لتظهر كعمودين في الهاتف */
  .pgrid {
    grid-template-columns: repeat(2, 1fr) !important;
    gap: 10px !important;
    padding: 5px;
  }

  /* جعل النوافذ المنبثقة (Modals) تتناسب مع حجم شاشة الهاتف */
  .mdl {
    width: 95% !important;
    margin: 10px auto !important;
    max-height: 90vh;
    overflow-y: auto;
  }
}

/* --- 3. قواعد الشاشات الصغيرة جداً (أقل من 480px) --- */
@media (max-width: 480px) {
  .hdr-btns {
    grid-template-columns: repeat(2, 1fr); /* زرين فقط في الصف الواحد لزيادة الوضوح */
  }
  .hb.sh {
    grid-column: span 2;
  }
  .pname { font-size: 11px; height: 30px; }
  .pprice { font-size: 13px; }
}
</style>
</head>
<body>

<div id="ntf" class="notif"></div>

<!-- HEADER -->
<header class="hdr">
<div class="hdr-row">
  <div class="logo" onclick="nav('home')">🛒 <b id="pName">BABA SANOOD</b></div>
  <div class="srch"><input type="text" id="sInp" placeholder="🔍 ابحث عن منتجات، متاجر، وظائف..." oninput="doSearch(this.value)"></div>
  <div class="hdr-btns">
    <button class="hb" onclick="nav('home')">🏠 الرئيسية</button>
    <button class="hb" onclick="nav('jobs')">💼 وظائف</button>
    <button class="hb" onclick="oMod('regMod')">🏪 فتح متجر</button>
    <button class="hb" onclick="oMod('logMod')">🔑 دخول</button>
    <button class="hb" onclick="oMod('contactMod')">📞 تواصل معنا</button>
    <button class="hb sh" onclick="oMod('admMod')">🛡️</button>
  </div>
</div>
</header>

<!-- PAGES -->
<div id="pg_home" class="page act">
  <div class="cats"><div class="cats-scroll" id="catsBar"></div></div>
  <div class="feed">
    <h2 class="stitle">🔥 أحدث المنتجات</h2>
    <div class="pgrid" id="mainGrid"></div>
    <div id="emptyMsg" class="empty" style="display:none"><div class="eico">🛍️</div><p>لا توجد منتجات. كن أول من يفتح متجره!</p></div>
  </div>
</div>

<div id="pg_cat" class="page">
  <div class="feed"><button class="back" onclick="nav('home')">→ العودة</button><h2 class="stitle" id="catTitle"></h2><div class="pgrid" id="catGrid"></div></div>
</div>

<div id="pg_store" class="page">
  <div class="feed"><button class="back" onclick="nav('home')">→ العودة</button><div id="storeHdr" style="background:#fff;padding:18px;border-radius:12px;margin-bottom:15px;box-shadow:var(--sh)"></div><h2 class="stitle">📦 منتجات المتجر</h2><div class="pgrid" id="storeGrid"></div></div>
</div>

<div id="pg_det" class="page">
  <div class="feed"><button class="back" onclick="nav('home')">→ العودة</button><div id="detContent"></div></div>
</div>

<div id="pg_jobs" class="page">
  <div class="feed">
    <button class="back" onclick="nav('home')">→ العودة</button>
    <h2 class="stitle">💼 مركز التوظيف</h2>
    <div class="jtabs">
      <div class="jtab act" onclick="jTab(this,'browse')">📋 الوظائف</div>
      <div class="jtab" onclick="jTab(this,'post')">📝 نشر</div>
      <div class="jtab" onclick="jTab(this,'seek')">🔍 أبحث عن عمل</div>
    </div>
    <div id="jBrowse" class="dsec act"><div id="jobList"></div></div>
    <div id="jPost" class="dsec">
      <div class="fg"><label>المؤسسة</label><input id="jComp"></div>
      <div class="fg"><label>نوع الوظيفة</label><input id="jType"></div>
      <div class="fg"><label>المتطلبات</label><textarea id="jReq"></textarea></div>
      <div class="fg"><label>الراتب</label><input id="jSal"></div>
      <div class="fg"><label>الموقع</label><input id="jLoc"></div>
      <div class="fg"><label>الاتصال</label><input id="jCont"></div>
      <button class="sbtn" onclick="postJob()">✅ نشر</button>
    </div>
    <div id="jSeek" class="dsec">
      <div class="fg"><label>الاسم</label><input id="skName"></div>
      <div class="fg"><label>السن</label><input type="number" id="skAge"></div>
      <div class="fg"><label>التخصص</label><input id="skSkill"></div>
      <div class="fg"><label>الخبرات</label><textarea id="skExp"></textarea></div>
      <div class="fg"><label>الهاتف</label><input type="tel" id="skPhone"></div>
      <button class="sbtn" onclick="subSeeker()">✅ تسجيل</button>
    </div>
  </div>
</div>

<!-- MERCHANT DASHBOARD -->
<div id="pg_dash" class="page">
  <div class="feed">
    <button class="back" onclick="mLogout()">🚪 خروج</button>
    <h2 class="stitle" id="dName">📊 لوحة التحكم</h2>
    <div class="dnav" id="dNav">
      <div class="dtab act" onclick="dTab(this,'prods')">📦 المنتجات</div>
      <div class="dtab" onclick="dTab(this,'addP')">➕ إضافة</div>
      <div class="dtab" onclick="dTab(this,'ords')">📋 الطلبات</div>
      <div class="dtab" onclick="dTab(this,'sett')">⚙️ الإعدادات</div>
      <div class="dtab" onclick="dTab(this,'mComp')">📩 تواصل مع الإدارة</div>
    </div>
    <div id="dProds" class="dsec act"><div id="myProds"></div></div>
    <div id="dAddP" class="dsec">
      <h3 style="margin-bottom:12px">➕ إضافة منتج</h3>
      <div class="fg"><label>📸 الصور (حتى 5)</label>
        <div class="uparea" id="mUpArea"><div class="uico">📷</div><div class="utxt">اضغط أو اسحب الصور</div><div class="uhint">JPG, PNG, WebP</div><input type="file" id="mFileIn" accept="image/*" multiple></div>
        <div class="previews" id="mPrevs"></div>
      </div>
      <div class="fg"><label>اسم المنتج</label><input id="npName"></div>
      <div class="fg"><label>السعر (دج)</label><input type="number" id="npPrice"></div>
      <div class="fg"><label>القسم</label><select id="npCat"></select></div>
      <div class="fg"><label>الوصف</label><textarea id="npDesc"></textarea></div>
      <div class="fg"><label>التوصيل</label><select id="npDel"><option value="yes">✅ متاح</option><option value="no">❌ غير متاح</option></select></div>
      <div class="fg"><label>طرق الطلب</label><div class="chkg"><label><input type="checkbox" id="omMsg" checked> 📱 مسنجر</label><label><input type="checkbox" id="omPh"> 📞 اتصال</label><label><input type="checkbox" id="omIn"> 📋 داخلي</label></div></div>
      <button class="sbtn g" onclick="addProd()">✅ نشر</button>
    </div>
    <div id="dOrds" class="dsec"><div id="mOrds"></div></div>
    <div id="dSett" class="dsec">
      <h3 style="margin-bottom:12px">⚙️ الإعدادات</h3>
      <div class="fg"><label>اسم المتجر</label><input id="sName"></div>
      <div class="fg"><label>فيسبوك</label><input id="sFb"></div>
      <div class="fg"><label>الهاتف</label><input type="tel" id="sPh"></div>
      <div class="fg"><label>الوصف</label><textarea id="sDesc"></textarea></div>
      <button class="sbtn" onclick="saveSett()">💾 حفظ</button>
    </div>
    <!-- تواصل مع الإدارة -->
    <div id="dMComp" class="dsec">
      <h3 style="margin-bottom:12px">📩 تواصل مع الإدارة</h3>
      <div id="adminContactInfo"></div>
      <div class="fg"><label>نوع الرسالة</label>
        <select id="mCompType"><option value="شكوى">📛 شكوى</option><option value="استفسار">❓ استفسار</option><option value="اقتراح">💡 اقتراح</option><option value="مشكلة تقنية">🔧 مشكلة تقنية</option></select>
      </div>
      <div class="fg"><label>الرسالة</label><textarea id="mCompTxt" placeholder="اكتب رسالتك للإدارة..."></textarea></div>
      <button class="sbtn" onclick="subMerchComp()">📨 إرسال</button>
      <div id="mCompHistory" style="margin-top:15px"></div>
    </div>
  </div>
</div>

<!-- ADMIN PANEL -->
<div id="pg_admin" class="page">
  <div class="feed">
    <button class="back" onclick="nav('home')">🚪 خروج</button>
    <h2 class="stitle">🛡️ لوحة الإدارة الكبرى</h2>
    <div class="amnav" id="amNav">
      <button class="ambtn act" onclick="aTab(this,'look')">🎨 المظهر</button>
      <button class="ambtn" onclick="aTab(this,'contact')">📞 معلومات الاتصال</button>
      <button class="ambtn" onclick="aTab(this,'merch')">🏪 التجار</button>
      <button class="ambtn" onclick="aTab(this,'stat')">📊 إحصائيات</button>
      <button class="ambtn" onclick="aTab(this,'comp')">📩 الشكاوى والرسائل</button>
      <button class="ambtn" onclick="aTab(this,'myS')">🛒 متجري</button>
    </div>
    <!-- المظهر -->
    <div id="amLook" class="amsec act">
      <h3 style="margin-bottom:12px">🎨 المظهر</h3>
      <div class="fg"><label>اسم المنصة</label><input id="apName" oninput="$('pName').textContent=this.value||'BABA SANOOD'"></div>
      <div class="cpg"><label>اللون الرئيسي</label><input type="color" id="apClr1" value="#1a73e8" onchange="document.documentElement.style.setProperty('--pr',this.value)"></div>
      <div class="cpg"><label>اللون الثانوي</label><input type="color" id="apClr2" value="#ff6b35" onchange="document.documentElement.style.setProperty('--sec',this.value)"></div>
      <button class="sbtn" onclick="saveApp()">💾 حفظ المظهر</button>
    </div>
    <!-- ★ معلومات الاتصال ★ -->
    <div id="amContact" class="amsec">
      <h3 style="margin-bottom:12px">📞 معلومات الاتصال بالإدارة</h3>
      <p style="font-size:12px;color:#888;margin-bottom:12px">هذه المعلومات ستظهر للتجار والزوار عند التواصل</p>
      <div class="fg"><label>📱 رقم الهاتف</label><input id="adPh" placeholder="0555357030"></div>
      <div class="fg"><label>📱 واتساب</label><input id="adWa" placeholder="213667795458"></div>
      <div class="fg"><label>📧 البريد الإلكتروني</label><input type="email" id="adEmail" placeholder="bayssahmr@gmail.com"></div>
      <div class="fg"><label>📘 فيسبوك</label><input id="adFb" placeholder="https://www.facebook.com/Sawaql?locale=ar_AR"></div>
      <div class="fg"><label>📍 العنوان</label><input id="adAddr" placeholder="تبسة، الجزائر"></div>
      <div class="fg"><label>🕐 أوقات العمل</label><input id="adHours" placeholder="من 8 صباحاً إلى 6 مساءً"></div>
      <button class="sbtn" onclick="saveContact()">💾 حفظ معلومات الاتصال</button>
    </div>
    <!-- التجار -->
    <div id="amMerch" class="amsec"><h3 style="margin-bottom:12px">🏪 التجار</h3><div id="amStores"></div></div>
    <!-- الإحصائيات -->
    <div id="amStat" class="amsec"><h3 style="margin-bottom:12px">📊 الإحصائيات</h3><div id="amStats"></div></div>
    <!-- ★ الشكاوى والرسائل المتطورة ★ -->
    <div id="amComp" class="amsec">
      <h3 style="margin-bottom:12px">📩 الشكاوى والرسائل الواردة</h3>
      <div style="display:flex;gap:8px;margin-bottom:12px;flex-wrap:wrap">
        <button class="dtab act" onclick="filterComp(this,'all')">📬 الكل</button>
        <button class="dtab" onclick="filterComp(this,'store')">🏪 من التجار</button>
        <button class="dtab" onclick="filterComp(this,'visitor')">👤 من الزوار</button>
      </div>
      <div id="compList"></div>
    </div>
    <!-- ★ متجري الخاص - محسّن ★ -->
    <div id="amMyS" class="amsec">
      <h3 style="margin-bottom:12px">🛒 متجري الخاص</h3>
      <div style="padding:15px;background:#f0fff0;border-radius:12px;margin-bottom:18px">
        <h4 style="margin-bottom:8px">📁 رفع CSV مع فرز ذكي</h4>
        <p style="font-size:12px;color:#666;margin-bottom:4px">✅ يقرأ الأعمدة تلقائياً | ✅ يضيف 20% | ✅ يفرز في الأقسام ذكياً</p>
        <p style="font-size:11px;color:#999;margin-bottom:8px">الأعمدة: اسم المنتج | السعر | رابط الصورة | الوصف | الفئة</p>
        <div class="csv-area" id="csvArea"><div style="font-size:36px;pointer-events:none">📄</div><div style="color:#666;pointer-events:none">اضغط أو اسحب CSV</div><input type="file" id="csvIn" accept=".csv,.txt,text/csv,text/plain"></div>
        <div class="csv-fn" id="csvFn"></div>
        <div class="csv-res" id="csvRes"></div>
      </div>
      <div style="padding:15px;background:#fff3e0;border-radius:12px;margin-bottom:18px">
        <h4 style="margin-bottom:8px">✏️ إضافة يدوية (+20%)</h4>
        <div class="fg"><label>📸 الصور</label>
          <div class="uparea" id="aUpArea"><div class="uico">📷</div><div class="utxt">اضغط لرفع صور</div><input type="file" id="aFileIn" accept="image/*" multiple></div>
          <div class="previews" id="aPrevs"></div>
        </div>
        <div class="fg"><label>الاسم</label><input id="apPName"></div>
        <div class="fg"><label>السعر (دج)</label><input type="number" id="apPPrice"><div class="fhint">+20% تلقائياً</div></div>
        <div class="fg"><label>القسم</label><select id="apPCat"></select></div>
        <div class="fg"><label>الوصف</label><textarea id="apPDesc"></textarea></div>
        <button class="sbtn g" onclick="addAdmProd()">✅ نشر (+20%)</button>
      </div>
      <h4>📦 منتجاتي (<span id="admPCount">0</span>)</h4>
      <div id="amMyProds" style="margin-top:12px"></div>
    </div>
  </div>
</div>

<!-- ★ مودال التسجيل - مع الموافقة على الخصوصية ★ -->
<div id="regMod" class="mov"><div class="mdl"><div class="mdl-h"><h2>🏪 فتح متجر جديد</h2><button class="mdl-x" onclick="cMod('regMod')">✕</button></div><div class="mdl-b">
  <div class="fg"><label>اسم المتجر *</label><input id="rName" placeholder="متجر النور..."></div>
  <div class="fg"><label>نوع النشاط *</label><select id="rType"><option value="">-- اختر --</option><option value="تاجر">🛒 تاجر</option><option value="حرفي">🔧 حرفي</option><option value="مهنة حرة">⚖️ مهنة حرة</option><option value="خدمات رقمية">💻 خدمات رقمية</option><option value="مطعم">🍽️ مطعم</option></select></div>
  <div class="fg"><label>إيميل (اختياري)</label><input type="email" id="rEmail"></div>
  <div class="fg"><label>هاتف (اختياري)</label><input type="tel" id="rPhone"></div>
  <div class="fg"><label>كلمة السر *</label><input type="password" id="rPass"></div>
  <div class="privacy-check">
    <input type="checkbox" id="privacyAgree">
    <div class="ptxt">أوافق على <a onclick="infoPage('priv')">سياسة الخصوصية</a> و<a onclick="infoPage('terms')">شروط الاستخدام</a> الخاصة بمنصة سوق تبسة العملاق. أتعهد بالالتزام بقوانين المنصة وعدم نشر محتوى مخالف.</div>
  </div>
  <button class="sbtn g" id="regBtn" onclick="regStore()">🎉 إنشاء المتجر</button>
</div></div></div>

<!-- Login -->
<div id="logMod" class="mov"><div class="mdl"><div class="mdl-h"><h2>🔑 دخول التاجر</h2><button class="mdl-x" onclick="cMod('logMod')">✕</button></div><div class="mdl-b">
  <div class="fg"><label>اسم المتجر</label><input id="lName"></div>
  <div class="fg"><label>كلمة السر</label><input type="password" id="lPass"></div>
  <div class="fg"><label style="font-weight:normal;display:flex;align-items:center;gap:5px"><input type="checkbox" id="lRem"> تذكرني</label></div>
  <button class="sbtn" onclick="mLogin()">🔓 دخول</button>
</div></div></div>

<!-- Admin Login -->
<div id="admMod" class="mov"><div class="mdl" style="max-width:380px"><div class="mdl-h" style="background:linear-gradient(135deg,#2c3e50,#34495e)"><h2>🛡️ الإدارة</h2><button class="mdl-x" onclick="cMod('admMod')">✕</button></div><div class="mdl-b">
  <div class="fg"><label>الرقم السري</label><input type="password" id="admPass"></div>
  <button class="sbtn" style="background:linear-gradient(135deg,#2c3e50,#34495e)" onclick="admLogin()">🔓 دخول</button>
</div></div></div>

<!-- ★ مودال تواصل معنا (للزوار والتجار) ★ -->
<div id="contactMod" class="mov"><div class="mdl"><div class="mdl-h" style="background:linear-gradient(135deg,#00897b,#004d40)"><h2>📞 تواصل معنا</h2><button class="mdl-x" onclick="cMod('contactMod')">✕</button></div><div class="mdl-b">
  <div id="publicContactInfo"></div>
  <hr style="margin:12px 0;border:none;border-top:1px solid #eee">
  <h4 style="margin-bottom:10px">📨 أرسل رسالة للإدارة</h4>
  <div class="fg"><label>اسمك</label><input id="vName" placeholder="اسمك الكامل"></div>
  <div class="fg"><label>الهاتف أو الإيميل</label><input id="vContact" placeholder="للرد عليك"></div>
  <div class="fg"><label>نوع الرسالة</label>
    <select id="vType"><option value="استفسار">❓ استفسار</option><option value="شكوى">📛 شكوى</option><option value="اقتراح">💡 اقتراح</option></select>
  </div>
  <div class="fg"><label>الرسالة</label><textarea id="vMsg" placeholder="اكتب رسالتك..."></textarea></div>
  <button class="sbtn g" onclick="subVisitorMsg()">📨 إرسال</button>
</div></div></div>

<!-- Order -->
<div id="ordMod" class="mov"><div class="mdl"><div class="mdl-h"><h2>📋 طلب منتج</h2><button class="mdl-x" onclick="cMod('ordMod')">✕</button></div><div class="mdl-b">
  <div class="fg"><label>اسمك *</label><input id="oName"></div>
  <div class="fg"><label>الهاتف *</label><input type="tel" id="oPhone"></div>
  <div class="fg"><label>الولاية</label><input id="oWil" placeholder="تبسة"></div>
  <div class="fg"><label>العنوان</label><textarea id="oAddr"></textarea></div>
  <div class="fg"><label>ملاحظات</label><textarea id="oNotes"></textarea></div>
  <input type="hidden" id="oPid"><input type="hidden" id="oSid">
  <button class="sbtn g" onclick="subOrd()">✅ تأكيد</button>
</div></div></div>

<!-- FOOTER -->
<footer class="ftr">
<div class="ftr-grid">
  <div class="ftr-sec"><h4>🛒 سوق تبسة العملاق</h4><p style="font-size:12px;color:#bbb;line-height:1.5">منصة تجارية تجمع كل التجار والخدمات في تبسة</p></div>
  <div class="ftr-sec"><h4>📌 روابط</h4><a onclick="infoPage('priv')">🔒 الخصوصية</a><a onclick="infoPage('terms')">📜 شروط الاستخدام</a><a onclick="infoPage('guide')">📖 الدليل</a><a onclick="infoPage('faq')">❓ أسئلة شائعة</a><a onclick="infoPage('copy')">©️ حقوق الملكية</a></div>
  <div class="ftr-sec"><h4>📞 تواصل</h4><a onclick="oMod('contactMod')">📩 أرسل رسالة</a><div id="footerContact" style="margin-top:8px;font-size:11px;color:#aaa"></div></div>
</div>
<div class="ftr-bot">© 2025 سوق تبسة العملاق - BABA SANOOD</div>
</footer>

<script>
const $=id=>document.getElementById(id);
const D={s:'bs_s',p:'bs_p',o:'bs_o',j:'bs_j',c:'bs_c',a:'bs_a',ap:'bs_ap',ct:'bs_ct'};
const gA=k=>{try{return JSON.parse(localStorage.getItem(k))||[]}catch(e){return[]}};
const sA=(k,v)=>{try{localStorage.setItem(k,JSON.stringify(v))}catch(e){ntf('خطأ حفظ!','er')}};
const gO=k=>{try{return JSON.parse(localStorage.getItem(k))||{}}catch(e){return{}}};
const sO=(k,v)=>{try{localStorage.setItem(k,JSON.stringify(v))}catch(e){}};

let idb=null;
function initIDB(){return new Promise(r=>{try{const q=indexedDB.open('BS_IMG',1);q.onupgradeneeded=e=>{if(!e.target.result.objectStoreNames.contains('i'))e.target.result.createObjectStore('i',{keyPath:'id'})};q.onsuccess=e=>{idb=e.target.result;r()};q.onerror=()=>r()}catch(e){r()}})}
function sImg(id,d){return new Promise(r=>{if(!idb)return r();try{const t=idb.transaction('i','readwrite');t.objectStore('i').put({id,data:d});t.oncomplete=()=>r();t.onerror=()=>r()}catch(e){r()}})}
function gImg(id){return new Promise(r=>{if(!idb)return r(null);try{const t=idb.transaction('i','readonly');const q=t.objectStore('i').get(id);q.onsuccess=()=>r(q.result?q.result.data:null);q.onerror=()=>r(null)}catch(e){r(null)}})}

// ★★★ SMART CATEGORY DETECTION KEYWORDS ★★★
const CATS=[
  {id:'fruits',n:'خضر وفواكه',i:'🥬',kw:['خضر','فواكه','طماطم','بطاطا','تفاح','برتقال','بصل','فلفل','جزر','خيار','خس','موز','عنب','فراولة','ليمون','بطيخ','كوسة','باذنجان','ثوم','بازلاء','سبانخ','نعناع','بقدونس','fruits','vegetables','légumes']},
  {id:'butcher',n:'جزارة',i:'🥩',kw:['لحم','جزار','دجاج','كباب','مرقاز','ستيك','لحوم','بقر','غنم','خروف','meat','viande','poulet','butcher']},
  {id:'bakery',n:'مخابز',i:'🍞',kw:['خبز','مخبز','كرواسون','بيتزا','حلويات','كعك','بسكويت','فطائر','bread','bakery','boulangerie','gâteau','cake']},
  {id:'grocery',n:'بقالة',i:'🛒',kw:['بقالة','سكر','زيت','أرز','معكرونة','حليب','جبن','عصير','شاي','قهوة','grocery','épicerie']},
  {id:'homefood',n:'أكلات منزلية',i:'🍲',kw:['أكلات','منزلي','طبخ','كسكس','شوربة','طاجين','محاجب','بوراك','homefood']},
  {id:'restaurant',n:'مطاعم',i:'🍽️',kw:['مطعم','وجبات','سندويش','شاورما','برغر','بيتزا','restaurant','fast food']},
  {id:'phones',n:'هواتف',i:'📱',kw:['هاتف','موبايل','سامسونغ','آيفون','هواوي','شاومي','أوبو','ريدمي','phone','samsung','iphone','huawei','xiaomi','oppo','realme','infinix','tecno','smartphone','mobile','جوال','تلفون','غلاف','شاحن','سماعات','إكسسوارات هاتف']},
  {id:'computers',n:'كمبيوتر',i:'💻',kw:['كمبيوتر','لابتوب','حاسوب','شاشة','لوحة مفاتيح','ماوس','طابعة','computer','laptop','pc','clavier','écran','imprimante']},
  {id:'electronics',n:'إلكترونيات',i:'🔌',kw:['إلكتروني','تلفزيون','ريسيفر','كاميرا','بطارية','شاحن','سبيكر','سماعة','electronic','tv','camera','speaker']},
  {id:'cars',n:'سيارات',i:'🚗',kw:['سيارة','سيارات','رينو','بيجو','هيونداي','تويوتا','فولكسفاغن','car','voiture','auto','renault','peugeot','hyundai','toyota']},
  {id:'motorcycles',n:'دراجات نارية',i:'🏍️',kw:['دراجة نارية','موتو','سكوتر','moto','motorcycle','scooter']},
  {id:'bicycles',n:'دراجات هوائية',i:'🚲',kw:['دراجة هوائية','فيلو','vélo','bicycle']},
  {id:'parts',n:'قطع غيار',i:'🔧',kw:['قطع غيار','فلتر','زيت محرك','فرامل','إطارات','بطارية سيارة','pièces','spare parts']},
  {id:'furniture',n:'أثاث',i:'🛋️',kw:['أثاث','كنبة','سرير','طاولة','خزانة','كرسي','صالون','meuble','furniture','canapé','lit','table']},
  {id:'decor',n:'ديكور',i:'🖼️',kw:['ديكور','لوحة','ستائر','سجاد','مرآة','décor','rideau','tapis']},
  {id:'household',n:'أدوات منزلية',i:'🏠',kw:['منزل','مطبخ','قدر','صحون','ملعقة','غسالة','ثلاجة','مكنسة','ménage','cuisine','household']},
  {id:'menclothes',n:'ملابس رجالية',i:'👔',kw:['ملابس رجال','قميص','بنطلون','جاكيت','بدلة','كوستيم','رجالي','homme','men','chemise','pantalon','costume']},
  {id:'womenclothes',n:'ملابس نسائية',i:'👗',kw:['ملابس نساء','فستان','حجاب','عباية','جلابة','قفطان','نسائي','femme','women','robe','hijab']},
  {id:'kidclothes',n:'ملابس أطفال',i:'👶',kw:['أطفال','بيبي','طفل','ملابس أطفال','enfant','bébé','kids']},
  {id:'shoes',n:'أحذية',i:'👟',kw:['حذاء','أحذية','صندل','نعل','رياضي','كروكس','chaussure','shoes','baskets']},
  {id:'jewelry',n:'مجوهرات',i:'💎',kw:['مجوهرات','ذهب','فضة','خاتم','سلسلة','أقراط','bijoux','or','argent','jewelry']},
  {id:'watches',n:'ساعات',i:'⌚',kw:['ساعة','ساعات','montre','watch']},
  {id:'tailor',n:'خياطة',i:'✂️',kw:['خياطة','تفصيل','قماش','couture','tailor','tissu']},
  {id:'barber',n:'حلاقة رجالية',i:'💈',kw:['حلاقة','حلاق','coiffeur','barber']},
  {id:'salon',n:'حلاقة نسائية',i:'💇',kw:['صالون','تجميل','مكياج','salon','coiffeuse','beauté','makeup']},
  {id:'carpenter',n:'نجارة',i:'🪵',kw:['نجارة','نجار','خشب','menuiserie','bois']},
  {id:'blacksmith',n:'حدادة',i:'⚒️',kw:['حدادة','حديد','لحام','fer','soudure']},
  {id:'electrician',n:'كهربائي',i:'⚡',kw:['كهربائي','كهرباء','électricien','electrician']},
  {id:'plumber',n:'سباكة',i:'🔧',kw:['سباك','سباكة','حنفية','plombier','plumber']},
  {id:'painter',n:'دهان',i:'🎨',kw:['دهان','صباغة','طلاء','peinture','painter']},
  {id:'handcraft',n:'حرف يدوية',i:'🧶',kw:['حرف','يدوي','صناعة تقليدية','كروشيه','تريكو','artisanat','handcraft']},
  {id:'lawyer',n:'محامين',i:'⚖️',kw:['محامي','محاماة','قانون','avocat','lawyer']},
  {id:'notary',n:'كاتب عمومي',i:'📝',kw:['كاتب عمومي','وثائق','notaire']},
  {id:'accountant',n:'محاسبين',i:'🧮',kw:['محاسب','محاسبة','comptable']},
  {id:'translator',n:'ترجمة',i:'🌐',kw:['ترجمة','مترجم','traduction','translator']},
  {id:'internet',n:'قاعات إنترنت',i:'🌐',kw:['إنترنت','سايبر','cyber','internet']},
  {id:'design',n:'تصميم',i:'🎨',kw:['تصميم','جرافيك','فوتوشوب','design','graphic','photoshop']},
  {id:'digital',n:'خدمات رقمية',i:'💻',kw:['رقمي','خدمة رقمية','digital','numérique']},
  {id:'bookstore',n:'مكتبات',i:'📚',kw:['مكتبة','كتب','قرطاسية','librairie','books','papeterie']},
  {id:'school',n:'لوازم مدرسية',i:'🎒',kw:['مدرسة','مدرسي','محفظة','دفتر','أقلام','scolaire','école']},
  {id:'tutoring',n:'دروس خصوصية',i:'📖',kw:['دروس','خصوصي','تعليم','cours','tutoring']},
  {id:'pets',n:'حيوانات أليفة',i:'🐾',kw:['حيوان','قط','كلب','عصفور','أرنب','سمك','animal','chat','chien','oiseau','pet']},
  {id:'used',n:'سوق المستعمل',i:'🔄',kw:['مستعمل','occasion','used','للبيع']},
  {id:'sports',n:'رياضة',i:'🏋️',kw:['رياضة','رياضي','كرة','sport','fitness','gym']},
  {id:'misc',n:'متنوعات',i:'🛍️',kw:['متنوع','أخرى','divers','misc']}
];

let cMer=null,mImgs=[],aImgs=[],compFilter='all';

function ntf(m,t='ok'){const n=$('ntf');n.textContent=m;n.className='notif '+t+' show';setTimeout(()=>n.classList.remove('show'),3500)}
function nav(p){document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_'+p).classList.add('act');if(p==='home')renderProds();if(p==='jobs')renderJobs();scrollTo(0,0)}
function oMod(id){$(id).classList.add('act');if(id==='contactMod')loadPublicContact()}
function cMod(id){$(id).classList.remove('act')}
document.querySelectorAll('.mov').forEach(o=>o.addEventListener('click',e=>{if(e.target===o)o.classList.remove('act')}));

function renderCats(){$('catsBar').innerHTML=CATS.map(c=>`<div class="cat-item" onclick="openCat('${c.id}')"><div class="cat-ico">${c.i}</div><div class="cat-nm">${c.n}</div></div>`).join('')}
function fillCatSel(){const h='<option value="">-- القسم --</option>'+CATS.map(c=>`<option value="${c.id}">${c.i} ${c.n}</option>`).join('');['npCat','apPCat'].forEach(id=>{const s=$(id);if(s)s.innerHTML=h})}
function openCat(cid){const c=CATS.find(x=>x.id===cid);if(!c)return;document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_cat').classList.add('act');$('catTitle').textContent=c.i+' '+c.n;renderCards(allProds().filter(p=>p.category===cid),'catGrid');scrollTo(0,0)}

// ★★★ SMART CATEGORY DETECTION ★★★
function detectCategory(name,desc=''){
  const text=(name+' '+desc).toLowerCase();
  let best=null,bestScore=0;
  for(const cat of CATS){
    if(cat.id==='misc')continue;
    let score=0;
    for(const kw of cat.kw){
      if(text.includes(kw.toLowerCase())){
        score+=kw.length; // longer match = better
      }
    }
    if(score>bestScore){bestScore=score;best=cat.id}
  }
  return best||'misc';
}

function allProds(){
  const stores=gA(D.s),prods=gA(D.p),admP=gA(D.ap);let v=[];
  prods.forEach(p=>{const s=stores.find(x=>x.id===p.sid);if(s&&s.on!==false)v.push({...p,sName:s.name,sType:s.type})});
  admP.forEach(p=>v.push({...p,sName:'BABA SANOOD',sType:'admin',sid:'admin'}));
  return v.sort((a,b)=>(b.ts||0)-(a.ts||0));
}

async function renderProds(){const p=allProds(),g=$('mainGrid'),e=$('emptyMsg');if(!p.length){g.innerHTML='';e.style.display='block';return}e.style.display='none';g.innerHTML='';for(const x of p)g.innerHTML+=await mkCard(x)}
async function renderCards(arr,gid){const g=$(gid);if(!arr.length){g.innerHTML='<div class="empty"><div class="eico">📭</div><p>لا توجد منتجات</p></div>';return}g.innerHTML='';for(const x of arr)g.innerHTML+=await mkCard(x)}

async function mkCard(p){
  let img='<div class="pimg">📷</div>';
  if(p.imgs&&p.imgs.length){const f=p.imgs[0];let src=f;if(!f.startsWith('data:')&&!f.startsWith('http'))src=await gImg(f);if(src)img=`<div class="pimg"><img src="${src}" onerror="this.parentElement.innerHTML='📷'"></div>`}
  else if(p.imgUrl)img=`<div class="pimg"><img src="${p.imgUrl}" onerror="this.parentElement.innerHTML='📷'"></div>`;
  const ini=(p.sName||'?')[0],pr=p.price?Number(p.price).toLocaleString()+' دج':'السعر';
  const st=gA(D.s).find(s=>s.id===p.sid);
  let acts='';
  if(st&&st.fb)acts+=`<button class="abtn msg" onclick="event.stopPropagation();window.open('${st.fb}','_blank')">📱</button>`;
  if(st&&st.ph)acts+=`<button class="abtn cal" onclick="event.stopPropagation();location.href='tel:${st.ph}'">📞</button>`;
  acts+=`<button class="abtn ord" onclick="event.stopPropagation();oOrd('${p.id}','${p.sid}')">🛒</button>`;
  return`<div class="pcard" onclick="openDet('${p.id}')">${img}<div class="pinfo"><div class="pname">${p.name||''}</div><div class="pprice">${pr}</div><div class="pstore" onclick="event.stopPropagation();openSt('${p.sid}')"><div class="av">${ini}</div><span>${p.sName||''}</span></div><div class="pacts">${acts}</div></div></div>`;
}

async function openDet(pid){const p=allProds().find(x=>x.id===pid);if(!p)return;document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_det').classList.add('act');let imgs='';if(p.imgs&&p.imgs.length){for(const im of p.imgs){let s=im;if(!im.startsWith('data:')&&!im.startsWith('http'))s=await gImg(im);if(s)imgs+=`<img src="${s}" onerror="this.remove()">`}}else if(p.imgUrl)imgs=`<img src="${p.imgUrl}" onerror="this.remove()">`;if(!imgs)imgs='<div style="width:280px;height:280px;background:#f0f0f0;display:flex;align-items:center;justify-content:center;border-radius:10px;font-size:50px">📷</div>';const pr=p.price?Number(p.price).toLocaleString()+' دج':'السعر';const st=gA(D.s).find(s=>s.id===p.sid);let acts='';if(st&&st.fb)acts+=`<button class="abtn msg" onclick="window.open('${st.fb}','_blank')">📱 مسنجر</button>`;if(st&&st.ph)acts+=`<button class="abtn cal" onclick="location.href='tel:${st.ph}'">📞 اتصال</button>`;acts+=`<button class="abtn ord" onclick="oOrd('${p.id}','${p.sid}')">🛒 طلب</button>`;$('detContent').innerHTML=`<div style="background:#fff;border-radius:12px;overflow:hidden;box-shadow:var(--sh)"><div class="det-imgs">${imgs}</div><div class="det-info"><h1>${p.name}</h1><div class="dprice">${pr}</div><div class="ddesc">${p.description||''}</div><div style="margin-bottom:12px"><b>المتجر:</b> <span style="cursor:pointer;color:var(--pr)" onclick="openSt('${p.sid}')">${p.sName}</span></div>${p.delivery==='yes'?'<div style="color:var(--suc);margin-bottom:12px">✅ التوصيل متاح</div>':''}<div class="det-acts">${acts}</div></div></div>`;scrollTo(0,0)}

async function openSt(sid){document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_store').classList.add('act');if(sid==='admin'){$('storeHdr').innerHTML='<div style="display:flex;align-items:center;gap:12px"><div class="sav" style="width:55px;height:55px;font-size:22px">🛒</div><div><h2>BABA SANOOD</h2><p style="color:#888">المتجر الرسمي</p></div></div>';await renderCards(gA(D.ap).map(p=>({...p,sName:'BABA SANOOD',sid:'admin'})),'storeGrid')}else{const s=gA(D.s).find(x=>x.id===sid);if(!s)return;let ct='';if(s.fb)ct+=`<a href="${s.fb}" target="_blank" style="color:var(--pr)">📱 فيسبوك</a> `;if(s.ph)ct+=`<a href="tel:${s.ph}" style="color:var(--suc)">📞 ${s.ph}</a>`;$('storeHdr').innerHTML=`<div style="display:flex;align-items:center;gap:12px"><div class="sav" style="width:55px;height:55px;font-size:22px">${s.name[0]}</div><div><h2>${s.name}</h2><p style="color:#888">${s.type||''}</p><div style="margin-top:6px">${ct}</div></div></div>`;await renderCards(gA(D.p).filter(p=>p.sid===sid).map(p=>({...p,sName:s.name})),'storeGrid')}scrollTo(0,0)}

// ★ REGISTRATION WITH PRIVACY AGREEMENT ★
function regStore(){
  const nm=$('rName').value.trim(),tp=$('rType').value,em=$('rEmail').value.trim(),ph=$('rPhone').value.trim(),pw=$('rPass').value;
  if(!nm)return ntf('أدخل اسم المتجر','er');if(!tp)return ntf('اختر النوع','er');if(!pw)return ntf('أدخل كلمة السر','er');if(!em&&!ph)return ntf('أدخل إيميل أو هاتف','er');
  if(!$('privacyAgree').checked)return ntf('يجب الموافقة على سياسة الخصوصية وشروط الاستخدام','er');
  const ss=gA(D.s);if(ss.find(s=>s.name.toLowerCase()===nm.toLowerCase()))return ntf('الاسم موجود!','er');
  ss.push({id:'s_'+Date.now(),name:nm,type:tp,email:em,ph,password:pw,fb:'',desc:'',on:true,ts:Date.now(),agreedPrivacy:true});
  sA(D.s,ss);cMod('regMod');ntf('🎉 تم إنشاء "'+nm+'" بنجاح!');
  setTimeout(()=>{$('lName').value=nm;$('lPass').value=pw;oMod('logMod')},800);
}

function mLogin(){const nm=$('lName').value.trim(),pw=$('lPass').value;if(!nm||!pw)return ntf('أدخل البيانات','er');const s=gA(D.s).find(x=>x.name.toLowerCase()===nm.toLowerCase()&&x.password===pw);if(!s)return ntf('بيانات خاطئة','er');if(s.on===false)return ntf('متجرك معطّل','er');cMer=s;if($('lRem').checked)localStorage.setItem('bs_rem',JSON.stringify({n:nm,p:pw}));cMod('logMod');openDash();ntf('مرحباً في "'+s.name+'" ✅')}
function loadRem(){try{const r=localStorage.getItem('bs_rem');if(r){const{n,p}=JSON.parse(r);$('lName').value=n||'';$('lPass').value=p||'';$('lRem').checked=true}}catch(e){}}
function mLogout(){cMer=null;mImgs=[];nav('home')}

function openDash(){document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_dash').classList.add('act');$('dName').textContent='📊 '+cMer.name;$('sName').value=cMer.name;$('sFb').value=cMer.fb||'';$('sPh').value=cMer.ph||'';$('sDesc').value=cMer.desc||'';renderMyP();renderMyOrd();loadAdminContactForMerchant();document.querySelectorAll('#dNav .dtab').forEach(t=>t.classList.remove('act'));document.querySelectorAll('#pg_dash .dsec').forEach(s=>s.classList.remove('act'));document.querySelector('#dNav .dtab').classList.add('act');$('dProds').classList.add('act');scrollTo(0,0)}
function dTab(el,t){document.querySelectorAll('#dNav .dtab').forEach(x=>x.classList.remove('act'));document.querySelectorAll('#pg_dash .dsec').forEach(x=>x.classList.remove('act'));el.classList.add('act');$({prods:'dProds',addP:'dAddP',ords:'dOrds',sett:'dSett',mComp:'dMComp'}[t]).classList.add('act');if(t==='addP'){mImgs=[];$('mPrevs').innerHTML=''}if(t==='mComp')renderMerchCompHistory()}

// FILES
function setupFiles(){
  $('mFileIn').onchange=function(){procImgs(this.files,'m');this.value=''};
  $('aFileIn').onchange=function(){procImgs(this.files,'a');this.value=''};
  $('csvIn').onchange=function(){if(this.files[0])procCSV(this.files[0]);this.value=''};
  ['mUpArea','aUpArea'].forEach(id=>{const a=$(id),t=id==='mUpArea'?'m':'a';a.ondragover=e=>{e.preventDefault();a.classList.add('dov')};a.ondragleave=()=>a.classList.remove('dov');a.ondrop=e=>{e.preventDefault();a.classList.remove('dov');if(e.dataTransfer.files.length)procImgs(e.dataTransfer.files,t)}});
  const ca=$('csvArea');ca.ondragover=e=>{e.preventDefault();ca.classList.add('dov')};ca.ondragleave=()=>ca.classList.remove('dov');ca.ondrop=e=>{e.preventDefault();ca.classList.remove('dov');if(e.dataTransfer.files.length)procCSV(e.dataTransfer.files[0])};
}

function procImgs(files,t){
  const arr=t==='m'?mImgs:aImgs,pid=t==='m'?'mPrevs':'aPrevs',mx=5;
  if(arr.length>=mx)return ntf('الحد '+mx+' صور','er');
  const rem=mx-arr.length,ok=Array.from(files).filter(f=>f.type.startsWith('image/')).slice(0,rem);
  if(!ok.length)return ntf('صور فقط','er');
  let done=0;
  ok.forEach((f,i)=>{if(f.size>15e6)return ntf('كبيرة جداً','er');const r=new FileReader();r.onload=async ev=>{const d=ev.target.result;const comp=await new Promise(res=>{const img=new Image();img.onload=()=>{try{const c=document.createElement('canvas');let w=img.width,h=img.height;if(w>800){h=800/w*h;w=800}c.width=w;c.height=h;c.getContext('2d').drawImage(img,0,0,w,h);res(c.toDataURL('image/jpeg',.7))}catch(e){res(d)}};img.onerror=()=>res(d);img.src=d});const id='im_'+Date.now()+'_'+i+'_'+Math.random().toString(36).slice(2,6);await sImg(id,comp);arr.push(id);done++;await showPrev(arr,pid,t);if(done===ok.length)ntf('✅ '+done+' صورة')};r.readAsDataURL(f)});
}
async function showPrev(arr,cid,t){const c=$(cid);c.innerHTML='';for(let i=0;i<arr.length;i++){const id=arr[i];let src=id.startsWith('data:')||id.startsWith('http')?id:await gImg(id);if(!src)continue;const d=document.createElement('div');d.className='prev-item';d.innerHTML=`<img src="${src}"><button class="rm" data-i="${i}" data-t="${t}">✕</button>`;d.querySelector('.rm').onclick=function(e){e.preventDefault();e.stopPropagation();const idx=+this.dataset.i,tp=this.dataset.t;if(tp==='m'){mImgs.splice(idx,1);showPrev(mImgs,'mPrevs','m')}else{aImgs.splice(idx,1);showPrev(aImgs,'aPrevs','a')}};c.appendChild(d)}}

function addProd(){if(!cMer)return ntf('سجل الدخول','er');const nm=$('npName').value.trim(),pr=$('npPrice').value,ct=$('npCat').value,ds=$('npDesc').value.trim(),dl=$('npDel').value;if(!nm)return ntf('الاسم','er');if(!pr)return ntf('السعر','er');if(!ct)return ntf('القسم','er');const mt=[];if($('omMsg').checked)mt.push('msg');if($('omPh').checked)mt.push('ph');if($('omIn').checked)mt.push('in');const ps=gA(D.p);ps.push({id:'p_'+Date.now(),sid:cMer.id,name:nm,price:+pr,category:ct,description:ds,delivery:dl,methods:mt,imgs:[...mImgs],ts:Date.now()});sA(D.p,ps);$('npName').value='';$('npPrice').value='';$('npCat').value='';$('npDesc').value='';mImgs=[];$('mPrevs').innerHTML='';ntf('✅ تم النشر!');renderMyP();renderProds()}
async function renderMyP(){if(!cMer)return;const ps=gA(D.p).filter(p=>p.sid===cMer.id),c=$('myProds');if(!ps.length){c.innerHTML='<div class="empty"><div class="eico">📦</div><p>لا منتجات</p></div>';return}let h='<table class="dtbl"><thead><tr><th>صورة</th><th>المنتج</th><th>السعر</th><th>حذف</th></tr></thead><tbody>';for(const p of ps){let img='📷';if(p.imgs&&p.imgs.length){const f=p.imgs[0];let s=f.startsWith('data:')||f.startsWith('http')?f:await gImg(f);if(s)img=`<img src="${s}" style="width:42px;height:42px;object-fit:cover;border-radius:5px" onerror="this.outerHTML='📷'">`}h+=`<tr><td>${img}</td><td>${p.name}</td><td>${(+p.price).toLocaleString()} دج</td><td><button onclick="delP('${p.id}')" style="background:var(--dan);color:#fff;border:none;padding:4px 10px;border-radius:6px;cursor:pointer">🗑️</button></td></tr>`}c.innerHTML=h+'</tbody></table>'}
function delP(id){if(!confirm('حذف؟'))return;sA(D.p,gA(D.p).filter(p=>p.id!==id));renderMyP();renderProds();ntf('حذف','inf')}
function saveSett(){if(!cMer)return;const ss=gA(D.s),i=ss.findIndex(s=>s.id===cMer.id);if(i<0)return;ss[i].name=$('sName').value.trim()||ss[i].name;ss[i].fb=$('sFb').value.trim();ss[i].ph=$('sPh').value.trim();ss[i].desc=$('sDesc').value.trim();sA(D.s,ss);cMer=ss[i];$('dName').textContent='📊 '+cMer.name;ntf('✅ حفظ')}

function oOrd(pid,sid){$('oPid').value=pid;$('oSid').value=sid;oMod('ordMod')}
function subOrd(){const nm=$('oName').value.trim(),ph=$('oPhone').value.trim();if(!nm)return ntf('اسمك','er');if(!ph)return ntf('الهاتف','er');const pid=$('oPid').value,sid=$('oSid').value,all=[...gA(D.p),...gA(D.ap)],pr=all.find(p=>p.id===pid);const os=gA(D.o);os.push({id:'o_'+Date.now(),sid,pid,pName:pr?pr.name:'?',cName:nm,cPh:ph,wil:$('oWil').value.trim(),addr:$('oAddr').value.trim(),notes:$('oNotes').value.trim(),st:'جديد',ts:Date.now()});sA(D.o,os);cMod('ordMod');['oName','oPhone','oWil','oAddr','oNotes'].forEach(id=>$(id).value='');ntf('✅ تم الطلب!')}
function renderMyOrd(){if(!cMer)return;const os=gA(D.o).filter(o=>o.sid===cMer.id),c=$('mOrds');if(!os.length){c.innerHTML='<div class="empty"><div class="eico">📋</div><p>لا طلبات</p></div>';return}c.innerHTML='<table class="dtbl"><thead><tr><th>المنتج</th><th>الزبون</th><th>الهاتف</th><th>الولاية</th></tr></thead><tbody>'+os.slice().reverse().map(o=>`<tr><td>${o.pName}</td><td>${o.cName}</td><td>${o.cPh}</td><td>${o.wil||'-'}</td></tr>`).join('')+'</tbody></table>'}

// ★★★ CSV WITH SMART CATEGORY DETECTION ★★★
function procCSV(file){
  const ext=file.name.split('.').pop().toLowerCase();
  if(!['csv','txt'].includes(ext)&&!file.type.includes('csv')&&!file.type.includes('text'))return ntf('ارفع CSV','er');
  $('csvFn').textContent='📄 '+file.name;$('csvFn').classList.add('show');ntf('⏳ جاري القراءة...','inf');
  const r=new FileReader();r.onload=e=>{try{parseCSV(e.target.result)}catch(er){ntf('❌ '+er.message,'er')}};r.onerror=()=>ntf('❌ فشل','er');r.readAsText(file,'UTF-8');
}
function parseCSV(txt){
  txt=txt.replace(/^\uFEFF/,'');
  const fl=txt.split('\n')[0]||'';let dl=',';
  if((fl.match(/;/g)||[]).length>(fl.match(/,/g)||[]).length)dl=';';
  else if((fl.match(/\t/g)||[]).length>(fl.match(/,/g)||[]).length)dl='\t';
  const lines=txt.split(/\r?\n/).map(l=>l.trim()).filter(l=>l);
  if(lines.length<2)return ntf('❌ ملف فارغ','er');
  const hds=csvSplit(lines[0],dl).map(h=>h.toLowerCase().replace(/['"]/g,'').trim());
  const ni=fCol(hds,['name','product_name','اسم','title','اسم المنتج','nom']);
  const pi=fCol(hds,['price','original_price','سعر','السعر','prix','cost']);
  const ii=fCol(hds,['image','image_url','img','صورة','photo','url','الصورة','image_src']);
  const di=fCol(hds,['description','desc','الوصف','وصف','detail']);
  const ci=fCol(hds,['category','cat','القسم','الفئة','type','categorie']);
  let ok=0,fl2=0,errs=[],catStats={};const ap=gA(D.ap);
  for(let i=1;i<lines.length;i++){
    try{
      const cols=csvSplit(lines[i],dl);if(cols.length<2){fl2++;continue}
      const nm=clean(ni>=0?cols[ni]:cols[0]||'');
      if(!nm){fl2++;errs.push('سطر '+(i+1)+': فارغ');continue}
      let pr=clean(pi>=0?cols[pi]:cols[1]||'0').replace(/[^\d.,]/g,'').replace(',','.');
      let num=Math.round((parseFloat(pr)||0)*1.2);
      const im=clean(ii>=0&&cols[ii]?cols[ii]:'');
      const ds=clean(di>=0&&cols[di]?cols[di]:'');
      const rawCat=clean(ci>=0&&cols[ci]?cols[ci]:'');
      // ★ Smart detection: try raw category first, then detect from name+desc
      let mc='misc';
      if(rawCat){
        const cl=rawCat.toLowerCase();
        const fc=CATS.find(c=>c.n.includes(rawCat)||c.id===cl||cl.includes(c.id));
        if(fc)mc=fc.id;else mc=detectCategory(nm+' '+rawCat,ds);
      }else{
        mc=detectCategory(nm,ds);
      }
      catStats[mc]=(catStats[mc]||0)+1;
      ap.push({id:'ap_'+Date.now()+'_'+i,name:nm,price:num,imgUrl:im,imgs:im?[im]:[],description:ds,category:mc,delivery:'yes',sid:'admin',ts:Date.now()+i});
      ok++;
    }catch(e){fl2++;errs.push('سطر '+(i+1))}
  }
  sA(D.ap,ap);
  // Show results with category breakdown
  let catHtml='<div style="margin-top:8px"><b>📊 التوزيع على الأقسام:</b><div style="display:flex;flex-wrap:wrap;gap:4px;margin-top:4px">';
  for(const[cid,cnt]of Object.entries(catStats)){const c=CATS.find(x=>x.id===cid);catHtml+=`<span class="smart-cat-badge">${c?c.i:''} ${c?c.n:cid}: ${cnt}</span>`}
  catHtml+='</div></div>';
  const rs=$('csvRes');rs.classList.add('show');
  rs.innerHTML=`<div style="color:var(--suc);font-weight:700">✅ ${ok} منتج (+20%)</div>${fl2?`<div style="color:var(--dan);font-size:12px">❌ فشل ${fl2}</div>`:''}${catHtml}`;
  ntf('✅ '+ok+' منتج مع فرز ذكي!');$('admPCount').textContent=gA(D.ap).length;renderAdmP();renderProds();
}
function clean(s){return(s||'').replace(/^["'\s]+|["'\s]+$/g,'').trim()}
function csvSplit(l,d){const r=[];let c='',q=false;for(let i=0;i<l.length;i++){const ch=l[i];if(ch==='"'){if(q&&l[i+1]==='"'){c+='"';i++}else q=!q}else if(ch===d&&!q){r.push(c);c=''}else c+=ch}r.push(c);return r}
function fCol(h,ns){for(let i=0;i<h.length;i++){const x=h[i];for(const n of ns)if(x===n||x.includes(n)||n.includes(x))return i}return -1}

// ADMIN PRODUCTS
function addAdmProd(){const nm=$('apPName').value.trim(),pr=$('apPPrice').value;if(!nm)return ntf('الاسم','er');if(!pr)return ntf('السعر','er');const fp=Math.round(+pr*1.2);const cat=$('apPCat').value||detectCategory(nm,$('apPDesc').value);const ap=gA(D.ap);ap.push({id:'ap_'+Date.now(),name:nm,price:fp,category:cat,description:$('apPDesc').value.trim(),imgs:[...aImgs],delivery:'yes',sid:'admin',ts:Date.now()});sA(D.ap,ap);$('apPName').value='';$('apPPrice').value='';$('apPDesc').value='';aImgs=[];$('aPrevs').innerHTML='';ntf('✅ '+fp.toLocaleString()+' دج');$('admPCount').textContent=gA(D.ap).length;renderAdmP();renderProds()}
async function renderAdmP(){const ap=gA(D.ap),c=$('amMyProds');$('admPCount').textContent=ap.length;if(!ap.length){c.innerHTML='<div class="empty"><div class="eico">📦</div><p>لا منتجات</p></div>';return}let h='<table class="dtbl"><thead><tr><th>صورة</th><th>المنتج</th><th>السعر</th><th>القسم</th><th>حذف</th></tr></thead><tbody>';for(const p of ap.slice(-50).reverse()){let img='📷';if(p.imgs&&p.imgs.length){const f=p.imgs[0];let s=(f.startsWith('data:')||f.startsWith('http'))?f:await gImg(f);if(s)img=`<img src="${s}" style="width:42px;height:42px;object-fit:cover;border-radius:5px" onerror="this.outerHTML='📷'">`}else if(p.imgUrl)img=`<img src="${p.imgUrl}" style="width:42px;height:42px;object-fit:cover;border-radius:5px" onerror="this.outerHTML='📷'">`;const cat=CATS.find(x=>x.id===p.category);h+=`<tr><td>${img}</td><td style="max-width:140px;overflow:hidden;text-overflow:ellipsis">${p.name}</td><td>${p.price?p.price.toLocaleString():'-'}</td><td><span class="smart-cat-badge">${cat?cat.i+' '+cat.n:'?'}</span></td><td><button onclick="delAP('${p.id}')" style="background:var(--dan);color:#fff;border:none;padding:4px 8px;border-radius:6px;cursor:pointer">🗑️</button></td></tr>`}c.innerHTML=h+'</tbody></table>'}
function delAP(id){if(!confirm('حذف؟'))return;sA(D.ap,gA(D.ap).filter(p=>p.id!==id));renderAdmP();renderProds();ntf('حذف','inf')}

// ★★★ ADMIN CONTACT INFO ★★★
function saveContact(){
  sO(D.ct,{ph:$('adPh').value.trim(),wa:$('adWa').value.trim(),email:$('adEmail').value.trim(),fb:$('adFb').value.trim(),addr:$('adAddr').value.trim(),hours:$('adHours').value.trim()});
  ntf('✅ تم حفظ معلومات الاتصال');updateFooterContact();
}
function loadAdminContact(){const c=gO(D.ct);$('adPh').value=c.ph||'';$('adWa').value=c.wa||'';$('adEmail').value=c.email||'';$('adFb').value=c.fb||'';$('adAddr').value=c.addr||'';$('adHours').value=c.hours||''}
function loadPublicContact(){const c=gO(D.ct);let h='<div class="contact-box"><h4>📞 معلومات الاتصال بالإدارة</h4>';if(c.ph)h+=`<div class="ci"><span>📱</span><a href="tel:${c.ph}">${c.ph}</a></div>`;if(c.wa)h+=`<div class="ci"><span>📱</span><a href="https://wa.me/${c.wa}" target="_blank">واتساب: ${c.wa}</a></div>`;if(c.email)h+=`<div class="ci"><span>📧</span><a href="mailto:${c.email}">${c.email}</a></div>`;if(c.fb)h+=`<div class="ci"><span>📘</span><a href="${c.fb}" target="_blank">فيسبوك</a></div>`;if(c.addr)h+=`<div class="ci"><span>📍</span>${c.addr}</div>`;if(c.hours)h+=`<div class="ci"><span>🕐</span>${c.hours}</div>`;if(!c.ph&&!c.wa&&!c.email)h+='<p style="color:#aaa;font-size:12px">لم يتم إضافة معلومات اتصال بعد</p>';h+='</div>';$('publicContactInfo').innerHTML=h}
function loadAdminContactForMerchant(){const c=gO(D.ct);let h='<div class="contact-box"><h4>📞 معلومات الإدارة</h4>';if(c.ph)h+=`<div class="ci"><span>📱</span><a href="tel:${c.ph}">${c.ph}</a></div>`;if(c.wa)h+=`<div class="ci"><span>📱</span><a href="https://wa.me/${c.wa}" target="_blank">واتساب</a></div>`;if(c.email)h+=`<div class="ci"><span>📧</span>${c.email}</div>`;h+='</div>';$('adminContactInfo').innerHTML=h}
function updateFooterContact(){const c=gO(D.ct);let h='';if(c.ph)h+=`📱 ${c.ph}<br>`;if(c.email)h+=`📧 ${c.email}`;$('footerContact').innerHTML=h}

// ★★★ COMPLAINTS SYSTEM ★★★
function subMerchComp(){
  if(!cMer)return;const txt=$('mCompTxt').value.trim(),tp=$('mCompType').value;
  if(!txt)return ntf('اكتب الرسالة','er');
  const cs=gA(D.c);cs.push({id:'c_'+Date.now(),txt,type:tp,from:'store',storeName:cMer.name,storeId:cMer.id,ts:Date.now()});
  sA(D.c,cs);$('mCompTxt').value='';ntf('✅ تم الإرسال');renderMerchCompHistory();
}
function renderMerchCompHistory(){
  if(!cMer)return;const cs=gA(D.c).filter(c=>c.storeId===cMer.id);
  const c=$('mCompHistory');
  if(!cs.length){c.innerHTML='<p style="color:#aaa;font-size:12px">لم ترسل أي رسالة بعد</p>';return}
  c.innerHTML='<h4 style="margin-bottom:8px">📬 رسائلي السابقة</h4>'+cs.slice().reverse().map(x=>`<div class="comp-card from-store"><div class="comp-meta"><span>${x.type}</span><span>${new Date(x.ts).toLocaleString('ar')}</span></div><p style="font-size:13px">${x.txt}</p></div>`).join('');
}

function subVisitorMsg(){
  const nm=$('vName').value.trim(),ct=$('vContact').value.trim(),tp=$('vType').value,msg=$('vMsg').value.trim();
  if(!nm)return ntf('أدخل اسمك','er');if(!msg)return ntf('اكتب الرسالة','er');
  const cs=gA(D.c);cs.push({id:'c_'+Date.now(),txt:msg,type:tp,from:'visitor',visitorName:nm,visitorContact:ct,ts:Date.now()});
  sA(D.c,cs);$('vName').value='';$('vContact').value='';$('vMsg').value='';cMod('contactMod');ntf('✅ تم إرسال رسالتك!');
}

function filterComp(el,f){compFilter=f;document.querySelectorAll('#amComp .dtab').forEach(x=>x.classList.remove('act'));el.classList.add('act');renderComp()}
function renderComp(){
  let cs=gA(D.c);
  if(compFilter==='store')cs=cs.filter(c=>c.from==='store');
  else if(compFilter==='visitor')cs=cs.filter(c=>c.from==='visitor');
  const c=$('compList');
  if(!cs.length){c.innerHTML='<div class="empty"><div class="eico">📭</div><p>لا رسائل</p></div>';return}
  c.innerHTML=cs.slice().reverse().map(x=>{
    const isStore=x.from==='store';
    const sender=isStore?`🏪 ${x.storeName||'تاجر'}`:`👤 ${x.visitorName||'زائر'}${x.visitorContact?' ('+x.visitorContact+')':''}`;
    return`<div class="comp-card ${isStore?'from-store':'from-visitor'}"><div class="comp-meta"><span>${sender}</span><span class="comp-type ${isStore?'t-store':'t-visitor'}">${x.type||'رسالة'}</span><span>${new Date(x.ts).toLocaleString('ar')}</span></div><p style="font-size:13px">${x.txt}</p></div>`;
  }).join('');
}

// ADMIN
function admLogin(){if($('admPass').value==='04081985HMR'){cMod('admMod');document.querySelectorAll('.page').forEach(x=>x.classList.remove('act'));$('pg_admin').classList.add('act');const a=gO(D.a);$('apName').value=a.n||'BABA SANOOD';$('apClr1').value=a.c1||'#1a73e8';$('apClr2').value=a.c2||'#ff6b35';loadAdminContact();renderAmSt();renderStats();renderComp();renderAdmP();ntf('مرحباً 🛡️');scrollTo(0,0)}else ntf('❌','er');$('admPass').value=''}
function aTab(el,t){document.querySelectorAll('#amNav .ambtn').forEach(x=>x.classList.remove('act'));document.querySelectorAll('#pg_admin .amsec').forEach(x=>x.classList.remove('act'));el.classList.add('act');$({look:'amLook',contact:'amContact',merch:'amMerch',stat:'amStat',comp:'amComp',myS:'amMyS'}[t]).classList.add('act');if(t==='myS'){aImgs=[];$('aPrevs').innerHTML='';renderAdmP()}if(t==='comp')renderComp()}
function saveApp(){sO(D.a,{n:$('apName').value.trim(),c1:$('apClr1').value,c2:$('apClr2').value});ntf('✅ حفظ')}
function renderAmSt(){const ss=gA(D.s),c=$('amStores');if(!ss.length){c.innerHTML='<div class="empty"><div class="eico">🏪</div><p>لا متاجر</p></div>';return}c.innerHTML=ss.map(s=>`<div class="scard"><div class="sav">${s.name[0]}</div><div class="sinf"><h4>${s.name}</h4><p>${s.type} | ${s.email||s.ph||'-'}</p><p style="font-size:10px">${s.agreedPrivacy?'✅ وافق على الشروط':'⚠️ قديم'}</p></div><div><label class="tgl"><input type="checkbox" ${s.on!==false?'checked':''} onchange="tglSt('${s.id}',this.checked)"><span></span></label><div style="font-size:10px;text-align:center;margin-top:3px">${s.on!==false?'<span class="badge g">مفعّل</span>':'<span class="badge r">معطّل</span>'}</div></div></div>`).join('')}
function tglSt(id,on){const ss=gA(D.s),i=ss.findIndex(s=>s.id===id);if(i>=0){ss[i].on=on;sA(D.s,ss);renderAmSt();renderProds();ntf(on?'✅':'❌',on?'ok':'er')}}
function renderStats(){const ss=gA(D.s),ps=gA(D.p),ap=gA(D.ap),os=gA(D.o),js=gA(D.j),cs=gA(D.c);$('amStats').innerHTML=`<div class="stat-grid"><div class="stat-card" style="background:linear-gradient(135deg,#4CAF50,#388E3C)"><div class="snum">${ss.length}</div><div class="slbl">متجر</div></div><div class="stat-card" style="background:linear-gradient(135deg,#2196F3,#1976D2)"><div class="snum">${ps.length+ap.length}</div><div class="slbl">منتج</div></div><div class="stat-card" style="background:linear-gradient(135deg,#FF9800,#F57C00)"><div class="snum">${os.length}</div><div class="slbl">طلب</div></div><div class="stat-card" style="background:linear-gradient(135deg,#9C27B0,#7B1FA2)"><div class="snum">${js.length}</div><div class="slbl">وظيفة</div></div><div class="stat-card" style="background:linear-gradient(135deg,#00897b,#004d40)"><div class="snum">${cs.length}</div><div class="slbl">رسالة</div></div></div><table class="dtbl"><thead><tr><th>المتجر</th><th>النوع</th><th>المنتجات</th><th>الطلبات</th><th>الحالة</th></tr></thead><tbody>${ss.map(s=>`<tr><td>${s.name}</td><td>${s.type}</td><td>${ps.filter(p=>p.sid===s.id).length}</td><td>${os.filter(o=>o.sid===s.id).length}</td><td>${s.on!==false?'<span class="badge g">✓</span>':'<span class="badge r">✗</span>'}</td></tr>`).join('')}</tbody></table>`}

// JOBS
function jTab(el,t){document.querySelectorAll('#pg_jobs .jtab').forEach(x=>x.classList.remove('act'));document.querySelectorAll('#pg_jobs .dsec').forEach(x=>x.classList.remove('act'));el.classList.add('act');$({browse:'jBrowse',post:'jPost',seek:'jSeek'}[t]).classList.add('act');if(t==='browse')renderJobs()}
function postJob(){const co=$('jComp').value.trim(),tp=$('jType').value.trim(),ct=$('jCont').value.trim();if(!co||!tp)return ntf('المؤسسة والوظيفة','er');if(!ct)return ntf('الاتصال','er');const js=gA(D.j);js.push({id:'j_'+Date.now(),co,tp,req:$('jReq').value.trim(),sal:$('jSal').value.trim(),loc:$('jLoc').value.trim(),ct,jt:'offer',ts:Date.now()});sA(D.j,js);['jComp','jType','jReq','jSal','jLoc','jCont'].forEach(id=>$(id).value='');ntf('✅ نشر')}
function subSeeker(){const nm=$('skName').value.trim(),sk=$('skSkill').value.trim(),ph=$('skPhone').value.trim();if(!nm||!sk)return ntf('الاسم والتخصص','er');if(!ph)return ntf('الهاتف','er');const js=gA(D.j);js.push({id:'js_'+Date.now(),co:nm,tp:sk,req:$('skExp').value.trim(),sal:'',loc:'',ct:ph,jt:'seek',ts:Date.now()});sA(D.j,js);['skName','skAge','skSkill','skExp','skPhone'].forEach(id=>$(id).value='');ntf('✅ تسجيل')}
function renderJobs(){const js=gA(D.j),c=$('jobList');if(!js.length){c.innerHTML='<div class="empty"><div class="eico">💼</div><p>لا وظائف</p></div>';return}c.innerHTML=js.slice().reverse().map(j=>`<div class="jcard"><div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:6px"><h3>${j.tp}</h3><span class="badge ${j.jt==='offer'?'g':'r'}">${j.jt==='offer'?'📢 فرصة':'🔍 باحث'}</span></div><p><b>${j.co}</b></p>${j.req?`<p style="color:#555;margin-top:4px;font-size:13px">${j.req}</p>`:''}<div class="jmeta">${j.sal?`<span>💰 ${j.sal}</span>`:''}${j.loc?`<span>📍 ${j.loc}</span>`:''}<span>📞 ${j.ct}</span></div></div>`).join('')}

function doSearch(q){if(!q.trim()){renderProds();return}const ql=q.toLowerCase(),f=allProds().filter(p=>(p.name&&p.name.toLowerCase().includes(ql))||(p.description&&p.description.toLowerCase().includes(ql))||(p.sName&&p.sName.toLowerCase().includes(ql)));if(!f.length){$('mainGrid').innerHTML='';$('emptyMsg').innerHTML='<div class="eico">🔍</div><p>لا نتائج لـ "'+q+'"</p>';$('emptyMsg').style.display='block'}else{$('emptyMsg').style.display='none';renderCards(f,'mainGrid')}}

function infoPage(t){
  const pg={
    priv:{t:'🔒 سياسة الخصوصية',c:'<h3>حماية البيانات</h3><ul><li>نحمي بياناتك الشخصية ولا نشاركها مع أطراف ثالثة</li><li>كل تاجر مسؤول عن محتوى متجره</li><li>بيانات الطلبات محمية ولا يطلع عليها إلا التاجر المعني</li><li>يحق لك طلب حذف بياناتك في أي وقت</li><li>نستخدم التشفير لحماية المعلومات الحساسة</li><li>لا نقوم بتتبع نشاطك خارج المنصة</li></ul>'},
    terms:{t:'📜 شروط الاستخدام',c:'<h3>شروط استخدام المنصة</h3><ul><li>يمنع نشر محتوى مخالف للقانون أو الأخلاق</li><li>يمنع بيع منتجات محظورة أو مقلدة</li><li>كل تاجر مسؤول قانونياً عن منتجاته</li><li>يحق للإدارة تعطيل أي متجر مخالف</li><li>يجب احترام الزبائن والتجار الآخرين</li><li>عند التسجيل أنت توافق على هذه الشروط</li><li>يحق للإدارة تعديل الشروط في أي وقت</li></ul>'},
    guide:{t:'📖 الدليل',c:'<h4>🛒 للمتسوقين:</h4><ol><li>تصفح المنتجات أو استخدم الأقسام</li><li>اضغط على أي منتج لعرض التفاصيل</li><li>اطلب عبر مسنجر أو اتصال أو استمارة</li></ol><h4>🏪 للتجار:</h4><ol><li>اضغط "فتح متجر" وسجل بياناتك</li><li>وافق على سياسة الخصوصية</li><li>ادخل من "دخول التاجر"</li><li>أضف منتجاتك مع صور وأسعار</li><li>تابع الطلبات والشكاوى</li></ol>'},
    faq:{t:'❓ أسئلة شائعة',c:'<p><b>كيف أفتح متجر؟</b><br>اضغط فتح متجر، سجل بياناتك ووافق على الشروط</p><p><b>هل مجاني؟</b><br>نعم، التسجيل والنشر مجاني</p><p><b>كم صورة يمكنني رفعها؟</b><br>حتى 5 صور لكل منتج</p><p><b>كيف أتواصل مع الإدارة؟</b><br>من لوحة التحكم > تواصل مع الإدارة، أو زر "تواصل معنا"</p><p><b>نسيت كلمة السر؟</b><br>أرسل رسالة للإدارة</p>'},
    copy:{t:'©️ حقوق الملكية',c:'<p>© 2025 سوق تبسة العملاق - BABA SANOOD</p><ul><li>جميع الحقوق محفوظة لصاحب المشروع</li><li>يمنع النسخ أو الاستنساخ دون إذن</li><li>كل تاجر مسؤول عن محتوى متجره</li></ul>'}
  };
  const p=pg[t];if(!p)return;
  const o=document.createElement('div');o.className='mov act';o.onclick=e=>{if(e.target===o)o.remove()};
  o.innerHTML=`<div class="mdl" style="max-width:650px"><div class="mdl-h"><h2>${p.t}</h2><button class="mdl-x" onclick="this.closest('.mov').remove()">✕</button></div><div class="mdl-b" style="line-height:1.8">${p.c}</div></div>`;
  document.body.appendChild(o);
}

// INIT
async function init(){
  await initIDB();
  const a=gO(D.a);if(a.n)$('pName').textContent=a.n;if(a.c1)document.documentElement.style.setProperty('--pr',a.c1);if(a.c2)document.documentElement.style.setProperty('--sec',a.c2);
  renderCats();fillCatSel();setupFiles();loadRem();updateFooterContact();await renderProds();
}
init();
</script>
</body>
</html>
  
    
}

async function init(){
  await initIDB();
  // ★ محاولة جلب البيانات من السحابة عند التشغيل ★
  for(const key of Object.values(D)) {
    const cloudData = await cloudSync('load', key);
    if(cloudData) localStorage.setItem(key, JSON.stringify(cloudData));
  }
  const a=gO(D.a);if(a.n)$('pName').textContent=a.n;if(a.c1)document.documentElement.style.setProperty('--pr',a.c1);if(a.c2)document.documentElement.style.setProperty('--sec',a.c2);
  renderCats();fillCatSel();setupFiles();loadRem();updateFooterContact();await renderProds();
}
init();
</script>
</body>
</html>
