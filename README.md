<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RAJ FF - Colour Panel</title>
<script src="https://cdn.tailwindcss.com"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Orbitron:wght@700;800;900&display=swap" rel="stylesheet">
<style>
body{ background:#06070a; font-family:'Inter',sans-serif; min-height:100vh; }
.glass-panel{ background:rgba(15,18,25,0.85); backdrop-filter:blur(16px); border:1px solid rgba(255,255,255,0.1); box-shadow:0 20px 50px rgba(0,0,0,0.6); }
:root{ --main:#FF2A4B; --main-glow:rgba(255,42,75,0.5); }
.main-bg{ background:var(--main) !important; }
.main-text{ color:var(--main) !important; }
.main-border{ border-color:var(--main) !important; }
.main-shadow{ box-shadow:0 0 12px var(--main-glow) !important; }
input[type="range"]{ -webkit-appearance:none; appearance:none; background:transparent; cursor:pointer; }
input[type="range"]::-webkit-slider-runnable-track{ background:#1e2430; height:6px; border-radius:3px; }
input[type="range"]::-webkit-slider-thumb{ -webkit-appearance:none; appearance:none; margin-top:-5px; background:var(--main); height:16px; width:16px; border-radius:50%; box-shadow:0 0 10px var(--main); }
.toggle-dot{ transition:transform .25s; }
#toast{ transition:all .3s; }
.color-btn{ width:32px; height:32px; border-radius:9999px; border:2px solid white; cursor:pointer; }
.color-btn.active{ outline:2px solid white; outline-offset:2px; }
</style>
</head>
<body class="flex items-center justify-center p-4 select-none">

<div class="glass-panel w-full max-w-lg rounded-2xl p-6 my-6">
  <div class="flex items-center justify-between pb-5 border-b border-white/10 mb-4">
    <div class="flex items-center space-x-3">
      <div class="w-3 h-8 rounded-full main-bg main-shadow"></div>
      <div>
        <h1 class="font-orbitron font-extrabold text-2xl text-white" style="font-family:Orbitron">RAJ FF <span class="text-sm px-2 py-0.5 rounded border main-text main-border" style="background:rgba(255,255,255,0.05)">V1</span></h1>
        <p class="text-xs font-mono text-gray-400">LEGIT HUD & SENSITIVITY PANEL</p>
      </div>
    </div>
    <div class="flex items-center gap-2 bg-emerald-950/40 border border-emerald-500/30 px-3 py-1 rounded-full">
      <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span><span class="text-[11px] font-mono text-emerald-400">SAFE</span>
    </div>
  </div>

  <!-- COLOUR SELECTOR -->
  <div class="flex items-center justify-between bg-black/30 p-3 rounded-xl border border-white/5 mb-6">
    <span class="text-xs font-semibold text-gray-300"><i class="fa-solid fa-palette"></i> THEME COLOUR</span>
    <div class="flex gap-2">
      <div class="color-btn active" style="background:#FF2A4B" onclick="setColor('#FF2A4B', this)"></div>
      <div class="color-btn" style="background:#2A7BFF" onclick="setColor('#2A7BFF', this)"></div>
      <div class="color-btn" style="background:#00E676" onclick="setColor('#00E676', this)"></div>
      <div class="color-btn" style="background:#A855F7" onclick="setColor('#A855F7', this)"></div>
      <div class="color-btn" style="background:#FFB300" onclick="setColor('#FFB300', this)"></div>
    </div>
  </div>

  <div class="grid grid-cols-3 gap-1 bg-black/40 p-1 rounded-xl mb-6 text-xs font-medium border border-white/5">
    <button class="py-2 rounded-lg text-white font-semibold main-bg">MAIN</button>
    <button class="py-2 rounded-lg text-gray-400">HUD</button>
    <button class="py-2 rounded-lg text-gray-400">SETTINGS</button>
  </div>

  <div class="space-y-3 mb-6">
    <div class="flex items-center justify-between p-3.5 rounded-xl bg-white/[0.02] border border-white/5">
      <div class="flex items-center space-x-3"><div class="w-8 h-8 rounded-lg flex items-center justify-center main-text border main-border" style="background:rgba(255,255,255,0.05)"><i class="fa-solid fa-gamepad text-sm"></i></div><div><div class="text-sm font-semibold text-gray-100">CUSTOM HUD</div><div class="text-[11px] text-gray-400">Button layout on / off</div></div></div>
      <label class="relative inline-flex items-center cursor-pointer"><input type="checkbox" class="sr-only peer" onchange="showToast('Custom HUD '+(this.checked?'On':'Off'))" checked><div class="w-12 h-6 bg-gray-800 rounded-full peer-checked:bg-[var(--main)]"></div><div class="toggle-dot absolute left-1 top-1 bg-white w-4 h-4 rounded-full peer-checked:translate-x-6"></div></label>
    </div>
    <div class="flex items-center justify-between p-3.5 rounded-xl bg-white/[0.02] border border-white/5">
      <div class="flex items-center space-x-3"><div class="w-8 h-8 rounded-lg flex items-center justify-center main-text border main-border" style="background:rgba(255,255,255,0.05)"><i class="fa-solid fa-mobile-screen text-sm"></i></div><div><div class="text-sm font-semibold text-gray-100">GYRO CONTROL</div><div class="text-[11px] text-gray-400">Phone hilane se camera</div></div></div>
      <label class="relative inline-flex items-center cursor-pointer"><input type="checkbox" class="sr-only peer" onchange="showToast('Gyro '+(this.checked?'On':'Off'))"><div class="w-12 h-6 bg-gray-800 rounded-full peer-checked:bg-[var(--main)]"></div><div class="toggle-dot absolute left-1 top-1 bg-white w-4 h-4 rounded-full peer-checked:translate-x-6"></div></label>
    </div>
    <div class="flex items-center justify-between p-3.5 rounded-xl bg-white/[0.02] border border-white/5">
      <div class="flex items-center space-x-3"><div class="w-8 h-8 rounded-lg flex items-center justify-center main-text border main-border" style="background:rgba(255,255,255,0.05)"><i class="fa-solid fa-crosshair text-sm"></i></div><div><div class="text-sm font-semibold text-gray-100">CROSSHAIR STYLE</div><div class="text-[11px] text-gray-400">Crosshair colour & size</div></div></div>
      <label class="relative inline-flex items-center cursor-pointer"><input type="checkbox" class="sr-only peer" onchange="showToast('Crosshair '+(this.checked?'On':'Off'))"><div class="w-12 h-6 bg-gray-800 rounded-full peer-checked:bg-[var(--main)]"></div><div class="toggle-dot absolute left-1 top-1 bg-white w-4 h-4 rounded-full peer-checked:translate-x-6"></div></label>
    </div>
    <div class="flex items-center justify-between p-3.5 rounded-xl bg-white/[0.02] border border-white/5">
      <div class="flex items-center space-x-3"><div class="w-8 h-8 rounded-lg flex items-center justify-center main-text border main-border" style="background:rgba(255,255,255,0.05)"><i class="fa-solid fa-gauge-high text-sm"></i></div><div><div class="text-sm font-semibold text-gray-100">FPS / PING SHOW</div><div class="text-[11px] text-gray-400">Sirf dekhne ke liye</div></div></div>
      <label class="relative inline-flex items-center cursor-pointer"><input type="checkbox" class="sr-only peer" onchange="showToast('FPS '+(this.checked?'On':'Off'))" checked><div class="w-12 h-6 bg-gray-800 rounded-full peer-checked:bg-[var(--main)]"></div><div class="toggle-dot absolute left-1 top-1 bg-white w-4 h-4 rounded-full peer-checked:translate-x-6"></div></label>
    </div>
  </div>

  <div class="space-y-5 bg-black/30 p-4 rounded-xl border border-white/5 mb-6">
    <div><div class="flex justify-between mb-2"><span class="text-xs font-semibold text-gray-300">SENSITIVITY</span><span id="sensi
