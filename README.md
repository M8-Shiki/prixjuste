[index.html](https://github.com/user-attachments/files/34790612/index.html)
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Prixjuste – comparateur de prix</title>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,600;12..96,800&display=swap">
<style>
:root{--bg1:#ffd9c7;--bg2:#ffc6e5;--bg3:#cdbdff;--surface:rgba(255,255,255,.9);--ink:#1b1140;--muted:#5a4f7a;--line:#e6d8f0;--ok:#5b2fd6;--okbg:#efe6ff;--grad:linear-gradient(135deg,#ffb627,#ff6b4a);
box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg1:#2a0f3a;--bg2:#3b1030;--bg3:#14134a;--surface:rgba(28,16,50,.88);--ink:#f6edff;--muted:#c2b3df;--line:#3b2a5c;--ok:#c5a8ff;--okbg:#33215a;color-scheme:dark}}
:root[data-theme="dark"]{--bg1:#2a0f3a;--bg2:#3b1030;--bg3:#14134a;--surface:rgba(28,16,50,.88);--ink:#f6edff;--muted:#c2b3df;--line:#3b2a5c;--ok:#c5a8ff;--okbg:#33215a;color-scheme:dark}
*{box-sizing:border-box}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{margin:0;min-height:100vh;color:var(--ink);font-family:"Bricolage Grotesque",system-ui,-apple-system,"Segoe UI",sans-serif;line-height:1.5;background:radial-gradient(60rem 40rem at 0% 0%,var(--bg1),transparent 60%),radial-gradient(50rem 40rem at 100% 25%,var(--bg2),transparent 60%),radial-gradient(60rem 50rem at 40% 100%,var(--bg3),transparent 60%),var(--bg1);background-attachment:fixed}
.deco{position:fixed;inset:0;overflow:hidden;pointer-events:none;z-index:0}
.deco span{position:absolute;font-size:var(--s);opacity:.55;animation:drift var(--d) ease-in-out infinite alternate}
@keyframes drift{from{transform:translateY(0) rotate(var(--r))}to{transform:translateY(-26px) rotate(calc(var(--r) + 8deg))}}
@media (prefers-reduced-motion:reduce){.deco span{animation:none;transform:rotate(var(--r))}}
main{position:relative;z-index:1;max-width:860px;margin:0 auto;padding:56px 20px 64px}
h1{font-size:clamp(2.1rem,6.5vw,3.6rem);line-height:1.04;font-weight:800;letter-spacing:-.025em;margin:0 0 12px}
.lead{color:var(--muted);margin:0 0 28px;max-width:56ch;font-size:1.05rem}
form{display:flex;gap:8px}
input{font:inherit;color:var(--ink)}
input[type=search]{flex:1;min-width:0;font-size:1.1rem;padding:16px 18px;border:2px solid var(--ink);border-radius:12px;background:var(--surface);box-shadow:0 10px 30px rgba(90,40,120,.22)}
button{font:inherit;font-weight:700;cursor:pointer}
.go,.add,a.buy{border:0;background:var(--grad);color:#1b1140;border-radius:10px;text-decoration:none;box-shadow:0 4px 14px rgba(255,107,74,.35)}
.go{padding:0 26px;border-radius:12px}
.add{padding:9px 14px}
a.buy{display:inline-block;padding:9px 14px;font-weight:700;font-size:.95rem}
:focus-visible{outline:3px solid var(--ok);outline-offset:2px}
.hint,.meta{color:var(--muted);font-size:.86rem}
.hint{margin:14px 0 0}
.panel{margin-top:28px;background:var(--surface);backdrop-filter:blur(6px);border:1px solid var(--line);border-radius:16px;padding:6px 20px 16px}
.panel h2{font-size:1.15rem;margin:16px 0 4px}
.top{display:flex;flex-wrap:wrap;gap:10px 20px;align-items:center;justify-content:space-between}
.top label{font-size:.88rem;color:var(--muted)}
input[type=date],input[type=number]{padding:8px 10px;border:1.5px solid var(--line);border-radius:8px;background:transparent}
input[type=number]{width:120px}
ol{list-style:none;margin:8px 0 0;padding:0}
li.offer{display:grid;grid-template-columns:1fr auto;gap:8px 16px;align-items:center;padding:14px 0;border-top:1px solid var(--line)}
.name{font-weight:700;display:flex;flex-wrap:wrap;gap:6px 10px;align-items:center}
.badge{font-size:.76rem;font-weight:600;padding:2px 9px;border-radius:99px;background:var(--okbg);color:var(--ok)}
.best{background:var(--grad);color:#1b1140;font-size:.76rem;font-weight:800;padding:2px 9px;border-radius:5px}
.price{font-size:1.7rem;font-weight:800;text-align:right;font-variant-numeric:tabular-nums;line-height:1.1}
.pr{text-align:right}
.act{grid-column:1/-1;display:flex;flex-wrap:wrap;gap:8px;align-items:center}
.legend{display:flex;flex-wrap:wrap;gap:6px 16px;margin:8px 0 0;font-size:.85rem}
.legend i{display:inline-block;width:12px;height:12px;border-radius:50%;margin-right:6px;vertical-align:-1px}
svg{width:100%;height:auto;display:block}
.criteria{margin-top:26px;font-size:.88rem;color:var(--muted)}
.criteria strong{color:var(--ink)}
@media (max-width:520px){form{flex-direction:column}.go{padding:14px}.deco span{opacity:.35}}
.q{border:0;margin:16px 0 0;padding:0;min-width:0}
.q legend{font-weight:700;margin-bottom:8px;padding:0}
.chips{display:flex;flex-wrap:wrap;gap:8px}
.chips label{position:relative}
.chips input{position:absolute;opacity:0;inset:0;width:100%;height:100%;margin:0;cursor:pointer}
.chips span{display:inline-block;padding:8px 14px;border:1.5px solid var(--line);border-radius:99px}
.chips input:checked+span{background:var(--grad);border-color:transparent;color:#1b1140;font-weight:700}
.chips input:focus-visible+span{outline:3px solid var(--ok);outline-offset:2px}
.fld{display:flex;flex-direction:column;gap:6px;font-weight:700;flex:1;min-width:200px}
.fld input{padding:10px 12px;border:1.5px solid var(--line);border-radius:8px;background:transparent;font-weight:400;width:100%}
.row2{display:flex;flex-wrap:wrap;gap:12px;margin-top:16px}
.go2{padding:12px 22px;font-size:1rem}
.skip,.link{background:none;border:0;color:var(--ok);text-decoration:underline;font-weight:600}
.link{padding:0 0 0 8px}
.sum{margin:22px 0 0;font-size:.95rem}
.badge.over{background:rgba(255,77,109,.16);color:#c0123c}
@media (prefers-color-scheme:dark){.badge.over{color:#ff9bb0}}
</style>
</head>
<body>
<div class="deco" aria-hidden="true">
<span style="--s:4.2rem;--r:-12deg;--d:7s;left:4%;top:12%">🎧</span>
<span style="--s:3.4rem;--r:10deg;--d:9s;left:84%;top:8%">📱</span>
<span style="--s:5rem;--r:-6deg;--d:8s;left:90%;top:42%">👟</span>
<span style="--s:3.6rem;--r:14deg;--d:10s;left:6%;top:48%">🎮</span>
<span style="--s:4.4rem;--r:-10deg;--d:6.5s;left:78%;top:78%">⌚</span>
<span style="--s:3.8rem;--r:8deg;--d:9.5s;left:12%;top:82%">📷</span>
<span style="--s:3.2rem;--r:-16deg;--d:7.5s;left:48%;top:92%">🧳</span>
<span style="--s:3rem;--r:12deg;--d:8.5s;left:52%;top:3%">☕</span>
</div>
<main>
<h1>Trouvez-le au meilleur prix, chez des vendeurs de confiance.</h1>
<p class="lead">Cherchez un objet, répondez à quelques questions pour affiner, puis suivez le prix chez chaque marchand dans le temps.</p>
<form id="f" role="search">
<input id="q" type="search" placeholder="Ex. : casque Bluetooth, aspirateur robot…" aria-label="Rechercher un produit" autocomplete="off" required>
<button class="go" type="submit">Comparer</button>
</form>
<p class="hint">Les prix affichés sont ceux que vous relevez vous-même chez le marchand : aucun n’est inventé. Ils sont gardés sur votre appareil.</p>
<section id="res" aria-live="polite"></section>
<p class="criteria"><strong>Seuls les marchands de notre liste validée apparaissent.</strong> Critères : mentions légales et SIRET, domaine ancien, HTTPS valide, aucune alerte Google Safe Browsing, avis clients réels.</p>
</main>
<script>
const M=[
{n:"Amazon.fr",u:q=>`https://www.amazon.fr/s?k=${q}`},
{n:"Fnac",u:q=>`https://www.fnac.com/SearchResult/ResultList.aspx?Search=${q}`},
{n:"Darty",u:q=>`https://www.darty.com/nav/recherche?text=${q}`},
{n:"Boulanger",u:q=>`https://www.boulanger.com/resultats?tr=${q}`},
{n:"Cdiscount",u:q=>`https://www.cdiscount.com/search/10/${q}.html`},
{n:"eBay.fr",u:q=>`https://www.ebay.fr/sch/i.html?_nkw=${q}`},
{n:"Back Market",u:q=>`https://www.backmarket.fr/fr-fr/search?q=${q}`,used:true}
];
const CATS=[
{re:/casque|écouteur|ecouteur|enceinte|airpods/,qs:[{id:"co",t:"Connexion",o:[["Sans fil","sans fil"],["Filaire","filaire"]]},{id:"us",t:"Usage principal",o:[["Musique",""],["Sport","sport"],["Appels / bureau","micro"],["Voyage","réduction de bruit"]]}]},
{re:/téléphone|telephone|smartphone|iphone|galaxy|pixel/,qs:[{id:"st",t:"Stockage",o:[["64 Go","64 Go"],["128 Go","128 Go"],["256 Go ou plus","256 Go"]]},{id:"g5",t:"5G",o:[["Oui","5G"],["Peu importe",""]]}]},
{re:/chaussure|basket|sneaker|botte|running/,qs:[{id:"pu",t:"Pour qui",o:[["Homme","homme"],["Femme","femme"],["Enfant","enfant"]]},{id:"us",t:"Usage",o:[["Running","running"],["Ville","ville"],["Randonnée","randonnée"]]}]},
{re:/aspirateur|robot/,qs:[{id:"ty",t:"Type",o:[["Robot","robot"],["Balai sans fil","balai sans fil"],["Traîneau","traîneau"]]},{id:"an",t:"Poils d’animaux",o:[["Oui","animaux"],["Non",""]]}]},
{re:/ordinateur|laptop|portable|\bpc\b|macbook/,qs:[{id:"us",t:"Usage",o:[["Bureautique",""],["Jeux","gamer"],["Création","créateur"]]},{id:"ec",t:"Écran",o:[["13–14 pouces","14 pouces"],["15–16 pouces","15 pouces"]]}]},
{re:/télé|\btv\b|téléviseur|television/,qs:[{id:"ta",t:"Taille",o:[["43 pouces","43 pouces"],["55 pouces","55 pouces"],["65 pouces","65 pouces"]]},{id:"te",t:"Technologie",o:[["OLED","OLED"],["QLED","QLED"],["LED",""]]}]}
];
const COL=["#ff4d6d","#7c4dff","#ff9f1c","#06b6d4","#e11d8f","#2f6feb","#f97316"];
const esc=s=>String(s).replace(/[<>&"]/g,"");
const eur=v=>v.toLocaleString("fr-FR",{style:"currency",currency:"EUR"});
const fr=d=>new Date(d+"T00:00:00").toLocaleDateString("fr-FR");
const today=()=>{const d=new Date();return d.getFullYear()+"-"+String(d.getMonth()+1).padStart(2,"0")+"-"+String(d.getDate()).padStart(2,"0")};
let store={};
try{store=JSON.parse(localStorage.getItem("prixjuste")||"{}")}catch(e){store={}}
const persist=()=>{try{localStorage.setItem("prixjuste",JSON.stringify(store))}catch(e){}};
let q="",R="",etat="Neuf",budget=0,day=today(),qs=[];
const key=n=>R.toLowerCase()+"|"+n;
const hist=n=>(store[key(n)]||[]).slice().sort((a,b)=>a.d<b.d?-1:1);
const res=document.getElementById("res");

function ask(){
const cat=CATS.find(c=>c.re.test(q.toLowerCase()));
qs=cat?cat.qs:[];
const blocks=qs.map(s=>`<fieldset class="q"><legend>${s.t}</legend><div class="chips">${s.o.map((o,i)=>`<label><input type="radio" name="${s.id}" value="${i}"><span>${o[0]}</span></label>`).join("")}</div></fieldset>`).join("");
const etats=["Neuf","Reconditionné","Occasion"].map((e,i)=>`<label><input type="radio" name="etat" value="${e}" ${i?"":"checked"}><span>${e}</span></label>`).join("");
res.innerHTML=`<div class="panel"><h2>Quelques questions pour trouver le bon « ${esc(q)} »</h2><p class="meta">Vos réponses précisent la recherche chez chaque marchand. Tout est facultatif.</p><form id="ask">${blocks}<fieldset class="q"><legend>État souhaité</legend><div class="chips">${etats}</div></fieldset><div class="row2"><label class="fld">Marque<input name="br" type="text" placeholder="Ex. : Sony, Apple, Samsung" autocomplete="off"></label><label class="fld">Budget maximum (€)<input name="bu" type="number" min="0" step="1" inputmode="numeric" placeholder="Ex. : 150"></label></div><div class="act" style="margin-top:18px"><button class="add go2" type="submit">Voir les offres</button><button class="skip" type="button" id="skip">Passer les questions</button></div></form></div>`}

function chart(series){
const pts=series.flatMap(s=>s.h);
if(!pts.length)return`<p class="meta">Enregistrez un premier prix pour démarrer la courbe.</p>`;
const W=700,H=280,L=58,Rr=16,T=16,B=36;
const ts=pts.map(p=>+new Date(p.d)),ps=pts.map(p=>p.p);
let t0=Math.min(...ts),t1=Math.max(...ts),p0=Math.min(...ps),p1=Math.max(...ps);
if(t0===t1){t0-=864e5*3;t1+=864e5*3}
const pad=(p1-p0)||p1*.1||1;p0=Math.max(0,p0-pad*.25);p1+=pad*.25;
const X=t=>L+(t-t0)/(t1-t0)*(W-L-Rr),Y=p=>T+(1-(p-p0)/(p1-p0))*(H-T-B);
let g="";
for(let i=0;i<=4;i++){const v=p0+(p1-p0)*i/4,y=Y(v);g+=`<line x1="${L}" x2="${W-Rr}" y1="${y}" y2="${y}" stroke="var(--line)"/><text x="${L-8}" y="${y+4}" text-anchor="end" font-size="12" fill="var(--muted)">${Math.round(v)} €</text>`}
const lab=t=>new Date(t).toLocaleDateString("fr-FR",{day:"numeric",month:"short"});
g+=`<text x="${L}" y="${H-10}" font-size="12" fill="var(--muted)">${lab(t0)}</text><text x="${W-Rr}" y="${H-10}" text-anchor="end" font-size="12" fill="var(--muted)">${lab(t1)}</text>`;
series.forEach(s=>{
const c=COL[s.i%COL.length];
const xy=s.h.map(p=>`${X(+new Date(p.d)).toFixed(1)},${Y(p.p).toFixed(1)}`);
if(s.h.length>1)g+=`<polyline points="${xy.join(" ")}" fill="none" stroke="${c}" stroke-width="3" stroke-linejoin="round" stroke-linecap="round"/>`;
s.h.forEach(p=>{g+=`<circle cx="${X(+new Date(p.d)).toFixed(1)}" cy="${Y(p.p).toFixed(1)}" r="5" fill="${c}"><title>${s.n} : ${eur(p.p)} le ${fr(p.d)}</title></circle>`});
});
const leg=series.map(s=>`<span><i style="background:${COL[s.i%COL.length]}"></i>${s.n}</span>`).join("");
const hint=series.some(s=>s.h.length>1)?"":`<p class="meta">Ajoutez des relevés à d’autres dates pour voir la courbe se tracer.</p>`;
return`<svg viewBox="0 0 ${W} ${H}" role="img" aria-label="Évolution du prix dans le temps">${g}</svg><div class="legend">${leg}</div>${hint}`}

function render(){
const enc=encodeURIComponent(R);
let ms=M.map((m,i)=>({m,i})).filter(x=>!x.m.used||etat!=="Neuf");
if(etat!=="Neuf")ms.sort((a,b)=>(b.m.used?1:0)-(a.m.used?1:0)||(b.m.n==="eBay.fr"?-1:0)-(a.m.n==="eBay.fr"?-1:0));
const rows=ms.map(x=>{const h=hist(x.m.n);return{m:x.m,i:x.i,h,last:h[h.length-1]}});
const sorted=rows.slice().sort((a,b)=>(a.last?a.last.p:Infinity)-(b.last?b.last.p:Infinity));
const priced=rows.filter(x=>x.last).length;
const best=sorted[0].last?sorted[0].m.n:null;
const lis=sorted.map(r=>{
const bud=r.last&&budget?(r.last.p<=budget?`<span class="badge">Dans votre budget</span>`:`<span class="badge over">Au-dessus du budget</span>`):"";
return`<li class="offer" data-i="${r.i}"><div class="name">${r.m.n}<span class="badge">Marchand vérifié</span>${r.m.n===best&&priced>1?`<span class="best">Meilleur prix</span>`:""}${bud}</div><div class="pr">${r.last?`<div class="price">${eur(r.last.p)}</div><div class="meta">relevé le ${fr(r.last.d)}</div>`:`<div class="meta">Pas encore de prix relevé</div>`}</div><div class="act"><input type="number" step="0.01" min="0" inputmode="decimal" placeholder="Prix vu (€)" aria-label="Prix vu chez ${r.m.n}"><button class="add" type="button">Enregistrer</button><a class="buy" href="${r.m.u(enc)}" target="_blank" rel="noopener noreferrer">Voir l’article chez ${r.m.n}</a></div></li>`}).join("");
const series=rows.filter(r=>r.h.length).map(r=>({n:r.m.n,i:r.i,h:r.h}));
res.innerHTML=`<p class="sum">Recherche affinée : <strong>${esc(R)}</strong>${budget?` · budget max ${eur(budget)}`:""}<button class="link" id="edit" type="button">Modifier mes réponses</button></p><div class="panel"><div class="top"><h2>${rows.length} marchands vérifiés</h2><label>Date du relevé <input type="date" id="dt" value="${day}" max="${today()}"></label></div><ol>${lis}</ol></div><div class="panel"><h2>Évolution du prix</h2>${chart(series)}</div>`}

document.getElementById("f").addEventListener("submit",e=>{e.preventDefault();q=document.getElementById("q").value.trim();if(q)ask()});
res.addEventListener("submit",e=>{
if(e.target.id!=="ask")return;
e.preventDefault();
const fd=new FormData(e.target),words=[];
const br=(fd.get("br")||"").trim();if(br)words.push(br);
qs.forEach(s=>{const v=fd.get(s.id);if(v!==null&&s.o[+v][1])words.push(s.o[+v][1])});
etat=fd.get("etat")||"Neuf";
if(etat==="Reconditionné")words.push("reconditionné");
if(etat==="Occasion")words.push("occasion");
budget=parseFloat((fd.get("bu")||"").replace(",","."))||0;
R=[q,...words].join(" ");render()});
res.addEventListener("change",e=>{if(e.target.id==="dt")day=e.target.value||today()});
res.addEventListener("click",e=>{
const t=e.target;
if(t.id==="skip"){R=q;etat="Neuf";budget=0;render();return}
if(t.id==="edit"){ask();return}
if(!t.classList.contains("add")||t.type!=="button")return;
const li=t.closest("li"),v=parseFloat(li.querySelector("input").value.replace(",","."));
if(!(v>0))return;
const n=M[+li.dataset.i].n,k=key(n),h=(store[k]||[]).filter(p=>p.d!==day);
h.push({d:day,p:Math.round(v*100)/100});store[k]=h;persist();render()});
</script>
</body>
</html>
