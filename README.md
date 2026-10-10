# CrosshairLink

**One crosshair, two platforms.** Move the mouse over a TradingView chart and NinjaTrader 8 draws
the same crosshair — same price, same time. Move it over NinjaTrader and TradingView draws it back.
Both directions, live, 60 times per second. · [Español ↓](#español)

## Why it exists

I analyse in TradingView and execute in NinjaTrader. Comparing a level between two windows by eye —
"is that the same high?" — is exactly the kind of small friction that produces bad entries.
CrosshairLink removes it: the point you're looking at is the point you're looking at, in both apps.

## How it works (overview)

```
TradingView  ──►  local bridge (Python)  ──UDP──►  ReticulaTV indicator (NinjaTrader 8)
TradingView  ◄──  local bridge (Python)  ◄──UDP──  ReticulaTV indicator (NinjaTrader 8)
```

- A small bridge reads TradingView's crosshair and sends it over loopback UDP, no files involved.
- The **ReticulaTV** indicator paints it on the NinjaTrader chart and publishes its own mouse back.
- **Read-only as far as trading goes:** it never touches orders, positions or accounts.
- **Fails safe:** if the bridge stops, the crosshair disappears on its own after 1.5 s — no stale
  lines on your chart.

## Status

Source code is private. ReticulaTV is being prepared as a commercial product, with the same
per-computer license and automated checkout as [GhostLimit](https://github.com/KevssG/GhostLimit).
Interested? Get in touch.

## Contact

Kevin García · [kevin.garcia.quant@gmail.com](mailto:kevin.garcia.quant@gmail.com) ·
[LinkedIn](https://www.linkedin.com/in/kevingarcia-quant)

---

## Español

**Una retícula, dos plataformas.** Mueves el mouse en TradingView y NinjaTrader 8 dibuja la misma
retícula, en el mismo precio y la misma hora; y al revés. En los dos sentidos, 60 veces por segundo.

- Un puente local en Python lee la retícula de TradingView y la envía por UDP, sin archivos.
- El indicador **ReticulaTV** la dibuja en NinjaTrader y devuelve la suya.
- **Solo lectura:** nunca toca órdenes, posiciones ni cuentas.
- **Seguro ante fallos:** si el puente se detiene, la retícula desaparece sola en 1.5 s.

El código es privado. ReticulaTV se está preparando como producto comercial, con licencia por
computadora y cobro automático, igual que GhostLimit. ¿Te interesa? Escríbeme.

---

© 2026 Kevin García Lobato. All rights reserved. Todos los derechos reservados.
