# rgml
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>你的人格魅力是哪种？</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400;700;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
:root{--ink:#111;--paper:#F5F0E8;--white:#FFFDF8;--muted:#999}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Noto Sans SC',sans-serif;background:var(--paper);color:var(--ink);min-height:100vh;overflow-x:hidden}
.screen{display:none;min-height:100vh;flex-direction:column;align-items:center}
.screen.active{display:flex}

/* ══ INTRO ══ */
#intro{
  justify-content:center;
  padding:80px 32px 100px;
  text-align:center;
  position:relative;
  overflow:hidden;
}
.eyebrow{
  font-family:'Space Mono',monospace;
  font-size:10px;
  letter-spacing:.22em;
  border:2px solid var(--ink);
  padding:6px 18px;
  margin-bottom:52px;
  display:inline-block;
  transform:rotate(-1.2deg);
  color:var(--muted);
}
.intro-title{
  font-size:clamp(42px,10vw,82px);
  font-weight:900;
  line-height:.95;
  letter-spacing:-.04em;
  margin-bottom:24px;
}
.intro-title .stroke{
  -webkit-text-stroke:3px var(--ink);
  color:transparent;
  display:block;
}
.intro-title .solid{display:block}
.intro-sub{
  font-size:14px;
  color:var(--muted);
  margin-bottom:72px;
  line-height:2;
  letter-spacing:.04em;
}
.start-btn{
  background:var(--ink);
  color:var(--paper);
  border:none;
  padding:20px 60px;
  font-size:17px;
  font-weight:900;
  font-family:'Noto Sans SC',sans-serif;
  cursor:pointer;
  letter-spacing:.06em;
  transform:rotate(-.4deg);
  transition:all .15s;
  position:relative;
}
.start-btn::after{
  content:'';
  position:absolute;
  inset:0;
  border:2px solid var(--ink);
  transform:translate(4px,4px);
  pointer-events:none;
  transition:transform .15s;
}
.start-btn:hover{background:#FF3300;transform:rotate(0)}
.start-btn:hover::after{transform:translate(6px,6px)}
.start-btn:active{transform:scale(.97)}

/* hand-drawn deco */
.deco{position:absolute;pointer-events:none;overflow:visible}

/* ══ QUIZ ══ */
#quiz{
  padding:48px 24px 100px;
  position:relative;
  justify-content:flex-start;
}
.topbar{
  width:100%;
  max-width:520px;
  display:flex;
  align-items:center;
  gap:20px;
  margin-bottom:60px;
}
.qnum{
  font-family:'Space Mono',monospace;
  font-size:11px;
  letter-spacing:.1em;
  color:var(--muted);
  min-width:44px;
}
.prog-track{
  flex:1;
  height:3px;
  background:#ddd;
  overflow:hidden;
  position:relative;
}
/* hand-drawn progress bar — slightly wobbly via SVG filter illusion */
.prog-fill{
  height:100%;
  background:var(--ink);
  transition:width .5s cubic-bezier(.34,1.56,.64,1);
}
.qpct{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  min-width:28px;
  text-align:right;
}

.qcard{
  max-width:520px;
  width:100%;
  padding:0;
  animation:cardIn .4s cubic-bezier(.34,1.56,.64,1);
}
@keyframes cardIn{
  from{opacity:0;transform:translateY(28px)}
  to{opacity:1;transform:none}
}

.qemoji{
  font-size:52px;
  display:block;
  margin-bottom:28px;
  animation:pop .5s cubic-bezier(.34,1.56,.64,1);
  line-height:1;
}
@keyframes pop{
  from{transform:scale(0) rotate(-15deg);opacity:0}
  to{transform:none;opacity:1}
}
.qtitle{
  font-size:22px;
  font-weight:900;
  line-height:1.45;
  letter-spacing:-.02em;
  margin-bottom:12px;
}
.qhint{
  font-size:13px;
  color:var(--muted);
  margin-bottom:52px;
  line-height:1.7;
  font-style:italic;
}

/* LEFT-RIGHT OPTIONS with colored gradient slider */
.options-row{
  display:flex;
  align-items:flex-start;
  gap:0;
  margin-bottom:20px;
}
.opt{
  flex:1;
  font-size:13px;
  font-weight:700;
  line-height:1.5;
  padding:0 4px;
}
.opt.l{text-align:left;color:#0055AA;padding-right:16px}
.opt.r{text-align:right;color:#CC2200;padding-left:16px}

/* GRADIENT SLIDER */
.slider-wrap{margin-bottom:12px;position:relative}
.slider-track-bg{
  height:8px;
  border-radius:0;
  background:linear-gradient(to right,#0055AA,#ddd 40%,#ddd 60%,#CC2200);
  position:relative;
  margin-bottom:0;
  border:2px solid var(--ink);
}
input[type=range]{
  -webkit-appearance:none;
  width:100%;
  height:8px;
  background:transparent;
  outline:none;
  cursor:pointer;
  border:none;
  position:relative;
  margin-top:-8px;
  display:block;
}
input[type=range]::-webkit-slider-thumb{
  -webkit-appearance:none;
  width:32px;height:32px;
  border-radius:50%;
  background:var(--paper);
  border:3px solid var(--ink);
  cursor:grab;
  box-shadow:4px 4px 0 var(--ink);
  transition:transform .1s;
  margin-top:-12px;
}
input[type=range]::-webkit-slider-thumb:active{
  cursor:grabbing;
  transform:scale(1.12);
}
input[type=range]::-moz-range-thumb{
  width:32px;height:32px;
  border-radius:50%;
  background:var(--paper);
  border:3px solid var(--ink);
  cursor:grab;
  box-shadow:4px 4px 0 var(--ink);
}
/* live color fill on left side of thumb */
.slider-fill{
  position:absolute;
  top:0;left:0;
  height:100%;
  pointer-events:none;
  transition:width .05s;
  opacity:.5;
}

.smood{
  text-align:center;
  margin-top:16px;
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  letter-spacing:.08em;
  min-height:18px;
}

.nbtn{
  width:100%;
  margin-top:48px;
  background:var(--ink);
  color:var(--paper);
  border:none;
  padding:18px;
  font-size:16px;
  font-weight:900;
  font-family:'Noto Sans SC',sans-serif;
  cursor:pointer;
  letter-spacing:.06em;
  transition:all .15s;
  position:relative;
}
.nbtn::after{
  content:'';
  position:absolute;
  inset:0;
  border:2px solid var(--ink);
  transform:translate(4px,4px);
  pointer-events:none;
  transition:transform .15s;
}
.nbtn:hover{background:#FF3300}
.nbtn:hover::after{transform:translate(6px,6px)}
.nbtn:active{transform:scale(.98)}

/* ══ RESULT ══ */
#result{padding:48px 24px 120px}

.rlabel{
  font-family:'Space Mono',monospace;
  font-size:10px;
  letter-spacing:.22em;
  color:var(--muted);
  margin-bottom:28px;
  text-transform:uppercase;
}

/* HERO — full-bleed color block */
.hero{
  width:100%;
  max-width:520px;
  border:3px solid var(--ink);
  margin-bottom:16px;
  overflow:hidden;
  position:relative;
}
/* hand-drawn border offset */
.hero::after{
  content:'';
  position:absolute;
  inset:0;
  border:2px solid var(--ink);
  transform:translate(5px,5px);
  pointer-events:none;
  z-index:0;
}
.hero-top{
  padding:40px 32px 32px;
  position:relative;
  min-height:200px;
  z-index:1;
}
.hero-bot{
  padding:24px 32px 28px;
  border-top:3px solid var(--ink);
  background:var(--white);
  position:relative;
  z-index:1;
}
.hero-emoji{
  font-size:72px;
  display:block;
  margin-bottom:16px;
  animation:bigpop .7s cubic-bezier(.34,1.56,.64,1);
  line-height:1;
}
@keyframes bigpop{
  from{transform:scale(0) rotate(-18deg);opacity:0}
  to{transform:none;opacity:1}
}
.hero-name{
  font-size:clamp(32px,8vw,54px);
  font-weight:900;
  letter-spacing:-.04em;
  line-height:1;
  margin-bottom:10px;
}
.hero-tagline{
  font-size:13px;
  font-weight:700;
  letter-spacing:.05em;
  opacity:.65;
  line-height:1.6;
}
.hero-desc{
  font-size:14px;
  line-height:2;
  color:#444;
  white-space:pre-line;
}

/* SECTIONS */
.rsec{
  width:100%;
  max-width:520px;
  border:2.5px solid var(--ink);
  background:var(--white);
  margin-bottom:12px;
  padding:28px 28px;
  position:relative;
}
.rsec::after{
  content:'';
  position:absolute;
  inset:0;
  border:1.5px solid var(--ink);
  transform:translate(4px,4px);
  pointer-events:none;
}
.rsec-lbl{
  font-family:'Space Mono',monospace;
  font-size:9px;
  letter-spacing:.18em;
  color:var(--muted);
  margin-bottom:16px;
  text-transform:uppercase;
}
.rsec-body{
  font-size:13px;
  line-height:1.95;
  color:#444;
  white-space:pre-line;
}

.match-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.mcard{
  border:2px solid var(--ink);
  padding:16px;
  background:var(--paper);
  position:relative;
}
.mtag{
  font-size:9px;
  font-weight:900;
  letter-spacing:.1em;
  padding:3px 8px;
  border:1.5px solid var(--ink);
  display:inline-block;
  margin-bottom:10px;
  text-transform:uppercase;
}
.mname{font-size:15px;font-weight:900;margin-bottom:6px;letter-spacing:-.01em}
.mdesc{font-size:11px;color:#666;line-height:1.7}

/* RADAR — hand-drawn style canvas */
.radar-wrap{
  width:100%;
  max-width:520px;
  border:2.5px solid var(--ink);
  background:var(--white);
  margin-bottom:12px;
  padding:28px 24px 24px;
  position:relative;
}
.radar-wrap::after{
  content:'';
  position:absolute;
  inset:0;
  border:1.5px solid var(--ink);
  transform:translate(4px,4px);
  pointer-events:none;
}
.radar-lbl{
  font-family:'Space Mono',monospace;
  font-size:9px;
  letter-spacing:.18em;
  color:var(--muted);
  margin-bottom:20px;
  text-transform:uppercase;
}
canvas{display:block;margin:0 auto;max-width:340px;width:100%}

.dimlist{
  margin-top:24px;
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:8px;
}
.ditem{padding:10px 0;border-top:1.5px solid #e0d8cc}
.ditem-row{display:flex;justify-content:space-between;align-items:baseline;margin-bottom:6px}
.ditem-name{font-size:11px;font-weight:900;letter-spacing:.02em}
.ditem-pct{font-family:'Space Mono',monospace;font-size:10px;color:var(--muted)}
.dtrack{height:4px;background:#e8e0d0;overflow:hidden}
.dfill{height:100%;background:var(--ink);transition:width 1.3s cubic-bezier(.34,1.56,.64,1);width:0}

/* CELEB */
.celeb-row{display:flex;gap:10px}
.cchip{
  flex:1;
  border:2px solid var(--ink);
  padding:12px 14px;
  background:var(--paper);
  font-size:13px;
  font-weight:700;
  line-height:1.5;
}
.cchip small{display:block;font-size:10px;font-weight:400;color:var(--muted);margin-top:3px;letter-spacing:.02em}

/* QUOTE */
.qcard-result{
  width:100%;
  max-width:520px;
  border:3px solid var(--ink);
  padding:32px 28px;
  margin-bottom:14px;
  position:relative;
}
.qcard-result::after{
  content:'';
  position:absolute;
  inset:0;
  border:2px solid var(--ink);
  transform:translate(5px,5px);
  pointer-events:none;
}
.qmark{
  font-size:64px;
  font-weight:900;
  line-height:.5;
  opacity:.15;
  font-family:serif;
  display:block;
  margin-bottom:12px;
}
.qtext{
  font-size:clamp(16px,4.5vw,20px);
  font-weight:900;
  line-height:1.7;
  letter-spacing:.01em;
  white-space:pre-line;
}

/* SHARE */
.share-row{display:flex;gap:10px;width:100%;max-width:520px;margin-bottom:12px}
.sbtn{
  flex:1;
  padding:16px;
  border:2.5px solid var(--ink);
  background:var(--white);
  font-size:14px;
  font-weight:900;
  font-family:'Noto Sans SC',sans-serif;
  cursor:pointer;
  transition:all .15s;
  color:var(--ink);
  position:relative;
}
.sbtn::after{
  content:'';
  position:absolute;
  inset:0;
  border:1.5px solid var(--ink);
  transform:translate(3px,3px);
  pointer-events:none;
  transition:transform .15s;
}
.sbtn:hover{transform:translate(-1px,-1px)}
.sbtn:hover::after{transform:translate(5px,5px)}
.sbtn.pri{background:var(--ink);color:var(--paper)}
.sbtn.pri:hover{background:#FF3300;border-color:#FF3300}
.retry{
  background:none;border:none;
  font-size:12px;color:var(--muted);
  cursor:pointer;
  font-family:'Space Mono',monospace;
  letter-spacing:.08em;
  text-decoration:underline;
  text-underline-offset:4px;
  padding:8px;
}
.retry:hover{color:var(--ink)}

@media(max-width:480px){
  #intro{padding:60px 24px 80px}
  .match-grid{grid-template-columns:1fr}
  .dimlist{grid-template-columns:1fr}
  .hero-top{padding:28px 20px 24px}
  .hero-bot{padding:20px 20px 24px}
  .rsec{padding:22px 20px}
}
</style>
</head>
<body>

<!-- ══ INTRO ══ -->
<section class="screen" id="intro">

  <!-- hand-drawn SVG decorations — scattered, not centered -->
  <svg class="deco" style="top:32px;left:20px;width:100px;height:100px;opacity:.12" viewBox="0 0 100 100">
    <path d="M15,50 Q20,14 52,12 Q84,10 88,48 Q92,84 54,90 Q16,96 15,50Z"
      fill="none" stroke="#111" stroke-width="2.5" stroke-linecap="round"/>
    <path d="M34,50 Q36,32 52,30 Q68,28 70,50 Q72,70 54,73 Q34,76 34,50Z"
      fill="#AAFF00" stroke="#111" stroke-width="1.5" opacity=".6"/>
  </svg>

  <svg class="deco" style="top:24px;right:16px;width:70px;height:70px;opacity:.18" viewBox="0 0 70 70">
    <circle cx="35" cy="35" r="28" fill="none" stroke="#FF3300" stroke-width="2"
      stroke-dasharray="5 4" stroke-linecap="round"/>
    <circle cx="35" cy="35" r="14" fill="#FF0080" opacity=".25"/>
  </svg>

  <svg class="deco" style="top:45%;left:0;width:60px;height:120px;opacity:.1" viewBox="0 0 60 120">
    <path d="M50,10 Q10,30 12,60 Q14,90 50,110"
      fill="none" stroke="#6600FF" stroke-width="2.5" stroke-linecap="round"/>
  </svg>

  <svg class="deco" style="bottom:60px;right:24px;width:90px;height:90px;opacity:.12" viewBox="0 0 90 90">
    <rect x="8" y="8" width="72" height="72" rx="3"
      fill="none" stroke="#FF6B00" stroke-width="2.5" transform="rotate(10,45,45)"/>
    <rect x="24" y="24" width="40" height="40" rx="2"
      fill="#FF6B00" transform="rotate(-6,45,45)" opacity=".3"/>
  </svg>

  <svg class="deco" style="bottom:40px;left:24px;width:80px;height:50px;opacity:.15" viewBox="0 0 80 50">
    <path d="M4,40 Q18,6 40,4 Q62,2 76,36"
      fill="none" stroke="#111" stroke-width="2" stroke-linecap="round"/>
    <path d="M8,26 L72,28"
      fill="none" stroke="#FFE600" stroke-width="3" stroke-linecap="round" opacity=".8"/>
  </svg>

  <div class="eyebrow">CHARM LAB · 2025</div>

  <h1 class="intro-title">
    <span class="solid">你的人格</span>
    <span class="stroke">魅力类型</span>
    <span class="solid">是哪种？</span>
  </h1>

  <p class="intro-sub">16道题 · 5分钟 · 找到你的引力场</p>

  <button class="start-btn" onclick="startQuiz()">开始测试 →</button>

</section>

<!-- ══ QUIZ ══ -->
<section class="screen" id="quiz">

  <svg class="deco" style="top:20px;right:20px;width:50px;height:50px;opacity:.07" viewBox="0 0 50 50">
    <path d="M5,25 Q25,5 45,25 Q25,45 5,25Z" fill="#111"/>
  </svg>

  <div class="topbar">
    <span class="qnum" id="qNum">01 / 16</span>
    <div class="prog-track">
      <div class="prog-fill" id="pFill" style="width:0%"></div>
    </div>
    <span class="qpct" id="qPct">0%</span>
  </div>

  <div class="qcard" id="qCard">
    <span class="qemoji" id="qEmoji">🌙</span>
    <div class="qtitle" id="qTitle"></div>
    <div class="qhint" id="qHint"></div>

    <!-- LEFT-RIGHT layout -->
    <div class="options-row">
      <div class="opt l" id="sLeft"></div>
      <div class="opt r" id="sRight"></div>
    </div>

    <div class="slider-wrap">
      <div class="slider-track-bg">
        <div class="slider-fill" id="sliderFill"></div>
      </div>
      <input type="range" id="slider" min="0" max="100" value="50" step="1"
        oninput="onSlide(this.value)">
    </div>

    <div class="smood" id="sMood">· · ·</div>

    <button class="nbtn" id="nBtn" onclick="nextQ()">下一题 →</button>
  </div>

</section>

<!-- ══ RESULT ══ -->
<section class="screen" id="result">
  <div class="rlabel">✦ 你的魅力档案 ✦</div>

  <div class="hero" id="hero">
    <div class="hero-top" id="heroTop">
      <span class="hero-emoji" id="hEmoji"></span>
      <div class="hero-name" id="hName"></div>
      <div class="hero-tagline" id="hTag"></div>
    </div>
    <div class="hero-bot">
      <div class="hero-desc" id="hDesc"></div>
    </div>
  </div>

  <div class="rsec">
    <div class="rsec-lbl">BLIND SPOT · 魅力盲区</div>
    <div class="rsec-body" id="rBlind"></div>
  </div>

  <div class="rsec">
    <div class="rsec-lbl">CHEMISTRY · 关系图谱</div>
    <div class="match-grid" id="rMatch"></div>
  </div>

  <div class="radar-wrap">
    <div class="radar-lbl">CHARM RADAR · 魅力维度</div>
    <canvas id="radar" width="340" height="340"></canvas>
    <div class="dimlist" id="rDims"></div>
  </div>

  <div class="rsec">
    <div class="rsec-lbl">SAME VIBE · 名人同款</div>
    <div class="celeb-row" id="rCeleb"></div>
  </div>

  <div class="qcard-result" id="rQuote">
    <span class="qmark">"</span>
    <div class="qtext" id="rQText"></div>
  </div>

  <div class="share-row">
    <button class="sbtn pri" onclick="copyR()">📋 复制结果</button>
    <button class="sbtn" onclick="shareR()">🔗 分享</button>
  </div>
  <button class="retry" onclick="restart()">↩ 重新测试</button>
</section>

<script>
const DIMS_META=[
  {k:'G',name:'引力场'},{k:'E',name:'情绪感'},{k:'M',name:'神秘度'},{k:'L',name:'引领力'},
  {k:'C',name:'共情力'},{k:'I',name:'独立性'},{k:'X',name:'反差感'},{k:'S',name:'稳定感'}
];

const QS=[
  {e:'🌑',t:'你走进一个陌生的房间，还没开口，人们已经……',h:'感受一下你天然的存在感',
   l:'基本没人注意到我',r:'有人已经在看我了',d:{G:1},
   moods:['完全隐形，像空气一样','几乎没人注意','偶尔有人扫到我','说不清楚','有人会多看一眼','明显感觉被注意到了','一进去就有眼神过来']},
  {e:'🔥',t:'你高兴的时候，身边的人会……',h:'你的情绪有多容易传递出去',
   l:'通常感觉不到什么变化',r:'自然跟着一起开心起来',d:{E:1},
   moods:['完全感觉不到我的状态','基本不受影响','偶尔被带动一点','有时候会、有时候不会','经常跟着我的节奏','很容易被我带动','我一高兴整个场都高兴']},
  {e:'🌫️',t:'朋友眼中，你是那种……',h:'',
   l:'开放书本，没什么秘密',r:'永远有新的一面没被发现',d:{M:1},
   moods:['我基本是透明的','大家都挺了解我','偶尔有点神秘','说不清楚','有些面不轻易示人','大家觉得我难看透','朋友说永远猜不到我下一步']},
  {e:'⚡',t:'一群人不知道去哪吃饭，你会……',h:'',
   l:'等别人定，我随便',r:'好我来，我知道一个地方',d:{L:1},
   moods:['完全等别人拍板','基本不开口','偶尔会有建议','要看当时的状态','有时候会主动提','经常是那个给方向的人','通常是我直接做决定']},
  {e:'🫀',t:'朋友说起一件很难过的事，你的第一反应是……',h:'',
   l:'帮他想解决方案',r:'先把感受接住，跟着难过一会儿',d:{C:1},
   moods:['马上开始分析原因','更多是帮想方法','稍微共情但偏理性','两种都有一些','会先陪着，也会给建议','更多是跟着感受走','完全先沉浸在情绪里']},
  {e:'🌿',t:'一个人待着的时候，你感觉……',h:'独处对你来说是充电还是消耗',
   l:'有点空，需要有人陪',r:'很好，终于可以做自己的事了',d:{I:1},
   moods:['独处让我很难受','会比较容易感到空','独处还好，但不能太久','说不清，都可以','挺享受独处的','独处是我最好的状态之一','一个人是最理想的状态']},
  {e:'🎭',t:'第一次见你的人，通常会在熟了之后说……',h:'',
   l:'跟我想的差不多',r:'完全没想到你是这样的人',d:{X:1},
   moods:['就是他们第一印象的样子','基本符合预期','会有一点点惊讶','说不准','经常有一些出乎意料','大多数人都会说想错了','几乎所有人都大感意外']},
  {e:'⚓',t:'朋友遇到麻烦，你是那个……',h:'',
   l:'我也不知道怎么办，一起扛吧',r:'别慌，我来，我们这样做',d:{S:1},
   moods:['我自己也慌了，一起混乱吧','更多是陪着，没什么主意','会稍微稳一点，但不太确定','有时候能稳，有时候不行','通常能给一些方向','大多数时候我是那个稳住的人','不管多乱，我第一个冷静下来']},
  {e:'🌊',t:'你离开一个聚会之后，大家会……',h:'',
   l:'继续聊，没太大变化',r:'他/她怎么走了，感觉少了什么',d:{G:1},
   moods:['完全没变化，我走不走一样','基本没影响','偶尔有人提一句','说不清楚','会有人注意到我走了','明显感觉少了什么','气氛会直接变掉']},
  {e:'🌋',t:'一件让你愤怒的事发生了，你会……',h:'',
   l:'压住，不动声色，自己消化',r:'该说就说，不管场合',d:{E:1},
   moods:['完全压住，外表看不出来','基本不会表现出来','稍微透露一点情绪','要看情况','情绪会有一些流露','通常会说出来','当场就表达，没法藏']},
  {e:'🔮',t:'你觉得自己真正被人看懂过吗？',h:'',
   l:'有，我身边有几个很懂我的人',r:'没有，总觉得没被完全理解过',d:{M:1},
   moods:['被看懂不是问题，挺多人懂我','身边有几个挺了解我的','有一两个比较懂我的人','说不清楚','大多数时候觉得没被完全懂','很少觉得被真正理解','从来没觉得被完全看见过']},
  {e:'🎯',t:'团队讨论陷入僵局，你通常……',h:'',
   l:'安静听着，等有人拍板',r:'整合意见，推动往前走',d:{L:1},
   moods:['完全等别人来打破','基本保持沉默','偶尔会附和一个方向','看情况，不一定','有时候会出来推一下','通常会去整合大家','几乎是我来推动局面']},
  {e:'🪞',t:'看一部很虐的电影，你……',h:'',
   l:'就是一部电影，不太会入戏',r:'很容易被带进去，能哭好几次',d:{C:1},
   moods:['完全不会入戏','基本不受影响','偶尔有点感触','有时候会被触动','比较容易有感觉','很容易被带进情绪里','完全沉浸，哭了好几次']},
  {e:'🗺️',t:'做一个重要决定时，你会……',h:'',
   l:'广泛征求意见，让大家帮我想',r:'自己想清楚，最多跟一个人聊聊',d:{I:1},
   moods:['一定要问很多人','会广泛征求意见','听几个人的看法','两种都会做一些','主要靠自己，偶尔问问','基本靠自己判断','完全自己决定，不需要别人']},
  {e:'🌓',t:'你在不同场合会变成……',h:'',
   l:'差不多的人，换了场合也是我',r:'完全不同的状态，有时自己都惊讶',d:{X:1},
   moods:['任何场合都是同一个我','基本不太变','有一点点不同','看场合，有些差别','比较明显的状态切换','不同场合差异很大','完全像两个人，自己都惊讶']},
  {e:'🏔️',t:'计划被彻底打乱，你的内心戏是……',h:'',
   l:'烦死了，需要一段时间缓',r:'问题不大，重新排就行',d:{S:1},
   moods:['整个人崩掉了','很烦，需要好一会儿才能缓','会烦但能控制','有点不舒服，但不至于崩','接受得比较快','基本没什么影响','直接重新规划，完全没问题']}
];

const T={
  abyss:{emoji:'🐋',name:'深渊回响',tag:'沉默里有重量，靠近才知道有多深',
    cA:'#111',cB:'#00E5FF',tA:'#00E5FF',tB:'#111',
    desc:`你是那种让人"事后才反应过来"的存在。聚会散场，大家复盘谁最令人印象深刻，第一个被提起的往往是你——但你全程没说几句话。\n\n你不靠音量建立存在感，靠的是一种说不清的"密度"。你在场的时候，空气质地不一样。不评论，但在观察；不表态，但有判断。别人感受得到，却说不出哪里不对劲。\n\n深渊的特质不是空洞，是回声——你一旦开口，那个声音会在对方心里回荡很久。`,
    blind:`你太擅长"稳住"了，以至于身边人会忘记你也需要被照顾。你习惯承接别人的情绪，却极少开口说"我最近有点累"。\n\n还有：你的沉默有时候是温柔，有时候是回避。你不是不在乎，只是不知道怎么开口——但对方不知道这个区别，他们只会感受到"你好像有点远"。`,
    atLbl:'🌊 雷暴前夕',atDesc:'你们是"锚与雷"的组合。雷暴前夕把所有感受都活在外面，你却把所有感受都压在水面下。在你身边，他/她第一次感觉到"不需要表演"。',
    reLbl:'🪐 北极星座',reDesc:'见面不需要热场，沉默对你们来说不是尴尬而是舒适。两个都自带引力——危险是你们可能都在等对方先开口，一段好关系就这样安静地错过了。',
    celeb:['梁朝伟','巩俐'],
    quote:'有些人不需要说很多话。\n他们只要在场，\n就已经是答案。'},
  ember:{emoji:'🕯️',name:'炉火慢温',tag:'不知道什么时候开始，就是离不开了',
    cA:'#FF6B00',cB:'#F5F0E8',tA:'#F5F0E8',tB:'#111',
    desc:`你不是第一眼让人惊艳的那种，但你是"相处越久越觉得离不开"的那种。\n\n第一次见你，觉得你还好。第三次见你，开始主动找你。第十次之后，发现你已经成了某种生活里的锚点——有什么事第一个想说的是你，有什么难受第一个想找的也是你。\n\n炉火的温度不是爆发的，是持续的。你有一种罕见的能力：让人觉得被真正看见。不是表演出来的在乎，是一种细节里的留意。`,
    blind:`你给出去的温度太多，自己的能量池却常常在低水位运转。你不擅长说"我现在没有力气"，因为你觉得说了会让别人失望。\n\n学会偶尔让人看见你的需要，不是软弱，是让关系更对等。`,
    atLbl:'🦊 变色烟雾',atDesc:'你给温度，他/她给新鲜感。变色烟雾内心其实比谁都渴望一个真正安全的港湾，只是不会说。你是少数能让他/她卸下盔甲的人。',
    reLbl:'🌵 寒地孤星',reDesc:'你们都是"给出去的远比表现出来的多"的人，都在用自己的方式默默照顾身边人。在一起会心疼彼此，因为看见对方就像照镜子。',
    celeb:['彭于晏','宋慧乔'],
    quote:'不是所有的光都用来照亮舞台。\n有些光，只照一个人，\n但那个人一辈子都记得暖。'},
  polar:{emoji:'🌵',name:'寒地孤星',tag:'最冷的地方才能看见最亮的星',
    cA:'#AAFF00',cB:'#FF3300',tA:'#111',tB:'#F5F0E8',
    desc:`认识你的人分两种：没熟的觉得你有点难接近，熟了的死都不肯放手。\n\n你有一层天然的"外壳"，不是冷漠，是筛选。能真正进入你世界的人，都会觉得自己得到了某种特别的东西。\n\n寒地孤星的美不是等人发现的，是留给值得仰望的人看的。你的独立性很强——这件事本身就是一种气场，你站在那里，不需要做任何事，就已经让人想要走近。`,
    blind:`你的边界感有时候会被误读成"不在乎"。不是每个人都有耐心等你开门，有些好的关系可能在你意识到之前就走远了。\n\n偶尔让对方照顾你，不是失去独立，是给关系一个双向流动的机会。`,
    atLbl:'🪐 北极星座',atDesc:'你有边界感，他/她有向心力——你们不会黏在一起，但永远知道对方在。北极星座不会试图"打开你"，而是自然地让你愿意靠近。',
    reLbl:'🕯️ 炉火慢温',reDesc:'你们都是"低调的付出型"，都在用自己的方式默默让身边人好过。在一起会有一种被"认出来"的感觉。',
    celeb:['朴宝剑','刘亦菲'],
    quote:'不是所有的花都开在看得见的地方。\n有些人，你走近了才知道，\n原来这里有一整个春天。'},
  smoke:{emoji:'🦊',name:'变色烟雾',tag:'抓不住，散不掉，永远在变',
    cA:'#FF3300',cB:'#FFE600',tA:'#FFE600',tB:'#111',
    desc:`你是人群里的"变量"。刚以为摸清你了，你换了一面；刚觉得你好接近，你又有点远了；刚以为你不在乎，你来一句话把所有人都说进去了。\n\n烟雾的特质是：无处不在，却无法被困住。你懂人——不是学来的那种情商高，是天生对人有洞察。你的魅力有一种"信息差"的质感，你永远比别人想象的更复杂一点，更有趣一层。`,
    blind:`你太快了。你看人看场的速度比大多数人快很多，这让你有时候会失去耐心，然后选择沉默，因为解释太累了。但这个沉默会让人觉得"跟你在一起有点压力"。\n\n试着偶尔停下来，不用表现，不用分析，就只是做一个普通人待着——那一刻，你会比任何时候都更有魅力。`,
    atLbl:'🕯️ 炉火慢温',atDesc:'你变化快，他/她稳；你在外面消耗，他/她是你充电的地方。炉火慢温是少数真正"等得了你"的人——不催你回归，但你一回来就是满满的温度。',
    reLbl:'🌊 雷暴前夕',reDesc:'你们都活得很真实，不表演，不将就。在一起会很热闹，两个人气场叠加能量会翻倍。',
    celeb:['陈坤','张曼玉'],
    quote:'有些人是谜语。\n不是因为他们故意神秘，\n是因为他们真的有很多层。'},
  storm:{emoji:'🌊',name:'雷暴前夕',tag:'空气里有电，你说不清，但你感受得到',
    cA:'#FF0080',cB:'#00FFB3',tA:'#FFFDF8',tB:'#111',
    desc:`你是一个"情绪发生器"，但这不是贬义——这是你最稀有的天赋。\n\n你高兴的时候，周围的人会莫名其妙地跟着高兴；你沉下来，整个房间的温度也会降一度。你不需要宣布自己的状态，你的状态会自动广播。\n\n雷暴前夕不是破坏，是预兆。你有极强的感染力，不是靠表演，是靠真实——"真实"在这个时代是一种稀缺品。`,
    blind:`你的情绪能量很大，大能量需要出口，如果出口不对，会变成内耗或者误伤。你有时候会在没意识到的情况下，把自己的情绪状态"压"给了周围人。\n\n学会分层——不是每段关系都要全力投入，留一些轻盈给自己，也给对方。`,
    atLbl:'🐋 深渊回响',atDesc:'你是雷暴，他/她是深海——你需要一个能承接你全部重量的地方，而深渊回响恰好是。他/她不会被你的情绪淹没，反而会安静地接住你。',
    reLbl:'🦊 变色烟雾',reDesc:'你们都活得很满，感受浓，表达真。在一起话题永远停不下来，对彼此都有很强的好奇心。',
    celeb:['彭昱畅','杨幂'],
    quote:'有些人走进一个房间，\n带来的不是话题，是温度。\n你就是这种人。'},
  north:{emoji:'🪐',name:'北极星座',tag:'不移动，但所有人都用它来定位',
    cA:'#6600FF',cB:'#FFE600',tA:'#FFE600',tB:'#111',
    desc:`你没有刻意经营人缘，但你的通讯录比大多数人的都要真实——里面的人，大部分是主动找过来的。\n\n北极星不追人，不移动，不表演——但所有迷路的人都会抬头找它。你有一种天然的"可依赖感"，就是在那里，然后人会自动往你身边靠。\n\n你不急。这种"不急"本身就是一种气场，把那些真正有质量的人吸过来。`,
    blind:`你太平衡了，有时候会让人觉得"你好像对谁都一样"。你当然是有差别的，但你不擅长表达这个差别——学会偶尔偏心，让重要的人知道他/她是特别的。\n\n所有人都在找你，你却很少找别人。找一个可以让你"不用稳定"的人，对自己好一点。`,
    atLbl:'🌵 寒地孤星',atDesc:'你的稳定遇上他/她的独立，会产生一种罕见的"不用互相交代"的自由感。你有足够的耐心等那扇门自己开。',
    reLbl:'🐋 深渊回响',reDesc:'你们是"不声不响但让人安心"的同类。都不需要表演，都自带重量，在一起会有一种极深的默契。',
    celeb:['雷佳音','章子怡'],
    quote:'不是所有的中心都在聚光灯下。\n有些人站在那里，\n引力就自然发生了。'}
};

let cur=0, sc={G:50,E:50,M:50,L:50,C:50,I:50,X:50,S:50}, lastType='';

function show(id){
  document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo(0,0);
}

function startQuiz(){
  cur=0; sc={G:50,E:50,M:50,L:50,C:50,I:50,X:50,S:50};
  show('quiz'); renderQ(0);
}

function renderQ(i){
  const q=QS[i];
  const card=document.getElementById('qCard');
  card.style.animation='none'; card.offsetHeight;
  card.style.animation='cardIn .4s cubic-bezier(.34,1.56,.64,1)';
  document.getElementById('qEmoji').textContent=q.e;
  document.getElementById('qTitle').textContent=q.t;
  document.getElementById('qHint').textContent=q.h;
  document.getElementById('sLeft').textContent=q.l;
  document.getElementById('sRight').textContent=q.r;
  document.getElementById('slider').value=50;
  document.getElementById('sliderFill').style.width='50%';
  document.getElementById('sliderFill').style.background='#888';
  document.getElementById('sMood').textContent=q.moods[3];
  const pct=Math.round(i/QS.length*100);
  document.getElementById('pFill').style.width=pct+'%';
  document.getElementById('qPct').textContent=pct+'%';
  document.getElementById('qNum').textContent=String(i+1).padStart(2,'0')+' / '+QS.length;
  document.getElementById('nBtn').textContent=i===QS.length-1?'查看结果 ✨':'下一题 →';
}

function onSlide(v){
  v=parseInt(v);
  const fill=document.getElementById('sliderFill');
  fill.style.width=v+'%';
  if(v<43){
    fill.style.background='#0055AA';
    fill.style.opacity=0.15+(v/43)*0.65;
  } else if(v>57){
    fill.style.background='#CC2200';
    fill.style.opacity=0.15+((v-57)/43)*0.65;
  } else {
    fill.style.background='#888';
    fill.style.opacity=0.18;
  }
  // 7-zone labels from current question
  const q=QS[cur];
  const zones=[
    [0,8,   q.moods[0]],
    [8,22,  q.moods[1]],
    [22,43, q.moods[2]],
    [43,57, q.moods[3]],
    [57,78, q.moods[4]],
    [78,92, q.moods[5]],
    [92,101,q.moods[6]]
  ];
  for(const [a,b,txt] of zones){
    if(v>=a&&v<b){document.getElementById('sMood').textContent=txt;break}
  }
}

function nextQ(){
  const v=parseInt(document.getElementById('slider').value);
  const q=QS[cur];
  for(const d in q.d) sc[d]=sc[d]*0.55+v*0.45;
  cur++;
  cur>=QS.length?showResult():renderQ(cur);
}

function calcType(){
  const {G,E,M,L,C,I,X,S}=sc;
  if(G<45&&M>=55&&S>=55&&E<50) return'abyss';
  if(C>=55&&E<55&&I<50) return'ember';
  if(I>=55&&E<45&&X>=50) return'polar';
  if(X>=55&&M>=55&&E>=50) return'smoke';
  if(E>=55&&L>=55&&G>=55) return'storm';
  return'north';
}

function showResult(){
  show('result');
  const k=calcType(); lastType=k;
  const t=T[k];
  const ht=document.getElementById('heroTop');
  ht.style.background=t.cA;
  document.getElementById('hEmoji').textContent=t.emoji;
  const hn=document.getElementById('hName');
  hn.textContent=t.name; hn.style.color=t.tA;
  const htg=document.getElementById('hTag');
  htg.textContent=t.tag; htg.style.color=t.tA;
  document.getElementById('hDesc').textContent=t.desc;

  // Hand-drawn SVG deco on hero
  ht.insertAdjacentHTML('beforeend',`
    <svg style="position:absolute;top:12px;right:12px;width:70px;height:70px;opacity:.15;pointer-events:none" viewBox="0 0 70 70">
      <circle cx="35" cy="35" r="28" fill="none" stroke="${t.tA}" stroke-width="2.5"
        stroke-dasharray="8 5" stroke-linecap="round"/>
      <path d="M20,35 Q35,14 50,35 Q35,56 20,35Z" fill="${t.tA}" opacity=".5"/>
    </svg>`);

  document.getElementById('rBlind').textContent=t.blind;

  document.getElementById('rMatch').innerHTML=`
    <div class="mcard">
      <div class="mtag" style="background:${t.cA};color:${t.tA};border-color:${t.cA}">🧲 磁场相吸</div>
      <div class="mname">${t.atLbl}</div>
      <div class="mdesc">${t.atDesc}</div>
    </div>
    <div class="mcard">
      <div class="mtag" style="background:${t.cB};color:${t.tB}">🪞 同类共鸣</div>
      <div class="mname">${t.reLbl}</div>
      <div class="mdesc">${t.reDesc}</div>
    </div>`;

  document.getElementById('rCeleb').innerHTML=t.celeb.map((n,i)=>`
    <div class="cchip">${i===0?'👨':'👩'} ${n}
      <small>同款魅力类型</small>
    </div>`).join('');

  const qc=document.getElementById('rQuote');
  qc.style.background=t.cA; qc.style.borderColor=t.cA;
  const qt=document.getElementById('rQText');
  qt.textContent=t.quote; qt.style.color=t.tA;
  document.querySelector('.qmark').style.color=t.tA;

  renderDims();
  setTimeout(()=>drawRadar(t),450);
}

function renderDims(){
  const dl=document.getElementById('rDims'); dl.innerHTML='';
  DIMS_META.forEach(d=>{
    const p=Math.round(sc[d.k]);
    dl.insertAdjacentHTML('beforeend',`
      <div class="ditem">
        <div class="ditem-row">
          <span class="ditem-name">${d.name}</span>
          <span class="ditem-pct">${p}</span>
        </div>
        <div class="dtrack"><div class="dfill" id="df${d.k}"></div></div>
      </div>`);
  });
  setTimeout(()=>DIMS_META.forEach(d=>{
    const el=document.getElementById('df'+d.k);
    if(el)el.style.width=Math.round(sc[d.k])+'%';
  }),150);
}

function drawRadar(t){
  const cv=document.getElementById('radar');
  const ctx=cv.getContext('2d');
  const W=cv.width,H=cv.height,cx=W/2,cy=H/2;
  const R=Math.min(W,H)*0.32;
  const N=8;
  const labels=DIMS_META.map(d=>d.name);
  const vals=DIMS_META.map(d=>sc[d.k]/100);

  ctx.clearRect(0,0,W,H);

  // Seed for consistent wobble
  let seed=42;
  function rnd(){seed=(seed*9301+49297)%233280;return seed/233280}
  function wobble(x,y,amt){return{x:x+(rnd()-.5)*amt,y:y+(rnd()-.5)*amt}}

  function pt(i,r){
    const a=Math.PI*2*i/N-Math.PI/2;
    return{x:cx+r*Math.cos(a),y:cy+r*Math.sin(a)};
  }

  // Hand-drawn grid rings — wobbly
  [.25,.5,.75,1].forEach((f,ri)=>{
    ctx.beginPath();
    for(let i=0;i<=N;i++){
      const p=pt(i%N,R*f);
      const w=ri<3?wobble(p.x,p.y,3):p;
      i===0?ctx.moveTo(w.x,w.y):ctx.lineTo(w.x,w.y);
    }
    ctx.closePath();
    ctx.strokeStyle=ri===3?'#222':'#ccc';
    ctx.lineWidth=ri===3?2.5:1;
    ctx.setLineDash(ri<3?[4,5]:[]);
    ctx.stroke(); ctx.setLineDash([]);
  });

  // Axes — slightly uneven length for hand-drawn feel
  for(let i=0;i<N;i++){
    const p=pt(i,R*(0.98+rnd()*0.04));
    ctx.beginPath(); ctx.moveTo(cx,cy); ctx.lineTo(p.x,p.y);
    ctx.strokeStyle='#ddd'; ctx.lineWidth=1; ctx.stroke();
  }

  // Data polygon — hand-drawn: draw twice with slight offset
  for(let pass=0;pass<2;pass++){
    ctx.beginPath();
    for(let i=0;i<N;i++){
      const p=pt(i,R*vals[i]);
      const w=pass===0?wobble(p.x,p.y,2):p;
      i===0?ctx.moveTo(w.x,w.y):ctx.lineTo(w.x,w.y);
    }
    ctx.closePath();
    if(pass===0){
      ctx.fillStyle=t.cA+'33'; ctx.fill();
    } else {
      ctx.strokeStyle=t.cA;
      ctx.lineWidth=3;
      ctx.stroke();
    }
  }

  // Dots — rough circles
  for(let i=0;i<N;i++){
    const p=pt(i,R*vals[i]);
    const w=wobble(p.x,p.y,1.5);
    ctx.beginPath();
    ctx.arc(w.x,w.y,6,0,Math.PI*2);
    ctx.fillStyle='#111'; ctx.fill();
    ctx.strokeStyle=t.cB; ctx.lineWidth=2.5; ctx.stroke();
  }

  // Labels
  for(let i=0;i<N;i++){
    const lp=pt(i,R+30);
    ctx.fillStyle='#111';
    ctx.font='bold 12px "Noto Sans SC",sans-serif';
    ctx.textAlign='center'; ctx.textBaseline='middle';
    ctx.fillText(labels[i],lp.x,lp.y);
    // value
    const vp=pt(i,R*vals[i]+(vals[i]>0.55?-18:18));
    ctx.fillStyle='#aaa';
    ctx.font='10px "Space Mono",monospace';
    ctx.fillText(Math.round(vals[i]*100),vp.x,vp.y);
  }
}

function copyR(){
  const t=T[lastType||calcType()];
  const txt=`我做了「你的人格魅力是哪种？」测试\n结果是 ${t.emoji} ${t.name}\n「${t.tag}」\n\n${t.quote}\n\n你也来测测？`;
  navigator.clipboard.writeText(txt).then(()=>{
    const b=event.target,o=b.textContent;
    b.textContent='✅ 已复制！'; setTimeout(()=>b.textContent=o,2000);
  }).catch(()=>alert('请手动复制'));
}

function shareR(){
  const t=T[lastType||calcType()];
  if(navigator.share){
    navigator.share({title:`我的魅力类型是${t.name}`,text:`${t.emoji} ${t.name} — ${t.tag}\n\n${t.quote}`,url:location.href});
  }else copyR();
}

function restart(){
  cur=0; sc={G:50,E:50,M:50,L:50,C:50,I:50,X:50,S:50}; lastType='';
  show('intro');
}

document.addEventListener('DOMContentLoaded',()=>show('intro'));
</script>
</body>
</html>
