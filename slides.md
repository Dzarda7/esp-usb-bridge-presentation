---
# You can also start simply with 'default'
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://cover.sli.dev
# favicon, can be a local file path or URL
favicon: '/favicons/favicon-32x32.png'
# force color schema for the slides, can be 'auto', 'light', or 'dark'
colorSchema: dark
# aspect ratio for the slides
aspectRatio: 16/9
# real width of the canvas, unit in px
canvasWidth: 980
# some information about your slides (markdown enabled)
title: Espressif
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
# Config required for slidev-component-poll addon
pollSettings:
  anonymous: true
---

# ESP USB Bridge

<span style="font-size: 2rem;">Transformace ESP32-S2/S3<br>na univerzální debugovací nástroj</span>

<div style="position: absolute; bottom: 2rem; left: 0; width: 100%; text-align: center;">
  Jaroslav Burian<br>
  <span style="font-size: 0.8rem; display: inline-block;">17. 10. 2025</span>
</div>

<!--
ESP USB Bridge prezentace - úvodní slide
-->

---

# Seznamte se, ESP-USB-Bridge

### Jeden malý čip, tři velké úkoly

- 🔓 Open source firmware pro ESP32-S2/S3 (stačí jedno issue a i pro ESP32-P4)
- 🔧 Promění čip za 100 Kč v multi-tool pro embedded vývoj
- 📞 Stálá podpora a nové funkce na cestě

<div class="relative mt-1 h-80 flex items-center justify-center">
  <img 
    src="/images/ESP-USB-Bridge_auta.png" 
    class="absolute max-h-70 transition-opacity duration-500"
    :class="$clicks >= 1 ? 'opacity-0' : 'opacity-100'"
    alt="ESP USB Bridge"
  />
  <img 
    v-click
    src="/images/concept.png" 
    class="absolute max-h-70 transition-opacity duration-500"
    :class="$clicks >= 1 ? 'opacity-100' : 'opacity-0'"
    alt="Concept"
  />
</div>

---
transition: slide-up
---

# Když tě USB-UART převodník vyghostuje

- 🙅 USB-UART přece není potřeba
- 🎮 Nefunkční ovladače z pochybných stránek
- ❌ I tak to nefunguje

<div class="grid grid-cols-2 gap-4 mt-8">
  <img src="/images/missing-USB-UART.png" class="max-h-80 mx-auto" alt="Missing USB-UART" />
  <img src="/images/USB-UART-driver.png" class="max-h-80 mx-auto" alt="USB-UART Driver" />
</div>

---

# Konečně sériový port, který se ukáže

- 🎯 Žádný další čip, jen ESP32-S2/S3
- ✅ Žádné pochybné ovladače
- 🔘 Navíc BOOT a RESET pin
- 🚀 Funguje s esptoolem!

---
transition: slide-up
---

# Error: Příkaz esptool nenalezen ⚠️

- 🤔 Co všechno musím instalovat?
- 🖥️ Kde to má GUI?

<div class="flex justify-center mt-8">
  <img src="/images/esptool-error.png" class="max-h-80" alt="Esptool Error" />
</div>

---

# Táhni, pusť, hotovo 🎉

- 👶 Zvládne i BFU
- 🤝 Přátelské k zákazníkům
- 🖥️ Funguje všude
- 💯 Není potřeba nic instalovat
- 📁 Potřebujete jenom UF2 soubor z esptool nebo ESP-IDF

---
transition: slide-up
---

# Když je printf nejlepším (jediným) přítelem

- 😓 Notoricky složité debuggování
- ❌ Nemám debugger
- 🏆 USB-JTAG/Serial for the win (ale bez USB)

<div class="flex justify-center mt-8">
  <img src="/images/printf.jpg" class="max-h-80" alt="Printf Debugging" />
</div>

---

# Univerzální debugger pro Espressif čipy

- 🎯 Breakpointy místo nekonečných printfů
- 💪 Funguje pro všechny čipy
- ➕ Navíc podpora SWD CMSIS-DAP pro ARM

---

# ESP-Prog2

- 🔌 2.54 mm a 1.27 mm JTAG a UART konektory
- ⚡ 3.3 V nebo 5 V
- 📍 12 extra GPIO pinů
- 🔘 BOOT a RESET tlačítka
- ✅ Hotové řešení

<div class="grid grid-cols-2 gap-4 mt-8">
  <img src="/images/esp-prog-2.png" class="max-h-60 mx-auto" alt="ESP-Prog2" />
  <img src="/images/frodo.jpg" class="max-h-80 mx-auto" alt="Frodo" />
</div>

---
layout: center
---

<div class="text-center">
  <h1 class="text-8xl">Demo time 🎬</h1>
</div>

---

# Rozděleno na komponenty - vyber si co potřebuješ

- 🔍 `debug_probe` pro debuggování
- 🔧 `serial_bridge` pro flashování a UART interface
- 🌐 Neni omezeno na ESP32-S3/S2

---

# Co se ještě chystá?

- 📡 SPI, I2C
- 🧩 Vetší modularita, nahrání na Espressif Component Registry
- 🔄 Přepínání SWD a JTAG za běhu
- 📶 WiFi UART bridge (RFC2217), WiFi debug

---

# ESP-Serial-Flasher - pod pokličkou

- ⚡ Flashování ESP32 z jiného ESP32 a nejen to
- 💻 esptool pro embedded napsaný v C
- 🎯 Jednoduchá implementace vlastního portu

---

<div class="flex items-center justify-center h-full">
  <div class="text-center text-4xl">
  Konec první kapitoly <br>příště esp-serial-flasher spin-off <br>🎬
  </div>
</div>
