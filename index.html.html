<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>你的人格魅力是哪种？</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400;700;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
:root{
  --ink:#111;--paper:#F5F0E8;--white:#FFFDF8;
}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Noto Sans SC',sans-serif;background:var(--paper);color:var(--ink);min-height:100vh;overflow-x:hidden}

.screen{display:none;min-height:100vh;flex-direction:column;align-items:center}
.screen.active{display:flex}

/* ── INTRO ── */
#intro{justify-content:center;padding:60px 24px 80px;text-align:center;position:relative;overflow:hidden}

.eyebrow{font-family:'Space Mono',monospace;font-size:11px;letter-spacing:.18em;border:2.5px solid var(--ink);padding:6px 16px;margin-bottom:40px;display:inline-block;transform:rotate(-1deg)}

.intro-title{font-size:clamp(38px,9vw,76px);font-weight:900;line-height:1;letter-spacing:-.03em;margin-bottom:12px}
.intro-title .stroke{-webkit-text-stroke:3px var(--ink);color:transparent;display:block}
.intro-title .solid{display:block}

.intro-sub{font-size:15px;color:#666;margin-bottom:48px;line-height:1.8;max-width:340px}

.chips{display:flex;gap:8px;flex-wrap:wrap;justify-content:center;margin-bottom:52px;max-width:480px}
.chip{border:2.5px solid var(--ink);padding:8px 14px;font-size:13px;font-weight:700;background:var(--white);transition:transform .15s;cursor:default}
.chip:nth-child(odd){transform:rotate(-1.2deg)}
.chip:nth-child(even){transform:rotate(.8deg)}
.chip:hover{transform:rotate(0) scale(1.06)}

.start-btn{background:var(--ink);color:var(--paper);border:2.5px solid var(--ink);padding:18px 52px;font-size:18px;font-weight:900;font-family:'Noto Sans SC',sans-serif;cursor:pointer;letter-spacing:.04em;transform:rotate(-.5deg);transition:all .15s}
.start-btn:hover{background:#FF3300;border-color:#FF3300;transform:rotate(0) scale(1.04)}
.start-btn:active{transform:scale(.97)}

/* deco SVGs */
.deco{position:absolute;pointer-events:none;overflow:visible}

/* ── QUIZ ── */
#quiz{padding:32px 20px 80px;position:relative}

.topbar{width:100%;max-width:560px;display:flex;align-items:center;gap:16px;margin-bottom:40px}
.qnum{font-family:'Space Mono',monospace;font-size:12px;letter-spacing:.08em;min-width:48px}
.prog-track{flex:1;height:5px;background:#ddd;border:1.5px solid var(--ink);overflow:hidden}
.prog-fill{height:100%;background:var(--ink);transition:width .4s cubic-bezier(.34,1.56,.64,1)}
.qpct{font-family:'Space Mono',monospace;font-size:11px;color:#999;min-width:32px;text-align:right}

.qcard{background:var(--white);border:2.5px solid var(--ink);padding:36px 32px 32px;max-width:560px;width:100%;position:relative;animation:cardIn .35s cubic-bezier(.34,1.56,.64,1)}
@keyframes cardIn{from{opacity:0;transform:translateY(20px) scale(.97)}to{opacity:1;transform:none}}

.qemoji{font-size:44px;display:block;margin-bottom:18px;animation:pop .45s cubic-bezier(.34,1.56,.64,1)}
@keyframes pop{from{transform:scale(0) rotate(-12deg)}to{transform:none}}
.qtitle{font-size:20px;font-weight:900;line-height:1.4;letter-spacing:-.01em;margin-bottom:8px}
.qhint{font-size:12px;color:#999;margin-bottom:34px;font-style:italic}

.slider-ends{display:flex;justify-content:space-between;gap:10px;margin-bottom:12px}
.send{font-size:12px;font-weight:700;padding:6px 12px;border:2px solid var(--ink);line-height:1.4;background:var(--white);max-width:200px}
.send.l{color:#0066AA}.send.r{color:#CC2200}

input[type=range]{-webkit-appearance:none;width:100%;height:6px;background:var(--ink);outline:none;cursor:pointer;border:none}
input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:30px;height:30px;border-radius:50%;background:var(--paper);border:3px solid var(--ink);cursor:grab;box-shadow:3px 3px 0 var(--ink);transition:transform .1s}
input[type=range]::-webkit-slider-thumb:active{cursor:grabbing;transform:scale(1.15)}
input[type=range]::-moz-range-thumb{width:30px;height:30px;border-radius:50%;background:var(--paper);border:3px solid var(--ink);cursor:grab}
.smood{text-align:center;margin-top:10px;font-size:12px;color:#999;font-style:italic;min-height:20px}

.prev-row{width:100%;display:flex;align-items:center;justify-content:center;margin-top:20px;min-height:22px}
.prev-link{background:none;border:none;font-size:12px;color:#999;cursor:pointer;font-family:'Noto Sans SC',sans-serif;text-decoration:underline;text-underline-offset:3px;padding:4px 8px;font-weight:400;letter-spacing:.02em}
.prev-link:hover{color:#666}
.nbtn{width:100%;margin-top:10px;background:var(--ink);color:var(--paper);border:2.5px solid var(--ink);padding:16px;font-size:16px;font-weight:900;font-family:'Noto Sans SC',sans-serif;cursor:pointer;letter-spacing:.04em;transition:all .15s}
.nbtn:hover{background:#FF3300;border-color:#FF3300}
.nbtn:active{transform:scale(.98)}

/* ── RESULT ── */
#result{padding:40px 20px 100px}

.rlabel{font-family:'Space Mono',monospace;font-size:10px;letter-spacing:.2em;color:#999;margin-bottom:20px;text-transform:uppercase}

.hero{width:100%;max-width:560px;border:3px solid var(--ink);margin-bottom:14px;overflow:hidden}
.hero-top{padding:36px 28px 28px;position:relative;min-height:180px}
.hero-bot{padding:20px 28px 24px;border-top:3px solid var(--ink);background:var(--white)}
.hero-emoji{font-size:64px;display:block;margin-bottom:14px;animation:bigpop .6s cubic-bezier(.34,1.56,.64,1)}
@keyframes bigpop{from{transform:scale(0) rotate(-15deg);opacity:0}to{transform:none;opacity:1}}
.hero-name{font-size:clamp(30px,7vw,50px);font-weight:900;letter-spacing:-.03em;line-height:1;margin-bottom:8px}
.hero-tagline{font-size:14px;font-weight:700;letter-spacing:.04em;opacity:.7}
.hero-desc{font-size:14px;line-height:1.9;color:#333;white-space:pre-line}

.rsec{width:100%;max-width:560px;border:2.5px solid var(--ink);background:var(--white);margin-bottom:12px;padding:22px 24px;position:relative}
.rsec-lbl{font-family:'Space Mono',monospace;font-size:10px;letter-spacing:.15em;color:#999;margin-bottom:14px;text-transform:uppercase}
.rsec-body{font-size:13px;line-height:1.9;color:#333}

.match-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.mcard{border:2.5px solid var(--ink);padding:14px;background:var(--paper)}
.mtag{font-size:9px;font-weight:900;letter-spacing:.1em;padding:2px 7px;border:1.5px solid var(--ink);display:inline-block;margin-bottom:8px}
.mname{font-size:16px;font-weight:900;margin-bottom:4px}
.mdesc{font-size:11px;color:#555;line-height:1.6}

.radar-wrap{width:100%;max-width:560px;border:2.5px solid var(--ink);background:var(--white);margin-bottom:12px;padding:24px}
.radar-lbl{font-family:'Space Mono',monospace;font-size:10px;letter-spacing:.15em;color:#999;margin-bottom:16px;text-transform:uppercase}
canvas{display:block;margin:0 auto;max-width:300px;width:100%}

.dimlist{margin-top:16px}
.ditem{margin-bottom:14px}
.ditem:last-child{margin-bottom:0}
.dhead{display:flex;justify-content:space-between;font-size:12px;font-weight:700;margin-bottom:5px}
.dl{color:#0066AA}.dr{color:#CC2200}
.dpct{font-family:'Space Mono',monospace;font-size:11px;color:#999}
.dtrack{height:7px;background:#e8e0d0;border:1.5px solid var(--ink);overflow:hidden}
.dfill{height:100%;background:var(--ink);transition:width 1.2s cubic-bezier(.34,1.56,.64,1);width:0}

.celeb-row{display:flex;gap:10px}
.cchip{flex:1;border:2px solid var(--ink);padding:10px 12px;background:var(--paper);font-size:13px;font-weight:700;line-height:1.4}
.cchip small{display:block;font-size:10px;font-weight:400;color:#888;margin-top:2px}

.qcard-result{width:100%;max-width:560px;border:3px solid var(--ink);padding:28px;margin-bottom:12px}
.qmark{font-size:56px;font-weight:900;line-height:.6;opacity:.2;font-family:serif;display:block;margin-bottom:8px}
.qtext{font-size:clamp(15px,4vw,18px);font-weight:700;line-height:1.75;letter-spacing:.01em}

.share-row{display:flex;gap:10px;width:100%;max-width:560px;margin-bottom:10px}
.sbtn{flex:1;padding:14px;border:2.5px solid var(--ink);background:var(--white);font-size:14px;font-weight:700;font-family:'Noto Sans SC',sans-serif;cursor:pointer;transition:all .15s;color:var(--ink)}
.sbtn:hover{background:var(--paper);transform:translateY(-2px)}
.sbtn.pri{background:var(--ink);color:var(--paper)}
.sbtn.pri:hover{background:#FF3300;border-color:#FF3300}
.retry{background:none;border:none;font-size:13px;color:#999;cursor:pointer;font-family:'Noto Sans SC',sans-serif;text-decoration:underline;text-underline-offset:3px;padding:8px}
.retry:hover{color:var(--ink)}

@media(max-width:480px){
  .qcard{padding:24px 16px 20px}
  .slider-ends{flex-direction:column;gap:6px}
  .send{max-width:100%}
  .match-grid{grid-template-columns:1fr}
  .hero-top{padding:24px 18px 20px}
  .hero-bot{padding:16px 18px 20px}
}
</style>
</head>
<body>

<!-- INTRO -->
<section class="screen" id="intro">
  <svg class="deco" style="top:16px;left:8px;width:110px;height:110px" viewBox="0 0 110 110">
    <path d="M18,55 Q22,18 55,16 Q88,14 92,52 Q96,88 58,95 Q20,102 18,55Z" fill="none" stroke="#111" stroke-width="2" opacity=".1"/>
    <path d="M36,55 Q38,36 55,34 Q72,32 74,54 Q76,74 57,78 Q36,82 36,55Z" fill="#AAFF00" stroke="#111" stroke-width="1.5" opacity=".2"/>
  </svg>
  <svg class="deco" style="top:50px;right:12px;width:75px;height:75px" viewBox="0 0 75 75">
    <circle cx="37" cy="37" r="30" fill="none" stroke="#FF3300" stroke-width="2" stroke-dasharray="6 4" opacity=".25"/>
    <circle cx="37" cy="37" r="16" fill="#FF0080" opacity=".12"/>
  </svg>
  <svg class="deco" style="bottom:70px;left:16px;width:90px;height:55px" viewBox="0 0 90 55">
    <path d="M5,45 Q18,8 45,6 Q72,4 85,40" fill="none" stroke="#6600FF" stroke-width="2" stroke-linecap="round" opacity=".18"/>
    <path d="M8,28 L82,30" fill="none" stroke="#FFE600" stroke-width="2" opacity=".35"/>
  </svg>
  <svg class="deco" style="bottom:30px;right:20px;width:85px;height:85px" viewBox="0 0 85 85">
    <rect x="8" y="8" width="68" height="68" rx="4" fill="none" stroke="#FF6B00" stroke-width="2" transform="rotate(8,42,42)" opacity=".18"/>
    <rect x="24" y="24" width="36" height="36" rx="2" fill="#FF6B00" transform="rotate(-5,42,42)" opacity=".1"/>
  </svg>

  <div class="eyebrow">PERSONALITY × CHARM LAB · 2025</div>
  <h1 class="intro-title">
    <span class="solid">你的人格</span>
    <span class="stroke">魅力类型</span>
    <span class="solid">是哪种？</span>
  </h1>
  <p class="intro-sub">12道滑动题 · 3分钟 · 揭开你身上那道无声的引力场</p>
  <div class="chips">
    <div class="chip">🐋 沉默磁场</div>
    <div class="chip">🕯️ 温水烛心</div>
    <div class="chip">🌵 冷面热核</div>
    <div class="chip">🦊 猜不到底</div>
    <div class="chip">🌊 满场带电</div>
    <div class="chip">🪐 天然圆心</div>
  </div>
  <button class="start-btn" onclick="startQuiz()">开始测试 →</button>
</section>

<!-- QUIZ -->
<section class="screen" id="quiz">
  <div class="topbar">
    <span class="qnum" id="qNum">01/12</span>
    <div class="prog-track"><div class="prog-fill" id="pFill" style="width:0%"></div></div>
    <span class="qpct" id="qPct">0%</span>
  </div>
  <div class="qcard" id="qCard">
    <span class="qemoji" id="qEmoji">🌙</span>
    <div class="qtitle" id="qTitle"></div>
    <div class="qhint" id="qHint"></div>
    <div class="slider-ends">
      <div class="send l" id="sLeft"></div>
      <div class="send r" id="sRight"></div>
    </div>
    <input type="range" id="slider" min="0" max="100" value="50" step="1" oninput="onSlide(this.value)">
    <div class="smood" id="sMood">拖动滑块感受一下自己偏向哪边</div>
    <div class="prev-row">
      <button type="button" class="prev-link" id="pBtn" onclick="prevQ()">← 上一题</button>
    </div>
    <button class="nbtn" id="nBtn" onclick="nextQ()">下一题 →</button>
  </div>
</section>

<!-- RESULT -->
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
    <canvas id="radar" width="300" height="300"></canvas>
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
const QS=[
  {e:'🎉',t:'你被临时拉去一个全是陌生人的饭局，你的第一反应是…',h:'诚实选，没有对错，只有真实',l:'😮‍💨 内心os：为什么要这样对我',r:'🤩 好耶，说不定有意思的人',d:{E:1}},
  {e:'🧠',t:'喜欢上一个人的时候，你通常是…',h:'心动那一刻，你的大脑在干嘛',l:'📊 先在脑子里跑一遍「他/她适合我吗」',r:'🫀 已经喜欢了，分析有什么用',d:{A:1}},
  {e:'🎲',t:'买东西你会…',h:'小事也能看出一个人的决策风格',l:'✅ 货比三家，看完所有评价再下单',r:'⚡ 看顺眼就买，后悔了再说',d:{R:1}},
  {e:'🎤',t:'小组讨论没人开口，你会…',h:'这道题测的是你的「启动成本」',l:'🪑 等别人先说，我来补充',r:'🎯 算了我来吧，说说我的想法',d:{L:1}},
  {e:'🌙',t:'连续社交三天之后，你最需要的是…',h:'能量的补充方式，暴露了你是哪种人',l:'🛋️ 一个人待着，充电',r:'📱 找人聊天，把这三天的事全说一遍',d:{E:1}},
  {e:'💔',t:'和朋友闹矛盾了，你更难受的是…',h:'同一件事，不同的人卡在不同的地方',l:'🤔 「这件事哪里出了问题」',r:'😢 「他/她是不是不喜欢我了」',d:{A:1}},
  {e:'🗺️',t:'旅行你更喜欢…',h:'旅行风格 = 人生风格，基本上',l:'📋 提前做好攻略，行程安排满满',r:'🎒 买张票出发，到了再说',d:{R:1}},
  {e:'👥',t:'你在一段关系里，更多扮演…',h:'不用说「两者都有」——偏哪边多一点？',l:'🫂 那个被照顾、被安排的',r:'🧭 那个拿主意、做决定的',d:{L:1}},
  {e:'🎭',t:'有人当众夸你，你的反应是…',h:'被看见的时候，你是什么感受',l:'😳 脸红，不知道说什么，想逃',r:'😄 谢谢！然后自然接话聊下去',d:{E:1}},
  {e:'🔮',t:'做一个重要决定时，你更相信…',h:'人生关键时刻，你的导航靠什么',l:'📐 数据、逻辑、别人的经验',r:'🌊 直觉，感觉对了就是对了',d:{A:1}},
  {e:'🌪️',t:'计划被临时打乱，你的内心戏是…',h:'稳定型 vs 弹性型，你是哪个',l:'😤 已经在脑子里崩溃了（表面还好）',r:'😎 计划是用来打乱的，随机应变',d:{R:1}},
  {e:'✨',t:'你觉得自己身上最吸引人的一点是…',h:'最后一题，相信第一反应',l:'🌑 神秘感——让人想靠近，又捉摸不透',r:'🌞 亲近感——让人觉得安全，什么都想说',d:{L:1}}
];

const T={
  whale:{emoji:'🐋',name:'沉默磁场',tag:'不说话也有引力',cA:'#111',cB:'#00E5FF',tA:'#00E5FF',tB:'#111',
    desc:`你是那种让人"事后才反应过来"的存在。聚会结束，大家复盘谁最有意思，第一个被提起的往往是你——但你全程没说几句话。\n\n你的存在感不靠音量，靠的是一种说不清的"重量"。你在的时候，空气的密度不一样。你不评论，但你在观察；你不表态，但你有判断。别人感受得到，却说不出哪里不对劲。\n\n你给人安全感，不是因为你温柔，是因为你稳。亲密关系里，你是那个"少说一句，对方反而更在意"的人。你一旦认定一个人，那种深情是无声的、持久的，像海底洋流，表面看不见，但一直在流。`,
    blind:`你太擅长"稳住"了，以至于身边人会忘记你也需要被照顾。你习惯承接别人的情绪，却极少开口说"我最近有点累"。时间久了，你会在某一个普通的夜里突然觉得——好像所有人都在找我，但没有人在找我。\n\n还有一点：你的沉默有时候是温柔，有时候是回避。你不是不在乎，你只是不知道怎么开口——但对方不知道这个区别，他们只会感受到"你好像有点远"。`,
    atLbl:'🌊 满场带电',atDesc:'你们是"锚与浪"的组合。满场带电把所有感受都活在脸上，你却把所有感受都压在水面下。他/她第一次在你身边感觉到"不需要表演"，而你会在他/她身上学到如何把感受说出口。',
    reLbl:'🪐 天然圆心',reDesc:'见面不需要热场，沉默对你们来说不是尴尬而是舒适。两个人都自带引力——危险是你们可能都在等对方先开口，结果一段好关系就这样安静地错过了。',
    celeb:['梁朝伟','巩俐'],
    quote:'有些人不需要说很多话。\n他们只要在场，\n就已经是答案。'},

  candle:{emoji:'🕯️',name:'温水烛心',tag:'悄悄就让人离不开',cA:'#FF6B00',cB:'#F5F0E8',tA:'#F5F0E8',tB:'#111',
    desc:`你不是第一眼就让人惊艳的那种，但你是"相处越久越觉得离不开"的那种。\n\n第一次见你，觉得你还好。第三次见你，开始主动找你。第十次之后，发现你已经成了某种生活里的锚点——有什么事第一个想说的是你，有什么难受第一个想找的也是你。\n\n你有一种罕见的能力：让人觉得被真正看见。不是表演出来的"我很在乎你"，是一种细节里的留意——你记得他上次说起的那件小事，你注意到她今天状态不对，你不说破，但你会递过去一杯热的。`,
    blind:`你给出去的温度太多，自己的能量池却常常在低水位运转。你不擅长说"我现在没有力气"，因为你觉得说了会让别人失望。\n\n还有一点：你的好，有时候会被人当成"理所当然"。不是因为他们坏，是因为你从不设防，从不喊疼，别人就以为你不会疼。学会偶尔让人看见你的需要，不是软弱，是让关系更对等。`,
    atLbl:'🦊 猜不到底',atDesc:'你给温度，他/她给新鲜感。猜不到底的人内心其实比谁都渴望一个真正安全的港湾，只是不会说。你是少数能让他/她卸下"永远有趣"这层盔甲的人。',
    reLbl:'🌵 冷面热核',reDesc:'你们都是"给出去的远比表现出来的多"的人，都在用自己的方式默默照顾身边的人。你们在一起会心疼彼此，因为看见对方就像照镜子。',
    celeb:['彭于晏','宋慧乔'],
    quote:'不是所有的光都用来照亮舞台。\n有些光，只照一个人，\n但那个人一辈子都记得暖。'},

  cactus:{emoji:'🌵',name:'冷面热核',tag:'熟了之后完全不一样',cA:'#AAFF00',cB:'#FF3300',tA:'#111',tB:'#F5F0E8',
    desc:`认识你的人分两种：没熟的觉得你有点难接近，熟了的死都不肯放手。\n\n你有一层天然的"外壳"，不是冷漠，是筛选。你不会对所有人敞开——这让你在第一印象里显得有距离感，但也正是因为这个，能真正进入你世界的人，都会觉得自己得到了某种特别的东西。\n\n你的反差是你最大的魅力来源。大家以为你很冷，结果你私下可以为一个朋友的小事操心半个月。你的独立性非常强，不依赖、不黏人——这件事本身就是一种气场。`,
    blind:`你的边界感有时候会被误读成"不在乎"。你以为自己只是在保护空间，但对方接收到的信号是"你不需要我"。不是每个人都有耐心等你开门，有些好的关系可能在你意识到之前就走远了。\n\n另一点：你不擅长主动示弱，这让你在亲密关系里常常积累委屈。偶尔让对方照顾你，不是失去独立，是给关系一个双向流动的机会。`,
    atLbl:'🪐 天然圆心',atDesc:'你有边界感，他/她有向心力——你们不会黏在一起，但永远知道对方在。天然圆心不会试图"打开你"，而是自然地让你愿意靠近；你的独立反而让他/她觉得轻松。',
    reLbl:'🕯️ 温水烛心',reDesc:'你们都是"低调的付出型"。你用独立保护自己，他/她用温柔包裹别人——方式不同，但都在默默让身边的人好过。在一起会有一种被"认出来"的感觉。',
    celeb:['朴宝剑','刘亦菲'],
    quote:'不是所有的花都开在看得见的地方。\n有些人，你走近了才知道，\n原来这里有一整个春天。'},

  fox:{emoji:'🦊',name:'猜不到底',tag:'永远比你想的更有趣一层',cA:'#FF3300',cB:'#FFE600',tA:'#FFE600',tB:'#111',
    desc:`你是人群里的"变量"。刚以为摸清你了，你换了一面；刚觉得你好接近，你又有点远了；刚以为你不在乎，你来一句话把所有人都说进去了。\n\n你懂人。不是学来的那种"情商高"，是天生对人有洞察——谁在表演，谁是真实的，你一眼就有判断。但你不揭穿，你只是默默知道。\n\n你的魅力有一种"信息差"的质感：你永远比别人想象的更复杂一点，更有趣一层。这让人跟你相处有一种停不下来的感觉——因为永远有新东西在等着被发现。`,
    blind:`你太快了。你看人看场的速度比大多数人快很多——这让你有时候会失去耐心：对方还没想明白，你已经看到三步之后了，然后你选择沉默，因为解释太累了。但这个沉默会让人觉得"跟你在一起有点压力"。\n\n还有：你的多面性有时候让人找不到"真实的你在哪里"。试着偶尔停下来，不用表现，不用分析，就只是做一个普通人待着——那一刻，你会比任何时候都更有魅力。`,
    atLbl:'🕯️ 温水烛心',atDesc:'你变化快，他/她稳；你在外面消耗，他/她是你充电的地方。温水烛心是少数真正"等得了你"的人——不催你回归，不需要你解释消失，但你一回来就是满满的温度。',
    reLbl:'🌊 满场带电',reDesc:'你们都活得很真实，不表演，不将就。都是"宁可直接，不要敷衍"的人，都有很强的感染力。在一起会很热闹，两个人的气场叠加整个场的能量会翻倍。',
    celeb:['陈坤','张曼玉'],
    quote:'有些人是谜语。\n不是因为他们故意神秘，\n是因为他们真的有很多层。'},

  wave:{emoji:'🌊',name:'满场带电',tag:'你定场，整个场就定了',cA:'#FF0080',cB:'#00FFB3',tA:'#FFFDF8',tB:'#111',
    desc:`你是一个"情绪发生器"，但这不是贬义——这是你最稀有的天赋。\n\n你高兴的时候，周围的人会莫名其妙地跟着高兴；你沉下来，整个房间的温度也会降一度。你不需要宣布自己的状态，你的状态会自动广播。\n\n你有极强的感染力，不是靠表演，是靠真实。"真实"在这个时代是一种稀缺品。你在一段关系里是"启动者"——你敢先开口说喜欢，你的关系浓度很高，不做表面朋友。`,
    blind:`你的情绪能量很大，大能量需要出口，如果出口不对，会变成内耗或者误伤。你有时候会在没意识到的情况下，把自己的情绪状态"压"给了周围人——对方承接了你的重量，却说不清楚自己哪里不舒服。\n\n另一点：你对关系的浓度要求很高，但不是所有人都能在这个浓度里呼吸。学会分层——不是每段关系都要全力投入，留一些轻盈给自己，也给对方。`,
    atLbl:'🐋 沉默磁场',atDesc:'你是海浪，他/她是海床。沉默磁场不会被你的情绪淹没，反而会安静地接住你，让你第一次感觉到"不用控制自己的烈度"。而你给他/她带来的，是他/她自己很难做到的事：让关系流动起来。',
    reLbl:'🦊 猜不到底',reDesc:'你们都活得很满，感受浓，表达真，不愿意过平淡的日子。在一起话题永远停不下来，对彼此都有很强的好奇心。难点是两个都需要被看见的人，有时候会不自觉地竞争谁更被关注。',
    celeb:['彭昱畅','杨幂'],
    quote:'有些人走进一个房间，\n带来的不是话题，是温度。\n你就是这种人。'},

  orbit:{emoji:'🪐',name:'天然圆心',tag:'没做什么，但大家都围着你',cA:'#6600FF',cB:'#FFE600',tA:'#FFE600',tB:'#111',
    desc:`你没有刻意经营人缘，但你的通讯录比大多数人的都要真实——里面的人，大部分是主动找过来的。\n\n你有一种天然的"可依赖感"，不需要证明，不需要表演，就是在那里——然后人会自动往你身边靠。你处理关系有一种天然的公平感，这让你在任何群体里都是稳定的核心，不是因为你争，是因为你平。\n\n你不急。不急着表现，不急着被认可——这种"不急"本身就是一种气场，把那些真正有质量的人吸过来。`,
    blind:`你太平衡了，有时候会让人觉得"你好像对谁都一样"。亲密的人会困惑：我在你心里，跟别人不一样吗？你当然是有差别的，但你不擅长表达这个差别——学会偶尔偏心，让重要的人知道他/她是特别的。\n\n另一点：所有人都在找你，你却很少找别人。你以为自己不需要，其实只是习惯了独自扛着。找一个可以让你"不用稳定"的人，对自己好一点。`,
    atLbl:'🌵 冷面热核',atDesc:'你的稳定遇上他/她的独立，会产生一种罕见的"不用互相交代"的自由感。冷面热核不会因为你"对谁都好"而嫉妒，你也不会因为他/她难接近而受挫，因为你有足够的耐心等那扇门自己开。',
    reLbl:'🐋 沉默磁场',reDesc:'你们是"不声不响但让人安心"的同类。都不需要表演，都自带重量，在一起会有一种极深的默契。要注意两个习惯照顾别人的人，都可能忘了照顾彼此。',
    celeb:['雷佳音','章子怡'],
    quote:'不是所有的中心都在聚光灯下。\n有些人站在那里，\n引力就自然发生了。'}
};

const DIMS=[
  {k:'E',l:'内向型',r:'外向型'},
  {k:'A',l:'理性派',r:'感性派'},
  {k:'R',l:'稳定系',r:'冒险系'},
  {k:'L',l:'跟随者',r:'引领者'}
];

let cur=0, sc={E:50,A:50,R:50,L:50}, lastType='', answers=[];

function show(id){
  document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo(0,0);
}

function startQuiz(){
  cur=0; sc={E:50,A:50,R:50,L:50}; answers=[];
  show('quiz'); renderQ(0);
}

function renderQ(i){
  const q=QS[i];
  const card=document.getElementById('qCard');
  card.style.animation='none'; card.offsetHeight;
  card.style.animation='cardIn .35s cubic-bezier(.34,1.56,.64,1)';
  document.getElementById('qEmoji').textContent=q.e;
  document.getElementById('qTitle').textContent=q.t;
  document.getElementById('qHint').textContent=q.h;
  document.getElementById('sLeft').textContent=q.l;
  document.getElementById('sRight').textContent=q.r;
  document.getElementById('slider').value=50;
  document.getElementById('sMood').textContent='拖动滑块感受一下自己偏向哪边';
  const pct=Math.round(i/QS.length*100);
  document.getElementById('pFill').style.width=pct+'%';
  document.getElementById('qPct').textContent=pct+'%';
  document.getElementById('qNum').textContent=String(i+1).padStart(2,'0')+'/'+QS.length;
  document.getElementById('nBtn').textContent=i===QS.length-1?'查看结果 ✨':'下一题 →';
  document.getElementById('pBtn').hidden=(i===0);
}

function onSlide(v){
  v=parseInt(v);
  const m=v<20?'非常偏左边 👈':v<40?'偏左一些':v<62?'嗯……两边都有点像':v<82?'偏右一些':'非常偏右边 👉';
  document.getElementById('sMood').textContent=m;
}

function nextQ(){
  const v=parseInt(document.getElementById('slider').value);
  answers.push(v);
  const q=QS[cur];
  for(const d in q.d) sc[d]=sc[d]*0.55+v*0.45;
  cur++;
  cur>=QS.length?showResult():renderQ(cur);
}

function prevQ(){
  if(cur<=0)return;
  const restore=answers.pop();
  cur--;
  sc={E:50,A:50,R:50,L:50};
  for(let j=0;j<answers.length;j++){
    const vv=answers[j]; const qq=QS[j];
    for(const d in qq.d) sc[d]=sc[d]*0.55+vv*0.45;
  }
  renderQ(cur);
  document.getElementById('slider').value=restore;
  onSlide(String(restore));
}

function calcType(){
  const {E,A,R,L}=sc;
  if(E<40&&A<45&&L<50)return'whale';
  if(E<45&&A>=50)return'candle';
  if(E>=55&&R<45&&L<50)return'cactus';
  if(E>=50&&A>=55&&L>=55)return'wave';
  if(L>=58&&E<55)return'orbit';
  return'fox';
}

function showResult(){
  show('result');
  const k=calcType(); lastType=k;
  const t=T[k];

  // Hero
  const ht=document.getElementById('heroTop');
  ht.style.background=t.cA; ht.style.color=t.tA;
  document.getElementById('hEmoji').textContent=t.emoji;
  const hn=document.getElementById('hName');
  hn.textContent=t.name; hn.style.color=t.tA;
  const htg=document.getElementById('hTag');
  htg.textContent=t.tag; htg.style.color=t.tA;
  document.getElementById('hDesc').textContent=t.desc;

  // Hand-drawn deco on hero
  ht.insertAdjacentHTML('beforeend',`<svg style="position:absolute;top:10px;right:10px;width:65px;height:65px;opacity:.18;pointer-events:none" viewBox="0 0 65 65">
    <circle cx="32" cy="32" r="27" fill="none" stroke="${t.tA}" stroke-width="2.5" stroke-dasharray="7 4"/>
    <path d="M18,32 Q32,12 46,32 Q32,52 18,32Z" fill="${t.tA}" opacity=".45"/>
  </svg>`);

  // Blind
  document.getElementById('rBlind').textContent=t.blind;

  // Match
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

  // Celeb
  document.getElementById('rCeleb').innerHTML=t.celeb.map((n,i)=>`
    <div class="cchip">${i===0?'👨':'👩'} ${n}<small>同款魅力类型</small></div>`).join('');

  // Quote
  const qc=document.getElementById('rQuote');
  qc.style.background=t.cA; qc.style.borderColor=t.cA;
  const qt=document.getElementById('rQText');
  qt.textContent=t.quote; qt.style.color=t.tA;
  document.querySelector('.qmark').style.color=t.tA;

  // Dims
  const dl=document.getElementById('rDims'); dl.innerHTML='';
  DIMS.forEach(d=>{
    const p=Math.round(sc[d.k]);
    dl.insertAdjacentHTML('beforeend',`
      <div class="ditem">
        <div class="dhead"><span class="dl">${d.l}</span><span class="dpct">${p}%</span><span class="dr">${d.r}</span></div>
        <div class="dtrack"><div class="dfill" id="df${d.k}"></div></div>
      </div>`);
  });
  setTimeout(()=>DIMS.forEach(d=>{
    const el=document.getElementById('df'+d.k);
    if(el)el.style.width=Math.round(sc[d.k])+'%';
  }),120);

  setTimeout(()=>drawRadar(t),400);
}

function drawRadar(t){
  const cv=document.getElementById('radar');
  const ctx=cv.getContext('2d');
  const W=cv.width,H=cv.height,cx=W/2,cy=H/2,R=Math.min(W,H)*0.35;
  const N=4,labels=['外向','感性','冒险','引领'];
  const vals=[sc.E/100,sc.A/100,sc.R/100,sc.L/100];
  ctx.clearRect(0,0,W,H);

  function pt(i,r){
    const a=Math.PI*2*i/N-Math.PI/2;
    return{x:cx+r*Math.cos(a),y:cy+r*Math.sin(a)};
  }

  // Grid rings with slight wobble for hand-drawn feel
  [.25,.5,.75,1].forEach((f,ri)=>{
    ctx.beginPath();
    for(let i=0;i<N;i++){
      const p=pt(i,R*f);
      const wx=p.x+(ri<3?(Math.random()-.5)*3:0);
      const wy=p.y+(ri<3?(Math.random()-.5)*3:0);
      i===0?ctx.moveTo(wx,wy):ctx.lineTo(wx,wy);
    }
    ctx.closePath();
    ctx.strokeStyle=ri===3?'#111':'#ccc';
    ctx.lineWidth=ri===3?2:1;
    ctx.setLineDash(ri<3?[4,4]:[]);
    ctx.stroke(); ctx.setLineDash([]);
  });

  // Axes
  for(let i=0;i<N;i++){
    const p=pt(i,R);
    ctx.beginPath(); ctx.moveTo(cx,cy); ctx.lineTo(p.x,p.y);
    ctx.strokeStyle='#ddd'; ctx.lineWidth=1; ctx.stroke();
  }

  // Data fill
  ctx.beginPath();
  for(let i=0;i<N;i++){
    const p=pt(i,R*vals[i]);
    i===0?ctx.moveTo(p.x,p.y):ctx.lineTo(p.x,p.y);
  }
  ctx.closePath();
  ctx.fillStyle=t.cA+'55'; ctx.fill();
  ctx.strokeStyle=t.cA; ctx.lineWidth=3; ctx.stroke();

  // Dots
  for(let i=0;i<N;i++){
    const p=pt(i,R*vals[i]);
    ctx.beginPath(); ctx.arc(p.x,p.y,6,0,Math.PI*2);
    ctx.fillStyle='#111'; ctx.fill();
    ctx.strokeStyle=t.cB; ctx.lineWidth=2.5; ctx.stroke();
  }

  // Labels
  for(let i=0;i<N;i++){
    const p=pt(i,R+26);
    ctx.fillStyle='#111';
    ctx.font='bold 13px "Noto Sans SC",sans-serif';
    ctx.textAlign='center'; ctx.textBaseline='middle';
    ctx.fillText(labels[i],p.x,p.y);
    const vp=pt(i,R*vals[i]-16);
    ctx.fillStyle='#888';
    ctx.font='10px "Space Mono",monospace';
    ctx.fillText(Math.round(vals[i]*100)+'%',vp.x,vp.y);
  }
}

function copyR(){
  const t=T[lastType||calcType()];
  const txt=`我做了「你的人格魅力是哪种？」测试\n结果是 ${t.emoji} ${t.name}「${t.tag}」\n\n${t.quote}\n\n你也来测测？`;
  navigator.clipboard.writeText(txt).then(()=>{
    const b=event.target; const o=b.textContent;
    b.textContent='✅ 已复制！'; setTimeout(()=>b.textContent=o,2000);
  }).catch(()=>alert('请手动复制'));
}

function shareR(){
  const t=T[lastType||calcType()];
  if(navigator.share){
    navigator.share({title:`我的人格魅力是${t.name}`,text:`${t.emoji} ${t.name}——${t.tag}\n\n${t.quote}`,url:location.href});
  }else copyR();
}

function restart(){
  cur=0; sc={E:50,A:50,R:50,L:50}; lastType='';
  show('intro');
}

document.addEventListener('DOMContentLoaded',()=>show('intro'));
</script>
</body>
</html>
