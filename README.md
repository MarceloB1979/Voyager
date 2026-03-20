# Voyager
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rota Encantada Viagens · Solicite sua Cotação</title>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700;900&family=Nunito:wght@300;400;600;700;800&display=swap" rel="stylesheet">
<style>
:root{
  --void:#0A0714;--card:rgba(20,12,48,0.90);--border:rgba(180,130,255,0.18);
  --gold:#D4A843;--gold2:#F5D06A;--gold-dim:rgba(212,168,67,0.13);
  --purple:#7B3FE4;--pink:#C060FF;--teal:#2ABFBF;--coral:#FF7070;--green:#4ADE80;
  --text:#F0EAFF;--text-muted:rgba(240,234,255,0.58);--text-dim:rgba(240,234,255,0.27);
  --inp:rgba(255,255,255,0.04);--inp-border:rgba(180,130,255,0.22);
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Nunito',sans-serif;background:var(--void);color:var(--text);min-height:100vh;overflow-x:hidden;}

/* ── BG ── */
.bg{position:fixed;inset:0;z-index:0;overflow:hidden;
  background:
    radial-gradient(ellipse 90% 60% at 10% 0%,rgba(123,63,228,.22) 0%,transparent 55%),
    radial-gradient(ellipse 70% 50% at 90% 100%,rgba(212,168,67,.1) 0%,transparent 50%),
    radial-gradient(ellipse 50% 60% at 80% 20%,rgba(192,96,255,.08) 0%,transparent 50%),
    linear-gradient(155deg,#120A2A 0%,#0A0714 60%,#0D0A1A 100%);}
.stars{position:absolute;inset:0;animation:twinkle 6s ease-in-out infinite alternate;
  background-image:
    radial-gradient(1.5px 1.5px at 8% 14%,rgba(255,245,200,.9) 0%,transparent 100%),
    radial-gradient(1px 1px at 19% 4%,rgba(255,245,200,.7) 0%,transparent 100%),
    radial-gradient(1px 1px at 33% 21%,rgba(255,245,200,.8) 0%,transparent 100%),
    radial-gradient(2px 2px at 47% 9%,rgba(255,245,200,.45) 0%,transparent 100%),
    radial-gradient(1px 1px at 59% 17%,rgba(255,245,200,.9) 0%,transparent 100%),
    radial-gradient(1.5px 1.5px at 71% 7%,rgba(192,96,255,.75) 0%,transparent 100%),
    radial-gradient(1px 1px at 83% 24%,rgba(255,245,200,.8) 0%,transparent 100%),
    radial-gradient(1px 1px at 93% 11%,rgba(255,245,200,.55) 0%,transparent 100%),
    radial-gradient(1px 1px at 26% 78%,rgba(255,245,200,.3) 0%,transparent 100%),
    radial-gradient(1px 1px at 57% 88%,rgba(212,168,67,.4) 0%,transparent 100%),
    radial-gradient(1.5px 1.5px at 77% 70%,rgba(255,245,200,.3) 0%,transparent 100%),
    radial-gradient(1px 1px at 42% 50%,rgba(255,245,200,.2) 0%,transparent 100%),
    radial-gradient(1px 1px at 66% 42%,rgba(212,168,67,.25) 0%,transparent 100%);}
@keyframes twinkle{0%{opacity:.45}100%{opacity:1}}
.orb{position:absolute;border-radius:50%;filter:blur(90px);pointer-events:none;animation:drift 20s ease-in-out infinite alternate;}
.o1{width:500px;height:400px;background:rgba(123,63,228,.18);top:-80px;left:-80px;}
.o2{width:400px;height:400px;background:rgba(192,96,255,.09);top:35%;right:-100px;animation-delay:-8s;}
.o3{width:550px;height:230px;background:rgba(212,168,67,.07);bottom:0;left:10%;animation-delay:-13s;}
@keyframes drift{0%{transform:translate(0,0) scale(1)}100%{transform:translate(22px,-28px) scale(1.07)}}

/* Silhueta do castelo no rodapé */
.castle{
  position:fixed;bottom:0;left:0;right:0;height:160px;z-index:1;pointer-events:none;
  background:
    linear-gradient(transparent 0%, rgba(10,7,20,.9) 60%, var(--void) 100%);
}
.castle::before{
  content:'';position:absolute;bottom:0;left:0;right:0;height:120px;
  background:
    linear-gradient(rgba(10,7,20,0) 0%, rgba(10,7,20,.95) 100%);
  /* Silhueta simplificada com box-shadows empilhados */
}

/* ── HEADER ── */
header{
  position:sticky;top:0;z-index:100;
  display:flex;align-items:center;justify-content:space-between;
  padding:12px 36px;backdrop-filter:blur(22px);
  background:rgba(10,7,20,.72);border-bottom:1px solid var(--border);
  animation:slideDown .6s ease both;
}
@keyframes slideDown{from{opacity:0;transform:translateY(-12px)}to{opacity:1;transform:translateY(0)}}
.logo-wrap{display:flex;align-items:center;gap:11px;text-decoration:none;}
.logo-img{width:48px;height:48px;object-fit:contain;filter:drop-shadow(0 0 13px rgba(212,168,67,.55));transition:filter .3s;}
.logo-wrap:hover .logo-img{filter:drop-shadow(0 0 20px rgba(212,168,67,.8));}
.logo-name{font-family:'Cinzel',serif;font-size:.95rem;font-weight:700;
  background:linear-gradient(135deg,var(--gold2),var(--gold));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;letter-spacing:.5px;}
.logo-tagline{font-size:.58rem;color:var(--text-dim);letter-spacing:2px;text-transform:uppercase;margin-top:1px;}
.hd-badge{
  display:flex;align-items:center;gap:7px;
  background:rgba(74,222,128,.08);border:1px solid rgba(74,222,128,.28);
  border-radius:20px;padding:6px 14px;font-size:.68rem;color:var(--green);
  letter-spacing:1px;text-transform:uppercase;font-weight:700;
}
.hd-badge::before{content:'';width:6px;height:6px;background:var(--green);border-radius:50%;animation:blink 2s infinite;flex-shrink:0;}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.15}}

/* ── PAGE ── */
.page{position:relative;z-index:10;min-height:100vh;display:flex;flex-direction:column;}

/* ── HERO ── */
.hero{
  text-align:center;padding:52px 20px 32px;
  animation:fadeUp .8s .1s ease both;opacity:0;
}
@keyframes fadeUp{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
.hero-spark{font-size:1.5rem;margin-bottom:12px;animation:pulse 3s ease-in-out infinite;display:block;}
@keyframes pulse{0%,100%{opacity:.6;transform:scale(1)}50%{opacity:1;transform:scale(1.15)}}
.hero h1{
  font-family:'Cinzel',serif;font-size:clamp(1.8rem,4vw,2.8rem);font-weight:900;line-height:1.15;
  background:linear-gradient(145deg,#fff 0%,var(--gold2) 40%,var(--gold) 70%,#fff 100%);
  background-size:200% 200%;
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  animation:shimmerText 5s ease-in-out infinite;margin-bottom:12px;
}
@keyframes shimmerText{0%,100%{background-position:0% 50%}50%{background-position:100% 50%}}
.hero p{font-size:clamp(.88rem,2vw,1rem);color:var(--text-muted);max-width:480px;margin:0 auto;line-height:1.7;}
.hero-dots{display:flex;align-items:center;justify-content:center;gap:6px;margin-top:14px;}
.hero-dots span{width:5px;height:5px;border-radius:50%;background:var(--gold);opacity:.3;animation:dotPulse 2s ease-in-out infinite;}
.hero-dots span:nth-child(2){animation-delay:.3s;}
.hero-dots span:nth-child(3){animation-delay:.6s;}
@keyframes dotPulse{0%,100%{opacity:.2;transform:scale(1)}50%{opacity:.8;transform:scale(1.4)}}

/* ── LAYOUT ── */
.layout{
  display:grid;grid-template-columns:240px 1fr 240px;
  gap:22px;max-width:1120px;margin:0 auto;
  padding:0 24px 80px;
  animation:fadeUp .8s .25s ease both;opacity:0;
}

/* ── SIDE PANELS ── */
.side-panel{display:flex;flex-direction:column;gap:14px;padding-top:6px;}
.sp-card{
  background:rgba(18,10,40,.75);border:1px solid var(--border);
  border-radius:14px;padding:18px 16px;backdrop-filter:blur(10px);
}
.sp-title{font-family:'Cinzel',serif;font-size:.75rem;font-weight:700;color:var(--gold);
  letter-spacing:.8px;margin-bottom:12px;display:flex;align-items:center;gap:7px;}
.sp-title::before{content:'✦';font-size:.55rem;opacity:.7;}
.sp-item{display:flex;align-items:flex-start;gap:10px;margin-bottom:10px;font-size:.8rem;color:var(--text-muted);line-height:1.5;}
.sp-item:last-child{margin-bottom:0;}
.sp-ico{font-size:.9rem;flex-shrink:0;margin-top:1px;}
.dest-list{display:flex;flex-direction:column;gap:8px;}
.dest-item{
  display:flex;align-items:center;gap:10px;
  padding:9px 12px;border-radius:9px;
  background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.06);
  font-size:.8rem;color:var(--text-muted);
  transition:all .2s;cursor:default;
}
.dest-item:hover{background:var(--gold-dim);border-color:rgba(212,168,67,.25);color:var(--text);}
.dest-flag{font-size:1.1rem;}

/* ── FORM CARD ── */
.form-card{
  background:var(--card);border:1px solid var(--border);border-radius:20px;
  backdrop-filter:blur(18px);overflow:hidden;
  box-shadow:0 24px 70px rgba(0,0,0,.45),0 0 70px rgba(123,63,228,.1);
}
.fc-shimmer{
  height:3px;
  background:linear-gradient(90deg,var(--purple) 0%,var(--pink) 25%,var(--gold2) 50%,var(--pink) 75%,var(--purple) 100%);
  background-size:300% 100%;animation:shimmer 4s linear infinite;
}
@keyframes shimmer{0%{background-position:100% 0}100%{background-position:-200% 0}}
.fc-head{
  background:linear-gradient(135deg,rgba(45,18,96,.92) 0%,rgba(22,8,55,.85) 100%);
  padding:20px 26px;border-bottom:1px solid rgba(212,168,67,.1);
  display:flex;align-items:center;gap:14px;position:relative;overflow:hidden;
}
.fc-head::after{content:'✦';position:absolute;right:18px;top:50%;transform:translateY(-50%);font-size:4.5rem;opacity:.04;color:var(--gold);pointer-events:none;}
.fc-ico{
  width:44px;height:44px;border-radius:12px;flex-shrink:0;
  background:linear-gradient(135deg,rgba(212,168,67,.25),rgba(212,168,67,.06));
  border:1px solid rgba(212,168,67,.3);display:flex;align-items:center;justify-content:center;
  font-size:1.3rem;box-shadow:0 0 22px rgba(212,168,67,.18);
}
.fc-head h2{font-family:'Cinzel',serif;font-size:1rem;font-weight:700;color:var(--text);letter-spacing:.5px;}
.fc-head p{font-size:.76rem;color:var(--text-muted);margin-top:3px;}
.fc-body{padding:24px 26px 28px;}

/* ── FORM ELEMENTS ── */
.sec-label{
  display:flex;align-items:center;gap:9px;
  margin:20px 0 11px;font-size:.61rem;text-transform:uppercase;letter-spacing:2.5px;color:var(--text-dim);font-weight:700;
}
.sec-label:first-child{margin-top:0;}
.sec-ico{
  width:22px;height:22px;border-radius:6px;
  background:linear-gradient(135deg,rgba(212,168,67,.18),rgba(212,168,67,.04));
  border:1px solid rgba(212,168,67,.18);display:flex;align-items:center;justify-content:center;font-size:.68rem;flex-shrink:0;
}
.sec-label::after{content:'';flex:1;height:1px;background:rgba(180,130,255,.12);}
.row2{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.fg{margin-bottom:10px;}
.fg label{display:block;font-size:.66rem;font-weight:700;text-transform:uppercase;letter-spacing:1px;color:var(--text-muted);margin-bottom:5px;}
.fg input,.fg select,.fg textarea{
  width:100%;padding:10px 13px;
  background:var(--inp);border:1.5px solid var(--inp-border);
  border-radius:9px;color:var(--text);
  font-family:'Nunito',sans-serif;font-size:.88rem;
  outline:none;transition:all .22s;appearance:none;-webkit-appearance:none;
}
.fg input::placeholder,.fg textarea::placeholder{color:var(--text-dim);}
.fg input:hover,.fg select:hover,.fg textarea:hover{border-color:rgba(180,130,255,.38);background:rgba(123,63,228,.05);}
.fg input:focus,.fg select:focus,.fg textarea:focus{
  border-color:rgba(212,168,67,.55);background:rgba(212,168,67,.04);
  box-shadow:0 0 0 3px rgba(212,168,67,.08);
}
.fg select{cursor:pointer;}
.fg select option{background:#1A0A3A;color:var(--text);}
.fg textarea{resize:vertical;min-height:76px;line-height:1.6;}

/* ── TOGGLE CRIANÇAS ── */
.toggle-row{
  display:flex;align-items:center;gap:13px;
  padding:11px 14px;background:rgba(255,255,255,.025);
  border:1.5px solid var(--inp-border);border-radius:9px;
  cursor:pointer;user-select:none;transition:all .2s;margin-bottom:10px;
}
.toggle-row:hover{background:rgba(123,63,228,.07);border-color:rgba(180,130,255,.38);}
.sw{width:38px;height:21px;background:rgba(255,255,255,.12);border-radius:11px;position:relative;flex-shrink:0;transition:background .22s;}
.sw::after{content:'';position:absolute;width:15px;height:15px;background:#fff;border-radius:50%;top:3px;left:3px;transition:transform .22s;box-shadow:0 2px 6px rgba(0,0,0,.4);}
.sw.on{background:linear-gradient(135deg,var(--gold),var(--gold2));box-shadow:0 0 14px rgba(212,168,67,.4);}
.sw.on::after{transform:translateX(17px);}
.tl{font-size:.85rem;color:var(--text-muted);} .tl b{color:var(--text);}
input[type=checkbox]{display:none;}

.children-box{
  display:none;background:rgba(123,63,228,.07);
  border:1.5px solid rgba(123,63,228,.22);border-radius:9px;
  padding:14px;margin-bottom:10px;
}
.children-box.show{display:block;animation:expandIn .3s ease;}
@keyframes expandIn{from{opacity:0;transform:translateY(-5px)}to{opacity:1;transform:translateY(0)}}
.ch-head{display:flex;align-items:center;justify-content:space-between;margin-bottom:10px;}
.ch-lbl{font-size:.62rem;text-transform:uppercase;letter-spacing:1.5px;color:var(--text-muted);font-weight:700;}
.ch-ctrl{display:flex;align-items:center;gap:10px;}
.ch-btn{width:26px;height:26px;border-radius:50%;border:1.5px solid rgba(180,130,255,.4);background:transparent;color:rgba(180,130,255,.9);font-size:1.05rem;font-weight:700;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .15s;line-height:1;}
.ch-btn:hover{background:var(--purple);color:#fff;border-color:var(--purple);}
.ch-n{font-size:.95rem;font-weight:800;color:var(--text);min-width:20px;text-align:center;}
.ages-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(90px,1fr));gap:8px;}
.age-item label{display:block;font-size:.62rem;text-transform:uppercase;letter-spacing:.8px;color:var(--text-muted);font-weight:700;margin-bottom:4px;}
.age-item input{width:100%;padding:8px 10px;background:rgba(255,255,255,.04);border:1.5px solid rgba(180,130,255,.2);border-radius:7px;color:var(--text);font-family:'Nunito',sans-serif;font-size:.86rem;outline:none;transition:border-color .2s;}
.age-item input:focus{border-color:rgba(212,168,67,.5);}
.ch-note{font-size:.7rem;color:var(--text-dim);margin-top:8px;font-style:italic;}

/* ── MENSAGENS ── */
.msg-err{display:none;background:rgba(255,112,112,.08);border:1px solid rgba(255,112,112,.28);border-radius:9px;padding:11px 14px;color:var(--coral);font-size:.82rem;font-weight:600;margin-bottom:12px;}
.msg-ok{display:none;flex-direction:column;align-items:center;text-align:center;padding:36px 20px;}
.ok-ring{
  width:72px;height:72px;border-radius:50%;margin:0 auto 16px;
  background:linear-gradient(135deg,rgba(74,222,128,.15),rgba(74,222,128,.05));
  border:2px solid rgba(74,222,128,.4);display:flex;align-items:center;justify-content:center;
  font-size:2rem;animation:ringPulse 2s ease-in-out infinite;
}
@keyframes ringPulse{0%,100%{box-shadow:0 0 0 0 rgba(74,222,128,.3)}50%{box-shadow:0 0 0 14px rgba(74,222,128,0)}}
.ok-ring{}
.ok-title{font-family:'Cinzel',serif;font-size:1.15rem;font-weight:700;color:var(--green);margin-bottom:8px;}
.ok-text{font-size:.86rem;color:var(--text-muted);line-height:1.6;max-width:340px;margin:0 auto 20px;}
.ok-steps{display:flex;flex-direction:column;gap:8px;width:100%;max-width:300px;}
.ok-step{display:flex;align-items:center;gap:10px;background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);border-radius:9px;padding:10px 13px;font-size:.8rem;color:var(--text-muted);}
.ok-step-n{width:22px;height:22px;border-radius:50%;background:linear-gradient(135deg,var(--gold),var(--gold2));color:#1A0A00;font-size:.7rem;font-weight:800;display:flex;align-items:center;justify-content:center;flex-shrink:0;}

/* ── BOTÃO ENVIAR ── */
.btn-send{
  width:100%;padding:14px 20px;margin-top:6px;
  background:linear-gradient(135deg,var(--gold) 0%,#BF8A28 40%,var(--gold2) 100%);
  border:none;border-radius:11px;color:#1A0A00;
  font-family:'Cinzel',serif;font-size:.88rem;font-weight:700;letter-spacing:1.5px;
  cursor:pointer;display:flex;align-items:center;justify-content:center;gap:11px;
  transition:all .22s;position:relative;overflow:hidden;
  box-shadow:0 6px 28px rgba(212,168,67,.3),0 2px 8px rgba(0,0,0,.3);
}
.btn-send::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(255,255,255,.16) 0%,transparent 50%);pointer-events:none;}
.btn-send:hover{transform:translateY(-2px);box-shadow:0 12px 40px rgba(212,168,67,.42),0 4px 14px rgba(0,0,0,.3);}
.btn-send:active{transform:translateY(0);}
.btn-send:disabled{opacity:.55;cursor:not-allowed;transform:none;}
.btn-ico{font-size:1.05rem;transition:transform .22s;}
.btn-send:hover .btn-ico{transform:translateX(5px) rotate(-20deg);}

/* ── TRUST BADGES ── */
.trust-row{display:flex;justify-content:center;gap:20px;margin-top:14px;flex-wrap:wrap;}
.trust-item{display:flex;align-items:center;gap:7px;font-size:.72rem;color:var(--text-dim);}
.trust-ico{font-size:.85rem;}

@media(max-width:1000px){.layout{grid-template-columns:1fr;}.side-panel{display:none;}}
@media(max-width:600px){header{padding:11px 18px;}.fc-body{padding:18px 18px 22px;}.hero{padding:36px 16px 22px;}.layout{padding:0 12px 60px;}}
</style>
</head>
<body>
<div class="bg"><div class="stars"></div><div class="orb o1"></div><div class="orb o2"></div><div class="orb o3"></div></div>

<div class="page">
  <header>
    <a href="#" class="logo-wrap">
      <img class="logo-img" src="data:image/png;base64,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" alt="Rota Encantada Viagens">
      <div>
        <div class="logo-name">Rota Encantada Viagens</div>
        <div class="logo-tagline">Realizando sonhos, destino a destino</div>
      </div>
    </a>
    <div class="hd-badge">Atendimento Online</div>
  </header>

  <div class="hero">
    <span class="hero-spark">🌙</span>
    <h1>Sua Viagem dos Sonhos<br>Começa Aqui</h1>
    <p>Preencha o formulário e nossa equipe preparará uma proposta encantada, especialmente para você.</p>
    <div class="hero-dots"><span></span><span></span><span></span></div>
  </div>

  <div class="layout">

    <!-- Painel esquerdo -->
    <aside class="side-panel">
      <div class="sp-card">
        <div class="sp-title">Destinos em Alta</div>
        <div class="dest-list">
          <div class="dest-item"><span class="dest-flag">🏰</span> Orlando &amp; Disney</div>
          <div class="dest-item"><span class="dest-flag">🌴</span> Cancún</div>
          <div class="dest-item"><span class="dest-flag">🗼</span> Paris &amp; Europa</div>
          <div class="dest-item"><span class="dest-flag">☀️</span> Nordeste Brasileiro</div>
          <div class="dest-item"><span class="dest-flag">🏝️</span> Caribe</div>
        </div>
      </div>
      <div class="sp-card">
        <div class="sp-title">Como Funciona</div>
        <div class="sp-item"><span class="sp-ico">1️⃣</span> Preencha seus dados e destino desejado</div>
        <div class="sp-item"><span class="sp-ico">2️⃣</span> Nossa equipe elabora a proposta personalizada</div>
        <div class="sp-item"><span class="sp-ico">3️⃣</span> Você recebe a cotação via WhatsApp ou e-mail</div>
      </div>
    </aside>

    <!-- FORMULÁRIO PRINCIPAL -->
    <main>
      <div class="form-card">
        <div class="fc-shimmer"></div>
        <div class="fc-head">
          <div class="fc-ico">✈️</div>
          <div>
            <h2>Solicitar Cotação</h2>
            <p>Grátis · Sem compromisso · Resposta em até 2h</p>
          </div>
        </div>
        <div class="fc-body">
          <div class="msg-err" id="msgErr"></div>
          <div class="msg-ok" id="msgOk" style="display:none">
            <div class="ok-ring">✨</div>
            <div class="ok-title">Solicitação Enviada!</div>
            <div class="ok-text">Recebemos seu pedido. Nossa equipe vai preparar a proposta perfeita e entrar em contato em breve.</div>
            <div class="ok-steps">
              <div class="ok-step"><div class="ok-step-n">1</div> Análise do seu pedido</div>
              <div class="ok-step"><div class="ok-step-n">2</div> Pesquisa de melhores preços</div>
              <div class="ok-step"><div class="ok-step-n">3</div> Contato com sua proposta</div>
            </div>
          </div>

          <div id="formFields">
            <div class="sec-label"><span class="sec-ico">👤</span>Seus Dados</div>
            <div class="fg"><label>Nome Completo *</label><input type="text" id="fNome" placeholder="Ex: Maria Silva"></div>
            <div class="row2">
              <div class="fg"><label>Telefone / WhatsApp *</label><input type="text" id="fTel" placeholder="(11) 99999-9999"></div>
              <div class="fg"><label>E-mail</label><input type="email" id="fEmail" placeholder="seu@email.com"></div>
            </div>

            <div class="sec-label"><span class="sec-ico">✈️</span>Destino</div>
            <div class="row2">
              <div class="fg"><label>Destino Desejado *</label><input type="text" id="fDestino" placeholder="Ex: Orlando, Cancún, Paris…"></div>
              <div class="fg"><label>Cidade de Origem</label><input type="text" id="fOrigem" placeholder="Ex: São Paulo – SP"></div>
            </div>

            <div class="sec-label"><span class="sec-ico">📅</span>Período</div>
            <div class="row2">
              <div class="fg"><label>Data de Ida</label><input type="date" id="fIda"></div>
              <div class="fg"><label>Data de Volta</label><input type="date" id="fVolta"></div>
            </div>

            <div class="sec-label"><span class="sec-ico">🌟</span>Viajantes</div>
            <div class="row2">
              <div class="fg">
                <label>Nº de Adultos</label>
                <select id="fPessoas">
                  <option value="1">1 adulto</option>
                  <option value="2" selected>2 adultos</option>
                  <option value="3">3 adultos</option>
                  <option value="4">4 adultos</option>
                  <option value="5">5 adultos</option>
                  <option value="6">6+ adultos</option>
                </select>
              </div>
              <div class="fg">
                <label>Orçamento Aproximado</label>
                <select id="fOrcamento">
                  <option value="">Não sei ainda</option>
                  <option value="5000">Até R$ 5.000</option>
                  <option value="10000">R$ 5.000 – R$ 10.000</option>
                  <option value="20000">R$ 10.000 – R$ 20.000</option>
                  <option value="40000">R$ 20.000 – R$ 40.000</option>
                  <option value="60000">Acima de R$ 40.000</option>
                </select>
              </div>
            </div>

            <label class="toggle-row" onclick="toggleCriancas()">
              <div class="sw" id="sw"></div>
              <span class="tl">🧒 <b>Vou com crianças</b> (até 17 anos)</span>
              <input type="checkbox" id="temCri">
            </label>

            <div class="children-box" id="childBox">
              <div class="ch-head">
                <span class="ch-lbl">Quantas crianças?</span>
                <div class="ch-ctrl">
                  <button class="ch-btn" type="button" onclick="mudaCri(-1)">−</button>
                  <span class="ch-n" id="numCriDisplay">1</span>
                  <button class="ch-btn" type="button" onclick="mudaCri(1)">+</button>
                </div>
              </div>
              <div class="ages-grid" id="agesGrid"></div>
              <div class="ch-note">* A idade ajuda a encontrar as melhores tarifas.</div>
            </div>

            <div class="sec-label"><span class="sec-ico">💬</span>Preferências</div>
            <div class="fg"><label>Conte-nos mais sobre sua viagem ideal</label>
              <textarea id="fObs" placeholder="Tipo de hotel, passeios, comemorações especiais, preferências alimentares, necessidades de acessibilidade…"></textarea>
            </div>

            <button class="btn-send" id="btnEnviar" onclick="enviar()">
              <span id="btnTxt">Solicitar Minha Cotação</span>
              <span class="btn-ico">✈</span>
            </button>

            <div class="trust-row">
              <div class="trust-item"><span class="trust-ico">🔒</span> Dados seguros</div>
              <div class="trust-item"><span class="trust-ico">💬</span> Resposta em até 2h</div>
              <div class="trust-item"><span class="trust-ico">⭐</span> 100% gratuito</div>
            </div>
          </div>
        </div>
      </div>
    </main>

    <!-- Painel direito -->
    <aside class="side-panel">
      <div class="sp-card">
        <div class="sp-title">Por que Rota Encantada?</div>
        <div class="sp-item"><span class="sp-ico">🏅</span> Especialistas em viagens em família e parques temáticos</div>
        <div class="sp-item"><span class="sp-ico">✈️</span> Parceria com as principais companhias aéreas</div>
        <div class="sp-item"><span class="sp-ico">🏨</span> Hotéis selecionados com curadoria especial</div>
        <div class="sp-item"><span class="sp-ico">💬</span> Atendimento personalizado do início ao fim</div>
        <div class="sp-item"><span class="sp-ico">🛡️</span> Suporte durante toda a viagem</div>
      </div>
      <div class="sp-card">
        <div class="sp-title">Fale pelo WhatsApp</div>
        <div class="sp-item"><span class="sp-ico">📲</span> Prefere falar diretamente? Clique e nos chame agora!</div>
        <a href="https://wa.me/5511999999999" target="_blank" style="display:flex;align-items:center;justify-content:center;gap:9px;margin-top:10px;padding:11px 16px;background:rgba(74,222,128,.1);border:1.5px solid rgba(74,222,128,.3);border-radius:10px;color:var(--green);font-size:.82rem;font-weight:700;text-decoration:none;transition:all .2s;" onmouseover="this.style.background='rgba(74,222,128,.18)'" onmouseout="this.style.background='rgba(74,222,128,.1)'">
          💬 Abrir WhatsApp
        </a>
      </div>
    </aside>

  </div>
</div>

<script>
const API = '/api.php';
let numCri = 1;

function toggleCriancas() {
  const cb = document.getElementById('temCri');
  const sw = document.getElementById('sw');
  const box = document.getElementById('childBox');
  cb.checked = !cb.checked;
  sw.classList.toggle('on', cb.checked);
  box.classList.toggle('show', cb.checked);
  if(cb.checked) renderAges();
}
function mudaCri(d) {
  numCri = Math.max(1, Math.min(10, numCri + d));
  document.getElementById('numCriDisplay').textContent = numCri;
  renderAges();
}
function renderAges() {
  const g = document.getElementById('agesGrid');
  const prev = [...g.querySelectorAll('input')].map(i => i.value);
  g.innerHTML = '';
  for(let i = 0; i < numCri; i++) {
    const d = document.createElement('div'); d.className = 'age-item';
    d.innerHTML = `<label>Criança ${i+1}</label><input type="number" min="0" max="17" placeholder="idade" id="idCri_${i}" value="${prev[i]||''}">`;
    g.appendChild(d);
  }
}
function getCriancas() {
  if(!document.getElementById('temCri').checked) return null;
  const idades = [];
  for(let i = 0; i < numCri; i++) {
    const v = document.getElementById('idCri_' + i)?.value;
    idades.push(v !== '' && v != null ? parseInt(v) : null);
  }
  return {quantidade: numCri, idades};
}

async function enviar() {
  const nome    = document.getElementById('fNome').value.trim();
  const tel     = document.getElementById('fTel').value.trim();
  const email   = document.getElementById('fEmail').value.trim();
  const destino = document.getElementById('fDestino').value.trim();
  const errBox  = document.getElementById('msgErr');
  errBox.style.display = 'none';

  if(!nome || !tel || !destino) {
    errBox.textContent = '⚠️ Por favor, preencha Nome, Telefone e Destino.';
    errBox.style.display = 'block';
    errBox.scrollIntoView({behavior:'smooth',block:'center'});
    return;
  }
  const btn = document.getElementById('btnEnviar');
  const txt = document.getElementById('btnTxt');
  btn.disabled = true; txt.textContent = 'Enviando…';
  try {
    const contato = tel + (email ? ' / ' + email : '');
    const res = await fetch(API + '?action=cotacao', {
      method: 'POST', headers: {'Content-Type':'application/json'},
      body: JSON.stringify({
        nome, contato, destino,
        origem:     document.getElementById('fOrigem').value.trim(),
        data_ida:   document.getElementById('fIda').value || null,
        data_volta: document.getElementById('fVolta').value || null,
        pessoas:    parseInt(document.getElementById('fPessoas').value),
        orcamento:  document.getElementById('fOrcamento').value || null,
        obs:        document.getElementById('fObs').value.trim(),
        criancas:   getCriancas(),
      })
    });
    const data = await res.json();
    if(res.ok && data.ok) {
      document.getElementById('formFields').style.display = 'none';
      const ok = document.getElementById('msgOk');
      ok.style.display = 'flex';
      ok.scrollIntoView({behavior:'smooth',block:'center'});
    } else throw new Error(data.error || 'Erro ao enviar');
  } catch(e) {
    errBox.textContent = '❌ ' + e.message; errBox.style.display = 'block';
    btn.disabled = false; txt.textContent = 'Solicitar Minha Cotação';
  }
}
</script>
</body>
</html>

<?php
require_once 'config.php';
try {
    db()->exec("CREATE TABLE IF NOT EXISTS cotacoes (
        id          INT AUTO_INCREMENT PRIMARY KEY,
        nome        VARCHAR(200) NOT NULL,
        contato     VARCHAR(200) NOT NULL,
        destino     VARCHAR(200) NOT NULL,
        origem      VARCHAR(200),
        data_ida    DATE,
        data_volta  DATE,
        pessoas     INT DEFAULT 1,
        orcamento   DECIMAL(12,2),
        observacoes TEXT,
        criancas    JSON,
        created_at  TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;");
    echo '<h2 style="font-family:sans-serif;color:green">✅ Tabela criada com sucesso!</h2>';
    echo '<p style="font-family:sans-serif">Pode deletar este arquivo do servidor.</p>';
} catch (Exception $e) {
    echo '<h2 style="font-family:sans-serif;color:red">❌ Erro: ' . $e->getMessage() . '</h2>';
}


<?php
require_once 'config.php';
header('Content-Type: application/json');
header('Access-Control-Allow-Origin: *');
header('Access-Control-Allow-Methods: GET, POST, OPTIONS');
header('Access-Control-Allow-Headers: Content-Type');

if ($_SERVER['REQUEST_METHOD'] === 'OPTIONS') { http_response_code(204); exit; }

$action = $_GET['action'] ?? '';

if ($action === 'cotacao' && $_SERVER['REQUEST_METHOD'] === 'POST') {
    $data = json_decode(file_get_contents('php://input'), true);
    if (!$data) { http_response_code(400); echo json_encode(['error' => 'JSON inválido']); exit; }

    $nome      = trim($data['nome']      ?? '');
    $contato   = trim($data['contato']   ?? '');
    $destino   = trim($data['destino']   ?? '');
    $origem    = trim($data['origem']    ?? '');
    $data_ida  = $data['data_ida']       ?? null;
    $data_volta= $data['data_volta']     ?? null;
    $pessoas   = intval($data['pessoas'] ?? 1);
    $orcamento = $data['orcamento']      ?? null;
    $obs       = trim($data['obs']       ?? '');
    $criancas  = isset($data['criancas']) && $data['criancas'] ? json_encode($data['criancas']) : null;

    if (!$nome || !$contato || !$destino) {
        http_response_code(422);
        echo json_encode(['error' => 'Campos obrigatórios: nome, contato, destino']);
        exit;
    }

    $stmt = db()->prepare("INSERT INTO cotacoes
        (nome, contato, destino, origem, data_ida, data_volta, pessoas, orcamento, observacoes, criancas)
        VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?, ?)");
    $stmt->execute([$nome, $contato, $destino, $origem, $data_ida, $data_volta, $pessoas, $orcamento ?: null, $obs, $criancas]);

    echo json_encode(['ok' => true, 'id' => db()->lastInsertId()]);

} elseif ($action === 'listar' && $_SERVER['REQUEST_METHOD'] === 'GET') {
    $rows = db()->query("SELECT * FROM cotacoes ORDER BY id DESC")->fetchAll();
    echo json_encode($rows);

} else {
    http_response_code(404);
    echo json_encode(['error' => 'Ação não encontrada']);
}
<?php
function db(): PDO {
    static $pdo;
    if (!$pdo) {
        $pdo = new PDO(
            'mysql:host=localhost;dbname=voyager;charset=utf8mb4',
            'root',
            '',
            [PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
             PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC]
        );
    }
    return $pdo;
}
[ViewState]
Mode=
Vid=
FolderType=Generic

<?php
require_once 'config.php';
$rows = db()->query("SELECT * FROM cotacoes ORDER BY id DESC")->fetchAll(PDO::FETCH_ASSOC);
$total = count($rows);
$hoje  = count(array_filter($rows, fn($r) => date('Y-m-d', strtotime($r['created_at'])) === date('Y-m-d')));
$destinos = count(array_unique(array_column($rows, 'destino')));
?>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Painel de Cotações · Rota Encantada</title>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Nunito:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #120829; --bg2: #1A0F3A;
    --card: rgba(255,255,255,0.04); --card-h: rgba(255,255,255,0.07);
    --border: rgba(255,255,255,0.1); --border-g: rgba(212,168,67,0.3);
    --gold: #D4A843; --gold2: #F2CF6A; --gold-dim: rgba(212,168,67,0.15);
    --purple: #7C3FBF; --purple-d: rgba(124,63,191,0.2);
    --teal: #2ABFBF; --coral: #FF6B8A;
    --w90: rgba(255,255,255,.9); --w70: rgba(255,255,255,.7);
    --w40: rgba(255,255,255,.4); --w20: rgba(255,255,255,.2);
    --r: 12px;
  }
  *, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
  body {
    font-family: 'Nunito', sans-serif; background: var(--bg); color: white; min-height: 100vh;
  }
  body::before {
    content: ''; position: fixed; inset: 0; z-index: 0; pointer-events: none;
    background:
      radial-gradient(ellipse 80% 50% at 20% 0%, rgba(124,63,191,.25) 0%, transparent 55%),
      radial-gradient(ellipse 60% 60% at 85% 100%, rgba(212,168,67,.1) 0%, transparent 50%),
      linear-gradient(180deg, #120829 0%, #0D0520 100%);
  }
  .shell { position: relative; z-index: 1; display: flex; flex-direction: column; min-height: 100vh; }

  header {
    display: flex; align-items: center; justify-content: space-between;
    padding: 16px 36px;
    background: rgba(18,8,41,.8); backdrop-filter: blur(16px);
    border-bottom: 1px solid var(--border-g);
    position: sticky; top: 0; z-index: 100;
  }
  .hd-left { display:flex; align-items:center; gap:14px; }
  .hd-icon { width:40px; height:40px; border-radius:10px; background:linear-gradient(135deg,rgba(212,168,67,.3),rgba(212,168,67,.1)); border:1px solid var(--border-g); display:flex; align-items:center; justify-content:center; font-size:1.1rem; box-shadow:0 0 16px rgba(212,168,67,.2); }
  .hd-title { font-family:'Cinzel',serif; font-size:1.05rem; font-weight:700; }
  .hd-sub { font-size:.67rem; letter-spacing:1.5px; text-transform:uppercase; color:var(--w40); margin-top:1px; }
  .hd-badge { display:flex; align-items:center; gap:7px; background:rgba(42,191,191,.1); border:1px solid rgba(42,191,191,.3); border-radius:20px; padding:5px 14px; font-size:.7rem; color:var(--teal); letter-spacing:1px; text-transform:uppercase; font-weight:700; }
  .hd-badge::before { content:''; width:6px; height:6px; background:var(--teal); border-radius:50%; animation:blink 2s infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:.2} }

  .stats { display:flex; gap:16px; padding:24px 36px 8px; animation:fadeDown .6s ease both; }
  .stat { flex:1; background:var(--card); border:1px solid var(--border); border-radius:var(--r); padding:18px 20px; display:flex; align-items:center; gap:14px; transition:all .2s; }
  .stat:hover { background:var(--card-h); border-color:var(--border-g); }
  .stat-ic { width:42px; height:42px; border-radius:10px; flex-shrink:0; display:flex; align-items:center; justify-content:center; font-size:1.2rem; }
  .stat-ic.gold   { background:rgba(212,168,67,.15); border:1px solid rgba(212,168,67,.3); }
  .stat-ic.teal   { background:rgba(42,191,191,.1);  border:1px solid rgba(42,191,191,.3); }
  .stat-ic.purple { background:rgba(124,63,191,.15); border:1px solid rgba(124,63,191,.3); }
  .stat-num { font-family:'Cinzel',serif; font-size:1.6rem; font-weight:700; line-height:1; }
  .stat-num.gold   { color:var(--gold); }
  .stat-num.teal   { color:var(--teal); }
  .stat-num.purple { color:#A87BF5; }
  .stat-label { font-size:.72rem; color:var(--w40); margin-top:3px; text-transform:uppercase; letter-spacing:.8px; font-weight:600; }

  .content { padding:20px 36px 48px; animation:fadeUp .7s .1s ease both; opacity:0; }
  .section-head { display:flex; align-items:center; justify-content:space-between; margin-bottom:16px; }
  .section-title { font-family:'Cinzel',serif; font-size:1rem; font-weight:600; color:var(--w90); display:flex; align-items:center; gap:10px; }
  .section-title::before { content:'✦'; font-size:.5rem; color:var(--gold); }
  .count-badge { background:var(--gold-dim); border:1px solid var(--border-g); border-radius:20px; padding:3px 12px; font-size:.72rem; color:var(--gold); font-weight:700; }

  .table-wrap { background:rgba(26,15,58,.6); border:1px solid var(--border-g); border-radius:16px; overflow:hidden; box-shadow:0 20px 60px rgba(0,0,0,.4); }
  .shimmer { height:2px; background:linear-gradient(90deg,var(--purple) 0%,var(--gold) 30%,#C93FC0 60%,var(--gold2) 80%,var(--purple) 100%); background-size:300% 100%; animation:shimmerBar 4s linear infinite; }
  @keyframes shimmerBar { 0%{background-position:100% 0} 100%{background-position:-100% 0} }

  table { width:100%; border-collapse:collapse; }
  thead tr { background:rgba(212,168,67,.08); border-bottom:1px solid rgba(212,168,67,.2); }
  th { padding:13px 18px; font-size:.67rem; text-transform:uppercase; letter-spacing:1.5px; color:var(--gold); font-weight:700; text-align:left; white-space:nowrap; }
  tbody tr { border-bottom:1px solid rgba(255,255,255,.05); transition:background .15s; }
  tbody tr:last-child { border-bottom:none; }
  tbody tr:hover { background:rgba(255,255,255,.04); }
  td { padding:14px 18px; font-size:.88rem; color:var(--w90); vertical-align:middle; }

  .td-name { font-weight:700; }
  .td-dest { display:inline-flex; align-items:center; gap:6px; background:var(--purple-d); border:1px solid rgba(124,63,191,.35); border-radius:6px; padding:3px 10px; font-size:.82rem; color:#C4A0FF; font-weight:600; }
  .td-people { display:inline-flex; align-items:center; justify-content:center; background:rgba(42,191,191,.1); border:1px solid rgba(42,191,191,.25); border-radius:6px; padding:3px 10px; font-size:.82rem; color:var(--teal); font-weight:700; }
  .td-date { font-size:.82rem; color:var(--w70); white-space:nowrap; }
  .ch-pill { display:inline-flex; align-items:center; gap:5px; background:rgba(212,168,67,.1); border:1px solid rgba(212,168,67,.25); border-radius:20px; padding:2px 8px; font-size:.72rem; color:var(--gold); font-weight:700; }
  .empty { text-align:center; padding:60px 24px; color:var(--w40); font-size:.9rem; }
  .empty-icon { font-size:3rem; margin-bottom:12px; opacity:.5; }

  @keyframes fadeDown { from{opacity:0;transform:translateY(-12px)} to{opacity:1;transform:translateY(0)} }
  @keyframes fadeUp   { from{opacity:0;transform:translateY(14px)}  to{opacity:1;transform:translateY(0)} }

  @media(max-width:900px) {
    header { padding:14px 20px; } .stats { padding:16px 20px 4px; flex-wrap:wrap; } .content { padding:16px 20px 40px; }
  }
  @media(max-width:640px) {
    th:nth-child(n+5), td:nth-child(n+5) { display:none; }
  }
</style>
</head>
<body>
<div class="shell">
  <header>
    <div class="hd-left">
      <div class="hd-icon">✦</div>
      <div>
        <div class="hd-title">Rota Encantada Viagens</div>
        <div class="hd-sub">Painel de Cotações · Voyager</div>
      </div>
    </div>
    <div class="hd-badge">Painel Admin</div>
  </header>

  <div class="stats">
    <div class="stat">
      <div class="stat-ic gold">📋</div>
      <div><div class="stat-num gold"><?= $total ?></div><div class="stat-label">Total de Cotações</div></div>
    </div>
    <div class="stat">
      <div class="stat-ic teal">🌟</div>
      <div><div class="stat-num teal"><?= $hoje ?></div><div class="stat-label">Recebidas Hoje</div></div>
    </div>
    <div class="stat">
      <div class="stat-ic purple">✈️</div>
      <div><div class="stat-num purple"><?= $destinos ?></div><div class="stat-label">Destinos Distintos</div></div>
    </div>
  </div>

  <div class="content">
    <div class="section-head">
      <div class="section-title">Solicitações de Cotação</div>
      <span class="count-badge"><?= $total ?> registros</span>
    </div>
    <div class="table-wrap">
      <div class="shimmer"></div>
      <?php if(empty($rows)): ?>
        <div class="empty"><div class="empty-icon">🌙</div><div>Nenhuma cotação recebida ainda.</div></div>
      <?php else: ?>
      <table>
        <thead>
          <tr>
            <th>#</th><th>Nome</th><th>Contato</th><th>Destino</th>
            <th>Pessoas</th><th>Crianças</th><th>Observações</th><th>Data</th>
          </tr>
        </thead>
        <tbody>
        <?php foreach($rows as $r): ?>
          <?php
            $criancas = json_decode($r['criancas'] ?? 'null', true);
            $dt = new DateTime($r['created_at']);
          ?>
          <tr>
            <td style="color:var(--w40);font-size:.78rem;">#<?= $r['id'] ?></td>
            <td class="td-name"><?= htmlspecialchars($r['nome']) ?></td>
            <td style="font-size:.82rem;color:var(--w70);"><?= htmlspecialchars($r['contato']) ?></td>
            <td><span class="td-dest">✈ <?= htmlspecialchars($r['destino']) ?></span></td>
            <td><span class="td-people"><?= $r['pessoas'] ?> 👤</span></td>
            <td>
              <?php if($criancas && isset($criancas['quantidade'])): ?>
                <span class="ch-pill">🧒 <?= $criancas['quantidade'] ?></span>
              <?php else: ?>
                <span style="color:var(--w20);">—</span>
              <?php endif; ?>
            </td>
            <td style="font-size:.8rem;color:var(--w70);max-width:200px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;">
              <?= htmlspecialchars($r['observacoes'] ?? '—') ?>
            </td>
            <td class="td-date"><?= $dt->format('d/m/Y H:i') ?></td>
          </tr>
        <?php endforeach; ?>
        </tbody>
      </table>
      <?php endif; ?>
    </div>
  </div>
</div>
</body>
</html>

════════════════════════════════════════════════
  ROTA ENCANTADA VIAGENS · Sistema de Cotações
════════════════════════════════════════════════

ARQUIVOS DO PROJETO
────────────────────
  index.html     → Formulário público para clientes (página inicial)
  agentes.php    → Portal dos agentes (área privada da equipe)
  painel.php     → Painel administrativo (área privada)
  api.php        → API REST — recebe e lista cotações
  config.php     → Configuração do banco de dados
  instalar.php   → Cria a tabela no banco (rodar uma vez, depois deletar)

COMO INSTALAR
────────────────────
1. Faça upload de todos os arquivos para seu servidor (raiz ou pasta desejada)

2. Abra config.php e ajuste as credenciais do banco de dados:
     host    → geralmente 'localhost'
     dbname  → nome do seu banco (ex: 'voyager' ou o nome da sua conta)
     usuário → seu usuário MySQL
     senha   → sua senha MySQL

3. Acesse no navegador:
     https://seusite.com/instalar.php
   Isso cria a tabela. Após aparecer "✅ Tabela criada", DELETE o instalar.php.

4. Pronto! Acesse:
     /index.html    → clientes pedem cotação
     /agentes.php   → equipe registra e gerencia cotações
     /painel.php    → visão administrativa completa

SEGURANÇA RECOMENDADA
────────────────────
  • Proteja /agentes.php e /painel.php com senha via .htaccess
    ou adicione uma tela de login (posso criar para você)
  • Delete instalar.php após a instalação
  • Nunca compartilhe o config.php

SUPORTE
────────────────────
  Desenvolvido com ❤ para Rota Encantada Viagens
════════════════════════════════════════════════

app 
