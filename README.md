# Calculadora de Griegas

Calculadora interactiva de precio teórico y griegas (delta, gamma, vega, theta y rho) para opciones europeas, basada en el modelo Black-Scholes-Merton con rentabilidad por dividendo continua.

## Qué incluye

- Precio de call y put.
- Griegas en el orden habitual de mesa: delta, gamma, vega, theta y rho.
  - Vega y rho: cambio por 1 punto porcentual.
  - Theta: cambio por día natural.
- d1, d2, N(d2) y comprobación de la paridad put-call.
- Gráfico de cualquier griega (o del precio) frente al subyacente, los días al vencimiento o la volatilidad implícita, con una línea que marca el valor actual.

## Cómo usarla

Abre `index.html` en cualquier navegador. No necesita instalación ni servidor.

## Publicarla con GitHub Pages

1. Crea un repositorio nuevo y sube `index.html` y `README.md` a la raíz.
2. Ve a **Settings → Pages**.
3. En **Source**, elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y guarda.
4. En uno o dos minutos la calculadora estará disponible en `https://<tu-usuario>.github.io/<nombre-del-repo>/`.

## Modelo

```
d1 = [ln(S/K) + (r − q + σ²/2)·T] / (σ·√T)
d2 = d1 − σ·√T
Call = S·e^(−qT)·N(d1) − K·e^(−rT)·N(d2)
Put  = K·e^(−rT)·N(−d2) − S·e^(−qT)·N(−d1)
```

T = días naturales / 365. Todo el cálculo está en el bloque `MOTOR BLACK-SCHOLES-MERTON` de `index.html`, comentado para quien quiera leer el código.

## Aviso

Herramienta educativa. Los valores son teóricos y no constituyen recomendación de inversión.
