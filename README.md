# PAINEL-OLIVEIRA-
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>FF AIM PRO</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
* { box-sizing: border-box; }

body {
  margin: 0;
  background: linear-gradient(180deg, #050b18, #020617);
  font-family: Arial, sans-serif;
  color: #ffffff;
}

header {
  text-align: center;
  padding: 15px;
  border-bottom: 1px solid #0a2a4a;
}

header h1 {
  margin: 0;
  color: #00aaff;
  font-size: 22px;
}

header p {
  margin: 5px 0 0;
  font-size: 12px;
  color: #8fbce6;
}

/* Mira */
.crosshair {
  position: fixed;
  top: 50%;
  left: 50%;
  width: 20px;
  height: 20px;
  border: 2px solid #00aaff;
  transform: translate(-50%, -50%);
  pointer-events: none;
}

/* FOV Circular */
.fov {
  position: fixed;
  top: 50%;
  left: 50%;
  width: 120px;
  height: 120px;
  border: 2px solid #00aaff;
  border-radius: 50%;
  transform: translate(-50%, -50%);
  pointer-events: none;
  opacity: 0.4;
  box-shadow: 0 0 20px rgba(0,170,255,0.4);
}

/* Painel */
.panel {
  position: fixed;
  bottom: 15px;
  left: 50%;
  transform: translateX(-50%);
  width: 92%;
  background: rgba(10, 30, 60, 0.95);
  padding: 15px;
  border-radius: 15px;
  box-shadow: 0 0 15px rgba(0,170,255,0.3);
}

.panel label {
  font-size: 12px;
  color: #9ad7ff;
}

.panel input {
  width: 100%;
  margin-bottom: 10px;
}

button {
  width: 100%;
  padding: 10px;
  margin-top: 6px;
  border: none;
  border-radius: 10px;
  background: linear-gradient(135deg, #00aaff, #0066cc);
  color: #001018;
  font-weight: bold;
  font-size: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

/* Botão MAX */
.ff-btn.max {
  background: linear-gradient(135deg, #4da6ff, #1a75ff);
}

/* Ícones */
.icon svg {
  width: 20px;
  height: 20px;
  fill: #001018;
}
</style>
</head>

<body>

<header>
  <h1>FF AIM PRO</h1>
  <p>Auxílio visual profissional</p>
</header>

<div class="crosshair" id="crosshair"></div>
<div class="fov" id="fov"></div>

<div class="panel">

  <label>Cor da mira</label>
  <input type="color" id="color" value="#00aaff">

  <label>Tamanho da mira</label>
  <input type="range" id="size" min="10" max="40" value="20">

  <label>Espessura da mira</label>
  <input type="range" id="thickness" min="1" max="5" value="2">

  <button id="toggleCross">Ativar / Desativar Mira</button>

  <label>Tamanho do FOV</label>
  <input type="range" id="fovSize" min="50" max="300" value="120">

  <label>Opacidade do FOV</label>
  <input type="range" id="fovOpacity" min="0" max="100" value="40">

  <button id="toggleFov">Ativar / Desativar FOV</button>

  <button class="ff-btn" id="ffNormal">
    <span class="icon">
      <svg viewBox="0 0 24 24">
        <path d="M13 2L3 14h7l-1 8 10-12h-7z"/>
      </svg>
    </span>
    Free Fire
  </button>

  <button class="ff-btn max" id="ffMax">
    <span class="icon">
      <svg viewBox="0 0 24 24">
        <path d="M12 2l4 8 8 1-6 6 1 9-7-4-7 4 1-9-6-6 8-1z"/>
      </svg>
    </span>
    Free Fire MAX
  </button>

</div>

<script>
const crosshair = document.getElementById("crosshair");
const fov = document.getElementById("fov");

const color = document.getElementById("color");
const size = document.getElementById("size");
const thickness = document.getElementById("thickness");

const fovSize = document.getElementById("fovSize");
const fovOpacity = document.getElementById("fovOpacity");

const toggleCross = document.getElementById("toggleCross");
const toggleFov = document.getElementById("toggleFov");

const ffNormal = document.getElementById("ffNormal");
const ffMax = document.getElementById("ffMax");

let crossAtivo = true;
let fovAtivo = true;

color.oninput = () => crosshair.style.borderColor = color.value;

size.oninput = () => {
  crosshair.style.width = size.value + "px";
  crosshair.style.height = size.value + "px";
};

thickness.oninput = () =>
  crosshair.style.borderWidth = thickness.value + "px";

toggleCross.onclick = () => {
  crossAtivo = !crossAtivo;
  crosshair.style.display = crossAtivo ? "block" : "none";
};

fovSize.oninput = () => {
  fov.style.width = fovSize.value + "px";
  fov.style.height = fovSize.value + "px";
};

fovOpacity.oninput = () =>
  fov.style.opacity = fovOpacity.value / 100;

toggleFov.onclick = () => {
  fovAtivo = !fovAtivo;
  fov.style.display = fovAtivo ? "block" : "none";
};

ffNormal.onclick = () =>
  window.location.href =
  "https://play.google.com/store/apps/details?id=com.dts.freefireth";

ffMax.onclick = () =>
  window.location.href =
  "https://play.google.com/store/apps/details?id=com.dts.freefiremax";
</script>

</body>
</html>
