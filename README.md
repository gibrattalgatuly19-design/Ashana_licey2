<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Асхана Білім-Инновация лицея · Учёт питания</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,600;9..144,700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --navy-900:#151F35;
    --navy-800:#1D2C4B;
    --navy-700:#2A3E64;
    --parchment:#F6F1E6;
    --parchment-dark:#ECE3CE;
    --brass:#AD8A50;
    --brass-light:#D4B876;
    --ink:#221E17;
    --ink-soft:#645D4C;
    --debt:#9A3B2C;
    --paid:#49624C;
    --line:#D9CEB2;
    --line-dark:#3C4E75;
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:var(--navy-900);
    font-family:'Inter',system-ui,sans-serif;
    color:var(--ink);
    -webkit-font-smoothing:antialiased;
  }
  .shell{max-width:1120px;margin:0 auto;padding:0 0 48px;}
  header.top{
    background:linear-gradient(180deg,var(--navy-900),var(--navy-800));
    border-bottom:1px solid var(--line-dark);
    padding:28px 24px 0;
  }
  .top-inner{max-width:1120px;margin:0 auto;}
  .crest-row{display:flex;align-items:baseline;justify-content:space-between;flex-wrap:wrap;gap:12px;}
  .crest-name{display:flex;align-items:center;gap:12px;}
  .crest-logo{
    width:44px;
    height:44px;
    object-fit:contain;
    background:var(--parchment);
    border-radius:50%;
    padding:3px;
    flex:0 0 auto;
  }
  .crest-title{
    font-family:'Fraunces',serif;
    color:var(--parchment);
    font-size:26px;
    font-weight:600;
    letter-spacing:.2px;
    margin:0;
  }
  .crest-sub{
    color:#9FB0CE;
    font-size:13px;
    margin:2px 0 0;
  }
  nav.tabs{display:flex;gap:4px;margin-top:22px;}
  nav.tabs button{
    background:none;
    border:none;
    color:#9FB0CE;
    font-family:'Inter',sans-serif;
    font-size:14.5px;
    font-weight:500;
    padding:12px 6px;
    margin-right:22px;
    cursor:pointer;
    border-bottom:2px solid transparent;
  }
  nav.tabs button.active{
    color:var(--parchment);
    border-bottom:2px solid var(--brass-light);
  }
  main{
    background:var(--parchment);
    padding:32px 24px 56px;
    border-radius:0;
  }
  h2.section-title{
    font-family:'Fraunces',serif;
    font-size:21px;
    font-weight:600;
    margin:0 0 4px;
    color:var(--ink);
  }
  p.section-hint{
    color:var(--ink-soft);
    font-size:13.5px;
    margin:0 0 22px;
  }
  select.student-select{
    width:100%;
    max-width:520px;
    font-family:'Inter',sans-serif;
    font-size:14.5px;
    padding:11px 12px;
    border:1px solid var(--line);
    background:#fff;
    color:var(--ink);
    border-radius:2px;
  }
  .student-meta{
    margin-top:14px;
    font-size:13.5px;
    color:var(--ink-soft);
  }
  .student-meta b{color:var(--ink);font-weight:600;}
  .login-box{display:flex;gap:8px;max-width:420px;flex-wrap:wrap;}
  .login-box .search-box{max-width:280px;}
  .welcome-box{
    background:var(--navy-800);
    color:var(--parchment);
    padding:22px 24px;
    margin-bottom:26px;
    border-left:4px solid var(--brass-light);
  }
  .welcome-title{
    font-family:'Fraunces',serif;
    font-size:18px;
    font-weight:600;
    margin:0 0 8px;
  }
  .welcome-text{
    font-size:13.5px;
    line-height:1.6;
    color:#C9D4E8;
    margin:0;
    max-width:640px;
  }
  .login-btn{
    font-family:'Inter',sans-serif;font-size:14px;font-weight:500;
    background:var(--navy-800);color:var(--parchment);border:none;
    padding:0 20px;cursor:pointer;border-radius:2px;
  }
  .login-error{color:var(--debt);font-size:13px;margin-top:10px;}
  .cabinet-topbar{
    display:flex;justify-content:space-between;align-items:center;
    flex-wrap:wrap;gap:10px;margin-bottom:6px;
  }
  .logout-btn{
    font-family:'Inter',sans-serif;font-size:13px;font-weight:500;
    background:#fff;color:var(--ink-soft);border:1px solid var(--line);
    padding:7px 14px;cursor:pointer;border-radius:2px;
  }
  .card-grid{
    display:grid;
    grid-template-columns:1fr;
    gap:1px;
    background:var(--line);
    border:1px solid var(--line);
    margin-top:24px;
  }
  .meal-card{
    background:var(--parchment);
    padding:16px 18px;
    display:flex;
    align-items:center;
    gap:16px;
  }
  .meal-card .emoji{font-size:26px;flex:0 0 auto;}
  .meal-card .label{
    font-family:'Fraunces',serif;
    font-size:16px;
    font-weight:600;
    margin:0;
    flex:1 1 auto;
    min-width:100px;
  }
  .meal-card .stats{
    display:flex;
    gap:28px;
    flex:0 0 auto;
  }
  .meal-card .row{
    display:flex;
    flex-direction:column;
    font-size:12.5px;
    color:var(--ink-soft);
    gap:3px;
    text-align:right;
  }
  .meal-card .row b{color:var(--ink);font-weight:600;font-size:15px;font-variant-numeric:tabular-nums;}
  .totals{
    margin-top:1px;
    border:1px solid var(--line);
    border-top:none;
    background:var(--parchment-dark);
    padding:18px 20px;
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
    gap:14px;
  }
  .totals .t-item .t-label{font-size:12.5px;color:var(--ink-soft);margin-bottom:4px;}
  .totals .t-item .t-value{font-family:'Fraunces',serif;font-size:20px;font-weight:600;font-variant-numeric:tabular-nums;}
  .totals .t-item.debt .t-value{color:var(--debt);}
  .totals .t-item.paid .t-value{color:var(--paid);}
  .admin-controls{display:flex;flex-direction:column;gap:16px;margin-bottom:22px;}
  input.search-box{
    width:100%;
    max-width:420px;
    font-family:'Inter',sans-serif;
    font-size:14px;
    padding:10px 12px;
    border:1px solid var(--line);
    background:#fff;
    border-radius:2px;
  }
  .class-filters{display:flex;flex-direction:column;gap:6px;max-width:340px;}
  .class-filters .row-all button{width:100%;}
  .class-filters .row-pair{display:grid;grid-template-columns:1fr 1fr;gap:6px;}
  .class-filters button{
    font-family:'Inter',sans-serif;
    font-size:13.5px;
    font-weight:500;
    padding:8px 10px;
    border:1px solid var(--line);
    background:#fff;
    color:var(--ink-soft);
    cursor:pointer;
    border-radius:2px;
  }
  .class-filters button.active{
    background:var(--navy-800);
    border-color:var(--navy-800);
    color:var(--parchment);
  }
  .result-count{font-size:12.5px;color:var(--ink-soft);}
  table.admin-table{
    width:100%;
    border-collapse:collapse;
    background:#fff;
    border:1px solid var(--line);
  }
  table.admin-table thead th{
    text-align:left;
    font-size:12px;
    font-weight:600;
    color:var(--ink-soft);
    padding:10px 12px;
    border-bottom:1px solid var(--line);
    background:var(--parchment-dark);
  }
  table.admin-table tbody td{
    font-size:13.5px;
    padding:10px 12px;
    border-bottom:1px solid var(--line);
  }
  table.admin-table tbody tr{cursor:pointer;}
  table.admin-table tbody tr:hover{background:var(--parchment);}
  table.admin-table td.code{font-variant-numeric:tabular-nums;color:var(--ink-soft);}
  table.admin-table td.debt-cell{font-variant-numeric:tabular-nums;font-weight:600;color:var(--debt);}
  table.admin-table td.debt-cell.zero{color:var(--paid);}
  .pager{
    display:flex;
    align-items:center;
    justify-content:space-between;
    margin-top:16px;
    font-size:13px;
    color:var(--ink-soft);
    flex-wrap:wrap;
    gap:10px;
  }
  .pager .btns{display:flex;gap:6px;}
  .pager button{
    font-family:'Inter',sans-serif;
    font-size:13px;
    padding:7px 12px;
    border:1px solid var(--line);
    background:#fff;
    color:var(--ink);
    cursor:pointer;
    border-radius:2px;
  }
  .pager button:disabled{opacity:.4;cursor:default;}
  .modal-backdrop{
    position:fixed;inset:0;background:rgba(21,31,53,.55);
    display:flex;align-items:flex-start;justify-content:center;
    padding:32px 16px;overflow-y:auto;z-index:50;
  }
  .modal{
    background:var(--parchment);
    max-width:760px;width:100%;
    border:1px solid var(--line);
    margin-bottom:32px;
  }
  .modal-head{
    background:var(--navy-800);
    color:var(--parchment);
    padding:18px 22px;
    display:flex;justify-content:space-between;align-items:flex-start;
  }
  .modal-head h3{font-family:'Fraunces',serif;margin:0 0 4px;font-size:19px;font-weight:600;}
  .modal-head p{margin:0;font-size:12.5px;color:#9FB0CE;}
  .modal-head button{
    background:none;border:none;color:var(--parchment);
    font-size:20px;cursor:pointer;line-height:1;padding:2px;
  }
  .modal-body{padding:22px;}
  .edit-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:12px;margin-bottom:4px;}
  .field-label{display:block;font-size:12px;color:var(--ink-soft);margin-bottom:5px;}
  .edit-grid .search-box{width:100%;max-width:none;}
  table.att-table{width:100%;border-collapse:collapse;font-size:12.5px;margin-bottom:22px;}
  table.att-table th,table.att-table td{
    border:1px solid var(--line);
    padding:7px 6px;
    text-align:center;
  }
  table.att-table th{background:var(--parchment-dark);font-weight:600;color:var(--ink-soft);}
  table.att-table td.date-cell{text-align:left;color:var(--ink-soft);white-space:nowrap;}
  table.att-table td input[type=checkbox]{width:16px;height:16px;cursor:pointer;accent-color:var(--navy-800);}
  .pay-history{font-size:13px;margin-bottom:18px;}
  .pay-history ul{list-style:none;padding:0;margin:8px 0 0;}
  .pay-history li{
    display:flex;justify-content:space-between;
    padding:6px 0;border-bottom:1px solid var(--line);
    color:var(--ink-soft);
  }
  .pay-history li b{color:var(--paid);font-variant-numeric:tabular-nums;}
  .pay-form{display:flex;gap:8px;margin-top:10px;}
  .pay-form input{
    flex:1;font-family:'Inter',sans-serif;font-size:13.5px;
    padding:8px 10px;border:1px solid var(--line);border-radius:2px;
  }
  .pay-form button{
    background:var(--navy-800);color:var(--parchment);border:none;
    padding:8px 16px;font-size:13.5px;font-weight:500;cursor:pointer;border-radius:2px;
  }
  .site-footer{
    background:var(--navy-900);
    border-top:1px solid var(--line-dark);
    padding:18px 24px;
  }
  .footer-inner{
    display:flex;
    align-items:center;
    justify-content:space-between;
    flex-wrap:wrap;
    gap:10px;
    padding:0 !important;
  }
  .footer-note{color:#7C8CAE;font-size:12.5px;}
  .footer-credit{
    text-align:center;
    color:#4E5C7C;
    font-size:11.5px;
    padding-top:12px;
    margin-top:12px;
    border-top:1px solid var(--line-dark);
  }
  .footer-admin-link{
    background:none;
    border:1px solid var(--line-dark);
    color:#9FB0CE;
    font-family:'Inter',sans-serif;
    font-size:12.5px;
    font-weight:500;
    padding:8px 14px;
    cursor:pointer;
    border-radius:2px;
  }
  .footer-admin-link:hover{color:var(--parchment);border-color:var(--brass-light);}
  @media (max-width:560px){
    .crest-title{font-size:21px;}
    main{padding:24px 14px 48px;}
    table.att-table{font-size:11px;}
    .meal-card{flex-wrap:wrap;}
    .meal-card .stats{gap:18px;width:100%;justify-content:flex-start;margin-top:4px;}
    .meal-card .row{text-align:left;}
  }
</style>
</head>
<body>
<div id="app"></div>

<script>
/* ======================= DATA MODEL ======================= */
const LOGO_SRC = "data:image/jpeg;base64,...(base64 data omitted for readability)...";

const MEALS = [
  {key:'breakfast', label:'Завтрак',  emoji:'🥐', price:450, prob:.82},
  {key:'lunch',     label:'Обед',     emoji:'🍲', price:900, prob:.90},
  {key:'snack',     label:'Полдник',  emoji:'🥪', price:350, prob:.68},
  {key:'dinner',    label:'Ужин',     emoji:'🍽️', price:750, prob:.75},
  {key:'late',      label:'Поздник',  emoji:'🌙', price:300, prob:.40},
];

const CLASSES = ["7а", "7ә", "8а", "8ә", "9а", "9ә", "10а", "10ә", "11а", "11ә"];

const ROSTER = {
  "11а": [
    "Абубакиров Жанибек","Аманжан Әли","Әміржан Нұрмұхамед","Барлык Исламбек","Болат Олжас",
    "Жандулет Асхат","Жумабек Санжар","Давлетов Есентай","Қазанбаев Сулеймен","Қыдырбай Нұрислам",
    "Маратов Тамир","Малік Нұртай","Мухтубаев Али","Мынбай Санжар","Манарбеков Диас",
    "Нұрмұхан Нұрали","Рат Мадияр","Суйесинов Алмас","Тайжан Асылбек","Танирбергенов Ануар",
    "Тенелгали Бекарыстан","Тлеумбетов Инкарбек","Хамит Дінислам","Шокат Шыңғыс","Шуйіншбай Актілек"
  ],
  "10а": [
    "Азуханов Алим","Али Ахмет","Алтайулы Али","Бакыт Султан","Бегалы Ахмад",
    "Бисенгалиев Ислам","Варин Марк","Досанов Батыр","Дуйсенбаев Орас","Ерали Тамерлан",
    "Еркин Диас","Ернар Арнат","Эменов Омар","Жумаженов Азамат","Латиф Дамир",
    "Михальченко Ильфат","Мырсакан Мадияр","Нагашибаев Амир","Наурызбаев Исмаил","Нығмет Әбдірасул",
    "Тимуруллы Абдуллах","Тлеумбетов Ерамир","Турмахан Нуртас","Шакирбай Рахман","Шекей Бауыржан"
  ],
  "9а": [
    "Ақылбек Сардар","Аманғос Омаралым","Аширгали Алишер","Базарбай Өміржан","Бердіұрат Ахмет",
    "Ғабит Әбубакр","Даулетов Жаңгір","Джусупов Амирхан","Жайыкұлы Хакім","Жангельдиев Данияр",
    "Жандосулы Жансерик","Караман Тамерлан","Кадір Айбар","Кубенкулов Даулен","Мұхамбет Бекалы",
    "Наурыз Әміржан","Орда Дастан","Сериков Темірлан","Тайшиев Дамир","Талғатұлы Гибрат",
    "Тәнкиев Ескендір","Турдыбеков Алихан","Уайсбаев Альтаир","Уланды Алимхан","Хажиолиев Телеген"
  ],
  "8а": [
    "Аманкелді Бактияр","Амантай Санжар","Аяндлы Алинур","Базарбай Баубек","Бердіұрат Ибрахим",
    "Гасер Бекзат","Дельмагамбетов Жанибек","Даулеткерей Бектас","Досмагамбетов Азат","Ермек Ансар",
    "Жаксыбаев Бекет","Жанатов Әділет","Жарылгасын Абдулазиз","Жетпісбай Нурасыл","Биранов Дамир",
    "Жумабеков Дарын","Имашев Нурдаулет","Кептілеу Тлеш","Куат Дінмухамед","Мардонкулов Жаффар",
    "Махамбет Ісбасар","Мұса Яссауи","Нуркасын Хантере","Тулен Санжар","Теміржан Ерсултан"
  ],
  "7а": [
    "Абілеріков Хасан","Аманкельдин Айдын","Амантай Мират","Бексұлтан Рауан","Гиниат Мират",
    "Даулет Дастан","Жаксылык Айсултан","Жаксылык Ерсултан","Жанғали Дінмұхаммед","Закария Расул",
    "Керимбай Халид","Қалыков Санжар","Куаныш Дамир","Мокушев Амир","Мурат Арман",
    "Мураткалиев Али","Нуржан Азиз","Нурыш Жан","Орда Әлішер","Өмірзак Әлихан",
    "Салыкбаев Әлинур","Сафи Бек","Тайбукенов Таир","Токтар Мади","Усенов Карим"
  ],
  "11ә": [
    "Ақжанбеков Нұрдаулет","Ақпанов Арсен","Амантай Ырысбек","Асхат Ерасыл","Әбілов Бекнұр",
    "Болаш Қасым","Дуйжанов Арсен","Жайыкулы Мухаммед","Жакия Әділжан","Жалғаспай Әділ",
    "Жолдыбай Ибрагим","Жумабеков Манас","Исмагулов Данияр","Қыдырулы Хасан","Мамбеталы Султанбейбарыс",
    "Ниетов Асыл","Нурхан Нурлан","Орал Әли","Рахметов Даулет","Сағынгали Абдуссатар",
    "Садыков Аланур","Хамит Арсен","Іскендір Әлихан"
  ],
  "10ә": [
    "Аудандаев Нуртас","Ахметалиев Гумар","Бахыткали Бауыржан","Бурумбаев Аяз","Ермекбай Нурислам",
    "Есберген Кайсар","Есеналин Нурлан","Есенкулов Мирас","Жангельдин Бексат","Жанбурбаев Нурдаулет",
    "Косанов Алишер","Майор Есет","Мурат Алихан","Нуржан Куантхан","Омар Нурасыл",
    "Орынбасар Расул","Карабалин Бейбарыс","Рахимов Аман","Рахманов Даниал","Салык Мансур",
    "Саматов Ерасыл","Сейтказиев Нурсейит","Султанбек Салих","Талгатулы Әділет","Тазу Сулеймен",
    "Тулеген Расул"
  ],
  "9ә": [
    "Абай Ерасыл","Ақжулов Жарылкасын","Алимов Арман","Ахмет Султан","Ахметов Шыныгыс",
    "Бактыгереев Нурдос","Ғалымжан Нурислам","Елеусіз Бекарыс","Ермуханов Ислам","Әбіідолла Бактияр",
    "Жаксыбаев Есет","Жакып Расым","Жоныс Ахмет","Илиясов Ерсултан","Кулфаизов Досан",
    "Каиргали Оркен","Кайырбек Нурасыл","Мусаев Магжан","Наурызбай Әділет","Ондасын Әділхан",
    "Оразов Азамат","Сабыр Санжар","Тахгуразов Санат","Таубай Еркебулан","Хамит Даниал"
  ],
  "8ә": [
    "Айткали Арыстан","Ақылбек Әділет","Балтабай Наурызбай","Баянгали Жангир","Бек Мансур",
    "Ертерек Әділ","Әбдіразак Әмір","Әлмырза Шадияр","Жанабаев Санжар","Коспаев Аміржан",
    "Кулманов Амир","Калжан Ерасыл","Кожабай Даулет","Максатбай Ғалымжан","Мейржанулы Хасан",
    "Нагашыбай Бекарыс","Нургалиев Әмиржан","Нуркасымов Нурислам","Отанбаев Турсынбек","Разиев Ерасыл",
    "Сайран Бибарс","Сейітказы Дилахмет","Сулиханов Умар","Тхралы Таир"
  ],
  "7ә": [
    "Абай Әділ","Амандык Нуралы","Базарбай Аманжан","Боранғали Дидар","Ғали Нурсултан",
    "Ғалымжанов Әділет","Даулетов Абылайхан","Ерболов Нурлат","Ернар Нурали","Есенбаев Айдархан",
    "Имаш Талгын","Истемиров Мирхан","Кансултанов Азиз","Кусетов Беколат","Кыдырбай Мухаммедали",
    "Мурсарматов Нурсаид","Ерланды Медет","Нурланов Ержан","Самбай Мухаммед Әли","Сансызбаев Данияр",
    "Сапаров Ерали","Тілеш Мирас","Шыңғыс Арсен","Іліяс Абдусалям"
  ]
};

function pad4(n){ return String(n).padStart(4,'0'); }

function businessDays(n){
  const out=[]; let d=new Date();
  while(out.length<n){
    const day=d.getDay();
    if(day!==0 && day!==6) out.unshift(new Date(d));
    d.setDate(d.getDate()-1);
  }
  return out;
}
const DATES = businessDays(15);
const DATE_KEYS = DATES.map(d=>d.toISOString().slice(0,10));
function fmtDate(k){
  const d=new Date(k);
  return d.toLocaleDateString('ru-RU',{day:'2-digit',month:'2-digit'});
}

function buildStudentCode(className, positionInClass, usedCodes){
  const gradeNum = parseInt(className.match(/\d+/)[0], 10);
  const gradeDigit = String(gradeNum % 10);           // 7,8,9 as-is; 10→0, 11→1
  const literaDigit = className.includes('ә') ? '2' : '1';
  const posDigits = String(positionInClass).padStart(2,'0');
  let code;
  do{
    const rand3 = String(Math.floor(Math.random()*1000)).padStart(3,'0');
    code = gradeDigit + literaDigit + posDigits + rand3;
  } while(usedCodes.has(code));
  usedCodes.add(code);
  return code;
}

function makeStudents(){
  const usedCodes = new Set();

  const stubs = [];
  let counter = 0;
  CLASSES.forEach(cn=>{
    (ROSTER[cn] || []).forEach(fullName=>{
      counter++;
      const parts = fullName.trim().split(/\s+/);
      const lastName = parts[0];
      const firstName = parts.slice(1).join(' ') || parts[0];
      stubs.push({
        internalId: 'S'+pad4(counter),
        className: cn,
        firstName,
        lastName,
      });
    });
  });

  CLASSES.forEach(cn=>{
    stubs.filter(s=>s.className===cn)
      .sort((a,b)=> a.lastName.localeCompare(b.lastName,'ru') || a.firstName.localeCompare(b.firstName,'ru'))
      .forEach((s,i)=>{ s.positionInClass = i+1; });
  });

  const students = stubs.map(s=>{
    const code = buildStudentCode(s.className, s.positionInClass, usedCodes);
    const attendance = {};
    let totalCost = 0;
    DATE_KEYS.forEach(dk=>{
      attendance[dk] = {};
      MEALS.forEach(m=>{
        const was = Math.random() < m.prob;
        attendance[dk][m.key] = was;
        if(was) totalCost += m.price;
      });
    });
    const paidFactor = Math.random()*0.65 + 0.45;
    let paid = Math.round(totalCost * paidFactor / 50) * 50;
    paid = Math.max(0, paid);
    const payments = [];
    let remaining = paid;
    const nPayments = remaining > 0 ? (Math.random()<0.5 ? 2 : 3) : 0;
    for(let p=0; p<nPayments; p++){
      const isLast = p === nPayments-1;
      const amt = isLast ? remaining : Math.round((remaining/(nPayments-p)) * (0.7+Math.random()*0.6) / 50)*50;
      const clamped = Math.max(0, Math.min(amt, remaining));
      if(clamped>0){
        const randDate = DATES[Math.floor(Math.random()*DATES.length)];
        payments.push({date: randDate.toISOString().slice(0,10), amount: clamped});
      }
      remaining -= clamped;
    }
    payments.sort((a,b)=>a.date.localeCompare(b.date));

    return {
      id: s.internalId,
      code,
      firstName: s.firstName,
      lastName: s.lastName,
      className: s.className,
      attendance,
      payments,
    };
  });

  return students;
}

let STUDENTS = makeStudents();
let STUDENTS_BY_ID = {};
STUDENTS.forEach(s=>STUDENTS_BY_ID[s.id]=s);

function calcAggregates(student){
  const perMeal = {};
  let totalVisits = 0, totalCost = 0;
  MEALS.forEach(m=>{
    let count=0;
    DATE_KEYS.forEach(dk=>{ if(student.attenda
