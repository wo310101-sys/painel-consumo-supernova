<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Minha Casa — Consumo</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:        #f7f6f3;
      --surface:   #ffffff;
      --text:      #2b2b27;
      --text2:     #74726b;
      --text3:     #a8a59c;
      --border:    #e8e6e0;

      --gas:       #d9772f;
      --gas-bg:    #fdf1e6;
      --energy:    #2f8f5b;
      --energy-bg: #e9f6ef;
      --water:     #2f7fb8;
      --water-bg:  #e9f3fb;

      --radius:    16px;
      --radius-sm: 10px;
    }

    body {
      font-family: -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
    }

    header {
      text-align: center;
      padding: 32px 20px 24px;
    }

    header .emoji {
      font-size: 38px;
      margin-bottom: 6px;
    }

    header h1 {
      font-size: 22px;
      font-weight: 700;
      color: var(--text);
    }

    header p {
      font-size: 14px;
      color: var(--text2);
      margin-top: 6px;
    }

    .status-line {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      margin-top: 14px;
      font-size: 13px;
      color: var(--text2);
    }

    .dot { width: 8px; height: 8px; border-radius: 50%; background: #ccc; flex-shrink: 0; }
    .dot.ok      { background: var(--energy); }
    .dot.err     { background: #c94a3f; }
    .dot.loading { background: var(--gas); animation: blink 1s infinite; }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.3} }

    main {
      max-width: 640px;
      margin: 0 auto;
      padding: 0 16px 40px;
    }

    /* ── BLOCO DE CADA SERVIÇO ────────────────────────────── */
    .servico {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 22px 22px 18px;
      margin-bottom: 18px;
    }

    .servico-titulo {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 16px;
    }

    .servico-titulo .icone {
      width: 38px; height: 38px;
      border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
      font-size: 19px;
      flex-shrink: 0;
    }

    .servico.gas    .icone { background: var(--gas-bg); }
    .servico.energia .icone { background: var(--energy-bg); }
    .servico.agua   .icone { background: var(--water-bg); }

    .servico-titulo h2 {
      font-size: 17px;
      font-weight: 600;
    }

    .servico-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .dado {
      background: var(--bg);
      border-radius: var(--radius-sm);
      padding: 14px 16px;
      text-align: center;
    }

    .dado .rotulo {
      font-size: 12px;
      color: var(--text2);
      margin-bottom: 6px;
    }

    .dado .numero {
      font-size: 26px;
      font-weight: 700;
      line-height: 1.1;
    }

    .servico.gas    .numero { color: var(--gas); }
    .servico.energia .numero { color: var(--energy); }
    .servico.agua   .numero { color: var(--water); }

    .dado .numero.carregando { color: var(--text3); font-size: 18px; }

    .dado .unidade {
      font-size: 11px;
      color: var(--text3);
      margin-top: 3px;
    }

    /* ── RESUMO TOTAL ──────────────────────────────────────── */
    .resumo {
      background: var(--text);
      border-radius: var(--radius);
      padding: 22px;
      text-align: center;
      margin-bottom: 22px;
      color: #fff;
    }

    .resumo .rotulo {
      font-size: 13px;
      opacity: 0.7;
      margin-bottom: 6px;
    }

    .resumo .numero {
      font-size: 38px;
      font-weight: 700;
    }

    .resumo .numero.carregando { opacity: 0.5; font-size: 24px; }

    /* ── BOTÃO ATUALIZAR ───────────────────────────────────── */
    .botao-area {
      text-align: center;
      margin-bottom: 22px;
    }

    .botao {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 99px;
      padding: 12px 26px;
      font-size: 14px;
      font-weight: 600;
      color: var(--text);
      cursor: pointer;
    }

    .botao:active { transform: scale(0.97); }

    /* ── AVISO DE ERRO ─────────────────────────────────────── */
    .aviso {
      display: none;
      background: #fdecea;
      border: 1px solid #f3c4bf;
      border-radius: var(--radius-sm);
      padding: 14px 16px;
      font-size: 13px;
      color: #a33a30;
      margin-bottom: 20px;
      text-align: center;
    }
    .aviso.visivel { display: block; }

    footer {
      text-align: center;
      font-size: 12px;
      color: var(--text3);
      padding-bottom: 20px;
    }

    @media (max-width: 380px) {
      .servico-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<header>
  <div class="emoji">🏠</div>
  <h1>Consumo da Minha Casa</h1>
  <p>Acompanhe gás, energia e água em tempo real</p>
  <div class="status-line">
    <div class="dot loading" id="dot"></div>
    <span id="status-text">carregando...</span>
  </div>
</header>

<main>

  <!-- RESUMO -->
  <div class="resumo">
    <div class="rotulo">Gasto total estimado hoje</div>
    <div class="numero carregando" id="total-gasto">—</div>
  </div>

  <div class="botao-area">
    <button class="botao" onclick="buscarDados()">
      🔄 Atualizar agora
    </button>
  </div>

  <div class="aviso" id="aviso">
    Não foi possível buscar os dados agora. Verifique sua internet e tente novamente.
  </div>

  <!-- GÁS -->
  <div class="servico gas">
    <div class="servico-titulo">
      <div class="icone">🔥</div>
      <h2>Gás</h2>
    </div>
    <div class="servico-grid">
      <div class="dado">
        <div class="rotulo">Quanto sobra no botijão</div>
        <div class="numero carregando" id="gas-volume">—</div>
        <div class="unidade">% do botijão</div>
      </div>
      <div class="dado">
        <div class="rotulo">Quanto já gastou</div>
        <div class="numero carregando" id="gas-valor">—</div>
        <div class="unidade">reais</div>
      </div>
    </div>
  </div>

  <!-- ENERGIA -->
  <div class="servico energia">
    <div class="servico-titulo">
      <div class="icone">⚡</div>
      <h2>Energia</h2>
    </div>
    <div class="servico-grid">
      <div class="dado">
        <div class="rotulo">Quanto está consumindo</div>
        <div class="numero carregando" id="energia-consumo">—</div>
        <div class="unidade">kWh</div>
      </div>
      <div class="dado">
        <div class="rotulo">Quanto já gastou</div>
        <div class="numero carregando" id="energia-valor">—</div>
        <div class="unidade">reais</div>
      </div>
    </div>
  </div>

  <!-- ÁGUA -->
  <div class="servico agua">
    <div class="servico-titulo">
      <div class="icone">💧</div>
      <h2>Água</h2>
    </div>
    <div class="servico-grid">
      <div class="dado">
        <div class="rotulo">Quanto está consumindo</div>
        <div class="numero carregando" id="agua-consumo">—</div>
        <div class="unidade">metros cúbicos (m³)</div>
      </div>
      <div class="dado">
        <div class="rotulo">Quanto já gastou</div>
        <div class="numero carregando" id="agua-valor">—</div>
        <div class="unidade">reais</div>
      </div>
    </div>
  </div>

</main>

<footer>
  Os dados são atualizados automaticamente a cada 20 segundos.
</footer>

<script>
  // ─── CONFIGURAÇÃO ────────────────────────────────────────
  // ID do canal no ThingSpeak
  var CANAL_ID = "2066280";

  // Mapeamento dos campos do ThingSpeak (conforme cadastrado):
  // Field 1: GLP VOLUME      → field1
  // Field 2: GLR R$ (gás)    → field2
  // Field 3: VALOR kW/h      → field3
  // Field 4: CONSUMO kW/h    → field4
  // Field 5: CONSUMO M³      → field5
  // Field 6: VALOR M³        → field6

  var INTERVALO_MS = 20000; // 20 segundos

  function setStatus(estado, texto) {
    document.getElementById('dot').className = 'dot ' + estado;
    document.getElementById('status-text').textContent = texto;
  }

  function mostrarAviso(mostrar) {
    var aviso = document.getElementById('aviso');
    if (mostrar) {
      aviso.classList.add('visivel');
    } else {
      aviso.classList.remove('visivel');
    }
  }

  function formatarNumero(valor, casas) {
    var n = parseFloat(valor);
    if (isNaN(n)) return "—";
    return n.toFixed(casas !== undefined ? casas : 2);
  }

  function preencher(id, texto) {
    var el = document.getElementById(id);
    el.textContent = texto;
    el.classList.remove('carregando');
  }

  function buscarDados() {
    setStatus('loading', 'atualizando...');

    var url = "https://api.thingspeak.com/channels/" + CANAL_ID + "/feeds/last.json";

    var xhr = new XMLHttpRequest();
    xhr.open("GET", url, true);
    xhr.timeout = 8000;

    xhr.onload = function () {
      if (xhr.status !== 200) {
        falhou();
        return;
      }
      try {
        var dados = JSON.parse(xhr.responseText);

        if (!dados || !dados.created_at) {
          falhou();
          return;
        }

        var glpVolume   = formatarNumero(dados.field1, 1);
        var glpValor    = formatarNumero(dados.field2, 2);
        var energiaValorKwh = formatarNumero(dados.field3, 3);
        var energiaConsumo  = formatarNumero(dados.field4, 3);
        var aguaConsumo = formatarNumero(dados.field5, 3);
        var aguaValor   = formatarNumero(dados.field6, 2);

        preencher('gas-volume', glpVolume);
        preencher('gas-valor', glpValor);
        preencher('energia-consumo', energiaConsumo);
        preencher('energia-valor', energiaValorKwh);
        preencher('agua-consumo', aguaConsumo);
        preencher('agua-valor', aguaValor);

        var total = (parseFloat(dados.field2) || 0)
                  + (parseFloat(dados.field3) || 0)
                  + (parseFloat(dados.field6) || 0);
        preencher('total-gasto', 'R$ ' + total.toFixed(2));

        setStatus('ok', 'atualizado agora');
        mostrarAviso(false);

      } catch (e) {
        falhou();
      }
    };

    xhr.onerror = falhou;
    xhr.ontimeout = falhou;

    xhr.send();
  }

  function falhou() {
    setStatus('err', 'sem conexão');
    mostrarAviso(true);
  }

  // Inicia e repete automaticamente
  buscarDados();
  setInterval(buscarDados, INTERVALO_MS);
</script>

</body>
</html>
