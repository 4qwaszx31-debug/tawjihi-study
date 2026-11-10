<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>مُذاكر التوجيهي</title>
<style>
:root{
  --bg:#f4f6fb;--card:#fff;--text:#1d2433;--muted:#6b7488;--border:#e2e6ef;
  --accent:#2563eb;--accent-text:#fff;--ok:#16a34a;--bad:#dc2626;--shadow:0 2px 10px rgba(20,30,60,.08);
}
body.dark{
  --bg:#0f141c;--card:#182030;--text:#e8ecf5;--muted:#9aa5bd;--border:#2a3550;--shadow:0 2px 10px rgba(0,0,0,.4);
}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{margin:0;background:var(--bg);color:var(--text);
  font-family:"Segoe UI",Tahoma,"Noto Naskh Arabic","Noto Sans Arabic",system-ui,sans-serif;line-height:1.7}
button,input,select,textarea{font:inherit;color:inherit}
button{cursor:pointer}
header{position:sticky;top:0;z-index:20;background:var(--card);border-bottom:1px solid var(--border);box-shadow:var(--shadow)}
.top{display:flex;align-items:center;gap:10px;padding:10px 14px;flex-wrap:wrap}
.logo{font-weight:800;font-size:1.15rem}
.spacer{flex:1}
.icon-btn{border:1px solid var(--border);background:var(--bg);border-radius:10px;padding:6px 12px}
.books{display:flex;gap:8px;overflow-x:auto;padding:0 14px 10px;scrollbar-width:none}
.books::-webkit-scrollbar{display:none}
.book{flex:0 0 auto;display:flex;align-items:center;gap:6px;border:2px solid var(--border);background:var(--bg);
  padding:6px 14px;border-radius:999px;font-weight:600;white-space:nowrap}
.book .dot{width:10px;height:10px;border-radius:50%}
.book.active{border-color:var(--c);background:var(--card);box-shadow:0 0 0 3px color-mix(in srgb,var(--c) 22%,transparent)}
.book .ed{opacity:.5;font-size:.8rem}
nav.views{display:flex;border-top:1px solid var(--border)}
nav.views button{flex:1;border:0;background:transparent;padding:10px 4px;font-weight:700;color:var(--muted);border-bottom:3px solid transparent}
nav.views button.active{color:var(--accent);border-bottom-color:var(--accent)}
main{max-width:1100px;margin:0 auto;padding:14px}
.view{display:none}.view.active{display:block}
.panel{background:var(--card);border:1px solid var(--border);border-radius:16px;box-shadow:var(--shadow);padding:14px;margin-bottom:14px}
h2{margin:0 0 10px;font-size:1.1rem}
.btn{border:1px solid var(--border);background:var(--bg);border-radius:10px;padding:7px 14px;font-weight:600}
.btn.primary{background:var(--accent);color:var(--accent-text);border-color:var(--accent)}
.btn.ok{background:var(--ok);border-color:var(--ok);color:#fff}
.btn.bad{background:var(--bad);border-color:var(--bad);color:#fff}
.btn.sm{padding:3px 10px;font-size:.85rem}
.btn:active{transform:scale(.97)}
.row{display:flex;gap:8px;flex-wrap:wrap;align-items:center}
input[type=text],textarea,select{width:100%;background:var(--bg);border:1px solid var(--border);border-radius:10px;padding:8px 12px}
textarea{min-height:140px;resize:vertical}

/* السبورة */
.toolbar{display:flex;gap:6px;flex-wrap:wrap;align-items:center;margin-bottom:10px}
.tool{border:1px solid var(--border);background:var(--bg);border-radius:10px;padding:6px 10px;font-weight:600}
.tool.active{background:var(--accent);color:#fff;border-color:var(--accent)}
.sw{width:26px;height:26px;border-radius:50%;border:2px solid var(--border);padding:0}
.sw.active{outline:3px solid var(--accent);outline-offset:1px}
input[type=color]{width:34px;height:30px;padding:0;border:0;background:none}
.canvas-wrap{border:2px solid var(--border);border-radius:14px;overflow:hidden;background:#fff}
canvas#cv{display:block;width:100%;height:auto;touch-action:none;cursor:crosshair}

/* التلخيص */
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:14px}
@media(max-width:800px){.grid2{grid-template-columns:1fr}}
.summary-out{background:var(--bg);border:1px dashed var(--border);border-radius:12px;padding:12px;min-height:90px}
.summary-out li{margin-bottom:6px}
.chips{display:flex;gap:6px;flex-wrap:wrap;margin:8px 0}
.chip{background:color-mix(in srgb,var(--accent) 14%,transparent);color:var(--accent);padding:2px 12px;border-radius:999px;font-weight:700;font-size:.9rem}
.item{display:flex;align-items:center;gap:8px;border:1px solid var(--border);border-radius:12px;padding:8px 12px;margin-bottom:8px;background:var(--bg)}
.item .t{flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.muted{color:var(--muted);font-size:.9rem}

/* الفلاش كاردز */
.stats{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:12px}
.stat{flex:1;min-width:90px;text-align:center;background:var(--bg);border:1px solid var(--border);border-radius:12px;padding:6px}
.stat b{display:block;font-size:1.3rem}
.scene{perspective:1200px;max-width:640px;margin:0 auto}
.flip{position:relative;height:280px;transform-style:preserve-3d;transition:transform .5s;cursor:pointer}
.flip.flipped{transform:rotateY(180deg)}
.face{position:absolute;inset:0;backface-visibility:hidden;-webkit-backface-visibility:hidden;border-radius:18px;
  display:flex;align-items:center;justify-content:center;text-align:center;padding:22px;font-size:1.25rem;font-weight:600;
  border:2px solid var(--border);box-shadow:var(--shadow);overflow:auto}
.face.front{background:var(--card)}
.face.back{background:color-mix(in srgb,var(--accent) 10%,var(--card));transform:rotateY(180deg);border-color:var(--accent)}
.face small{position:absolute;top:8px;right:14px;color:var(--muted);font-size:.75rem;font-weight:400}
.study-actions{display:flex;gap:10px;justify-content:center;margin-top:14px;flex-wrap:wrap}
.empty{text-align:center;padding:30px 10px;color:var(--muted)}
.boxbar{display:flex;gap:3px;margin-top:2px;justify-content:center}
.boxbar i{width:18px;height:6px;border-radius:3px;background:var(--border)}
.boxbar i.on{background:var(--ok)}
#toast{position:fixed;bottom:20px;left:50%;transform:translateX(-50%);background:#111c;color:#fff;padding:8px 18px;border-radius:999px;
  opacity:0;pointer-events:none;transition:.3s;z-index:99}
#toast.show{opacity:1}
</style>
</head>
<body>
<header>
  <div class="top">
    <div class="logo">📚 مُذاكر التوجيهي</div>
    <div class="spacer"></div>
    <button class="icon-btn" id="themeBtn" title="الوضع الليلي">🌙</button>
  </div>
  <div class="books" id="books"></div>
  <nav class="views" id="views">
    <button data-v="board">🖍️ السبورة</button>
    <button data-v="sum">📝 التلخيص</button>
    <button data-v="cards">🃏 الفلاش كاردز</button>
  </nav>
</header>

<main>
<!-- ======================= السبورة ======================= -->
<section class="view" id="v-board">
  <div class="panel">
    <div class="toolbar" id="tools">
      <button class="tool active" data-t="pen">✏️ قلم</button>
      <button class="tool" data-t="eraser">🧽 ممحاة</button>
      <button class="tool" data-t="line">╱ خط</button>
      <button class="tool" data-t="rect">▭ مستطيل</button>
      <button class="tool" data-t="ellipse">⬭ دائرة</button>
      <button class="tool" data-t="text">🔤 نص</button>
    </div>
    <div class="toolbar">
      <span id="swatches" class="row"></span>
      <input type="color" id="colorPick" value="#111111" title="لون مخصص">
      <label class="muted">السُمك</label>
      <input type="range" id="size" min="1" max="30" value="4">
      <select id="bgSel" style="width:auto">
        <option value="#ffffff">خلفية بيضاء</option>
        <option value="#1f4d3a">سبورة خضراء</option>
        <option value="#14181f">سبورة سوداء</option>
        <option value="#fff8dc">ورق أصفر</option>
      </select>
    </div>
    <div class="toolbar">
      <button class="btn" id="undoBtn">↩️ تراجع</button>
      <button class="btn bad" id="clearBtn">🗑️ مسح السبورة</button>
      <button class="btn primary" id="dlBtn">⬇️ حفظ كصورة</button>
      <span class="muted">كل كتاب له سبورة خاصة تُحفظ تلقائياً</span>
    </div>
    <div class="canvas-wrap"><canvas id="cv" width="1400" height="800"></canvas></div>
  </div>
</section>

<!-- ======================= التلخيص ======================= -->
<section class="view" id="v-sum">
  <div class="grid2">
    <div class="panel">
      <h2>الصق نص الدرس</h2>
      <input type="text" id="sumTitle" placeholder="عنوان الدرس (اختياري)">
      <textarea id="sumIn" placeholder="الصق هنا نص الدرس أو الفقرة المراد تلخيصها..." style="margin-top:8px;min-height:220px"></textarea>
      <div class="row" style="margin-top:10px">
        <label class="muted">نسبة التلخيص: <b id="pctLbl">30%</b></label>
        <input type="range" id="pct" min="10" max="70" value="30" style="flex:1;min-width:120px">
      </div>
      <div class="row" style="margin-top:10px">
        <button class="btn primary" id="sumBtn">✨ لخّص</button>
        <button class="btn" id="sumClear">مسح</button>
      </div>
      <p class="muted">التلخيص يتم داخل المتصفح بدون إنترنت: يختار أهم الجمل حسب تكرار المفاهيم وموقعها في النص.</p>
    </div>
    <div class="panel">
      <h2>الملخص</h2>
      <div class="muted" id="sumStats"></div>
      <div class="chips" id="kw"></div>
      <div class="summary-out" id="sumOut"><span class="muted">سيظهر الملخص هنا.</span></div>
      <div class="row" style="margin-top:10px">
        <button class="btn" id="copyBtn">📋 نسخ</button>
        <button class="btn" id="saveSum">💾 حفظ</button>
      </div>
      <hr style="border:0;border-top:1px solid var(--border);margin:14px 0">
      <h2>🃏 حوّل الملخص إلى بطاقات</h2>
      <div class="row">
        <select id="genMode" style="flex:1">
          <option value="term">سؤال عن مصطلح ← الجملة الشارحة</option>
          <option value="cloze">املأ الفراغ (إخفاء المصطلح)</option>
        </select>
        <button class="btn ok" id="genBtn">إنشاء بطاقات</button>
      </div>
    </div>
  </div>
  <div class="panel">
    <h2>ملخصاتي المحفوظة</h2>
    <div id="sumList"></div>
  </div>
</section>

<!-- ======================= الفلاش كاردز ======================= -->
<section class="view" id="v-cards">
  <div class="panel">
    <div class="stats" id="stats"></div>
    <div id="study"></div>
  </div>
  <div class="grid2">
    <div class="panel">
      <h2>➕ إضافة بطاقة</h2>
      <input type="text" id="cQ" placeholder="السؤال / الوجه الأمامي">
      <textarea id="cA" placeholder="الجواب / الوجه الخلفي" style="margin-top:8px;min-height:90px"></textarea>
      <div class="row" style="margin-top:8px">
        <button class="btn primary" id="addCard">إضافة</button>
        <button class="btn" id="expBtn">⬆️ تصدير</button>
        <button class="btn" id="impBtn">⬇️ استيراد</button>
        <input type="file" id="impFile" accept=".json" hidden>
      </div>
    </div>
    <div class="panel">
      <h2>بطاقات الكتاب</h2>
      <div id="cardList" style="max-height:360px;overflow:auto"></div>
    </div>
  </div>
</section>
</main>
<div id="toast"></div>

<script>
(function(){
'use strict';
const $=s=>document.querySelector(s), $$=s=>[...document.querySelectorAll(s)];
const KEY='tawjihi_study_v1';
const DEF_BOOKS=[
  {id:'b1',name:'اللغة العربية',color:'#e11d48'},
  {id:'b2',name:'اللغة الإنجليزية',color:'#2563eb'},
  {id:'b3',name:'الثقافة الإسلامية',color:'#16a34a'},
  {id:'b4',name:'تاريخ الأردن',color:'#d97706'}
];
let S=load();
function load(){
  try{const x=JSON.parse(localStorage.getItem(KEY));if(x&&x.books)return x}catch(e){}
  return {books:DEF_BOOKS,cur:'b1',view:'board',boards:{},bg:{},summaries:{},cards:{},theme:'light'};
}
function save(){try{localStorage.setItem(KEY,JSON.stringify(S))}catch(e){toast('⚠️ مساحة التخزين ممتلئة')}}
function esc(s){return String(s).replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]))}
function uid(){return Date.now().toString(36)+Math.random().toString(36).slice(2,6)}
let tt;function toast(m){const t=$('#toast');t.textContent=m;t.classList.add('show');clearTimeout(tt);tt=setTimeout(()=>t.classList.remove('show'),2000)}
const book=()=>S.books.find(b=>b.id===S.cur)||S.books[0];

/* ---------- الواجهة العامة ---------- */
function applyTheme(){document.body.classList.toggle('dark',S.theme==='dark');$('#themeBtn').textContent=S.theme==='dark'?'☀️':'🌙'}
$('#themeBtn').onclick=()=>{S.theme=S.theme==='dark'?'light':'dark';applyTheme();save()};

function renderBooks(){
  const el=$('#books');el.innerHTML='';
  S.books.forEach(b=>{
    const d=document.createElement('button');
    d.className='book'+(b.id===S.cur?' active':'');d.style.setProperty('--c',b.color);
    d.innerHTML=`<span class="dot" style="background:${b.color}"></span>${esc(b.name)} <span class="ed" title="تعديل الاسم">✎</span>`;
    d.onclick=e=>{
      if(e.target.classList.contains('ed')){
        const n=prompt('اسم الكتاب:',b.name);
        if(n&&n.trim()){b.name=n.trim();save();renderBooks()}
        return;
      }
      switchBook(b.id);
    };
    el.appendChild(d);
  });
}
function switchBook(id){
  if(id===S.cur)return;
  persistBoard();S.cur=id;save();renderBooks();loadBoard();renderSumList();renderCards();clearSummaryView();
}
function setView(v){
  S.view=v;save();
  $$('.view').forEach(x=>x.classList.toggle('active',x.id==='v-'+v));
  $$('#views button').forEach(x=>x.classList.toggle('active',x.dataset.v===v));
  if(v==='board')loadBoard();
  if(v==='cards')renderCards();
}
$$('#views button').forEach(b=>b.onclick=()=>setView(b.dataset.v));

/* ---------- السبورة ---------- */
const cv=$('#cv'),ctx=cv.getContext('2d');
let tool='pen',color='#111111',size=4,drawing=false,st=null,base=null,undo=[],saveT;
const COLORS=['#111111','#ffffff','#dc2626','#2563eb','#16a34a','#f59e0b','#9333ea'];
function renderSwatches(){
  const w=$('#swatches');w.innerHTML='';
  COLORS.forEach(c=>{
    const b=document.createElement('button');b.className='sw'+(c===color?' active':'');b.style.background=c;
    b.onclick=()=>{color=c;$('#colorPick').value=c;renderSwatches()};w.appendChild(b);
  });
}
renderSwatches();
$('#colorPick').oninput=e=>{color=e.target.value;renderSwatches()};
$('#size').oninput=e=>size=+e.target.value;
$$('#tools .tool').forEach(b=>b.onclick=()=>{
  tool=b.dataset.t;$$('#tools .tool').forEach(x=>x.classList.toggle('active',x===b));
});
const bgNow=()=>S.bg[S.cur]||'#ffffff';
function fillBg(){ctx.fillStyle=bgNow();ctx.fillRect(0,0,cv.width,cv.height)}
function loadBoard(){
  $('#bgSel').value=bgNow();undo=[];fillBg();
  const d=S.boards[S.cur];
  if(d){const im=new Image();im.onload=()=>ctx.drawImage(im,0,0,cv.width,cv.height);im.src=d}
}
function persistBoard(){clearTimeout(saveT);try{S.boards[S.cur]=cv.toDataURL('image/png');save()}catch(e){}}
function schedSave(){clearTimeout(saveT);saveT=setTimeout(persistBoard,600)}
function pushUndo(){undo.push(cv.toDataURL());if(undo.length>20)undo.shift()}
function pos(e){const r=cv.getBoundingClientRect();return{x:(e.clientX-r.left)*cv.width/r.width,y:(e.clientY-r.top)*cv.height/r.height}}
function style(){
  ctx.lineCap='round';ctx.lineJoin='round';
  ctx.strokeStyle=tool==='eraser'?bgNow():color;ctx.fillStyle=color;
  ctx.lineWidth=tool==='eraser'?size*4:size;
}
cv.addEventListener('pointerdown',e=>{
  e.preventDefault();const p=pos(e);
  if(tool==='text'){
    const t=prompt('اكتب النص:');if(t){pushUndo();ctx.fillStyle=color;
      ctx.font=`bold ${Math.max(18,size*6)}px "Segoe UI",Tahoma,sans-serif`;ctx.direction='rtl';ctx.textAlign='right';
      ctx.fillText(t,p.x,p.y);persistBoard()}
    return;
  }
  cv.setPointerCapture(e.pointerId);pushUndo();drawing=true;st=p;style();
  if(tool==='pen'||tool==='eraser'){ctx.beginPath();ctx.moveTo(p.x,p.y);ctx.lineTo(p.x+.01,p.y+.01);ctx.stroke()}
  else base=ctx.getImageData(0,0,cv.width,cv.height);
});
cv.addEventListener('pointermove',e=>{
  if(!drawing)return;const p=pos(e);
  if(tool==='pen'||tool==='eraser'){ctx.lineTo(p.x,p.y);ctx.stroke();return}
  ctx.putImageData(base,0,0);style();ctx.beginPath();
  if(tool==='line'){ctx.moveTo(st.x,st.y);ctx.lineTo(p.x,p.y)}
  else if(tool==='rect'){ctx.rect(st.x,st.y,p.x-st.x,p.y-st.y)}
  else if(tool==='ellipse'){ctx.ellipse((st.x+p.x)/2,(st.y+p.y)/2,Math.abs(p.x-st.x)/2,Math.abs(p.y-st.y)/2,0,0,Math.PI*2)}
  ctx.stroke();
});
['pointerup','pointercancel'].forEach(ev=>cv.addEventListener(ev,()=>{if(drawing){drawing=false;base=null;schedSave()}}));
$('#undoBtn').onclick=()=>{
  const d=undo.pop();if(!d){toast('لا يوجد ما يُتراجع عنه');return}
  const im=new Image();im.onload=()=>{ctx.drawImage(im,0,0,cv.width,cv.height);persistBoard()};
  fillBg();im.src=d;
};
$('#clearBtn').onclick=()=>{if(confirm('مسح السبورة بالكامل؟')){pushUndo();fillBg();persistBoard()}};
$('#bgSel').onchange=e=>{
  if(confirm('تغيير الخلفية سيمسح السبورة الحالية. متابعة؟')){S.bg[S.cur]=e.target.value;fillBg();persistBoard();
    color=e.target.value==='#ffffff'||e.target.value==='#fff8dc'?'#111111':'#ffffff';$('#colorPick').value=color;renderSwatches()}
  else e.target.value=bgNow();
};
$('#dlBtn').onclick=()=>{const a=document.createElement('a');a.href=cv.toDataURL('image/png');a.download='سبورة-'+book().name+'.png';a.click()};
window.addEventListener('beforeunload',persistBoard);

/* ---------- التلخيص ---------- */
const STOP=new Set(('في من على الى إلى عن مع هذا هذه ذلك تلك هو هي هم هن انا نحن انت التي الذي الذين اللذان كان كانت يكون تكون ان أن إن لا ما لم لن قد كل بعد قبل بين حتى او أو ثم اذا إذا كما لكن بل عند عندما حيث اي أي ايضا أيضا فقد وقد وهو وهي وفي ومن وعلى وان وأن وكان به بها بهم له لها لهم منه منها فيه فيها عليه عليها اي كذلك هنا هناك التى ضمن خلال عبر لدى دون غير سوى the a an of and to in is are was were be been it that this for on with as by at from or not'.split(/\s+/)).map(w=>norm(w)));
function norm(w){return w.replace(/[\u064B-\u0652\u0640]/g,'').replace(/[إأآ]/g,'ا').replace(/ى/g,'ي').replace(/ة/g,'ه').toLowerCase()}
function stem(w){
  w=norm(w);
  w=w.replace(/^(وال|بال|كال|فال|لل)/,'ال');
  if(w.length>4&&w.startsWith('ال'))w=w.slice(2);
  if(w.length>4&&/^[وفبل]/.test(w)&&!/^(وزير|وطن|وقت|ولاي|فلسط|بلاد|بدا|لغ)/.test(w))w=w.slice(1);
  if(w.length>4&&/(ات|ون|ين|ان|ها|هم)$/.test(w))w=w.slice(0,-2);
  return w;
}
const WORD=/[\u0600-\u06FFa-zA-Z0-9]+/g;
function sentences(t){
  return t.replace(/\r/g,'').split(/(?<=[.!?؟؛।。])\s+|\n+/).map(s=>s.trim()).filter(s=>s.split(/\s+/).length>=4);
}
function analyze(text,pct){
  const sents=sentences(text);
  const freq={},show={};
  sents.forEach(s=>(s.match(WORD)||[]).forEach(w=>{
    const k=stem(w);if(k.length<3||STOP.has(norm(w))||STOP.has(k)||/^\d+$/.test(k))return;
    freq[k]=(freq[k]||0)+1;if(!show[k])show[k]=w.replace(/^(وال|بال|كال|فال)/,'ال');
  }));
  const max=Math.max(1,...Object.values(freq));
  const scored=sents.map((s,i)=>{
    const ws=(s.match(WORD)||[]);let sc=0;
    ws.forEach(w=>{const k=stem(w);if(freq[k])sc+=freq[k]/max});
    sc=sc/Math.sqrt(ws.length||1);
    if(i===0)sc*=1.4;else if(i<3)sc*=1.15;
    if(ws.length>45)sc*=.7;
    return{s,i,sc};
  });
  const n=Math.max(1,Math.min(sents.length,Math.round(sents.length*pct/100)));
  const pick=[...scored].sort((a,b)=>b.sc-a.sc).slice(0,n).sort((a,b)=>a.i-b.i);
  const kws=Object.entries(freq).filter(([k,v])=>v>1||Object.keys(freq).length<10).sort((a,b)=>b[1]-a[1]).slice(0,10).map(([k])=>({k,w:show[k]}));
  return{sents,pick,kws,scored};
}
let lastSum=null;
$('#pct').oninput=e=>$('#pctLbl').textContent=e.target.value+'%';
function clearSummaryView(){lastSum=null;$('#sumOut').innerHTML='<span class="muted">سيظهر الملخص هنا.</span>';$('#kw').innerHTML='';$('#sumStats').textContent=''}
$('#sumBtn').onclick=()=>{
  const t=$('#sumIn').value.trim();
  if(t.length<40){toast('الصق نصاً أطول للتلخيص');return}
  const r=analyze(t,+$('#pct').value);
  if(!r.sents.length){toast('لم أجد جملاً كافية');return}
  lastSum={...r,text:t};
  $('#sumOut').innerHTML='<ul>'+r.pick.map(x=>`<li>${esc(x.s)}</li>`).join('')+'</ul>';
  $('#kw').innerHTML=r.kws.map(k=>`<span class="chip">${esc(k.w)}</span>`).join('');
  $('#sumStats').textContent=`اختير ${r.pick.length} من ${r.sents.length} جملة`;
};
$('#sumClear').onclick=()=>{$('#sumIn').value='';$('#sumTitle').value='';clearSummaryView()};
function sumText(){return lastSum?lastSum.pick.map(x=>'• '+x.s).join('\n'):''}
$('#copyBtn').onclick=()=>
