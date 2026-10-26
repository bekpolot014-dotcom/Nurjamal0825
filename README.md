<!DOCTYPE html>
<html lang="ky">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="theme-color" content="#0b0620">
<title>Нуржамал, мага турмушка чыгасыңбы? 💍</title>
<style>
:root{--rose:#ff5c8a;--gold:#ffd98a;--ink:#fff4f8}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{height:100%;margin:0;overflow:hidden}
body{background:radial-gradient(120% 80% at 50% 115%,#8a2468 0%,#33124f 42%,#0b0620 100%);color:var(--ink);font:17px/1.55 system-ui,"Segoe UI",Roboto,sans-serif}
canvas{position:fixed;inset:0;width:100%;height:100%;pointer-events:none}
#bg{z-index:1}#fx{z-index:30}
.moon{position:fixed;z-index:1;top:16%;right:9%;width:60px;height:60px;border-radius:50%;background:radial-gradient(circle at 35% 35%,#fffbe8,#ffe6a8 60%,#e8c377);box-shadow:0 0 50px 14px rgba(255,230,160,.35);opacity:.9}
h1,h2{font-family:"Noto Serif",Georgia,serif;line-height:1.25;margin:.2em 0 .5em;background:linear-gradient(90deg,#ffd98a,#ffc2d9,#ffd98a);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent}
h1{font-size:clamp(1.7rem,7.4vw,2.5rem)}h2{font-size:clamp(1.35rem,6vw,1.9rem)}
p{margin:.5em 0}.sub{color:#ffc2d9;font-size:1.05rem}.hint{font-size:.88rem;opacity:.75}.em{font-size:3rem;animation:float 3s ease-in-out infinite}
.sc{position:fixed;inset:0;z-index:5;display:flex;padding:calc(104px + env(safe-area-inset-top)) 18px calc(22px + env(safe-area-inset-bottom));overflow-y:auto;text-align:center;opacity:0;visibility:hidden;transform:translateY(16px) scale(.97);transition:opacity .8s,transform .8s,visibility 0s .8s}
.sc.on{opacity:1;visibility:visible;transform:none;transition:opacity .8s,transform .8s}
.in{margin:auto;width:100%;max-width:520px}
/* player */
#pl{position:fixed;z-index:40;top:calc(8px + env(safe-area-inset-top));left:50%;transform:translateX(-50%);width:min(94vw,440px);padding:8px 12px 10px;border-radius:18px;background:rgba(22,9,46,.88);border:1px solid rgba(255,255,255,.18);box-shadow:0 6px 24px rgba(0,0,0,.35)}
#pl b{font-family:Georgia,serif;font-size:1rem;color:var(--gold)}
.r1,.r2{display:flex;align-items:center;gap:8px}.r2{margin-top:6px}
.eq{display:inline-flex;gap:2px;align-items:flex-end;height:16px}.eq i{width:3px;height:4px;background:var(--rose);border-radius:2px}
#pl.on .eq i{animation:eq 1s ease-in-out infinite}.eq i:nth-child(2){animation-delay:.25s!important}.eq i:nth-child(3){animation-delay:.5s!important}
.ic{border:0;border-radius:12px;min-width:42px;height:38px;padding:0 10px;font:1.05rem system-ui;background:rgba(255,255,255,.13);color:#fff;cursor:pointer;touch-action:manipulation}
.ic.off{opacity:.4}.ic:disabled{opacity:.3}
#vl{flex:1;min-width:0;accent-color:var(--rose);height:30px;margin:0}
#nt{display:block;font-size:.78rem;color:#ffc2d9;margin-top:4px}
/* buttons */
.btn{border:0;border-radius:999px;padding:14px 26px;min-height:50px;font:700 1.05rem/1.2 system-ui,sans-serif;color:#fff;background:linear-gradient(135deg,#ff5c8a,#c13a8a);box-shadow:0 8px 22px rgba(255,92,138,.35);cursor:pointer;touch-action:manipulation;transition:transform .2s}
.btn:active{transform:scale(.95)}.btn.ghost{background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.3);box-shadow:none}.btn:disabled{opacity:.6}
.btns{display:flex;flex-wrap:wrap;gap:14px;justify-content:center;margin:22px 0 10px}
.yes{position:relative;transform:scale(var(--k,1));background:linear-gradient(135deg,#ff7a59,#ff3d7f)}.yes:active{transform:scale(calc(var(--k,1)*.95))}
.yes::after{content:"";position:absolute;inset:-5px;border-radius:999px;border:2px solid rgba(255,210,130,.75);animation:ringo 1.8s ease-out infinite}
.lnk{background:none;border:0;color:#ffc2d9;font:inherit;text-decoration:underline;padding:10px;cursor:pointer}
/* envelope */
.env{position:relative;width:min(70vw,250px);aspect-ratio:3/2;margin:14px auto 26px;perspective:700px;animation:float 4s ease-in-out infinite}
.env>*{position:absolute}
.eb{inset:0;background:#d98cbc;border-radius:8px}
.ep{left:8%;right:8%;top:6%;bottom:6%;background:#fffaf0;border-radius:6px;display:grid;place-items:center;font-size:2rem;transition:transform 1.1s .55s ease;z-index:2}
.ef{inset:0;background:#f4bfdc;clip-path:polygon(0 0,50% 56%,100% 0,100% 100%,0 100%);border-radius:8px;z-index:3}
.el{inset:0;background:#ffd3e8;clip-path:polygon(0 0,100% 0,50% 60%);transform-origin:top;z-index:4;transition:transform .8s}
.es{left:50%;top:44%;width:38px;height:38px;margin:-19px;border-radius:50%;background:#e0245e;display:grid;place-items:center;z-index:5;transition:opacity .4s;box-shadow:0 2px 8px rgba(0,0,0,.35)}
.env.open .el{transform:rotateX(180deg);z-index:1}.env.open .es{opacity:0}.env.open .ep{transform:translateY(-62%)}
/* letter */
.letter{background:linear-gradient(160deg,#fffaf2,#ffeef4);color:#5a2140;border-radius:18px;padding:22px 20px;text-align:left;box-shadow:0 20px 50px rgba(0,0,0,.45);margin-bottom:22px}
.letter h2{background:none;-webkit-text-fill-color:#b0245c;color:#b0245c}
.letter p{animation:fadeUp 1s calc(var(--i)*1.1s) both}.sg{font-family:Georgia,serif;font-style:italic;text-align:right}
.beat{font-size:56px;animation:beat 1.7s infinite}
.msg{min-height:6.5em;color:#ffe1ec;font-size:1.05rem}.msg.in{animation:fadeUp .8s both}
/* story */
.slide{display:none}.slide.on{display:block;animation:fadeUp .9s both}
.art{height:150px;display:flex;align-items:center;justify-content:center;font-size:62px;gap:6px}
.art span{display:inline-block;animation:float 3.4s ease-in-out infinite}.art span:nth-child(2){animation-delay:.6s}.art span:nth-child(3){animation-delay:1.2s}
.dots{display:flex;gap:8px;justify-content:center;margin:16px 0}.dots i{width:8px;height:8px;border-radius:50%;background:rgba(255,255,255,.25);transition:.4s}.dots i.on{background:var(--rose);transform:scale(1.3)}
.inf{width:min(78vw,300px);filter:drop-shadow(0 0 8px #ff7aa8)}.inf path{fill:none;stroke:url(#ig);stroke-width:7;stroke-linecap:round;stroke-dasharray:1;stroke-dashoffset:1;animation:draw 3.2s .3s ease forwards}
/* ring */
.ring{position:relative;width:150px;margin:0 auto 4px}.ring svg{width:100%;position:relative;animation:float 3s ease-in-out infinite}
.halo{position:absolute;inset:-35%;background:radial-gradient(circle,rgba(255,225,140,.6),transparent 62%);animation:pulse 2.2s ease-in-out infinite}
/* surprises */
.pt{position:fixed;z-index:25;pointer-events:none;font-size:var(--s);left:var(--x);will-change:transform,opacity}
.rise{bottom:-40px;animation:rise 3.2s var(--d) ease-out both}
.fall{top:-40px;animation:fall 3.6s var(--d) linear both}
.shoot{top:-5vh;left:calc(40vw + var(--x)*.6);animation:shoot 1.8s var(--d) ease-in both}
.burst{top:55%;left:50%;animation:burst 1.8s var(--d) ease-out both}
#bh{position:fixed;z-index:26;left:50%;top:44%;font-size:90px;pointer-events:none;opacity:0}
#bh.go{animation:bh 1.3s ease-out}
#gl{position:fixed;inset:0;z-index:4;pointer-events:none;opacity:0;transition:opacity .6s}
@keyframes float{50%{transform:translateY(-9px)}}
@keyframes fadeUp{from{opacity:0;transform:translateY(14px)}}
@keyframes pulse{50%{transform:scale(1.15);opacity:.7}}
@keyframes beat{0%,40%,100%{transform:scale(1)}15%{transform:scale(1.25)}30%{transform:scale(1.08)}}
@keyframes ringo{from{transform:scale(1);opacity:.8}to{transform:scale(1.2,1.55);opacity:0}}
@keyframes eq{50%{height:15px}}
@keyframes draw{to{stroke-dashoffset:0}}
@keyframes rise{0%{transform:translateY(0) scale(.6);opacity:0}15%{opacity:1}100%{transform:translateY(-105vh) rotate(20deg) scale(1.1);opacity:0}}
@keyframes fall{0%{transform:translate(0,0) rotate(0);opacity:0}10%{opacity:1}100%{transform:translate(40px,108vh) rotate(300deg);opacity:.9}}
@keyframes shoot{0%{transform:translate(0,0);opacity:0}10%{opacity:1}100%{transform:translate(-75vw,62vh);opacity:0}}
@keyframes burst{0%{transform:rotate(var(--a)) translateY(0) scale(.3);opacity:1}100%{transform:rotate(var(--a)) translateY(-38vmin) scale(1.2);opacity:0}}
@keyframes bh{0%{opacity:0;transform:translate(-50%,-50%) scale(.3)}25%{opacity:1;transform:translate(-50%,-50%) scale(1.2)}100%{opacity:0;transform:translate(-50%,-85%) scale(1.8)}}
@media(prefers-reduced-motion:reduce){*{animation-duration:.01s!important;animation-iteration-count:1!important}}
</style>
</head>
<body>
<div class="moon"></div><canvas id="bg"></canvas><div id="gl"></div><div id="bh">💖</div>

<div id="pl">
 <div class="r1"><span class="eq"><i></i><i></i><i></i></span><b>Биздин сүйүүбүз ❤️</b></div>
 <div class="r2">
  <button class="ic" id="pp" aria-label="Музыканы ойнотуу же токтотуу">▶</button>
  <button class="ic" id="mu" aria-label="Үндү өчүрүү же жандыруу">🔊</button>
  <input id="vl" type="range" min="0" max="100" value="70" aria-label="Үндүн деңгээли">
  <button class="ic" id="sf" aria-label="Үн эффекттерин өчүрүү же жандыруу" aria-pressed="true">✨ Эффект</button>
 </div>
 <small id="nt" hidden>Бул түзмөктө үн иштебейт 😔 Бирок сүйүү окуясы уланат 💞</small>
</div>

<section class="sc on" id="s0"><div class="in">
 <p class="sub">Нуржамал үчүн атайын сюрприз</p>
 <div class="env" id="env"><div class="eb"></div><div class="ep">💌</div><div class="ef"></div><div class="el"></div><div class="es">❤️</div></div>
 <button class="btn" id="open">Конвертти ачуу 💌</button>
 <p class="hint">🎧 Музыкасы менен — үнүңдү бир аз чыгарып кой</p>
</div></section>

<section class="sc" id="s1"><div class="in">
 <div class="letter">
  <h2>Сүйүктүү Нуржамал,</h2>
  <p style="--i:1">Сени көргөн күндөн баштап жүрөгүмдө жаз башталды. Күлкүң — менин эң сулуу таңым, көзүңдүн нуру түнкү жылдыздардан да жарык.</p>
  <p style="--i:2">Сен менен өткөн ар бир мүнөт — жашоомдун эң кымбат белеги. Сен жанымда болсоң, дүйнө жылуу, жолум жарык.</p>
  <p style="--i:3">Бүгүн жүрөгүмдөгү эң чоң сөздү айткым келет…</p>
  <p class="sg" style="--i:4">Сени чексиз сүйгөн,<br>сенин сүйүктүүң ❤️</p>
 </div>
 <button class="btn" id="to2">Улантуу 💞</button>
</div></section>

<section class="sc" id="s2"><div class="in">
 <div class="beat">💗</div>
 <h1>Нуржамал, мага турмушка чыгасыңбы?</h1>
 <div class="btns"><button class="btn yes" id="yes">Ооба, сүйүктүүм! 💍</button><button class="btn ghost" id="no">Жок...</button></div>
 <p class="msg in" id="msg" aria-live="polite">Жүрөгүм сенин жообуңду күтүп жатат… 💓</p>
 <button class="lnk" id="peek" hidden>Келечегибизди бир көрүп көрчү 🌠</button>
</div></section>

<section class="sc" id="s3"><div class="in">
 <div class="slide"><div class="art"><span>☁️</span><span>🏡</span><span>🌷</span></div><h2>Кыялдагы үйүбүз</h2><p>Терезесинде жылуу жарык, короосунда гүлдөр. Ар кечте чай үстүндө сүйүү жөнүндө кеп кылабыз.</p></div>
 <div class="slide"><div class="art"><span>🏔️</span><span>✈️</span><span>🌊</span></div><h2>Бирге саякат</h2><p>Тоолорду, деңиздерди, алыскы шаарларды сен менен бирге көргүм келет. Ар бир жол — биздин жаңы окуя.</p></div>
 <div class="slide"><div class="art"><span>💞</span><span>🤝</span><span>💪</span></div><h2>Бири-бирибизге таяныч</h2><p>Кыйын күндө колуңдан кармайм, кубанычта сени кучактайм. Бардыгына бирге чыдайбыз.</p></div>
 <div class="slide"><div class="art"><span>👨‍👩‍👧‍👦</span><span>🏡</span></div><h2>Үй-бүлөбүздүн бактысы</h2><p>Балдардын күлкүсү үйүбүздү толтурат, дасторконубуз ар дайым береке-бата менен толук болот.</p></div>
 <div class="slide"><div class="art"><svg class="inf" viewBox="0 0 200 100"><defs><linearGradient id="ig"><stop offset="0" stop-color="#ffd98a"/><stop offset=".5" stop-color="#ff5c8a"/><stop offset="1" stop-color="#c79bff"/></linearGradient></defs><path pathLength="1" d="M100 50C130 10 185 10 185 50C185 90 130 90 100 50C70 10 15 10 15 50C15 90 70 90 100 50Z"/></svg></div><h2>Чексиз сүйүү</h2><p>Биздин сүйүүбүз — башы да, аягы да жок чексиздик. Сени дайыма сүйөм, Нуржамал!</p></div>
 <div class="dots"><i></i><i></i><i></i><i></i><i></i></div>
 <button class="btn" id="nx">Кийинки ▶</button>
</div></section>

<section class="sc" id="s4"><div class="in">
 <div class="ring"><div class="halo"></div>
  <svg viewBox="0 0 120 130" aria-label="Нике шакеги"><defs><linearGradient id="gd" x1="0" y1="0" x2="1" y2="1"><stop offset="0" stop-color="#fff2b0"/><stop offset=".5" stop-color="#f5b942"/><stop offset="1" stop-color="#b9791a"/></linearGradient><linearGradient id="gm" x1="0" y1="0" x2="1" y2="1"><stop offset="0" stop-color="#fff"/><stop offset="1" stop-color="#8fd3ff"/></linearGradient></defs>
  <ellipse cx="60" cy="94" rx="30" ry="30" fill="none" stroke="url(#gd)" stroke-width="9"/>
  <polygon points="46,28 74,28 85,42 60,68 35,42" fill="url(#gm)"/>
  <path d="M35 42h50M46 28l14 40 14-40M60 28v14" stroke="#7fb8e6" stroke-width="1.2" fill="none"/></svg>
 </div>
 <div class="em">🎉</div>
 <h1>Ооба!</h1>
 <p>Нуржамал, сен менин жүрөгүмдүн ханышасысың! Бүгүндөн баштап биз бирге — бактыда да, кыйынчылыкта да, түбөлүккө!</p>
 <div class="btns"><button class="btn" id="fut">Биздин келечегибиз 🌅</button><button class="btn ghost" id="again">Кайра майрамдоо 🎆</button></div>
</div></section>

<canvas id="fx"></canvas>
<script>
'use strict';
const $=s=>document.querySelector(s),$$=s=>[...document.querySelectorAll(s)];
function hp(x,s){x.beginPath();x.moveTo(0,s*.3);x.bezierCurveTo(0,-s*.1,-s*.6,-s*.1,-s*.6,s*.3);x.bezierCurveTo(-s*.6,s*.7,0,s*.9,0,s*1.1);x.bezierCurveTo(0,s*.9,s*.6,s*.7,s*.6,s*.3);x.bezierCurveTo(s*.6,-s*.1,0,-s*.1,0,s*.3);x.fill()}

/* ===== AUDIO ===== */
const A=(()=>{
const st={m:false,s:true,mute:false,vol:.7};
let ctx,master,mus,sfx,noise,tm,idle,nt=0,bar=0,mood='soft',ok=true,run=false;
const B=60/66,f=m=>440*2**((m-69)/12),R=a=>a[Math.random()*a.length|0];
const CH=[[57,60,64,69],[53,57,60,65],[55,60,64,67],[55,59,62,67]],BS=[45,41,48,43],AR=[0,1,2,3,2,1,2,3],PE=[84,86,88,91,93];
const MEL=[[[0,76,2],[2,74,1],[3,72,1]],[[0,72,1.5],[1.5,69,.5],[2,72,2]],[[0,76,2],[2,79,1],[3,76,1]],[[0,74,3],[3,71,1]],[[0,69,1],[1,72,1],[2,76,2]],[[0,77,2],[2,76,1],[3,72,1]],[[0,74,1],[1,76,1],[2,72,2]],[[0,71,2],[2,74,2]]];
function init(){
 if(ctx)return ok;
 try{
  const C=window.AudioContext||window.webkitAudioContext;if(!C)throw 0;
  ctx=new C({latencyHint:'playback'});
  master=ctx.createGain();master.gain.value=0;
  const cp=ctx.createDynamicsCompressor();cp.threshold.value=-18;cp.ratio.value=4;
  master.connect(cp);cp.connect(ctx.destination);
  mus=ctx.createGain();sfx=ctx.createGain();mus.connect(master);sfx.connect(master);
  const L=Math.floor(ctx.sampleRate*2.2),ib=ctx.createBuffer(2,L,ctx.sampleRate);
  for(let k=0;k<2;k++){const d=ib.getChannelData(k);for(let i=0;i<L;i++)d[i]=(Math.random()*2-1)*Math.pow(1-i/L,2.6)}
  const cv=ctx.createConvolver(),rv=ctx.createGain();cv.buffer=ib;rv.gain.value=.55;cv.connect(rv);rv.connect(master);
  [mus,sfx].forEach(b=>{const s=ctx.createGain();s.gain.value=.4;b.connect(s);s.connect(cv)});
  noise=ctx.createBuffer(1,ctx.sampleRate,ctx.sampleRate);const nd=noise.getChannelData(0);for(let i=0;i<nd.length;i++)nd[i]=Math.random()*2-1;
  document.addEventListener('visibilitychange',()=>{
   if(document.hidden){clearTimeout(tm);ctx.suspend()}
   else if(run){wake();nt=ctx.currentTime+.1;clearTimeout(tm);tick()}
  });
 }catch(e){ok=false;ctx=null}
 return ok;
}
function apply(tc){if(ctx)master.gain.setTargetAtTime(st.mute?0:Math.pow(st.vol,1.6)*.9,ctx.currentTime,tc||.08)}
function wake(){clearTimeout(idle);if(ctx&&ctx.state!=='running'){try{const p=ctx.resume();if(p&&p.catch)p.catch(()=>{})}catch(e){}}}
function rest(){clearTimeout(idle);idle=setTimeout(()=>{if(!run&&ctx&&ctx.state==='running')ctx.suspend()},6000)}
/* piano-like note */
function note(fr,t,d,v,dest){
 const o=ctx.createOscillator(),o2=ctx.createOscillator(),g=ctx.createGain(),g2=ctx.createGain(),lp=ctx.createBiquadFilter();
 o.type='triangle';o2.type='sine';o.frequency.value=fr;o2.frequency.value=fr*2;g2.gain.value=.22;
 lp.type='lowpass';lp.frequency.setValueAtTime(Math.min(fr*7,6000),t);lp.frequency.exponentialRampToValueAtTime(Math.max(fr*1.6,400),t+d);
 g.gain.setValueAtTime(0,t);g.gain.linearRampToValueAtTime(v,t+.012);g.gain.exponentialRampToValueAtTime(.0001,t+d);
 o.connect(lp);o2.connect(g2);g2.connect(lp);lp.connect(g);g.connect(dest||mus);
 o.start(t);o2.start(t);o.stop(t+d+.05);o2.stop(t+d+.05);
}
/* dreamy pad */
function pad(ms,t,d,v,dest){
 const lp=ctx.createBiquadFilter();lp.type='lowpass';lp.frequency.value=1100;lp.connect(dest||mus);
 ms.forEach(m=>[-5,5].forEach(dt=>{
  const o=ctx.createOscillator(),g=ctx.createGain();o.type='triangle';o.frequency.value=f(m-12);o.detune.value=dt;
  g.gain.setValueAtTime(0,t);g.gain.linearRampToValueAtTime(v/3,t+d*.45);g.gain.linearRampToValueAtTime(0,t+d);
  o.connect(g);g.connect(lp);o.start(t);o.stop(t+d+.1);
 }));
}
/* gentle bell */
function bell(fr,t,v,dest){
 [[1,1,2.4],[2.76,.3,1.2],[5.4,.1,.6]].forEach(([r,a,d])=>{
  if(fr*r>9000)return;
  const o=ctx.createOscillator(),g=ctx.createGain();o.type='sine';o.frequency.value=fr*r;
  g.gain.setValueAtTime(0,t);g.gain.linearRampToValueAtTime(v*a,t+.006);g.gain.exponentialRampToValueAtTime(.0001,t+d);
  o.connect(g);g.connect(dest||mus);o.start(t);o.stop(t+d+.05);
 });
}
function barAt(t,i){
 const ch=CH[i%4],fu=mood!=='soft',jo=mood==='joy';
 pad(ch.slice(0,3),t,B*4.3,fu?.07:.05,mus);
 note(f(BS[i%4]),t,B*3.6,.17,mus);
 for(let k=0;k<8;k++){const m=ch[AR[k]],tt=t+k*B/2+Math.random()*.012;note(f(m),tt,B*2,(k%4?.07:.11)*(.9+Math.random()*.2),mus);if(jo)note(f(m+12),tt+B/4,B,.04,mus)}
 MEL[i].forEach(([b,m,d])=>{note(f(m),t+b*B,B*d*1.5,.17,mus);if(fu)bell(f(m+12),t+b*B+.03,.045,mus)});
 for(let k=0,n=jo?4:fu?2:1;k<n;k++)bell(f(R(PE)),t+(.5+Math.random()*3.2)*B,.035,mus);
}
function tick(){if(!run)return;while(nt<ctx.currentTime+1.4){barAt(nt,bar);nt+=B*4;bar=(bar+1)%8}tm=setTimeout(tick,350)}
function begin(){if(run)return;run=true;nt=ctx.currentTime+.12;clearTimeout(tm);mus.gain.setTargetAtTime(1,ctx.currentTime,.4);tick()}
function end(){run=false;clearTimeout(tm);if(ctx)mus.gain.setTargetAtTime(0,ctx.currentTime,.25);rest()}
function start(){if(!init())return false;wake();st.m=true;apply(.7);begin();return true}
function setMusic(b){st.m=b;if(!ctx)return b?start():true;if(b){wake();begin()}else end();return true}
/* sound effects */
function sx(){if(!ctx||!st.s||st.mute||document.hidden)return 0;wake();rest();return ctx.currentTime+.03}
function thump(t,v){const o=ctx.createOscillator(),g=ctx.createGain();o.type='triangle';o.frequency.setValueAtTime(90,t);o.frequency.exponentialRampToValueAtTime(48,t+.14);g.gain.setValueAtTime(0,t);g.gain.linearRampToValueAtTime(v,t+.015);g.gain.exponentialRampToValueAtTime(.0001,t+.22);o.connect(g);g.connect(sfx);o.start(t);o.stop(t+.25)}
function beat(){const t=sx();if(!t)return;thump(t,.26);thump(t+.25,.18)}
function chime(){const t=sx();if(!t)return;[84,88,91,96].forEach((m,i)=>bell(f(m),t+i*.1,.07,sfx))}
function nope(){const t=sx();if(!t)return;[79,83,86,91,95,98].forEach((m,i)=>bell(f(m),t+i*.12,.06,sfx));note(f(67),t,1.4,.08,sfx)}
function sparkle(n){const t=sx();if(!t)return;for(let i=0;i<(n||4);i++)bell(f(R(PE)+(Math.random()<.4?12:0)),t+Math.random()*.6,.035,sfx)}
function click(){const t=sx();if(t)bell(f(88),t,.04,sfx)}
function whoosh(){
 const t=sx();if(!t)return;
 const s=ctx.createBufferSource(),bp=ctx.createBiquadFilter(),g=ctx.createGain();
 s.buffer=noise;bp.type='bandpass';bp.Q.value=1.2;bp.frequency.setValueAtTime(250,t);bp.frequency.exponentialRampToValueAtTime(2200,t+.8);
 g.gain.setValueAtTime(0,t);g.gain.linearRampToValueAtTime(.05,t+.3);g.gain.linearRampToValueAtTime(0,t+.85);
 s.connect(bp);bp.connect(g);g.connect(sfx);s.start(t);s.stop(t+.9);
}
function pop(tt){
 const t=tt||sx();if(!t)return;
 const s=ctx.createBufferSource(),lp=ctx.createBiquadFilter(),g=ctx.createGain();
 s.buffer=noise;lp.type='lowpass';lp.frequency.setValueAtTime(2200,t);lp.frequency.exponentialRampToValueAtTime(180,t+.4);
 g.gain.setValueAtTime(0,t);g.gain.linearRampToValueAtTime(.09,t+.01);g.gain.exponentialRampToValueAtTime(.0001,t+.42);
 s.connect(lp);lp.connect(g);g.connect(sfx);s.start(t,Math.random()*.5);s.stop(t+.45);bell(f(R(PE)+12),t+.05,.03,sfx);
}
function yes(){
 const t=sx();if(!t)return;
 [72,76,79,84,88,91,96].forEach((m,i)=>{note(f(m),t+i*.11,1.8,.15,sfx);bell(f(m+12),t+i*.11,.05,sfx)});
 pad([60,64,67,71,74],t+.8,5,.12,sfx);
 for(let i=0;i<12;i++)bell(f(R(PE)+(i%3?0:12)),t+1+i*.22,.04,sfx);
 [0,.35,.7].forEach(d=>pop(t+1.2+d));
}
return{st,ok:()=>ok,start,setMusic,setSfx:b=>{st.s=b},setMute:b=>{st.mute=b;apply()},setVol:v=>{st.vol=v;apply()},setMood:m=>{mood=m},beat,chime,nope,sparkle,click,whoosh,pop,yes};
})();
/* ===== /AUDIO ===== */

/* ===== background: stars, hearts, shooting stars ===== */
const BG=(()=>{
const c=$('#bg'),x=c.getContext('2d'),rm=matchMedia('(prefers-reduced-motion:reduce)').matches;
let W,H,S=[],Hs=[],sh=null,last=0,raf;
const nh=y=>({x:Math.random()*W,y:y??H+Math.random()*H*.6,s:7+Math.random()*10,v:.2+Math.random()*.35,p:Math.random()*6});
function rs(){W=c.width=innerWidth;H=c.height=innerHeight;
 S=Array.from({length:W<600?55:100},()=>({x:Math.random()*W,y:Math.random()*H*.9,r:Math.random()*1.3+.3,p:Math.random()*6,v:.01+Math.random()*.02}));
 Hs=Array.from({length:7},()=>nh(Math.random()*H))}
function draw(t){
 raf=requestAnimationFrame(draw);if(t-last<33)return;last=t;
 x.clearRect(0,0,W,H);x.fillStyle='#fff';
 for(const s of S){x.globalAlpha=.35+.65*Math.abs(Math.sin(t*s.v*.1+s.p));x.beginPath();x.arc(s.x,s.y,s.r,0,6.3);x.fill()}
 x.fillStyle='#ff7aa8';x.globalAlpha=.28;
 for(const h of Hs){h.y-=h.v;h.x+=Math.sin(t/900+h.p)*.3;if(h.y<-30)Object.assign(h,nh());x.save();x.translate(h.x,h.y);hp(x,h.s);x.restore()}
 if(!sh&&Math.random()<.006)sh={x:W*.2+Math.random()*W*.8,y:Math.random()*H*.3,l:0};
 if(sh){sh.x-=9;sh.y+=4.5;sh.l++;x.globalAlpha=Math.max(0,1-sh.l/28);x.strokeStyle='#fff';x.lineWidth=2;x.beginPath();x.moveTo(sh.x,sh.y);x.lineTo(sh.x+50,sh.y-25);x.stroke();if(sh.l>28)sh=null}
}
function start(){rs();if(rm){draw(999);cancelAnimationFrame(raf)}else raf=requestAnimationFrame(draw)}
document.addEventListener('visibilitychange',()=>{if(rm)return;if(document.hidden)cancelAnimationFrame(raf);else raf=requestAnimationFrame(draw)});
return{rs,start};
})();

/* ===== celebration: fireworks, hearts, roses ===== */
const FX=(()=>{
const c=$('#fx'),x=c.getContext('2d');
let P=[],run=0,until=0,nb=0,last=0;
const col=['#ff5c8a','#ffd98a','#8fd3ff','#c79bff','#ff9e6b','#7dffb2'];
function rs(){const d=Math.min(devicePixelRatio||1,1.5);c.width=innerWidth*d;c.height=innerHeight*d;x.setTransform(d,0,0,d,0,0)}
function burst(){
 const X=innerWidth*(.15+Math.random()*.7),Y=innerHeight*(.14+Math.random()*.36),k=col[Math.random()*col.length|0];
 for(let i=0;i<32;i++){const a=i/32*6.283,v=2+Math.random()*2.6;P.push({t:0,x:X,y:Y,vx:Math.cos(a)*v,vy:Math.sin(a)*v,g:.045,l:60+Math.random()*30,L:60,c:k,s:2.2})}
 A.pop();
}
function item(r){
 const W=innerWidth;
 P.push(r?{t:2,x:Math.random()*W,y:-20,vx:(Math.random()-.5)*1.2,vy:1+Math.random(),g:0,l:400,s:16+Math.random()*14,r:Math.random()*6,vr:(Math.random()-.5)*.1}
 :{t:1,x:Math.random()*W,y:innerHeight+20,vx:(Math.random()-.5)*.8,vy:-1.4-Math.random()*1.6,g:0,l:400,s:10+Math.random()*16,c:Math.random()<.5?'#ff5c8a':'#ff9ec1'});
}
function loop(t){
 if(!run)return;requestAnimationFrame(loop);if(t-last<33)return;
 const dt=Math.min((t-last)/16.7,3);last=t;x.clearRect(0,0,innerWidth,innerHeight);
 if(t<until){if(t>nb){burst();nb=t+520}if(Math.random()<.14)item(0);if(Math.random()<.08)item(1)}
 P=P.filter(p=>{
  p.x+=p.vx*dt;p.y+=p.vy*dt;p.vy+=p.g*dt;p.l-=dt;
  x.save();x.globalAlpha=Math.max(0,Math.min(1,p.l/(p.L||40)));
  if(p.t===0){x.fillStyle=p.c;x.beginPath();x.arc(p.x,p.y,p.s,0,6.3);x.fill()}
  else if(p.t===1){x.fillStyle=p.c;x.translate(p.x,p.y);hp(x,p.s)}
  else{x.translate(p.x,p.y);x.rotate(p.r+=p.vr);x.font=p.s+'px serif';x.textAlign='center';x.fillText('🌹',0,0)}
  x.restore();return p.l>0&&p.y>-60&&p.y<innerHeight+40;
 });
 if(!P.length&&t>=until){run=0;x.clearRect(0,0,innerWidth,innerHeight)}
}
function go(ms){until=performance.now()+ms;nb=0;if(!run){run=1;last=0;requestAnimationFrame(loop)}}
return{rs,go};
})();

/* ===== story & buttons ===== */
let said=0,no=0,hb,st,opened=0;
const pl=$('#pl'),pp=$('#pp'),mu=$('#mu'),sf=$('#sf'),vl=$('#vl'),msg=$('#msg');
const MSG=[
'Жүрөгүм бир аз титиреп кетти, бирок сени дагы деле чексиз сүйөм. Кайра ойлонуп көрчү, сүйүктүүм… 💗',
'Сенин жылмайганың ушунчалык сулуу, ошондуктан мен күтүүгө даярмын. Жүрөгүң эмне дейт? 🌹',
'Ар бир «жок» менин сүйүүмдү дагы күчөтө берет. Сен менен өтчү өмүр — менин эң чоң кыялым. ✨',
'Асмандагы жылдыздар да биз үчүн күбө. Бир гана «ооба» дегин — мен сени бакытка бөлөйм. 🌠',
'Сен менен чай ичип, жамгырды угуп, карыганча кол кармашып жүргүм келет. Ойлонуп көрчү… ☕',
'Жүрөгүңдө мага бир кичинекей орун бар экенин сезип турам. Мен сабырдуу күтөм. 💫',
'Чыныгы сүйүү шашпайт, бирок сенин ар бир күнүңдү жарык кылууга мен ар дайым даярмын. 🦋',
'Сен менин эң сонун жолугушуумсуң. Бир гана «ооба» десең, бүт дүйнө бизге жылмаят! 🎈',
'Мен сенин үнүңдү, күлкүңдү жана ар бир көз карашыңды чексиз жакшы көрөм. Сүйүүмдү кабыл алгын… 🕯️',
'Түнкү жылдыздардай сабырдуу болом. Жүрөгүң даяр болгондо, мен дайыма жанындамын. 💞'];
const SUR=[
{e:['💖','💗','💕'],k:'rise',c:'#ff5c8a'},{e:['🌠','⭐'],k:'shoot',c:'#8fd3ff'},{e:['🌹','🌸'],k:'fall',c:'#ff9ec1'},{e:['🦋'],k:'rise',c:'#c79bff'},
{e:['✨','💫'],k:'burst',c:'#ffd98a'},{e:['🎈'],k:'rise',c:'#ff9e6b'},{e:['🕯️','🏮'],k:'rise',c:'#ffb347'},{e:['💞','💝','❤️'],k:'burst',c:'#ff5c8a'}];

function ui(){const s=A.st;pp.textContent=s.m?'⏸':'▶';mu.textContent=s.mute?'🔇':'🔊';sf.classList.toggle('off',!s.s);sf.setAttribute('aria-pressed',String(s.s));pl.classList.toggle('on',s.m&&!s.mute)}
function noAudio(){$('#nt').hidden=false;[pp,mu,sf,vl].forEach(e=>e.disabled=true)}
pp.onclick=()=>{if(!A.setMusic(!A.st.m))noAudio();ui()};
mu.onclick=()=>{A.setMute(!A.st.mute);ui()};
sf.onclick=()=>{A.setSfx(!A.st.s);ui();if(A.st.s)A.chime()};
vl.oninput=()=>{A.setVol(vl.value/100);if(A.st.mute){A.setMute(false);ui()}};

function go(id){
 $$('.sc').forEach(e=>e.classList.toggle('on',e.id===id));
 clearInterval(hb);clearTimeout(st);A.whoosh();A.sparkle(3);
 A.setMood(id==='s3'?'future':id==='s4'?'joy':'soft');
 if(id==='s2'){hb=setInterval(A.beat,1700);setTimeout(A.beat,800)}
 if(id==='s3')slide(0);
}
function slide(n){
 clearTimeout(st);
 $$('.slide').forEach((e,i)=>e.classList.toggle('on',i===n));
 $$('.dots i').forEach((e,i)=>e.classList.toggle('on',i<=n));
 const b=$('#nx');b.dataset.n=n;b.textContent=n<4?'Кийинки ▶':said?'Кайра майрамдоо 🎆':'Суроого кайтуу 💍';
 if(n)A.chime();if(n<4)st=setTimeout(()=>slide(n+1),7000);
}
function say(t){msg.classList.remove('in');void msg.offsetWidth;msg.textContent=t;msg.classList.add('in')}
function surprise(i){
 const s=SUR[i%SUR.length],n=s.k==='burst'?16:12;
 for(let k=0;k<n;k++){
  const p=document.createElement('span');p.className='pt '+s.k;p.textContent=s.e[k%s.e.length];
  p.style.cssText='--x:'+(Math.random()*95|0)+'vw;--d:'+(Math.random()*.9).toFixed(2)+'s;--s:'+(22+Math.random()*26|0)+'px;--a:'+(Math.random()*360|0)+'deg';
  document.body.appendChild(p);p.addEventListener('animationend',()=>p.remove());
 }
 const g=$('#gl');g.style.background='radial-gradient(circle at 50% 60%,'+s.c+'55,transparent 65%)';g.style.opacity=1;setTimeout(()=>g.style.opacity=0,700);
 const h=$('#bh');h.classList.remove('go');void h.offsetWidth;h.classList.add('go');
}
$('#open').onclick=()=>{
 if(opened)return;opened=1;
 if(!A.start())noAudio();
 ui();A.chime();$('#env').classList.add('open');$('#open').disabled=true;
 setTimeout(()=>go('s1'),2400);
};
$('#to2').onclick=()=>{A.click();go('s2')};
$('#yes').onclick=()=>{said=1;A.yes();go('s4');FX.go(10000)};
$('#no').onclick=()=>{
 const i=no++;A.nope();say(MSG[i%MSG.length]);surprise(i);
 $('#yes').style.setProperty('--k',Math.min(1.22,1+no*.03));
 if(no>=2)$('#peek').hidden=false;
};
$('#peek').onclick=()=>go('s3');
$('#nx').onclick=()=>{const n=+$('#nx').dataset.n;if(n<4)slide(n+1);else if(said){go('s4');FX.go(7000);A.yes()}else go('s2')};
$('#fut').onclick=()=>go('s3');
$('#again').onclick=()=>{A.yes();FX.go(8000)};

let lw=innerWidth;addEventListener('resize',()=>{if(innerWidth!==lw){lw=innerWidth;BG.rs();FX.rs()}});
BG.start();FX.rs();ui();
</script>
</body>
</html>
