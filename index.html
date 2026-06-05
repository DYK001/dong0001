<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>EconView - AI 경제 브리핑</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/18.2.0/umd/react.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/18.2.0/umd/react-dom.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/7.23.5/babel.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{background:#F7F8FC;font-family:'Noto Sans KR','Malgun Gothic',sans-serif;color:#1A202C;overflow-x:hidden}
button,input{font-family:'Noto Sans KR','Malgun Gothic',sans-serif}
::-webkit-scrollbar{width:6px;height:6px}
::-webkit-scrollbar-track{background:#F1F5F9}
::-webkit-scrollbar-thumb{background:#CBD5E1;border-radius:3px}

/* ── 핵심 애니메이션 키프레임 ── */
@keyframes fadeInUp     {from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeInDown   {from{opacity:0;transform:translateY(-16px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeInLeft   {from{opacity:0;transform:translateX(-20px)}to{opacity:1;transform:translateX(0)}}
@keyframes fadeInRight  {from{opacity:0;transform:translateX(20px)}to{opacity:1;transform:translateX(0)}}
@keyframes scaleIn      {from{opacity:0;transform:scale(0.93)}to{opacity:1;transform:scale(1)}}
@keyframes pageIn       {from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:translateY(0)}}
@keyframes float        {0%,100%{transform:translateY(0)}50%{transform:translateY(-7px)}}
@keyframes floatSlow    {0%,100%{transform:translateY(0) rotate(0deg)}50%{transform:translateY(-10px) rotate(2deg)}}
@keyframes pulse        {0%,100%{opacity:1;transform:scale(1)}50%{opacity:.5;transform:scale(.85)}}
@keyframes ringPulse    {0%{box-shadow:0 0 0 0 rgba(5,150,105,.5)}70%{box-shadow:0 0 0 9px rgba(5,150,105,0)}100%{box-shadow:0 0 0 0 rgba(5,150,105,0)}}
@keyframes shimmer      {0%{transform:translateX(-100%)}100%{transform:translateX(100%)}}
@keyframes marquee      {0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
@keyframes gradientMove {0%{background-position:0% 50%}50%{background-position:100% 50%}100%{background-position:0% 50%}}
@keyframes barFill      {from{width:0;opacity:0}to{opacity:1}}
@keyframes spin         {from{transform:rotate(0)}to{transform:rotate(360deg)}}
@keyframes ld           {0%{left:-40%}100%{left:100%}}
@keyframes popIn        {0%{transform:scale(0.6);opacity:0}70%{transform:scale(1.08)}100%{transform:scale(1);opacity:1}}
@keyframes ripple       {from{transform:scale(0);opacity:.5}to{transform:scale(3);opacity:0}}
@keyframes numberPop    {0%{transform:scale(1)}40%{transform:scale(1.12)}100%{transform:scale(1)}}
@keyframes glowPulse    {0%,100%{box-shadow:0 0 0 0 rgba(37,99,235,0)}50%{box-shadow:0 0 16px 2px rgba(37,99,235,.18)}}
@keyframes slideTab     {from{width:0;opacity:0}to{opacity:1}}
@keyframes heroGrad     {0%{background-position:0% 50%}50%{background-position:100% 50%}100%{background-position:0% 50%}}
@keyframes dotBounce    {0%,100%{transform:translateY(0)}50%{transform:translateY(-5px)}}
@keyframes shake        {0%,100%{transform:translateX(0)}25%{transform:translateX(-4px)}75%{transform:translateX(4px)}}

/* ── 유틸 클래스 ── */
.card-hover{transition:transform .22s cubic-bezier(.34,1.56,.64,1),box-shadow .22s ease,border-color .22s ease}
.card-hover:hover{transform:translateY(-4px) scale(1.01)}
.btn-press:active{transform:scale(.95)!important}
.fade-stagger>*{animation:fadeInUp .4s ease both}
</style>
</head>
<body>
<div id="root"></div>
<script type="text/babel">

// ══════════════════════════════════════
//  ⚠️  API 키를 아래에 입력하세요
// ══════════════════════════════════════
const API_KEY = "여기에_API_키_입력";
// ══════════════════════════════════════

const { useState, useEffect, useCallback, useRef } = React;

/* ── 색상 토큰 ─────────────────────────────────────────────── */
const C = {
  bg:"#F7F8FC", white:"#FFFFFF", light:"#F1F5F9", hov:"#F0F4FF",
  border:"#E2E8F0", text:"#1A202C", sub:"#4A5568", muted:"#94A3B8",
  blue:"#2563EB", blueSoft:"#EFF6FF", blueLight:"#DBEAFE",
  green:"#059669", greenSoft:"#ECFDF5",
  red:"#DC2626", redSoft:"#FEF2F2",
  yellow:"#D97706", yellowSoft:"#FFFBEB",
  purple:"#7C3AED", purpleSoft:"#F5F3FF",
  teal:"#0891B2", tealSoft:"#ECFEFF",
  orange:"#EA580C", orangeSoft:"#FFF7ED",
  shadow:"0 1px 3px rgba(0,0,0,.08),0 1px 2px rgba(0,0,0,.04)",
  shadowMd:"0 4px 16px rgba(0,0,0,.09),0 2px 4px rgba(0,0,0,.04)",
  shadowLg:"0 12px 32px rgba(0,0,0,.12),0 4px 8px rgba(0,0,0,.04)",
};
const CATS=["전체","금리","환율","물가","주식","부동산","글로벌경제","정책·규제"];
const CAT_CLR={금리:C.yellow,환율:C.teal,물가:C.red,주식:C.green,부동산:C.purple,글로벌경제:C.blue,"정책·규제":C.orange};
const CAT_SOFT={금리:C.yellowSoft,환율:C.tealSoft,물가:C.redSoft,주식:C.greenSoft,부동산:C.purpleSoft,글로벌경제:C.blueSoft,"정책·규제":C.orangeSoft};
const CAT_ICON={금리:"💰",환율:"💱",물가:"🛒",주식:"📈",부동산:"🏠",글로벌경제:"🌍","정책·규제":"⚖️"};
const BTOPICS=["📈 오늘의 종합 경제 브리핑","💰 금리 & 통화정책","💱 환율 최신 동향","📊 주식시장 분석","🏠 부동산 시장 현황","🛒 물가 & 인플레이션","🌍 글로벌 경제 이슈"];

const DEFAULT_IND={usdkrw:"1,371",usdkrw_chg:"+0.32",jpykrw:"9.15",jpykrw_chg:"-0.08",eurkrw:"1,497",eurkrw_chg:"+0.51",cnykrw:"188.4",cnykrw_chg:"+0.12",base_rate:"3.50",cpi:"2.4",cpi_chg:"-0.1",kospi:"2,634",kospi_chg:"-0.87",kosdaq:"854",kosdaq_chg:"+0.23",wti:"72.45",wti_chg:"+1.20",gold:"3,312",gold_chg:"+0.48",btc:"103,500",btc_chg:"+2.14",sp500:"5,820",sp500_chg:"-0.31",nasdaq:"18,740",nasdaq_chg:"-0.52",nikkei:"38,240",nikkei_chg:"+0.74",time:"--:--",isDefault:true};
const DEFAULT_NEWS=[
  {id:1,cat:"금리",src:"한국경제",time:"1시간 전",title:"연준 매파 발언에 금리 인하 기대 후퇴…국채금리 상승",preview:"연준 위원들의 잇따른 매파적 발언으로 9월 금리 인하 기대감이 약화됐습니다. 10년물 미국 국채금리는 4.3%대로 상승하며 글로벌 채권시장 변동성이 확대되고 있습니다. 한국은행도 당분간 현행 3.5% 기준금리를 유지할 것으로 예상됩니다.",tags:["금리","연준","국채"],views:12542},
  {id:2,cat:"환율",src:"매일경제",time:"2시간 전",title:"원·달러 환율 1,370원대 돌파…달러 강세 지속",preview:"달러 인덱스가 104선을 상회하며 원화 가치가 약세를 보이고 있습니다. 수출 기업들의 환차익 기대감이 높아지는 반면 수입 물가 상승 우려도 커지고 있습니다.",tags:["환율","달러","외환시장"],views:9873},
  {id:3,cat:"주식",src:"서울경제",time:"3시간 전",title:"코스피, 외국인 매도 속 2,630선 하락 마감",preview:"외국인 투자자들의 순매도세가 이어지며 코스피가 2,630선으로 내려앉았습니다. 반도체·2차전지 대형주 중심의 하락이 지수를 끌어내렸으며 개인의 저가 매수가 낙폭을 일부 제한했습니다.",tags:["코스피","외국인","반도체"],views:8621},
  {id:4,cat:"물가",src:"헤럴드경제",time:"4시간 전",title:"소비자물가 2.4% 상승…농산물·서비스 가격 여전히 불안",preview:"5월 소비자물가 상승률이 전년 동월 대비 2.4%를 기록하며 두 달 연속 2%대를 유지했습니다. 채소류 가격은 안정됐으나 외식·개인서비스 물가가 여전히 높은 수준입니다.",tags:["물가","CPI","소비자물가"],views:6114},
  {id:5,cat:"부동산",src:"조선비즈",time:"5시간 전",title:"서울 아파트값 4주 연속 상승…강남 재건축 단지 주도",preview:"서울 아파트 매매가격이 4주 연속 상승하며 상승폭이 점차 확대되는 추세입니다. 강남구 재건축 단지와 마포·용산 등 핵심 입지를 중심으로 매수 문의가 늘고 있습니다.",tags:["부동산","아파트","서울"],views:5882},
  {id:6,cat:"글로벌경제",src:"이데일리",time:"6시간 전",title:"미·중 무역갈등 재점화…반도체 수출 규제 추가 가능성",preview:"미국 정부가 중국에 대한 반도체 장비 수출 규제를 추가로 강화하는 방안을 검토 중인 것으로 알려졌습니다. 삼성전자·SK하이닉스 등 국내 반도체 기업들의 불확실성이 커지고 있습니다.",tags:["미중갈등","반도체","수출규제"],views:4997},
  {id:7,cat:"정책·규제",src:"한국경제",time:"7시간 전",title:"금융당국, 가계대출 증가세에 DSR 규제 강화 검토",preview:"금융위원회가 최근 빠르게 늘고 있는 가계대출을 억제하기 위해 DSR 기준을 강화하는 방안을 논의 중입니다. 은행권 주택담보대출 심사가 까다로워질 전망입니다.",tags:["DSR","가계대출","금융규제"],views:3741},
];

/* ── API ─────────────────────────────────────────────────────── */
function parseJ(r){if(!r)return null;try{const c=r.replace(/```json\s*/g,"").replace(/```\s*/g,"").trim();const m=c.match(/([\[{][\s\S]*[\]}])/s);return JSON.parse(m?m[1]:c)}catch{return null}}
async function aiFast(sys,usr){if(!API_KEY||API_KEY==="여기에_API_키_입력")return"";try{const r=await fetch("https://api.anthropic.com/v1/messages",{method:"POST",headers:{"Content-Type":"application/json","x-api-key":API_KEY,"anthropic-version":"2023-06-01","anthropic-dangerous-direct-browser-access":"true"},body:JSON.stringify({model:"claude-haiku-4-5-20251001",max_tokens:1500,system:sys,messages:[{role:"user",content:usr}]})});if(!r.ok)return"";const d=await r.json();return d.content?.filter(x=>x.type==="text").map(x=>x.text).join("")||""}catch{return""}}
async function aiSearch(sys,usr){if(!API_KEY||API_KEY==="여기에_API_키_입력")return"";try{const r=await fetch("https://api.anthropic.com/v1/messages",{method:"POST",headers:{"Content-Type":"application/json","x-api-key":API_KEY,"anthropic-version":"2023-06-01","anthropic-dangerous-direct-browser-access":"true"},body:JSON.stringify({model:"claude-sonnet-4-6",max_tokens:2000,system:sys,tools:[{type:"web_search_20250305",name:"web_search"}],messages:[{role:"user",content:usr}]})});if(r.ok){const d=await r.json();const t=d.content?.filter(x=>x.type==="text").map(x=>x.text).join("")||"";if(t.trim())return t}}catch{}return aiFast(sys,usr)}
async function fetchRealRates(){try{const r=await fetch("https://open.er-api.com/v6/latest/USD");const d=await r.json();if(d.rates?.KRW){const{KRW:k,JPY:j,EUR:e,CNY:c}=d.rates;const n=new Date();return{usdkrw:k.toFixed(1),jpykrw:(k/j*100).toFixed(2),eurkrw:(k/e).toFixed(1),cnykrw:(k/c).toFixed(2),time:`${n.getHours()}:${String(n.getMinutes()).padStart(2,"0")}`}}}catch{}return null}
async function fetchBTC(){try{const r=await fetch("https://api.coinbase.com/v2/prices/BTC-USD/spot");const d=await r.json();if(d.data?.amount)return Number(d.data.amount).toLocaleString()}catch{}return null}
async function loadIndicators(){const[rates,btc]=await Promise.all([fetchRealRates(),fetchBTC()]);const raw=await aiFast("Return ONLY valid JSON object. No markdown.",`2026년 5월 한국 금융시장 기반 JSON:\n{"kospi":"2634","kospi_chg":"-0.87","kosdaq":"854","kosdaq_chg":"+0.23","wti":"72.45","wti_chg":"+1.20","gold":"3312","gold_chg":"+0.48","sp500":"5820","sp500_chg":"-0.31","nasdaq":"18740","nasdaq_chg":"-0.52","nikkei":"38240","nikkei_chg":"+0.74","base_rate":"3.50","cpi":"2.4","cpi_chg":"-0.1"}`);const ai=parseJ(raw)||{};const n=new Date();return{...DEFAULT_IND,...ai,...(rates||{}),...(btc?{btc}:{}),time:rates?.time||`${n.getHours()}:${String(n.getMinutes()).padStart(2,"0")}`,isDefault:false}}
async function loadNews(){const raw=await aiFast("Return ONLY valid JSON array. No markdown.",`2026년 5월 한국 경제 뉴스 7개:\n[{"id":1,"cat":"금리","src":"한국경제","time":"30분 전","title":"뉴스 제목","preview":"2-3문장 요약","tags":["태그1","태그2","태그3"],"views":12542}]\n카테고리: 금리,환율,물가,주식,부동산,글로벌경제,정책·규제. 한국어로.`);return parseJ(raw)||[]}
async function loadSNS(){const raw=await aiFast("Return ONLY valid JSON array. No markdown.",`2026년 5월 한국 경제 SNS 분석 4개:\n[{"topic":"주제","pos":28,"neg":57,"neu":15,"topTweets":["반응1","반응2","반응3"],"summary":"요약 2문장","trend":"up","keywords":["키1","키2","키3"]}]\n한국어로.`);return parseJ(raw)||[]}
async function summarize1(a){return aiFast("Korean economic analyst. Be concise.",`다음 기사를 2-3문장으로 쉽게 요약하세요. 어려운 용어는 괄호로 설명하세요.\n제목: ${a.title}\n내용: ${a.preview}`)}
async function getBriefing(topic){const clean=topic.replace(/^\S+\s/,"");return aiSearch("당신은 한국 경제 전문 브리핑 AI입니다. 반드시 한국어로, 쉽고 친절하게 설명하세요.",`"${clean}"에 대해 2026년 5월 기준 경제 브리핑을 작성하세요.\n\n**📰 지금 무슨 일이?**\n현재 상황 2~3문장.\n\n**🤔 왜 중요한가요?**\n중요한 이유 2~3문장.\n\n**💼 내 생활에 미치는 영향**\n- 직장인: (1문장)\n- 소비자: (1문장)\n- 투자자: (1문장)\n\n**📚 핵심 용어 정리**\n어려운 용어 2~3개 쉽게 설명.\n\n**🔮 앞으로의 전망**\n단기 전망 2문장.\n\n한국어로, 쉬운 언어로 작성하세요.`)}

/* ── 커스텀 훅 ───────────────────────────────────────────────── */
// 숫자 카운트업 훅
function useCountUp(targetStr, duration=1400, enabled=true) {
  const [val, setVal] = useState(0);
  useEffect(() => {
    if (!enabled || !targetStr) return;
    const target = parseFloat(String(targetStr).replace(/[^-\d.]/g,""));
    if (isNaN(target)) return;
    const start = performance.now();
    let raf;
    const animate = (now) => {
      const p = Math.min((now - start) / duration, 1);
      const ease = 1 - Math.pow(1-p, 3);
      setVal(target * ease);
      if (p < 1) raf = requestAnimationFrame(animate);
      else setVal(target);
    };
    raf = requestAnimationFrame(animate);
    return () => cancelAnimationFrame(raf);
  }, [targetStr, enabled]);
  return val;
}

// 마운트 시 트리거 훅
function useMount() {
  const [mounted, setMounted] = useState(false);
  useEffect(() => { const t = setTimeout(() => setMounted(true), 50); return () => clearTimeout(t); }, []);
  return mounted;
}

/* ── 스켈레톤 ────────────────────────────────────────────────── */
function Sk({w="100%",h=14,r=6,mb=0}) {
  return <div style={{width:w,height:h,borderRadius:r,marginBottom:mb,background:"#F1F5F9",overflow:"hidden",position:"relative",flexShrink:0}}>
    <div style={{position:"absolute",inset:0,background:"linear-gradient(90deg,transparent,rgba(255,255,255,.8),transparent)",animation:"shimmer 1.5s infinite"}}/>
  </div>;
}

/* ── 공통 UI ─────────────────────────────────────────────────── */
function CatBadge({cat,size=11,animated=false}) {
  const bg=CAT_SOFT[cat]||C.blueSoft, color=CAT_CLR[cat]||C.blue;
  return <span style={{fontSize:size,fontWeight:700,padding:"3px 8px",borderRadius:99,background:bg,color,letterSpacing:".2px",display:"inline-block",animation:animated?"popIn .4s cubic-bezier(.34,1.56,.64,1) both":undefined}}>{cat}</span>;
}

function LiveDot({color=C.green,ring=false}) {
  return <span style={{width:7,height:7,borderRadius:"50%",background:color,display:"inline-block",animation:ring?"ringPulse 2s infinite":"pulse 1.8s infinite",flexShrink:0}}/>;
}

function ApiKeyBanner() {
  const [visible, setVisible] = useState(true);
  if (!visible || (API_KEY && API_KEY !== "여기에_API_키_입력")) return null;
  return <div style={{background:"#FFFBEB",border:"1px solid #FDE68A",borderRadius:12,padding:"12px 16px",marginBottom:16,display:"flex",gap:10,alignItems:"flex-start",animation:"fadeInDown .4s ease"}}>
    <span style={{fontSize:18,flexShrink:0,animation:"shake 1s ease .5s both"}}>⚠️</span>
    <div style={{flex:1}}>
      <div style={{fontSize:13,fontWeight:700,color:"#92400E",marginBottom:2}}>API 키 미설정</div>
      <div style={{fontSize:12,color:"#78350F"}}>파일 상단 <code style={{background:"#FEF3C7",padding:"1px 5px",borderRadius:4,color:"#92400E"}}>API_KEY</code> 변수에 Anthropic API 키를 입력해야 AI 기능이 작동합니다.</div>
    </div>
    <button onClick={()=>setVisible(false)} style={{background:"none",border:"none",color:"#92400E",cursor:"pointer",fontSize:16,lineHeight:1}}>✕</button>
  </div>;
}

/* ── 자동 스크롤 티커 ─────────────────────────────────────────── */
function Ticker({ind}) {
  const items=[
    {l:"USD/KRW",v:ind.usdkrw,c:ind.usdkrw_chg},{l:"EUR/KRW",v:ind.eurkrw,c:ind.eurkrw_chg},
    {l:"JPY/KRW",v:ind.jpykrw,c:ind.jpykrw_chg},{l:"KOSPI",v:ind.kospi,c:ind.kospi_chg},
    {l:"KOSDAQ",v:ind.kosdaq,c:ind.kosdaq_chg},{l:"S&P500",v:ind.sp500,c:ind.sp500_chg},
    {l:"WTI",v:`$${ind.wti}`,c:ind.wti_chg},{l:"Gold",v:`$${ind.gold}`,c:ind.gold_chg},
    {l:"BTC",v:`$${ind.btc}`,c:ind.btc_chg},{l:"Nikkei",v:ind.nikkei,c:ind.nikkei_chg},
  ];
  const tickerItem = (item, key) => {
    const n=parseFloat(String(item.c||"0").replace(/[^-\d.]/g,""));
    const col=n>0?"#FF6B6B":n<0?"#74C0FC":"#ADB5BD";
    return <div key={key} style={{display:"flex",gap:8,alignItems:"center",flexShrink:0,padding:"0 16px",borderRight:"1px solid rgba(255,255,255,.1)"}}>
      <span style={{fontSize:10,color:"#93B4D4",fontWeight:700,letterSpacing:".5px",textTransform:"uppercase"}}>{item.l}</span>
      <span style={{fontSize:12,fontWeight:700,color:ind.isDefault?"#6C8EAD":"#FFF"}}>{item.v}</span>
      <span style={{fontSize:10,color:col,fontWeight:700,padding:"1px 5px",borderRadius:4,background:`${col}22`}}>{n>0?"▲":n<0?"▼":""}{Math.abs(n).toFixed(2)}%</span>
    </div>;
  };
  return <div style={{background:"#1E3A5F",overflow:"hidden",height:36,display:"flex",alignItems:"center",position:"relative"}}>
    <div style={{display:"flex",animation:"marquee 30s linear infinite",width:"max-content"}}>
      {items.map((item,i)=>tickerItem(item,`a${i}`))}
      {items.map((item,i)=>tickerItem(item,`b${i}`))}
    </div>
    <div style={{position:"absolute",right:0,width:80,height:"100%",background:"linear-gradient(90deg,transparent,#1E3A5F)",pointerEvents:"none"}}/>
  </div>;
}

/* ── 기사 카드 ───────────────────────────────────────────────── */
function ArticleCard({a, onSum, summaries, sumLoading, index=0}) {
  const [hov,setHov]=useState(false);
  const [clicked,setClicked]=useState(false);
  const loading=sumLoading===a.id, sum=summaries[a.id];
  const accentColor=CAT_CLR[a.cat]||C.blue;

  const handleClick = () => { setClicked(true); setTimeout(()=>setClicked(false),300); };

  return <div
    onMouseEnter={()=>setHov(true)} onMouseLeave={()=>setHov(false)}
    onClick={handleClick}
    className="card-hover"
    style={{
      background:C.white, borderRadius:14, overflow:"hidden", cursor:"pointer",
      boxShadow:hov?C.shadowLg:C.shadow,
      border:`1.5px solid ${hov?"#BFDBFE":C.border}`,
      transform:clicked?"scale(.98)":hov?"translateY(-4px) scale(1.01)":"translateY(0) scale(1)",
      transition:"all .22s cubic-bezier(.34,1.56,.64,1)",
      animation:`fadeInUp .45s ease ${index*0.07}s both`,
    }}>
    {/* 상단 컬러 바 – 호버 시 그라디언트 이동 */}
    <div style={{height:5,background:`linear-gradient(90deg,${accentColor},${accentColor}88,${accentColor}44)`,backgroundSize:"200% 100%",animation:hov?"gradientMove 1.5s ease infinite":undefined,transition:"background .3s"}}/>
    <div style={{padding:"14px 18px"}}>
      <div style={{display:"flex",gap:8,alignItems:"center",marginBottom:10,flexWrap:"wrap"}}>
        <CatBadge cat={a.cat} animated/>
        <span style={{fontSize:11,color:C.muted,fontWeight:500}}>{a.src}</span>
        <span style={{fontSize:11,color:C.border}}>•</span>
        <span style={{fontSize:11,color:C.muted}}>{a.time}</span>
        <span style={{marginLeft:"auto",fontSize:11,color:C.muted,transition:"color .2s",color:hov?C.sub:C.muted}}>👁 {(a.views||0).toLocaleString()}</span>
      </div>
      <div style={{fontSize:15,fontWeight:700,color:C.text,marginBottom:8,lineHeight:1.5,transition:"color .2s",color:hov?accentColor:C.text}}>{a.title}</div>
      {!sum&&!loading&&<div style={{fontSize:13,color:C.sub,lineHeight:1.75,marginBottom:12}}>{a.preview}</div>}
      {loading&&<div style={{marginBottom:12,display:"flex",flexDirection:"column",gap:7}}><Sk h={13}/><Sk h={13} w="85%"/><Sk h={13} w="65%"/></div>}
      {sum&&!loading&&<div style={{background:C.blueSoft,border:`1px solid ${C.blueLight}`,borderLeft:`3px solid ${C.blue}`,borderRadius:"0 10px 10px 0",padding:"10px 14px",marginBottom:12,animation:"scaleIn .3s ease"}}>
        <div style={{fontSize:10,color:C.blue,fontWeight:700,marginBottom:5,letterSpacing:".5px",textTransform:"uppercase"}}>✦ AI 요약</div>
        <div style={{fontSize:13,color:"#1E40AF",lineHeight:1.75}}>{sum}</div>
      </div>}
      <div style={{display:"flex",justifyContent:"space-between",alignItems:"center"}}>
        <div style={{display:"flex",gap:6,flexWrap:"wrap"}}>
          {(a.tags||[]).slice(0,3).map((t,i)=><span key={t} style={{fontSize:11,padding:"2px 8px",borderRadius:99,background:C.light,color:C.sub,fontWeight:500,transition:"all .2s",animation:`fadeInUp .3s ease ${i*.06}s both`}}>#{t}</span>)}
        </div>
        <button onClick={e=>{e.stopPropagation();onSum(a)}} disabled={loading||!!sum}
          className="btn-press"
          style={{fontSize:11,fontWeight:700,padding:"6px 16px",borderRadius:99,border:"none",background:sum?C.greenSoft:loading?C.light:C.blue,color:sum?C.green:loading?C.muted:"#FFF",cursor:loading||sum?"default":"pointer",transition:"all .2s",boxShadow:sum||loading?"none":"0 3px 8px rgba(37,99,235,.3)",position:"relative",overflow:"hidden"}}>
          {loading?"분석 중…":sum?"✓ 요약 완료":"AI 요약"}
        </button>
      </div>
    </div>
  </div>;
}

/* ── 히어로 카드 ─────────────────────────────────────────────── */
function HeroCard({article}) {
  const mounted = useMount();
  const ac = article?(CAT_CLR[article.cat]||C.blue):C.blue;
  const sf = article?(CAT_SOFT[article.cat]||C.blueSoft):C.blueSoft;
  return <div style={{background:C.white,borderRadius:18,overflow:"hidden",boxShadow:C.shadowMd,border:`1.5px solid ${C.border}`,animation:mounted?"scaleIn .5s cubic-bezier(.34,1.56,.64,1) both":undefined}}>
    <div style={{height:7,background:`linear-gradient(90deg,${ac},${ac}88,transparent)`,backgroundSize:"200% 100%",animation:"gradientMove 4s ease infinite"}}/>
    <div style={{padding:"28px 32px",background:`linear-gradient(135deg,${sf}70 0%,#FFF 60%)`}}>
      {!article?<div style={{display:"flex",flexDirection:"column",gap:12}}><Sk w="20%" h={20} r={99}/><Sk h={26} w="75%" r={8}/><Sk h={14}/><Sk h={14} w="85%"/></div>:
      <div style={{animation:"fadeInUp .5s ease both"}}>
        <div style={{display:"flex",gap:10,alignItems:"center",marginBottom:14}}>
          <span style={{fontSize:10,fontWeight:800,padding:"5px 12px",borderRadius:99,background:ac,color:"#FFF",letterSpacing:".5px",textTransform:"uppercase",boxShadow:`0 3px 10px ${ac}44`,animation:"popIn .5s cubic-bezier(.34,1.56,.64,1) .1s both"}}>⭐ 헤드라인</span>
          <CatBadge cat={article.cat} animated/>
          <span style={{fontSize:11,color:C.muted}}>{article.src} · {article.time}</span>
        </div>
        <div style={{fontSize:22,fontWeight:800,color:C.text,lineHeight:1.45,marginBottom:12,maxWidth:680,animation:"fadeInUp .4s ease .1s both"}}>{article.title}</div>
        <div style={{fontSize:14,color:C.sub,lineHeight:1.8,maxWidth:640,marginBottom:16,animation:"fadeInUp .4s ease .15s both"}}>{article.preview}</div>
        <div style={{display:"flex",gap:8,flexWrap:"wrap"}}>
          {(article.tags||[]).map((t,i)=><span key={t} style={{fontSize:12,padding:"4px 14px",borderRadius:99,background:C.light,color:C.sub,fontWeight:500,animation:`fadeInUp .3s ease ${.2+i*.05}s both`}}>#{t}</span>)}
        </div>
      </div>}
    </div>
  </div>;
}

/* ── 카테고리 네비 ────────────────────────────────────────────── */
function CatNav({cat,setCat,news}) {
  return <div style={{background:C.white,borderRadius:14,border:`1px solid ${C.border}`,overflow:"hidden",boxShadow:C.shadow,animation:"fadeInLeft .4s ease .1s both"}}>
    <div style={{padding:"12px 16px 10px",borderBottom:`1px solid ${C.border}`,background:"#F8FAFC"}}>
      <div style={{fontSize:10,fontWeight:800,color:C.muted,letterSpacing:".8px",textTransform:"uppercase"}}>카테고리</div>
    </div>
    {CATS.map((c,i)=>{
      const active=cat===c, ac=CAT_CLR[c]||C.blue, sf=CAT_SOFT[c]||C.blueSoft;
      const count=c==="전체"?(news||[]).length:(news||[]).filter(a=>a.cat===c).length;
      return <button key={c} onClick={()=>setCat(c)}
        style={{display:"flex",justifyContent:"space-between",alignItems:"center",width:"100%",padding:"9px 16px",border:"none",borderLeft:`3px solid ${active?ac:"transparent"}`,background:active?sf:"transparent",color:active?ac:C.sub,cursor:"pointer",fontSize:13,fontWeight:active?700:400,transition:"all .2s",textAlign:"left",animation:`fadeInLeft .35s ease ${i*.04}s both`}}>
        <div style={{display:"flex",gap:8,alignItems:"center"}}><span style={{transition:"transform .2s",transform:active?"scale(1.2)":"scale(1)"}}>{c==="전체"?"🗂️":CAT_ICON[c]||"📰"}</span><span>{c}</span></div>
        <span style={{fontSize:11,padding:"1px 7px",borderRadius:99,background:active?`${ac}22`:"#F1F5F9",color:active?ac:C.muted,fontWeight:600,transition:"all .2s"}}>{count}</span>
      </button>;
    })}
    <div style={{borderTop:`1px solid ${C.border}`,padding:"12px 16px 10px"}}>
      <div style={{fontSize:10,fontWeight:800,color:C.muted,letterSpacing:".8px",textTransform:"uppercase",marginBottom:6}}>기간</div>
      {["전체","오늘","3일","7일","30일"].map((t,i)=><button key={t} style={{display:"block",width:"100%",padding:"6px 10px",border:"none",background:t==="전체"?C.blueSoft:"transparent",color:t==="전체"?C.blue:C.muted,cursor:"pointer",fontSize:12,textAlign:"left",borderRadius:8,fontWeight:t==="전체"?600:400,transition:"all .2s",animation:`fadeInLeft .3s ease ${.4+i*.04}s both`}}>{t}</button>)}
    </div>
  </div>;
}

/* ── 우측 패널 ───────────────────────────────────────────────── */
function RightPanel({ind,news}) {
  const mounted = useMount();
  const top=[...(news||[])].sort((a,b)=>(b.views||0)-(a.views||0)).slice(0,5);
  const indItems=[{l:"USD/KRW",v:`₩${ind.usdkrw}`,c:ind.usdkrw_chg},{l:"KOSPI",v:ind.kospi,c:ind.kospi_chg},{l:"WTI 원유",v:`$${ind.wti}`,c:ind.wti_chg},{l:"Bitcoin",v:`$${ind.btc}`,c:ind.btc_chg}];
  return <div style={{display:"flex",flexDirection:"column",gap:14,animation:"fadeInRight .4s ease .2s both"}}>
    <div style={{background:C.white,borderRadius:14,border:`1px solid ${C.border}`,overflow:"hidden",boxShadow:C.shadow}}>
      <div style={{padding:"12px 16px 10px",borderBottom:`1px solid ${C.border}`,background:"#F8FAFC",display:"flex",justifyContent:"space-between",alignItems:"center"}}>
        <span style={{fontSize:11,fontWeight:800,color:C.muted,letterSpacing:".8px",textTransform:"uppercase"}}>실시간 시세</span>
        <div style={{display:"flex",alignItems:"center",gap:5}}><LiveDot ring={!ind.isDefault}/><span style={{fontSize:10,color:C.green,fontWeight:600}}>{ind.isDefault?"로딩 중":"Live"}</span></div>
      </div>
      <div style={{padding:"10px 12px",display:"flex",flexDirection:"column",gap:8}}>
        {indItems.map((r,i)=>{
          const n=parseFloat(String(r.c||"0").replace(/[^-\d.]/g,""));
          const pos=n>0, neg=n<0;
          const col=pos?C.red:neg?C.blue:C.muted;
          return <div key={r.l} style={{display:"flex",justifyContent:"space-between",alignItems:"center",padding:"8px 10px",background:pos?C.redSoft:neg?C.blueSoft:"#F8FAFC",borderRadius:10,border:`1px solid ${C.border}`,transition:"all .3s",animation:`fadeInRight .35s ease ${i*.08}s both`}}>
            <span style={{fontSize:12,color:C.sub,fontWeight:500}}>{r.l}</span>
            <div style={{textAlign:"right"}}>
              <div style={{fontSize:13,fontWeight:700,color:ind.isDefault?C.muted:C.text,animation:mounted&&!ind.isDefault?"numberPop .5s ease both":undefined}}>{r.v}</div>
              <div style={{fontSize:10,color:col,fontWeight:700}}>{pos?"▲":neg?"▼":""}{Math.abs(n).toFixed(2)}%</div>
            </div>
          </div>;
        })}
      </div>
    </div>
    <div style={{background:C.white,borderRadius:14,border:`1px solid ${C.border}`,overflow:"hidden",boxShadow:C.shadow}}>
      <div style={{padding:"12px 16px 10px",borderBottom:`1px solid ${C.border}`,background:"#F8FAFC"}}>
        <span style={{fontSize:11,fontWeight:800,color:C.muted,letterSpacing:".8px",textTransform:"uppercase"}}>인기 기사</span>
      </div>
      <div style={{padding:"10px 14px",display:"flex",flexDirection:"column",gap:12}}>
        {top.map((a,i)=><div key={a.id} style={{display:"flex",gap:10,alignItems:"flex-start",animation:`fadeInRight .35s ease ${i*.07}s both`}}>
          <div style={{width:24,height:24,borderRadius:8,background:i===0?"linear-gradient(135deg,#2563EB,#60A5FA)":i===1?"linear-gradient(135deg,#3B82F6,#93C5FD)":i===2?"#BFDBFE":"#E2E8F0",display:"flex",alignItems:"center",justifyContent:"center",fontSize:11,fontWeight:800,color:i<3?"#FFF":C.muted,flexShrink:0,boxShadow:i===0?"0 2px 6px rgba(37,99,235,.3)":"none"}}>{i+1}</div>
          <div>
            <div style={{fontSize:12,color:C.text,lineHeight:1.5,marginBottom:3,fontWeight:500}}>{a.title}</div>
            <div style={{fontSize:10,color:C.muted}}>{a.src} · {(a.views||0).toLocaleString()}</div>
          </div>
        </div>)}
      </div>
    </div>
  </div>;
}

/* ── 경제 지표 카드 (카운트업) ────────────────────────────────── */
function IndCard({label,val,chg,sub,enabled}) {
  const numStr = val ? String(val).replace(/[^\d.]/g,"") : "";
  const hasComma = val && String(val).includes(",");
  const counted = useCountUp(numStr, 1200, enabled && !!val);
  const prefix = val ? (String(val).startsWith("₩")?"₩":String(val).startsWith("$")?"$":"") : "";
  const suffix = val ? (String(val).endsWith("%")?"%":"") : "";

  const displayVal = () => {
    if (!val) return null;
    if (!enabled) return val;
    const raw = counted;
    if (hasComma) return prefix + raw.toFixed(0).replace(/\B(?=(\d{3})+(?!\d))/g,",") + suffix;
    return prefix + raw.toFixed(raw < 10 ? 2 : 0) + suffix;
  };

  const n = chg ? parseFloat(String(chg).replace(/[^-\d.]/g,"")) : 0;
  const pos=n>0, neg=n<0;
  const col=pos?C.red:neg?C.blue:C.muted;

  return <div style={{background:pos?C.redSoft:neg?C.blueSoft:C.white,border:`1.5px solid ${pos?"#FECACA":neg?C.blueLight:C.border}`,borderRadius:14,padding:"16px",display:"flex",flexDirection:"column",gap:4,boxShadow:C.shadow,transition:"all .3s",animation:"scaleIn .4s cubic-bezier(.34,1.56,.64,1) both"}}>
    <div style={{fontSize:9,color:C.muted,fontWeight:700,letterSpacing:".5px",textTransform:"uppercase"}}>{sub}</div>
    <div style={{fontSize:10,color:C.sub,fontWeight:500}}>{label}</div>
    <div style={{fontSize:22,fontWeight:900,color:!enabled?C.muted:C.text,letterSpacing:"-.5px",lineHeight:1.15,animation:enabled?"numberPop .6s ease .2s both":undefined}}>{displayVal()||<Sk w="80%" h={22} r={4}/>}</div>
    {chg!=null&&<div style={{fontSize:11,color:col,fontWeight:700,display:"flex",alignItems:"center",gap:3}}>{pos?"▲":neg?"▼":""}{n!==0?Math.abs(n).toFixed(2)+"%":"—"}</div>}
  </div>;
}

/* ── SNS 바 애니메이션 ────────────────────────────────────────── */
function SNSBar({pos,neg,neu}) {
  const [ready, setReady] = useState(false);
  useEffect(() => { const t = setTimeout(()=>setReady(true), 300); return ()=>clearTimeout(t); }, []);
  const total=pos+neg+neu||100;
  const pw=`${(pos/total)*100}%`, nuw=`${(neu/total)*100}%`, ngw=`${(neg/total)*100}%`;
  return <div>
    <div style={{borderRadius:10,overflow:"hidden",height:30,display:"flex",marginBottom:10,boxShadow:"inset 0 2px 4px rgba(0,0,0,.06)"}}>
      {pos>0&&<div style={{width:ready?pw:"0%",background:"linear-gradient(90deg,#059669,#34D399)",display:"flex",alignItems:"center",justifyContent:"center",fontSize:11,fontWeight:800,color:"#FFF",transition:"width 1.2s cubic-bezier(.25,.46,.45,.94) .3s",overflow:"hidden",whiteSpace:"nowrap"}}>{ready&&pos>8?`${pos}%`:""}</div>}
      {neu>0&&<div style={{width:ready?nuw:"0%",background:"linear-gradient(90deg,#94A3B8,#CBD5E1)",display:"flex",alignItems:"center",justifyContent:"center",fontSize:11,fontWeight:800,color:"#FFF",transition:"width 1s cubic-bezier(.25,.46,.45,.94) .4s"}}>{ready&&neu>8?`${neu}%`:""}</div>}
      {neg>0&&<div style={{width:ready?ngw:"0%",background:"linear-gradient(90deg,#EF4444,#F87171)",display:"flex",alignItems:"center",justifyContent:"center",fontSize:11,fontWeight:800,color:"#FFF",transition:"width 1.2s cubic-bezier(.25,.46,.45,.94) .5s"}}>{ready&&neg>8?`${neg}%`:""}</div>}
    </div>
    <div style={{display:"flex",gap:18,fontSize:11}}>
      {[{l:`긍정 ${pos}%`,c:C.green},{l:`중립 ${neu}%`,c:C.muted},{l:`부정 ${neg}%`,c:C.red}].map(x=><span key={x.l} style={{color:x.c,fontWeight:600,display:"flex",alignItems:"center",gap:4}}><span style={{width:8,height:8,borderRadius:"50%",background:x.c,display:"inline-block"}}/>  {x.l}</span>)}
    </div>
  </div>;
}

/* ── 페이지 래퍼 (전환 애니메이션) ──────────────────────────── */
function PageWrapper({children, pageKey}) {
  return <div key={pageKey} style={{animation:"pageIn .35s ease both"}}>{children}</div>;
}

/* ── AI 브리핑 ───────────────────────────────────────────────── */
function BriefingView() {
  const [topic,setTopic]=useState("");
  const [result,setResult]=useState("");
  const [loading,setLoading]=useState(false);
  const [error,setError]=useState("");
  const [step,setStep]=useState(0);
  const steps=["주제 분석 중…","웹 검색으로 데이터 수집 중…","경제 데이터 정리 중…","브리핑 작성 중…"];

  const run=async(t)=>{
    setTopic(t);setResult("");setError("");setLoading(true);setStep(0);
    const t1=setTimeout(()=>setStep(1),3000),t2=setTimeout(()=>setStep(2),12000),t3=setTimeout(()=>setStep(3),22000);
    try{const res=await getBriefing(t);clearTimeout(t1);clearTimeout(t2);clearTimeout(t3);if(res&&res.trim())setResult(res);else setError("브리핑을 불러오지 못했습니다. API 키를 확인하거나 잠시 후 다시 시도해주세요.")}
    catch(e){clearTimeout(t1);clearTimeout(t2);clearTimeout(t3);setError("오류: "+e.message)}
    setLoading(false);
  };

  const render=(text)=>text.split("\n").map((line,i)=>{
    if(!line.trim())return <div key={i} style={{height:8}}/>;
    if(line.startsWith("**")&&line.endsWith("**"))
      return <div key={i} style={{fontSize:15,fontWeight:800,color:C.blue,marginTop:20,marginBottom:8,paddingBottom:8,borderBottom:`2px solid ${C.blueLight}`,animation:`fadeInUp .3s ease both`}}>{line.replace(/\*\*/g,"")}</div>;
    if(line.includes("**")){const parts=line.split(/\*\*([^*]+)\*\*/);return<div key={i} style={{fontSize:13,color:C.sub,lineHeight:1.85}}>{parts.map((p,j)=>j%2===1?<strong key={j} style={{color:C.text,fontWeight:700}}>{p}</strong>:<span key={j}>{p}</span>)}</div>}
    if(line.startsWith("- "))return<div key={i} style={{fontSize:13,color:C.sub,lineHeight:1.85,display:"flex",gap:8,paddingLeft:8,animation:`fadeInUp .3s ease ${i*.02}s both`}}><span style={{color:C.blue,flexShrink:0,fontWeight:700}}>·</span><span>{line.slice(2)}</span></div>;
    return<div key={i} style={{fontSize:13,color:C.sub,lineHeight:1.85}}>{line}</div>;
  });

  return <div style={{maxWidth:860,margin:"0 auto",animation:"pageIn .35s ease both"}}>
    <ApiKeyBanner/>
    <div style={{marginBottom:24}}>
      <h2 style={{fontSize:22,fontWeight:800,color:C.text,marginBottom:8,animation:"fadeInDown .4s ease both"}}>AI 경제 브리핑</h2>
      <div style={{display:"flex",gap:10,flexWrap:"wrap"}}>
        {[{icon:"🌐",text:"웹 검색 기반 실시간 분석",c:C.blue,bg:C.blueSoft,border:C.blueLight},{icon:"⚡",text:"약 20~40초 소요",c:C.green,bg:C.greenSoft,border:"#A7F3D0"}].map((b,i)=><div key={i} style={{fontSize:12,color:b.c,background:b.bg,border:`1px solid ${b.border}`,borderRadius:99,padding:"5px 14px",display:"inline-flex",gap:6,alignItems:"center",fontWeight:600,animation:`fadeInUp .4s ease ${.1+i*.1}s both`}}>
          <span style={{animation:"float 3s ease infinite"}}>{b.icon}</span>{b.text}
        </div>)}
      </div>
    </div>

    <div style={{display:"grid",gridTemplateColumns:"repeat(auto-fill,minmax(220px,1fr))",gap:10,marginBottom:28}}>
      {BTOPICS.map((t,i)=><button key={t} onClick={()=>!loading&&run(t)} disabled={loading}
        className="btn-press"
        style={{padding:"14px 16px",borderRadius:14,border:`2px solid ${topic===t?C.blue:C.border}`,background:topic===t?C.blueSoft:C.white,color:topic===t?C.blue:C.sub,cursor:loading?"not-allowed":"pointer",fontSize:13,fontWeight:topic===t?700:500,textAlign:"left",transition:"all .22s cubic-bezier(.34,1.56,.64,1)",boxShadow:topic===t?`0 0 0 3px ${C.blueLight},${C.shadowMd}`:C.shadow,opacity:loading&&topic!==t?.5:1,transform:topic===t?"scale(1.02)":"scale(1)",animation:`fadeInUp .4s ease ${i*.05}s both`}}>
        {t}
      </button>)}
    </div>

    {loading&&<div style={{background:C.white,borderRadius:18,padding:"44px 40px",textAlign:"center",boxShadow:C.shadowMd,border:`1px solid ${C.border}`,animation:"scaleIn .4s cubic-bezier(.34,1.56,.64,1) both"}}>
      <div style={{fontSize:48,marginBottom:18,animation:"floatSlow 3s ease infinite",display:"inline-block"}}>🛸</div>
      <div style={{fontSize:16,fontWeight:700,color:C.text,marginBottom:6,animation:"fadeInUp .3s ease both"}}>{steps[step]}</div>
      <div style={{fontSize:13,color:C.muted,marginBottom:18}}>{topic}</div>
      <div style={{display:"flex",gap:10,justifyContent:"center",marginBottom:22}}>
        {steps.map((_,i)=><div key={i} style={{width:i===step?24:8,height:8,borderRadius:99,background:i<=step?C.blue:C.light,transition:"all .4s cubic-bezier(.34,1.56,.64,1)",boxShadow:i===step?`0 2px 8px ${C.blue}44`:undefined}}/>)}
      </div>
      <div style={{width:300,height:5,background:C.light,borderRadius:99,margin:"0 auto",overflow:"hidden",position:"relative",boxShadow:"inset 0 1px 3px rgba(0,0,0,.08)"}}>
        <div style={{position:"absolute",width:"45%",height:"100%",background:`linear-gradient(90deg,${C.blue},#60A5FA)`,borderRadius:99,animation:"ld 1.8s ease-in-out infinite",boxShadow:"0 0 8px rgba(37,99,235,.4)"}}/>
      </div>
    </div>}

    {error&&!loading&&<div style={{background:"#FEF2F2",border:"1px solid #FECACA",borderRadius:14,padding:"18px 22px",display:"flex",gap:12,alignItems:"flex-start",animation:"scaleIn .3s ease both"}}>
      <span style={{fontSize:22,flexShrink:0,animation:"shake .5s ease both"}}>⚠️</span>
      <div>
        <div style={{fontSize:13,fontWeight:700,color:C.red,marginBottom:4}}>브리핑 로드 실패</div>
        <div style={{fontSize:12,color:"#7F1D1D",lineHeight:1.6}}>{error}</div>
        <button onClick={()=>run(topic)} className="btn-press" style={{marginTop:10,padding:"7px 18px",borderRadius:99,border:"none",background:C.red,color:"#FFF",cursor:"pointer",fontSize:11,fontWeight:700,boxShadow:"0 3px 8px rgba(220,38,38,.3)"}}>다시 시도</button>
      </div>
    </div>}

    {result&&!loading&&!error&&<div style={{background:C.white,borderRadius:18,overflow:"hidden",boxShadow:C.shadowMd,border:`1.5px solid ${C.blueLight}`,animation:"scaleIn .4s cubic-bezier(.34,1.56,.64,1) both"}}>
      <div style={{padding:"16px 24px",background:`linear-gradient(135deg,${C.blueSoft},#FFF)`,borderBottom:`1px solid ${C.blueLight}`,display:"flex",alignItems:"center",gap:12}}>
        <div style={{width:40,height:40,borderRadius:12,background:`linear-gradient(135deg,${C.blue},#60A5FA)`,display:"flex",alignItems:"center",justifyContent:"center",fontSize:20,boxShadow:`0 4px 12px ${C.blue}44`,animation:"float 3s ease infinite"}}>🛸</div>
        <div>
          <div style={{fontSize:10,fontWeight:800,color:C.blue,letterSpacing:".8px",textTransform:"uppercase",marginBottom:2}}>AI BRIEFING</div>
          <div style={{fontSize:13,color:C.sub,fontWeight:600}}>{topic}</div>
        </div>
        <div style={{marginLeft:"auto",display:"flex",gap:10,alignItems:"center"}}>
          <div style={{display:"flex",alignItems:"center",gap:5}}><LiveDot ring/><span style={{fontSize:10,color:C.green,fontWeight:600}}>실시간 분석</span></div>
          <button onClick={()=>run(topic)} className="btn-press" style={{padding:"5px 14px",borderRadius:99,border:`1px solid ${C.border}`,background:C.white,color:C.sub,cursor:"pointer",fontSize:11,fontWeight:600,boxShadow:C.shadow,transition:"all .2s"}}>↺ 재분석</button>
        </div>
      </div>
      <div style={{padding:"24px"}}>{render(result)}</div>
      <div style={{padding:"12px 24px",borderTop:`1px solid ${C.border}`,fontSize:11,color:C.muted,background:"#F8FAFC"}}>⚠ AI 생성 정보입니다. 투자 결정의 근거로 사용하지 마세요.</div>
    </div>}

    {!loading&&!result&&!error&&<div style={{background:C.white,borderRadius:18,padding:"60px 0",textAlign:"center",boxShadow:C.shadow,border:`1px solid ${C.border}`}}>
      <div style={{fontSize:56,marginBottom:14,animation:"float 3s ease infinite",display:"inline-block"}}>🛸</div>
      <div style={{fontSize:16,fontWeight:700,color:C.text,marginBottom:6}}>경제 브리핑 주제를 선택하세요</div>
      <div style={{fontSize:13,color:C.muted}}>AI가 웹 검색으로 최신 데이터를 분석해 쉽게 설명해드립니다.</div>
    </div>}
  </div>;
}

/* ── SNS 뷰 ──────────────────────────────────────────────────── */
function SNSView({snsData,snsLoading}) {
  return <PageWrapper pageKey="sns">
    <div style={{marginBottom:22}}>
      <h2 style={{fontSize:22,fontWeight:800,color:C.text,marginBottom:4,animation:"fadeInDown .4s ease both"}}>SNS 반응 분석</h2>
      <p style={{fontSize:13,color:C.muted,animation:"fadeInUp .4s ease .1s both"}}>AI가 분석한 경제 이슈별 소셜 미디어 여론입니다.</p>
    </div>
    <div style={{display:"flex",flexDirection:"column",gap:14}}>
      {snsLoading?Array(3).fill(0).map((_,i)=><div key={i} style={{background:C.white,borderRadius:14,padding:22,boxShadow:C.shadow,animation:`fadeInUp .4s ease ${i*.1}s both`}}><Sk h={18} w="50%" mb={16}/><Sk h={28} r={8} mb={12}/><Sk h={13} mb={6}/><Sk h={13} w="80%"/></div>):
      !snsData||!snsData.length?<div style={{background:C.white,borderRadius:14,padding:50,textAlign:"center",color:C.muted,boxShadow:C.shadow}}><div style={{fontSize:40,marginBottom:10,animation:"float 3s ease infinite",display:"inline-block"}}>💬</div><div>SNS 데이터 로딩 중…</div></div>:
      snsData.map((d,i)=>{
        const pos=parseInt(d.pos)||0,neg=parseInt(d.neg)||0,neu=parseInt(d.neu)||0;
        const overall=pos>neg?"긍정 우세":neg>pos?"부정 우세":"팽팽함";
        const oc=pos>neg?C.green:neg>pos?C.red:C.yellow;
        const osf=pos>neg?C.greenSoft:neg>pos?C.redSoft:C.yellowSoft;
        return <div key={i} style={{background:C.white,borderRadius:14,overflow:"hidden",boxShadow:C.shadow,border:`1px solid ${C.border}`,animation:`fadeInUp .4s ease ${i*.1}s both`}}>
          <div style={{padding:"14px 20px",borderBottom:`1px solid ${C.border}`,display:"flex",justifyContent:"space-between",alignItems:"center",background:"#F8FAFC"}}>
            <div style={{fontSize:15,fontWeight:700,color:C.text}}>{d.topic}</div>
            <div style={{display:"flex",alignItems:"center",gap:10}}>
              <span style={{fontSize:11,fontWeight:700,padding:"4px 12px",borderRadius:99,background:osf,color:oc,animation:"popIn .5s cubic-bezier(.34,1.56,.64,1) both"}}>{overall}</span>
              <span style={{fontSize:11,color:d.trend==="up"?C.red:C.blue,fontWeight:600}}>{d.trend==="up"?"▲ 주목도 상승":"▼ 관심 하락"}</span>
            </div>
          </div>
          <div style={{padding:"16px 20px"}}>
            <SNSBar pos={pos} neg={neg} neu={neu}/>
            <div style={{marginTop:14}}>
              {d.topTweets&&<div style={{display:"flex",flexDirection:"column",gap:6,marginBottom:14}}>
                {d.topTweets.map((tw,j)=><div key={j} style={{background:"#F8FAFC",border:`1px solid ${C.border}`,borderRadius:10,padding:"10px 14px",fontSize:12,color:C.sub,lineHeight:1.6,animation:`fadeInUp .3s ease ${j*.08}s both`}}>
                  <span style={{color:"#1DA1F2",marginRight:6}}>🐦</span>{tw}
                </div>)}
              </div>}
              <div style={{background:C.blueSoft,borderLeft:`4px solid ${C.blue}`,borderRadius:"0 10px 10px 0",padding:"10px 16px",fontSize:13,color:"#1E40AF",lineHeight:1.7,fontWeight:500}}>{d.summary}</div>
              {d.keywords&&<div style={{display:"flex",gap:6,flexWrap:"wrap",marginTop:12}}>
                {d.keywords.map((k,j)=><span key={k} style={{fontSize:11,padding:"3px 12px",borderRadius:99,background:C.blueSoft,color:C.blue,fontWeight:600,animation:`popIn .4s ease ${j*.07}s both`}}>#{k}</span>)}
              </div>}
            </div>
          </div>
        </div>;
      })}
    </div>
  </PageWrapper>;
}

/* ── 경제 지표 뷰 ────────────────────────────────────────────── */
function IndicatorsView({ind}) {
  const enabled = !ind.isDefault;
  const groups=[
    {title:"환율",icon:"💱",items:[{l:"USD/KRW",v:ind.usdkrw?`₩${ind.usdkrw}`:null,c:ind.usdkrw_chg,sub:"달러/원"},{l:"EUR/KRW",v:ind.eurkrw?`₩${ind.eurkrw}`:null,c:ind.eurkrw_chg,sub:"유로/원"},{l:"JPY/KRW",v:ind.jpykrw?`₩${ind.jpykrw}`:null,c:ind.jpykrw_chg,sub:"엔/원"},{l:"CNY/KRW",v:ind.cnykrw?`₩${ind.cnykrw}`:null,c:ind.cnykrw_chg,sub:"위안/원"}]},
    {title:"국내 주식",icon:"📈",items:[{l:"KOSPI",v:ind.kospi,c:ind.kospi_chg,sub:"코스피 지수"},{l:"KOSDAQ",v:ind.kosdaq,c:ind.kosdaq_chg,sub:"코스닥 지수"}]},
    {title:"글로벌 주식",icon:"🌍",items:[{l:"S&P 500",v:ind.sp500,c:ind.sp500_chg,sub:"미국 S&P"},{l:"NASDAQ",v:ind.nasdaq,c:ind.nasdaq_chg,sub:"나스닥"},{l:"Nikkei 225",v:ind.nikkei,c:ind.nikkei_chg,sub:"일본 닛케이"}]},
    {title:"원자재 & 디지털자산",icon:"⚡",items:[{l:"WTI 유가",v:ind.wti?`$${ind.wti}`:null,c:ind.wti_chg,sub:"배럴당"},{l:"금 (Gold)",v:ind.gold?`$${ind.gold}`:null,c:ind.gold_chg,sub:"트로이온스"},{l:"Bitcoin",v:ind.btc?`$${ind.btc}`:null,c:ind.btc_chg,sub:"BTC/USD"}]},
    {title:"국내 경제 지표",icon:"🏦",items:[{l:"기준금리",v:ind.base_rate?`${ind.base_rate}%`:null,c:null,sub:"한국은행"},{l:"CPI",v:ind.cpi?`${ind.cpi}%`:null,c:ind.cpi_chg,sub:"전년동월비"}]},
  ];
  return <PageWrapper pageKey="indicators">
    <div style={{display:"flex",justifyContent:"space-between",alignItems:"flex-end",marginBottom:26}}>
      <div>
        <h2 style={{fontSize:22,fontWeight:800,color:C.text,marginBottom:4,animation:"fadeInDown .4s ease both"}}>경제 지표 대시보드</h2>
        <p style={{fontSize:13,color:C.muted,animation:"fadeInUp .4s ease .1s both"}}>AI가 수집한 실시간 주요 경제 지표입니다.</p>
      </div>
      <div style={{display:"flex",alignItems:"center",gap:6,background:C.white,padding:"7px 16px",borderRadius:99,border:`1px solid ${C.border}`,boxShadow:C.shadow,animation:"fadeInRight .4s ease both"}}>
        <LiveDot color={ind.isDefault?C.yellow:C.green} ring={!ind.isDefault}/>
        <span style={{fontSize:11,color:C.sub,fontWeight:600}}>{ind.isDefault?"업데이트 중…":`${ind.time} 기준`}</span>
      </div>
    </div>
    {groups.map((g,gi)=><div key={g.title} style={{marginBottom:26,animation:`fadeInUp .4s ease ${gi*.1}s both`}}>
      <div style={{fontSize:13,fontWeight:700,color:C.sub,marginBottom:12,display:"flex",alignItems:"center",gap:8}}>
        <span style={{fontSize:20,animation:`float ${3+gi*.3}s ease infinite`}}>{g.icon}</span>
        <span style={{letterSpacing:".3px"}}>{g.title}</span>
        <div style={{flex:1,height:1,background:`linear-gradient(90deg,${C.border},transparent)`,marginLeft:8}}/>
      </div>
      <div style={{display:"grid",gridTemplateColumns:"repeat(auto-fill,minmax(160px,1fr))",gap:10}}>
        {g.items.map((item,ii)=><div key={item.l} style={{animation:`scaleIn .4s cubic-bezier(.34,1.56,.64,1) ${gi*.1+ii*.06}s both`}}>
          <IndCard label={item.l} val={item.v} chg={item.c} sub={item.sub} enabled={enabled}/>
        </div>)}
      </div>
    </div>)}
  </PageWrapper>;
}

/* ── 메인 앱 ─────────────────────────────────────────────────── */
function EconView() {
  const [page,setPage]=useState("home");
  const [cat,setCat]=useState("전체");
  const [search,setSearch]=useState("");
  const [ind,setInd]=useState(DEFAULT_IND);
  const [news,setNews]=useState(DEFAULT_NEWS);
  const [summaries,setSummaries]=useState({});
  const [sumLoading,setSumLoading]=useState(null);
  const [snsData,setSnsData]=useState(null);
  const [snsLoading,setSnsLoading]=useState(false);
  const [lastUpdated,setLastUpdated]=useState(null);
  const [refreshing,setRefreshing]=useState(false);
  const timer=useRef(null);

  const fetchAll=useCallback(async()=>{
    setRefreshing(true);
    const [indData,newsData]=await Promise.all([loadIndicators(),loadNews()]);
    if(indData)setInd(indData);
    if(newsData?.length)setNews(newsData);
    setLastUpdated(new Date());
    setRefreshing(false);
  },[]);

  useEffect(()=>{fetchAll();timer.current=setInterval(fetchAll,300000);return()=>clearInterval(timer.current)},[fetchAll]);
  useEffect(()=>{if(page==="sns"&&!snsData){setSnsLoading(true);loadSNS().then(d=>{setSnsData(d);setSnsLoading(false)})}},[page,snsData]);

  const handleSum=useCallback(async(a)=>{
    setSumLoading(a.id);
    const result=await summarize1(a);
    setSummaries(prev=>({...prev,[a.id]:result}));
    setSumLoading(null);
  },[]);

  const filtered=(news||[]).filter(a=>(cat==="전체"||a.cat===cat)&&(!search||a.title?.includes(search)||a.preview?.includes(search)));
  const featured=news?.[0]||null;
  const fmt=d=>d?`${d.getHours()}:${String(d.getMinutes()).padStart(2,"0")} 업데이트`:"";
  const NAV=[{id:"home",l:"홈"},{id:"briefing",l:"AI 브리핑"},{id:"articles",l:"기사 모음"},{id:"sns",l:"SNS 반응"},{id:"indicators",l:"경제 지표"}];

  const changePage = (id) => { setPage(id); window.scrollTo({top:0,behavior:"smooth"}); };

  return <div style={{minHeight:"100vh",background:C.bg,fontSize:14}}>
    {/* 헤더 */}
    <header style={{background:"rgba(255,255,255,.95)",backdropFilter:"blur(12px)",borderBottom:`1px solid ${C.border}`,position:"sticky",top:0,zIndex:100,boxShadow:"0 2px 8px rgba(0,0,0,.06)"}}>
      <div style={{maxWidth:1380,margin:"0 auto",padding:"0 24px",height:60,display:"flex",alignItems:"center",gap:24}}>
        <div style={{display:"flex",alignItems:"center",gap:10,flexShrink:0,animation:"fadeInLeft .5s ease both"}}>
          <div style={{width:36,height:36,borderRadius:12,background:`linear-gradient(135deg,${C.blue},#60A5FA)`,display:"flex",alignItems:"center",justifyContent:"center",fontSize:18,boxShadow:`0 3px 10px ${C.blue}44`,animation:"float 3s ease infinite"}}>🛸</div>
          <div>
            <div style={{fontSize:16,fontWeight:900,color:C.text,letterSpacing:"-.5px",lineHeight:1.1}}>EconView</div>
            <div style={{fontSize:9,color:C.muted,fontWeight:600,letterSpacing:".5px",textTransform:"uppercase"}}>AI 경제 브리핑</div>
          </div>
        </div>
        <nav style={{display:"flex",gap:0}}>
          {NAV.map((n,i)=><button key={n.id} onClick={()=>changePage(n.id)}
            style={{padding:"0 16px",height:60,border:"none",background:"transparent",color:page===n.id?C.blue:C.sub,cursor:"pointer",fontSize:13,fontWeight:page===n.id?700:500,borderBottom:`3px solid ${page===n.id?C.blue:"transparent"}`,transition:"all .2s",animation:`fadeInDown .4s ease ${i*.07}s both`,position:"relative"}}>
            {n.l}
            {page===n.id&&<span style={{position:"absolute",bottom:0,left:"50%",transform:"translateX(-50%)",width:4,height:4,borderRadius:"50%",background:C.blue,animation:"popIn .3s ease both"}}/>}
          </button>)}
        </nav>
        <div style={{flex:1}}/>
        <div style={{position:"relative",width:210,animation:"fadeInDown .4s ease .3s both"}}>
          <span style={{position:"absolute",left:12,top:"50%",transform:"translateY(-50%)",color:C.muted,fontSize:14}}>🔍</span>
          <input value={search} onChange={e=>setSearch(e.target.value)} placeholder="기사 검색…"
            style={{width:"100%",padding:"8px 14px 8px 34px",borderRadius:99,border:`1.5px solid ${C.border}`,background:C.bg,color:C.text,fontSize:13,outline:"none",transition:"all .2s"}}
            onFocus={e=>{e.target.style.borderColor=C.blue;e.target.style.background="#FFF";e.target.style.boxShadow=`0 0 0 3px ${C.blueLight}`}}
            onBlur={e=>{e.target.style.borderColor=C.border;e.target.style.background=C.bg;e.target.style.boxShadow="none"}}/>
        </div>
        {lastUpdated&&<div style={{display:"flex",alignItems:"center",gap:6,fontSize:11,color:C.muted,flexShrink:0}}>
          <LiveDot color={refreshing?C.yellow:C.green}/><span style={{fontWeight:500}}>{refreshing?"업데이트 중":fmt(lastUpdated)}</span>
        </div>}
        <button onClick={fetchAll} disabled={refreshing}
          className="btn-press"
          style={{padding:"7px 18px",borderRadius:99,border:`1.5px solid ${refreshing?C.border:C.blue}`,background:refreshing?C.light:C.blue,color:refreshing?C.muted:"#FFF",cursor:refreshing?"wait":"pointer",fontSize:12,fontWeight:700,flexShrink:0,boxShadow:refreshing?"none":`0 3px 10px ${C.blue}44`,transition:"all .2s",animation:"fadeInRight .4s ease .4s both"}}>
          {refreshing?"업데이트 중…":"↺ 새로고침"}
        </button>
      </div>
    </header>

    <Ticker ind={ind}/>

    <main style={{maxWidth:1380,margin:"0 auto",padding:"30px 24px"}}>
      {(page==="home"||page==="articles")&&<PageWrapper pageKey={page+cat}>
        {page==="home"&&<div style={{marginBottom:32}}>
          <div style={{display:"flex",alignItems:"center",gap:8,marginBottom:16,animation:"fadeInLeft .4s ease both"}}>
            <div style={{width:4,height:24,background:`linear-gradient(180deg,${C.blue},#60A5FA)`,borderRadius:2,animation:"scaleIn .5s ease both"}}/>
            <h2 style={{fontSize:20,fontWeight:800,color:C.text}}>오늘의 헤드라인</h2>
          </div>
          <HeroCard article={featured}/>
        </div>}
        <div style={{display:"grid",gridTemplateColumns:"162px 1fr 254px",gap:22,alignItems:"start"}}>
          <div style={{position:"sticky",top:72}}><CatNav cat={cat} setCat={setCat} news={news}/></div>
          <div>
            <div style={{display:"flex",alignItems:"center",gap:8,marginBottom:18,animation:"fadeInDown .4s ease both"}}>
              <div style={{width:4,height:20,background:`linear-gradient(180deg,${C.blue},#60A5FA)`,borderRadius:2}}/>
              <h3 style={{fontSize:17,fontWeight:700,color:C.text}}>{cat==="전체"?"전체 기사":cat}</h3>
              {news&&<span style={{fontSize:12,color:C.muted,background:C.light,padding:"2px 10px",borderRadius:99,fontWeight:500,animation:"popIn .4s ease .2s both"}}>{filtered.length}건</span>}
            </div>
            <div style={{display:"flex",flexDirection:"column",gap:12}}>
              {filtered.map((a,i)=><ArticleCard key={a.id} a={a} onSum={handleSum} summaries={summaries} sumLoading={sumLoading} index={i}/>)}
              {filtered.length===0&&<div style={{padding:50,textAlign:"center",color:C.muted,background:C.white,borderRadius:14,boxShadow:C.shadow,animation:"scaleIn .4s ease both"}}>
                <div style={{fontSize:40,marginBottom:10,animation:"float 3s ease infinite",display:"inline-block"}}>🔍</div>
                <div>검색 결과가 없습니다.</div>
              </div>}
            </div>
          </div>
          <div style={{position:"sticky",top:72}}><RightPanel ind={ind} news={news}/></div>
        </div>
      </PageWrapper>}
      {page==="briefing"&&<BriefingView/>}
      {page==="sns"&&<SNSView snsData={snsData} snsLoading={snsLoading}/>}
      {page==="indicators"&&<IndicatorsView ind={ind}/>}
    </main>

    <footer style={{borderTop:`1px solid ${C.border}`,padding:"22px 24px",marginTop:24,background:C.white}}>
      <div style={{maxWidth:1380,margin:"0 auto",display:"flex",justifyContent:"space-between",alignItems:"center"}}>
        <div style={{display:"flex",alignItems:"center",gap:8}}>
          <div style={{width:26,height:26,borderRadius:8,background:`linear-gradient(135deg,${C.blue},#60A5FA)`,display:"flex",alignItems:"center",justifyContent:"center",fontSize:14,animation:"float 3s ease infinite"}}>🛸</div>
          <span style={{fontSize:12,color:C.sub,fontWeight:700}}>EconView</span>
          <span style={{fontSize:12,color:C.muted}}>· AI 기반 경제 뉴스 큐레이션</span>
        </div>
        <span style={{fontSize:11,color:C.muted}}>본 서비스의 정보는 투자 조언이 아닙니다 · 5분마다 자동 갱신</span>
      </div>
    </footer>
  </div>;
}

ReactDOM.createRoot(document.getElementById("root")).render(<EconView/>);
</script>
</body>
</html>
