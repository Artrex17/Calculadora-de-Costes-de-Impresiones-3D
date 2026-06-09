# 🖨 Calculadora de Costes de Impresión 3D

Herramienta web para calcular el coste de producción de impresiones 3D y obtener un precio de venta sugerido.  
100% cliente — sin dependencias, sin backend, sin instalación.

---

## Características

- **Búsqueda de impresora** con autocompletado — 25 modelos de las principales marcas (Prusa, Creality, Bambu Lab, Anycubic, Elegoo, Ultimaker, Formlabs, Artillery, Raise3D…)
- **Cálculo detallado** de tres componentes de coste:
  - Filamento (€/kg × gramos usados)
  - Electricidad (consumo kW × horas × tarifa €/kWh)
  - Amortización de impresora (0,25 % del precio por impresión)
- **Tarifas eléctricas** españolas preconfiguradas (Punta / Llano / Valle) + opción de tarifa personalizada
- **Margen de beneficio** ajustable (0–1000 %) con slider en tiempo real
- **Desglose visual** con barra de porcentajes por componente
- **Precio de venta** con botón de redondeo y copia al portapapeles
- **Persistencia automática** — los datos del formulario se guardan en `localStorage`
- **Atajo de teclado** — pulsa `Enter` desde cualquier campo numérico para calcular
- **Botón Limpiar** para resetear todo el formulario

---

## Uso

1. Abre `index.html` en cualquier navegador moderno (o sirve la carpeta con cualquier servidor estático).
2. Busca y selecciona tu impresora 3D.
3. Rellena los datos de la pieza: coste de filamento, gramos consumidos y tiempo de impresión.
4. Elige la tarifa eléctrica del horario en que imprimirás.
5. Ajusta el margen de beneficio con el slider.
6. Pulsa **▶ Calcular** (o `Enter`).
7. Usa **≈ Redondear** para obtener un precio comercial limpio y **Copiar** para llevarlo al portapapeles.

---

## Fórmulas

```
Coste filamento    = (€/kg ÷ 1000) × gramos
Coste electricidad = kW_impresora × horas × €/kWh
Coste amortización = precio_impresora × 0,0025
─────────────────────────────────────────────
Coste total        = filamento + electricidad + amortización
Precio de venta    = coste_total × (1 + margen/100)
```

---

## Tecnología

- HTML5 + CSS3 + JavaScript (Vanilla) — archivo único, sin dependencias
- Tipografías: [Inter](https://fonts.google.com/specimen/Inter) + [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) vía Google Fonts
- Almacenamiento: `localStorage` del navegador

---

## Licencia

[AGPL-3.0](LICENSE)
