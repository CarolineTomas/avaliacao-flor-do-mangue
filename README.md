# avaliacao-flor-do-mangue
<!DOCTYPE html>

<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Avaliação de Atendimento – Flor do Mangue</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<style>
  :root {
    --verde: #1a3c2e;
    --verde-medio: #2d6a4f;
    --verde-claro: #52b788;
    --ouro: #c9a84c;
    --ouro-claro: #f4d47a;
    --creme: #faf6ef;
    --branco: #ffffff;
    --cinza: #6b7280;
    --cinza-claro: #f3f4f6;
    --sombra: 0 4px 24px rgba(26,60,46,0.10);
  }

- { box-sizing: border-box; margin: 0; padding: 0; }

body {
font-family: ‘DM Sans’, sans-serif;
background: var(–creme);
min-height: 100vh;
color: var(–verde);
}

/* ===== TELA ADMIN ===== */
#tela-admin {
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
min-height: 100vh;
padding: 32px 16px;
background: linear-gradient(135deg, var(–verde) 0%, var(–verde-medio) 60%, #1b4332 100%);
}

.admin-card {
background: var(–branco);
border-radius: 24px;
padding: 48px 40px;
width: 100%;
max-width: 540px;
box-shadow: 0 24px 80px rgba(0,0,0,0.25);
text-align: center;
}

.logo-area {
margin-bottom: 32px;
}

.logo-icon {
width: 64px;
height: 64px;
margin: 0 auto 12px;
background: var(–verde);
border-radius: 50%;
display: flex;
align-items: center;
justify-content: center;
font-size: 28px;
}

.logo-area h1 {
font-family: ‘Playfair Display’, serif;
font-size: 1.6rem;
color: var(–verde);
line-height: 1.2;
}

.logo-area p {
color: var(–cinza);
font-size: 0.88rem;
margin-top: 4px;
}

.divider {
width: 48px;
height: 3px;
background: var(–ouro);
margin: 20px auto;
border-radius: 2px;
}

.admin-card label {
display: block;
text-align: left;
font-size: 0.82rem;
font-weight: 500;
color: var(–cinza);
text-transform: uppercase;
letter-spacing: 0.08em;
margin-bottom: 8px;
}

.admin-card input {
width: 100%;
padding: 14px 18px;
border: 2px solid #e5e7eb;
border-radius: 12px;
font-size: 1rem;
font-family: ‘DM Sans’, sans-serif;
color: var(–verde);
background: var(–creme);
transition: border-color 0.2s;
outline: none;
margin-bottom: 24px;
}

.admin-card input:focus {
border-color: var(–verde-claro);
}

.btn-gerar {
width: 100%;
padding: 16px;
background: var(–verde);
color: var(–branco);
border: none;
border-radius: 12px;
font-size: 1rem;
font-family: ‘DM Sans’, sans-serif;
font-weight: 500;
cursor: pointer;
transition: background 0.2s, transform 0.1s;
letter-spacing: 0.04em;
}

.btn-gerar:hover { background: var(–verde-medio); transform: translateY(-1px); }
.btn-gerar:active { transform: translateY(0); }

/* QR + link */
.qr-area {
margin-top: 32px;
padding-top: 28px;
border-top: 1px solid #e5e7eb;
display: none;
flex-direction: column;
align-items: center;
gap: 16px;
}

.qr-area.visible { display: flex; }

.qr-label {
font-size: 0.82rem;
color: var(–cinza);
text-transform: uppercase;
letter-spacing: 0.08em;
}

#qrcode canvas, #qrcode img {
border-radius: 12px;
border: 4px solid var(–verde);
}

.link-box {
background: var(–cinza-claro);
border-radius: 10px;
padding: 12px 16px;
width: 100%;
display: flex;
align-items: center;
gap: 10px;
font-size: 0.85rem;
color: var(–verde-medio);
word-break: break-all;
cursor: pointer;
border: 1.5px solid transparent;
transition: border-color 0.2s;
}

.link-box:hover { border-color: var(–verde-claro); }

.link-box .copy-icon { font-size: 16px; flex-shrink: 0; }

.copy-feedback {
font-size: 0.78rem;
color: var(–verde-claro);
font-weight: 500;
display: none;
}

.btn-abrir {
width: 100%;
padding: 14px;
background: var(–ouro);
color: var(–verde);
border: none;
border-radius: 12px;
font-size: 0.95rem;
font-family: ‘DM Sans’, sans-serif;
font-weight: 600;
cursor: pointer;
transition: background 0.2s;
}

.btn-abrir:hover { background: var(–ouro-claro); }

/* ===== TELA AVALIAÇÃO ===== */
#tela-avaliacao {
display: none;
min-height: 100vh;
padding: 0 0 48px;
}

.header-aval {
background: var(–verde);
padding: 40px 24px 32px;
text-align: center;
color: var(–branco);
position: relative;
overflow: hidden;
}

.header-aval::before {
content: ‘’;
position: absolute;
inset: 0;
background: url(“data:image/svg+xml,%3Csvg width=‘60’ height=‘60’ viewBox=‘0 0 60 60’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cg fill=‘none’ fill-rule=‘evenodd’%3E%3Cg fill=’%23ffffff’ fill-opacity=‘0.04’%3E%3Ccircle cx=‘30’ cy=‘30’ r=‘20’/%3E%3C/g%3E%3C/g%3E%3C/svg%3E”) repeat;
}

.header-aval .tag {
display: inline-block;
background: rgba(201,168,76,0.25);
color: var(–ouro-claro);
font-size: 0.72rem;
font-weight: 500;
letter-spacing: 0.12em;
text-transform: uppercase;
padding: 5px 14px;
border-radius: 20px;
margin-bottom: 14px;
border: 1px solid rgba(201,168,76,0.4);
position: relative;
}

.header-aval h2 {
font-family: ‘Playfair Display’, serif;
font-size: 1.7rem;
color: var(–branco);
position: relative;
line-height: 1.25;
}

.header-aval .colaborador-nome {
margin-top: 12px;
font-size: 1.05rem;
color: var(–ouro-claro);
font-weight: 500;
position: relative;
}

.header-aval .subtitulo {
margin-top: 8px;
font-size: 0.85rem;
color: rgba(255,255,255,0.65);
position: relative;
}

.aval-body {
padding: 24px 16px;
max-width: 640px;
margin: 0 auto;
}

.aviso-legal {
background: #fff8e6;
border: 1.5px solid var(–ouro);
border-radius: 12px;
padding: 14px 18px;
font-size: 0.82rem;
color: #7a5f10;
margin-bottom: 28px;
line-height: 1.5;
display: flex;
gap: 10px;
align-items: flex-start;
}

.aviso-legal .icon { font-size: 18px; flex-shrink: 0; margin-top: 1px; }

/* Cartões de critério */
.criterio-card {
background: var(–branco);
border-radius: 18px;
padding: 24px 20px 20px;
margin-bottom: 16px;
box-shadow: var(–sombra);
border: 1.5px solid transparent;
transition: border-color 0.25s, box-shadow 0.25s;
}

.criterio-card.avaliado {
border-color: var(–verde-claro);
box-shadow: 0 4px 24px rgba(82,183,136,0.15);
}

.criterio-header {
display: flex;
align-items: center;
gap: 12px;
margin-bottom: 16px;
}

.criterio-icon {
width: 40px;
height: 40px;
background: var(–creme);
border-radius: 10px;
display: flex;
align-items: center;
justify-content: center;
font-size: 20px;
flex-shrink: 0;
}

.criterio-info h3 {
font-size: 1rem;
font-weight: 600;
color: var(–verde);
}

.criterio-info p {
font-size: 0.78rem;
color: var(–cinza);
margin-top: 2px;
}

.nota-badge {
margin-left: auto;
min-width: 38px;
height: 38px;
border-radius: 50%;
background: var(–verde);
color: var(–branco);
font-weight: 700;
font-size: 1.1rem;
display: none;
align-items: center;
justify-content: center;
flex-shrink: 0;
transition: background 0.2s;
}

.nota-badge.visivel { display: flex; }

/* Botões 0-10 */
.notas-grid {
display: grid;
grid-template-columns: repeat(11, 1fr);
gap: 5px;
}

@media (max-width: 480px) {
.notas-grid {
grid-template-columns: repeat(6, 1fr);
gap: 6px;
}
}

.nota-btn {
aspect-ratio: 1;
border: 2px solid #e5e7eb;
border-radius: 10px;
background: var(–creme);
font-size: 0.9rem;
font-weight: 600;
font-family: ‘DM Sans’, sans-serif;
color: var(–cinza);
cursor: pointer;
transition: all 0.15s;
display: flex;
align-items: center;
justify-content: center;
}

.nota-btn:hover { border-color: var(–verde-claro); color: var(–verde); transform: scale(1.08); }

.nota-btn.selecionado {
background: var(–verde);
border-color: var(–verde);
color: var(–branco);
transform: scale(1.1);
}

.nota-btn.nota-0, .nota-btn.nota-1, .nota-btn.nota-2 { }
.nota-btn.nota-0.selecionado, .nota-btn.nota-1.selecionado, .nota-btn.nota-2.selecionado { background: #dc2626; border-color: #dc2626; }
.nota-btn.nota-3.selecionado, .nota-btn.nota-4.selecionado, .nota-btn.nota-5.selecionado, .nota-btn.nota-6.selecionado { background: #d97706; border-color: #d97706; }
.nota-btn.nota-7.selecionado, .nota-btn.nota-8.selecionado { background: #059669; border-color: #059669; }
.nota-btn.nota-9.selecionado, .nota-btn.nota-10.selecionado { background: #047857; border-color: #047857; }

.escala-legenda {
display: flex;
justify-content: space-between;
margin-top: 8px;
font-size: 0.7rem;
color: var(–cinza);
}

/* Campo comentário */
.comentario-area {
margin-top: 8px;
}

.comentario-area textarea {
width: 100%;
border: 1.5px solid #e5e7eb;
border-radius: 10px;
padding: 12px 14px;
font-family: ‘DM Sans’, sans-serif;
font-size: 0.88rem;
color: var(–verde);
background: var(–creme);
resize: vertical;
min-height: 70px;
outline: none;
transition: border-color 0.2s;
}

.comentario-area textarea:focus { border-color: var(–verde-claro); }

/* Secção comentário geral */
.card-comentario {
background: var(–branco);
border-radius: 18px;
padding: 24px 20px;
margin-bottom: 16px;
box-shadow: var(–sombra);
}

.card-comentario h3 {
font-size: 1rem;
font-weight: 600;
margin-bottom: 4px;
display: flex;
gap: 8px;
align-items: center;
}

.card-comentario p {
font-size: 0.78rem;
color: var(–cinza);
margin-bottom: 12px;
}

.card-comentario textarea {
width: 100%;
border: 1.5px solid #e5e7eb;
border-radius: 10px;
padding: 14px;
font-family: ‘DM Sans’, sans-serif;
font-size: 0.88rem;
color: var(–verde);
background: var(–creme);
resize: vertical;
min-height: 90px;
outline: none;
transition: border-color 0.2s;
}

.card-comentario textarea:focus { border-color: var(–verde-claro); }

/* Progresso */
.progresso-bar {
background: #e5e7eb;
border-radius: 8px;
height: 6px;
margin-bottom: 24px;
overflow: hidden;
}

.progresso-fill {
height: 100%;
background: linear-gradient(90deg, var(–verde-claro), var(–verde));
border-radius: 8px;
transition: width 0.4s ease;
width: 0%;
}

.progresso-texto {
font-size: 0.78rem;
color: var(–cinza);
margin-bottom: 8px;
display: flex;
justify-content: space-between;
}

/* Botão enviar */
.btn-enviar {
width: 100%;
padding: 18px;
background: var(–verde);
color: var(–branco);
border: none;
border-radius: 14px;
font-size: 1.05rem;
font-family: ‘DM Sans’, sans-serif;
font-weight: 600;
cursor: pointer;
transition: all 0.2s;
letter-spacing: 0.04em;
margin-top: 8px;
position: relative;
overflow: hidden;
}

.btn-enviar:hover:not(:disabled) { background: var(–verde-medio); transform: translateY(-1px); box-shadow: 0 6px 20px rgba(26,60,46,0.25); }
.btn-enviar:disabled { opacity: 0.45; cursor: not-allowed; }

/* ===== TELA OBRIGADO ===== */
#tela-obrigado {
display: none;
min-height: 100vh;
align-items: center;
justify-content: center;
flex-direction: column;
padding: 32px 16px;
background: linear-gradient(160deg, var(–verde) 0%, #0f2d1e 100%);
text-align: center;
}

.obrigado-card {
background: var(–branco);
border-radius: 28px;
padding: 52px 40px;
max-width: 440px;
width: 100%;
box-shadow: 0 32px 80px rgba(0,0,0,0.3);
}

.obrigado-icon {
font-size: 56px;
margin-bottom: 20px;
display: block;
animation: pop 0.5s cubic-bezier(0.34,1.56,0.64,1);
}

@keyframes pop {
from { transform: scale(0); opacity: 0; }
to   { transform: scale(1); opacity: 1; }
}

.obrigado-card h2 {
font-family: ‘Playfair Display’, serif;
font-size: 1.8rem;
color: var(–verde);
margin-bottom: 12px;
}

.obrigado-card p {
color: var(–cinza);
font-size: 0.92rem;
line-height: 1.6;
margin-bottom: 16px;
}

.media-display {
background: var(–creme);
border-radius: 14px;
padding: 16px;
margin: 20px 0;
font-size: 2rem;
font-weight: 700;
font-family: ‘Playfair Display’, serif;
color: var(–verde);
}

.media-display small {
display: block;
font-family: ‘DM Sans’, sans-serif;
font-size: 0.78rem;
font-weight: 400;
color: var(–cinza);
margin-top: 2px;
}

.btn-nova {
width: 100%;
padding: 14px;
background: var(–verde);
color: var(–branco);
border: none;
border-radius: 12px;
font-family: ‘DM Sans’, sans-serif;
font-size: 0.9rem;
font-weight: 500;
cursor: pointer;
margin-top: 8px;
transition: background 0.2s;
}

.btn-nova:hover { background: var(–verde-medio); }

.rodape {
margin-top: 32px;
font-size: 0.75rem;
color: rgba(255,255,255,0.4);
}

/* Animações de entrada */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(20px); }
to   { opacity: 1; transform: translateY(0); }
}

.criterio-card, .card-comentario {
animation: fadeUp 0.4s ease both;
}

.criterio-card:nth-child(1) { animation-delay: 0.05s; }
.criterio-card:nth-child(2) { animation-delay: 0.10s; }
.criterio-card:nth-child(3) { animation-delay: 0.15s; }
.criterio-card:nth-child(4) { animation-delay: 0.20s; }
.criterio-card:nth-child(5) { animation-delay: 0.25s; }
.criterio-card:nth-child(6) { animation-delay: 0.30s; }
</style>

</head>
<body>

<!-- ======= TELA ADMIN ======= -->

<div id="tela-admin">
  <div class="admin-card">
    <div class="logo-area">
      <div class="logo-icon">🌸</div>
      <h1>Restaurante<br>Flor do Mangue</h1>
      <p>Sistema de Avaliação de Atendimento</p>
    </div>
    <div class="divider"></div>

```
<label for="nome-colaborador">Nome do colaborador</label>
<input type="text" id="nome-colaborador" placeholder="Ex: João Silva" autocomplete="off">

<button class="btn-gerar" onclick="gerarLink()">✦ Gerar QR Code & Link</button>

<div class="qr-area" id="qr-area">
  <p class="qr-label">📲 Compartilhe com o cliente</p>
  <div id="qrcode"></div>
  <div class="link-box" onclick="copiarLink()">
    <span class="copy-icon">🔗</span>
    <span id="link-texto"></span>
  </div>
  <span class="copy-feedback" id="copy-feedback">✓ Link copiado!</span>
  <button class="btn-abrir" onclick="abrirAvaliacao()">↗ Abrir avaliação agora</button>
</div>
```

  </div>
</div>

<!-- ======= TELA AVALIAÇÃO ======= -->

<div id="tela-avaliacao">
  <div class="header-aval">
    <div class="tag">Avaliação de Atendimento</div>
    <h2>Como foi sua experiência?</h2>
    <p class="colaborador-nome" id="nome-display">— —</p>
    <p class="subtitulo">Suas respostas são anônimas e nos ajudam a melhorar</p>
  </div>

  <div class="aval-body">
    <div class="aviso-legal">
      <span class="icon">🔒</span>
      <span>Esta avaliação é <strong>anônima</strong> e serve exclusivamente para fins de melhoria contínua. As informações são tratadas de forma agregada, em conformidade com a LGPD (Lei nº 13.709/2018).</span>
    </div>

```
<div class="progresso-texto">
  <span id="progresso-label">0 de 6 critérios avaliados</span>
  <span id="progresso-pct">0%</span>
</div>
<div class="progresso-bar"><div class="progresso-fill" id="progresso-fill"></div></div>

<!-- CRITÉRIOS -->
<div id="criterios-container"></div>

<!-- COMENTÁRIO GERAL -->
<div class="card-comentario">
  <h3>💬 Comentário (opcional)</h3>
  <p>Deseja deixar alguma sugestão ou observação sobre sua visita?</p>
  <textarea id="comentario-geral" placeholder="Escreva aqui sua sugestão ou elogio..." rows="3"></textarea>
</div>

<button class="btn-enviar" id="btn-enviar" onclick="enviarAvaliacao()" disabled>
  Enviar Avaliação
</button>
```

  </div>
</div>

<!-- ======= TELA OBRIGADO ======= -->

<div id="tela-obrigado">
  <div class="obrigado-card">
    <span class="obrigado-icon">🌸</span>
    <h2>Muito obrigado!</h2>
    <p>Sua avaliação foi registrada com sucesso. Seu feedback é essencial para continuarmos oferecendo um serviço de excelência.</p>
    <div class="media-display" id="media-display">
      —<small>Nota média desta avaliação</small>
    </div>
    <p style="font-size:0.8rem;color:#9ca3af">Volte sempre ao <strong style="color:var(--verde)">Restaurante Flor do Mangue</strong>! 🌿</p>
    <button class="btn-nova" onclick="novaAvaliacao()">← Nova avaliação</button>
  </div>
  <p class="rodape">Restaurante Flor do Mangue · Sistema de Qualidade</p>
</div>

<script>
// ======= CRITÉRIOS DE AVALIAÇÃO =======
const criterios = [
  {
    id: 'postura',
    icone: '🧍',
    titulo: 'Postura Profissional',
    descricao: 'Apresentação pessoal, organização e conduta'
  },
  {
    id: 'atendimento',
    icone: '🤝',
    titulo: 'Qualidade do Atendimento',
    descricao: 'Eficiência, atenção e resolução das suas necessidades'
  },
  {
    id: 'educacao',
    icone: '🎓',
    titulo: 'Educação e Cortesia',
    descricao: 'Respeito, gentileza e tratamento recebido'
  },
  {
    id: 'simpatia',
    icone: '😊',
    titulo: 'Simpatia e Acolhimento',
    descricao: 'Receptividade e disposição para ajudar'
  },
  {
    id: 'agilidade',
    icone: '⚡',
    titulo: 'Agilidade e Tempo de Espera',
    descricao: 'Rapidez e organização no serviço prestado'
  },
  {
    id: 'satisfacao',
    icone: '⭐',
    titulo: 'Satisfação Geral',
    descricao: 'Sua impressão geral sobre esta visita'
  }
];

let notasSelecionadas = {};
let colaboradorAtual = '';

// ======= ADMIN =======
function gerarLink() {
  const nome = document.getElementById('nome-colaborador').value.trim();
  if (!nome) { alert('Por favor, informe o nome do colaborador.'); return; }

  const encoded = encodeURIComponent(nome);
  const url = `${location.href.split('?')[0]}?colaborador=${encoded}`;

  document.getElementById('link-texto').textContent = url;

  // QR Code
  const qrDiv = document.getElementById('qrcode');
  qrDiv.innerHTML = '';
  new QRCode(qrDiv, { text: url, width: 200, height: 200, colorDark: '#1a3c2e', colorLight: '#ffffff' });

  document.getElementById('qr-area').classList.add('visible');
}

function copiarLink() {
  const link = document.getElementById('link-texto').textContent;
  navigator.clipboard.writeText(link).then(() => {
    const fb = document.getElementById('copy-feedback');
    fb.style.display = 'inline';
    setTimeout(() => fb.style.display = 'none', 2000);
  });
}

function abrirAvaliacao() {
  const link = document.getElementById('link-texto').textContent;
  window.open(link, '_blank');
}

// ======= AVALIAÇÃO =======
function renderCriterios() {
  const container = document.getElementById('criterios-container');
  container.innerHTML = '';
  criterios.forEach((c, idx) => {
    const card = document.createElement('div');
    card.className = 'criterio-card';
    card.id = `card-${c.id}`;
    card.style.animationDelay = `${idx * 0.05 + 0.05}s`;

    const notas = Array.from({length: 11}, (_, i) => `
      <button class="nota-btn nota-${i}" onclick="selecionarNota('${c.id}', ${i}, this)">
        ${i}
      </button>`).join('');

    card.innerHTML = `
      <div class="criterio-header">
        <div class="criterio-icon">${c.icone}</div>
        <div class="criterio-info">
          <h3>${c.titulo}</h3>
          <p>${c.descricao}</p>
        </div>
        <div class="nota-badge" id="badge-${c.id}">—</div>
      </div>
      <div class="notas-grid">${notas}</div>
      <div class="escala-legenda">
        <span>😞 Muito ruim</span>
        <span>😐 Regular</span>
        <span>😄 Excelente</span>
      </div>
    `;
    container.appendChild(card);
  });
}

function selecionarNota(criterioId, nota, btnEl) {
  notasSelecionadas[criterioId] = nota;

  // Visual: desmarcar todos, marcar escolhido
  const card = document.getElementById(`card-${criterioId}`);
  card.querySelectorAll('.nota-btn').forEach(b => b.classList.remove('selecionado'));
  btnEl.classList.add('selecionado');

  // Badge
  const badge = document.getElementById(`badge-${criterioId}`);
  badge.textContent = nota;
  badge.classList.add('visivel');
  card.classList.add('avaliado');

  // Progresso
  atualizarProgresso();
}

function atualizarProgresso() {
  const total = criterios.length;
  const feitos = Object.keys(notasSelecionadas).length;
  const pct = Math.round((feitos / total) * 100);

  document.getElementById('progresso-fill').style.width = pct + '%';
  document.getElementById('progresso-label').textContent = `${feitos} de ${total} critérios avaliados`;
  document.getElementById('progresso-pct').textContent = pct + '%';
  document.getElementById('btn-enviar').disabled = feitos < total;
}

function enviarAvaliacao() {
  const total = criterios.length;
  const feitos = Object.keys(notasSelecionadas).length;
  if (feitos < total) return;

  const soma = Object.values(notasSelecionadas).reduce((a, b) => a + b, 0);
  const media = (soma / total).toFixed(1);

  document.getElementById('media-display').innerHTML = `${media}<small>Nota média desta avaliação</small>`;

  document.getElementById('tela-avaliacao').style.display = 'none';
  const obrigado = document.getElementById('tela-obrigado');
  obrigado.style.display = 'flex';
}

function novaAvaliacao() {
  window.location.href = window.location.pathname;
}

// ======= INICIALIZAÇÃO =======
function init() {
  const params = new URLSearchParams(window.location.search);
  const colaborador = params.get('colaborador');

  if (colaborador) {
    colaboradorAtual = decodeURIComponent(colaborador);
    document.getElementById('tela-admin').style.display = 'none';
    document.getElementById('tela-avaliacao').style.display = 'block';
    document.getElementById('nome-display').textContent = `Colaborador(a): ${colaboradorAtual}`;
    renderCriterios();
  } else {
    document.getElementById('tela-admin').style.display = 'flex';
  }
}

init();
</script>

</body>
</html>