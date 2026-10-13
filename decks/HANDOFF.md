# Handoff — Deck Automotiva × Tealdev

Para el Claude en local. Te paso la presentación que se ha hecho en la nube; ajústala con la info que tú tienes.

## Archivos
- `decks/automotiva-tealdev.html` — presentación (HTML único, 25 slides).
- `decks/assets/duck.png` — logo del pato. **Tiene que estar en `assets/` junto al HTML** o no sale.
- Rama: `claude/automotiva-sales-deck-bjsy0e` · PR: https://github.com/bdjoseluis/bdjoseluis/pull/1

## Cómo funciona
- Modo presentación: 1 slide por pantalla. Navegación con ← → / espacio / rueda / swipe; `F` = pantalla completa; `#n` en la URL abre la slide n.
- Cada `<section class="slide">` es una slide. Temas de color: (sin clase) oscuro teal, `t-deep` índigo, `t-light` claro, `t-amber` premium.
- Elementos con clase `a` y `style="--d:.2s"` entran con retardo escalonado.
- Animaciones por slide vía `data-fx`: `cover` (texto tecleado), `dots` (338 puntos), `term` (código que se escribe, array `CODE1`), `wa` (chat WhatsApp, burbujas en `data-t`/`data-h`), `kanban` (tarjeta que avanza), `pay` (pasos de matrícula), `ocr` (DNI rellenándose, `data-v`), `calc` (calculadora).
- Números animados: `<span class="count" data-to="123">`.
- La numeración de las etiquetas (`.tag .n`) se pone sola con JS.
- Tipografías: Space Grotesk (títulos), JetBrains Mono (detalles técnicos), Inter (texto). Se cargan de Google Fonts.

## Orden de slides
1. Portada — "338 personas al mes te escriben. ¿Cuántas reciben un segundo mensaje?"
2. Tu año en cifras: 40.800 €/año Ads · 4.056 contactos/año · 48 alumnos
3. Investigación de Automotiva (6 datos de su web)
4. Mercado: 20.000 vacantes en talleres + tabla de competencia
5. Coste por contacto: 3.400 € ÷ 338 ≈ 10 €
6. Diagnóstico: dónde se rompe la cadena
7. Reparto de papeles: Jose (web + Ads) / Tealdev (todo lo de después del clic) / equipo Automotiva (cierre)
8. Arquitectura: motor propio (scripts Node/Python) entre entradas y Odoo/WhatsApp/email/panel/calendario
9–19. Módulos 01–11: entrada única a Odoo · chatbot WhatsApp · panel en vivo · prioridad con IA · seguimiento 14 días + nutrición · rescate de formularios + aviso fin de mes del descuento · citas y recordatorios · matrícula y pago (SeQura/contado) · DNI por foto (OCR) · informe semanal del lunes · post-matrícula (bienvenida, prácticas, reseñas, referidos)
20. Módulo premium opcional: asistente de voz (proyecto y presupuesto aparte)
21. Calculadora interactiva (contactos, % recuperado, ticket)
22. Seguridad del chatbot (checklist pequeña)
23. Sin humo: qué no prometemos / qué sí
24. Hoja de ruta: Fase 1 / 2 / 3 + voz opcional. **Sin precios**: cada módulo se presupuesta aparte
25. Cierre + CTA

## Decisiones del usuario (respetar)
- **Sin precios en la presentación.** El presupuesto va aparte, módulo a módulo, con sus tarifas habituales. El presupuesto anterior se queda corto para todo esto.
- **No usamos n8n**: scripts propios.
- **Ads y web los lleva Jose.** No ofrecer gestión de campañas ni subir conversiones a Google Ads.
- **El bot de voz es opcional**, aparte, porque lleva trabajo y cuesta dinero.
- **Seguridad: solo un apartado pequeño** sobre el chatbot. No auditar la web (es de Jose).
- No copiar a Anartra (tipografía serif, títulos, mismos datos/citas). Estilo propio Tealdev.
- Tono: español de España, tuteo, directo, sin florituras.

## Datos del cliente (briefing)
480 h · 3 o 6 meses · prácticas en talleres locales · 1.480 € contado / 1.680 € SeQura · Google Ads ~3.400 €/mes · 338 contactos/mes (formulario, teléfono, WhatsApp con IA) · 48 alumnos · Odoo instalado, pero no funciona bien · objetivo: +5 alumnos/mes ya, luego +15/mes.

## Investigación (solo buscador: la nube no pudo abrir automotiva.eu)
- 3 cursos: electromecánica del automóvil, chapa y pintura, mecánica de motos.
- 480 h en talleres y concesionarios oficiales de la localidad del alumno, toda España.
- En 3 meses o solo de mañanas; sin estudios previos.
- Incluye ropa de trabajo, seguro de RC y accidentes y material.
- Certificado **privado** de prácticas firmado por el jefe de taller y la escuela.
- Landings: cursomecanica.automotiva.eu y cursochapaypintura.automotiva.eu, con "200 € de descuento solo este mes". Tienen blog con testimonios.
- No se ven reseñas independientes. Grupo Atrium: 4,7★ / 1.067 reseñas.
- Competencia: Grupo Atrium mecánica 2.195 € (Madrid/Bcn), motos 1.995 €; ITA 500 h / 6 meses.
- Mercado: ~20.000 puestos sin cubrir en talleres españoles (sept. 2026), también chapistas y pintores.

## Por revisar (tú tienes más contexto o acceso)
1. Abrir automotiva.eu y sus landings y verificar/ampliar los datos de la slide 3. Comprobar si hay sede, teléfono, Google Business o redes.
2. La tabla de competencia (slide 4) puede no ser comparable (Atrium puede incluir aula). Decidir si se quita la columna "reseñas: no visibles" para no ofender al director.
3. Confirmar que la API de SeQura permite generar enlaces de pago (módulo matrícula). Si no, adaptar.
4. Verificar que hay taller colaborador en cualquier código postal antes de que el bot lo afirme.
5. Las cifras del panel, del informe y de la ficha (79, 23, 6, nota 87…) son **ejemplos inventados** y van marcadas así.
6. Sacar el presupuesto por módulo (Fase 1/2/3 + voz) con las tarifas del usuario, en un documento aparte.
7. Probar en móvil: solo se ha probado en escritorio con Chromium sin interfaz.
