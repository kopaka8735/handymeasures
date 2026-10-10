# handymeasures[index.html](https://github.com/user-attachments/files/33286224/index.html)
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<style>:root{color-scheme:light}body{margin:0}[hidden]{display:none!important}</style>
<title>Handy Measurements Test</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+3:wght@400;600;700&family=Source+Serif+4:wght@600;700&display=swap" rel="stylesheet">
<style>
/* Layout: one narrow column, phone first. Header with a ruler strip, a four-step progress row, one card per step, results as paired bars on a shared scale. */
:root{
  --bg:#EEF3F7;
  --surface:#FFFFFF;
  --fg:#14202E;
  --muted:#4A5A6C;
  --line:#D3DCE6;
  --head-bg:#0E2A47;
  --head-fg:#FFFFFF;
  --head-sub:#C9D8E8;
  --accent:#0B5C57;
  --accent-soft:#E3F1EF;
  --warm:#C2452D;
  --warm-soft:#FBEAE5;
  --before:#E8836A;
  --after:#0B5C57;
  --btn-bg:#0E2A47;
  --btn-fg:#FFFFFF;
  --track:#D7E1EA;
  --display:'Source Serif 4',Georgia,serif;
  --body:'Source Sans 3',system-ui,-apple-system,'Segoe UI',sans-serif;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --bg:#0A1624;--surface:#11243A;--fg:#EAF0F6;--muted:#A9B9CA;--line:#27415C;
    --head-bg:#0E2A47;--head-fg:#FFFFFF;--head-sub:#C9D8E8;
    --accent:#5FC4BB;--accent-soft:#12353A;--warm:#FF9D80;--warm-soft:#3A2420;
    --before:#E8836A;--after:#4DB6AC;--btn-bg:#E8836A;--btn-fg:#14202E;--track:#2B4560;
    color-scheme:dark;
  }
}
:root[data-theme="dark"]{
  --bg:#0A1624;--surface:#11243A;--fg:#EAF0F6;--muted:#A9B9CA;--line:#27415C;
  --head-bg:#0E2A47;--head-fg:#FFFFFF;--head-sub:#C9D8E8;
  --accent:#5FC4BB;--accent-soft:#12353A;--warm:#FF9D80;--warm-soft:#3A2420;
  --before:#E8836A;--after:#4DB6AC;--btn-bg:#E8836A;--btn-fg:#14202E;--track:#2B4560;
  color-scheme:dark;
}
*{box-sizing:border-box}
body{background:var(--bg);color:var(--fg);font-family:var(--body);font-size:18px;line-height:1.45;padding-inline:16px;padding-block:0 40px}
.wrap{max-width:640px;margin-inline:auto;display:flex;flex-direction:column;gap:20px}
header{margin-inline:-16px;background:var(--head-bg);color:var(--head-fg);padding:28px 16px 0}
header .in{max-width:640px;margin-inline:auto;display:flex;flex-direction:column;gap:10px;padding-bottom:22px}
.eyebrow{font-size:13px;font-weight:600;letter-spacing:.14em;text-transform:uppercase;color:var(--head-sub)}
h1{margin:0;font-family:var(--display);font-weight:700;font-size:40px;line-height:1.08;text-wrap:balance}
header p{margin:0;color:var(--head-sub);max-width:34em}
.ruler{height:20px;background-image:repeating-linear-gradient(90deg,#9FB6CC 0,#9FB6CC 2px,transparent 2px,transparent 12px),repeating-linear-gradient(90deg,#FF9D80 0,#FF9D80 3px,transparent 3px,transparent 60px);background-size:100% 10px,100% 20px;background-repeat:no-repeat;background-position:0 100%,0 100%}
.steps{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:8px;margin:0;padding:0;list-style:none}
.steps li{display:flex;flex-direction:column;gap:6px;font-size:13px;font-weight:600;letter-spacing:.04em;color:var(--muted)}
.steps li::before{content:"";height:6px;border-radius:3px;background:var(--track)}
.steps li.done::before,.steps li[aria-current="step"]::before{background:var(--accent)}
.steps li[aria-current="step"]{color:var(--fg)}
.card{background:var(--surface);border:1px solid var(--line);border-radius:16px;padding:22px 18px;display:flex;flex-direction:column;gap:18px}
h2{margin:0;font-family:var(--display);font-weight:700;font-size:28px;line-height:1.15;text-wrap:balance}
.lead{margin:0}
.hint{margin:0;font-size:15px;color:var(--muted)}
.wound{display:flex;flex-direction:column;gap:6px;padding-top:14px;border-top:1px solid var(--line)}
.wound:first-of-type{border-top:0;padding-top:0}
.wound-top{display:flex;justify-content:space-between;align-items:baseline;gap:12px}
.wound-top label{font-weight:700}
output{font-variant-numeric:tabular-nums;font-weight:700;font-size:22px;color:var(--accent)}
input[type=range]{width:100%;height:36px;margin:0;accent-color:var(--accent)}
.scale{display:flex;justify-content:space-between;font-size:13px;color:var(--muted);font-variant-numeric:tabular-nums}
.conf{display:flex;flex-direction:column;gap:8px;border:0;padding:0;margin:0}
.conf legend{font-weight:700;padding:0;margin-bottom:8px}
.pills{display:grid;grid-template-columns:repeat(5,minmax(0,1fr));gap:8px}
.pills input{position:absolute;opacity:0;width:1px;height:1px}
.pills label{display:flex;align-items:center;justify-content:center;min-height:48px;border:2px solid var(--line);border-radius:12px;font-weight:700;font-size:20px;cursor:pointer;background:var(--surface)}
.pills input:checked+label{background:var(--accent);border-color:var(--accent);color:var(--surface)}
.pills input:focus-visible+label{outline:3px solid var(--fg);outline-offset:2px}
.pill-ends{display:flex;justify-content:space-between;font-size:13px;color:var(--muted)}
button{font:inherit;font-weight:700;min-height:52px;padding:0 22px;border-radius:12px;border:0;background:var(--btn-bg);color:var(--btn-fg);cursor:pointer}
button:focus-visible{outline:3px solid var(--fg);outline-offset:3px}
button.ghost{background:transparent;color:var(--fg);border:2px solid var(--line)}
.fw{display:flex;flex-direction:column;gap:8px;background:var(--accent-soft);border-radius:12px;padding:16px}
.fw-top{display:flex;justify-content:space-between;align-items:baseline;gap:12px}
.fw-top label{font-weight:700}
.hand{display:block;width:100%;max-width:340px;height:auto;margin-inline:auto}
.big{display:flex;flex-direction:column;gap:6px;background:var(--accent-soft);border-radius:12px;padding:18px}
.big .nums{font-family:var(--display);font-weight:700;font-size:44px;line-height:1.05;font-variant-numeric:tabular-nums;color:var(--accent);text-wrap:balance}
.big .cap{margin:0;font-size:16px}
.verdict{margin:0;font-size:20px;font-weight:600}
.note{margin:0;padding:14px 16px;border-radius:12px;background:var(--warm-soft);font-size:16px}
.rw{display:flex;flex-direction:column;gap:6px;padding-top:14px;border-top:1px solid var(--line)}
.rw-head{display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap}
.rw-head b{font-size:18px}
.rw-head span{font-variant-numeric:tabular-nums;color:var(--muted);font-size:15px}
.bar-row{display:grid;grid-template-columns:62px minmax(0,1fr);gap:4px 10px;align-items:center}
.bar-row .tag{font-size:13px;font-weight:600;letter-spacing:.04em;color:var(--muted)}
.bar{height:16px;border-radius:8px;background:var(--track);overflow:hidden}
.bar i{display:block;height:100%;border-radius:8px}
.bar-row .val{grid-column:2;font-size:14px;font-variant-numeric:tabular-nums;color:var(--muted);margin-top:-2px}
.legend{display:flex;gap:18px;flex-wrap:wrap;font-size:14px;color:var(--muted)}
.legend span{display:flex;align-items:center;gap:8px}
.legend i{width:16px;height:16px;border-radius:5px;display:inline-block}
.study{font-size:15px;color:var(--muted);margin:0}
.foot{font-size:14px;color:var(--muted);margin:0;text-align:center}
.row2{display:flex;gap:12px;flex-wrap:wrap}
.row2>*{flex:1 1 200px}
@media (prefers-reduced-motion: no-preference){.card{animation:rise .25s ease-out}@keyframes rise{from{opacity:.4;transform:translateY(6px)}to{opacity:1;transform:none}}}
</style>

</head>
<body>
<header>
  <div class="in">
    <div class="eyebrow">Handy Measurements · Companion to the poster</div>
    <h1>Try it yourself</h1>
    <p>Estimate five wounds by eye, then use your own hand as a ruler and see how much your error changes. Takes about two minutes.</p>
  </div>
  <div class="ruler" aria-hidden="true"></div>
</header>

<div class="wrap">
  <ol class="steps" id="steps" aria-label="Progress">
    <li>1 Estimate</li><li>2 Your hand</li><li>3 Re-estimate</li><li>4 Result</li>
  </ol>

  <section class="card" id="s1">
    <h2>Estimate by eye</h2>
    <p class="lead">Look at wounds 1 to 5 on the A4 sheets beside the poster. For each one, slide to the length you think it is. Do not use a ruler.</p>
    <fieldset class="conf">
      <legend>How confident are you at judging wound length?</legend>
      <div class="pills" role="radiogroup">
        <input type="radio" name="conf" id="c1" value="1"><label for="c1">1</label>
        <input type="radio" name="conf" id="c2" value="2"><label for="c2">2</label>
        <input type="radio" name="conf" id="c3" value="3"><label for="c3">3</label>
        <input type="radio" name="conf" id="c4" value="4"><label for="c4">4</label>
        <input type="radio" name="conf" id="c5" value="5"><label for="c5">5</label>
      </div>
      <div class="pill-ends"><span>Not confident</span><span>Very confident</span></div>
    </fieldset>
    <div id="list1"></div>
    <button type="button" id="to2">Next: measure your hand</button>
  </section>

  <section class="card" id="s2" hidden>
    <h2>Measure your hand</h2>
    <p class="lead">Press your index, middle, ring and little fingers together. Measure across all four, at the widest part, with a ruler. You only need to do this once.</p>
    <svg class="hand" viewBox="0 0 400 190" role="img" aria-label="Four fingers held together with a bracket showing their combined width">
      <g fill="#EBC3A5" stroke="#B98A6A" stroke-width="5" stroke-linejoin="round">
        <rect x="70" y="26" width="50" height="104" rx="25"/>
        <rect x="134" y="8" width="50" height="122" rx="25"/>
        <rect x="198" y="18" width="50" height="112" rx="25"/>
        <rect x="262" y="44" width="50" height="86" rx="25"/>
        <rect x="64" y="96" width="254" height="62" rx="26"/>
      </g>
      <path d="M70 172 V184 H312 V172" fill="none" stroke="#0B5C57" stroke-width="5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
    <div class="fw">
      <div class="fw-top"><label for="fw">Four-finger width</label><output id="fwo" for="fw">7.0 cm</output></div>
      <input type="range" id="fw" min="4" max="10" step="0.1" value="7">
      <div class="scale"><span>4</span><span>6</span><span>8</span><span>10 cm</span></div>
    </div>
    <p class="hint">Rulers are hard to find in most clinical areas. In the study, 58.6% of staff rated ruler access as hard. Your hand is always with you.</p>
    <button type="button" id="to3">Next: estimate again</button>
  </section>

  <section class="card" id="s3" hidden>
    <h2>Estimate with your hand</h2>
    <p class="lead">Look at the same five wounds. This time, hold your four fingers against each one and count how many hand-widths long it is. Slide to your count.</p>
    <div id="list3"></div>
    <button type="button" id="to4">See my result</button>
  </section>

  <section class="card" id="s4" hidden>
    <h2>Your result</h2>
    <div class="big">
      <div class="nums" id="nums"></div>
      <p class="cap">Total error across the five wounds, by eye then with your hand.</p>
    </div>
    <p class="verdict" id="verdict"></p>
    <div class="legend"><span><i style="background:var(--before)"></i>By eye</span><span><i style="background:var(--after)"></i>With your hand</span></div>
    <div id="rows"></div>
    <p class="study">In the study of 70 clinicians, the median total error fell from 6.60 cm to 2.95 cm, a 55.3% reduction. 60 of 70 improved.</p>
    <p class="note" id="confnote" hidden></p>
    <div class="row2"><button type="button" id="again" class="ghost">Start again</button></div>
  </section>

  <p class="foot">Nothing you enter here is saved or sent anywhere.</p>
</div>

<script>
(function(){
  var TRUE=[1.6,4.2,6.3,7.9,16.1];
  var $=function(id){return document.getElementById(id)};
  var f1=function(n){return n.toFixed(1)};

  function build1(){
    $('list1').innerHTML=TRUE.map(function(_,i){
      var n=i+1;
      return '<div class="wound"><div class="wound-top"><label for="e'+n+'">Wound '+n+'</label><output id="o'+n+'" for="e'+n+'">5.0 cm</output></div>'+
        '<input type="range" id="e'+n+'" min="0" max="20" step="0.1" value="5">'+
        '<div class="scale"><span>0</span><span>5</span><span>10</span><span>15</span><span>20 cm</span></div></div>';
    }).join('');
    TRUE.forEach(function(_,i){
      var n=i+1;
      $('e'+n).addEventListener('input',function(){$('o'+n).textContent=f1(parseFloat(this.value))+' cm'});
    });
  }
  function fw(){return parseFloat($('fw').value)}
  function refresh3(){
    TRUE.forEach(function(_,i){
      var n=i+1, w=parseFloat($('h'+n).value);
      $('p'+n).textContent=w.toFixed(2)+' hands = '+f1(w*fw())+' cm';
    });
  }
  function build3(){
    $('list3').innerHTML=TRUE.map(function(_,i){
      var n=i+1;
      return '<div class="wound"><div class="wound-top"><label for="h'+n+'">Wound '+n+'</label><output id="p'+n+'" for="h'+n+'"></output></div>'+
        '<input type="range" id="h'+n+'" min="0" max="4" step="0.05" value="1">'+
        '<div class="scale"><span>0</span><span>1</span><span>2</span><span>3</span><span>4 hands</span></div></div>';
    }).join('');
    TRUE.forEach(function(_,i){
      $('h'+(i+1)).addEventListener('input',refresh3);
    });
  }
  function go(n){
    ['s1','s2','s3','s4'].forEach(function(id,k){$(id).hidden=(k!==n-1)});
    Array.prototype.forEach.call($('steps').children,function(li,k){
      li.className=(k<n-1)?'done':'';
      if(k===n-1){li.setAttribute('aria-current','step')}else{li.removeAttribute('aria-current')}
    });
    window.scrollTo(0,0);
  }
  function signed(d){
    if(d>0.05){return 'over by '+f1(d)+' cm'}
    if(d<-0.05){return 'under by '+f1(-d)+' cm'}
    return 'spot on';
  }
  function result(){
    var w=fw(), e1=[], e2=[], g1=[], g2=[];
    TRUE.forEach(function(t,i){
      var a=parseFloat($('e'+(i+1)).value), b=parseFloat($('h'+(i+1)).value)*w;
      g1.push(a); g2.push(b); e1.push(Math.abs(a-t)); e2.push(Math.abs(b-t));
    });
    var s1=e1.reduce(function(a,b){return a+b},0), s2=e2.reduce(function(a,b){return a+b},0);
    var mx=Math.max.apply(null,e1.concat(e2).concat([0.5]));
    $('nums').textContent=f1(s1)+' → '+f1(s2)+' cm';
    var v;
    if(s2<s1-0.05){
      v='Your hand cut your error by '+Math.round((s1-s2)/s1*100)+'%.';
    }else if(s2>s1+0.05){
      v='Your second round was '+Math.round((s2-s1)/Math.max(s1,0.1)*100)+'% less accurate. That happened to 9 of the 70 people in the study.';
    }else{
      v='Your two rounds scored the same. That happened to 1 of the 70 people in the study.';
    }
    $('verdict').textContent=v;
    $('rows').innerHTML=TRUE.map(function(t,i){
      var p1=Math.max(e1[i]/mx*100,2), p2=Math.max(e2[i]/mx*100,2);
      return '<div class="rw"><div class="rw-head"><b>Wound '+(i+1)+'</b><span>True length '+f1(t)+' cm</span></div>'+
        '<div class="bar-row"><span class="tag">By eye</span><div class="bar"><i style="width:'+p1+'%;background:var(--before)"></i></div><span class="val">You said '+f1(g1[i])+' cm, '+signed(g1[i]-t)+'</span></div>'+
        '<div class="bar-row"><span class="tag">Hand</span><div class="bar"><i style="width:'+p2+'%;background:var(--after)"></i></div><span class="val">You said '+f1(g2[i])+' cm, '+signed(g2[i]-t)+'</span></div></div>';
    }).join('');
    var c=document.querySelector('input[name="conf"]:checked'), note=$('confnote');
    if(c){
      note.hidden=false;
      note.textContent='You rated your confidence '+c.value+' out of 5 before starting. In the study, neither seniority nor confidence predicted accuracy (confidence vs error: ρ = −0.12).';
    }else{note.hidden=true}
    go(4);
  }
  function init(){
    build1(); build3();
    var r=document.querySelector('input[name="conf"]:checked'); if(r){r.checked=false}
    $('fw').value=7; $('fwo').textContent='7.0 cm';
    refresh3(); go(1);
  }
  $('fw').addEventListener('input',function(){$('fwo').textContent=f1(fw())+' cm'});
  $('to2').addEventListener('click',function(){go(2)});
  $('to3').addEventListener('click',function(){refresh3();go(3)});
  $('to4').addEventListener('click',result);
  $('again').addEventListener('click',init);
  init();
})();
</script>

</body>
</html>
