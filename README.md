<p align="center">
  <img src="docs/logo.png" alt="Logo de MoneyTrack: una M de tinta sobre una hoja blanca, subrayada en rojo, en una pared verde" width="88" height="88" />
</p>

<h1 align="center">MoneyTrack</h1>

<p align="center">
  <b>Apuntas un gasto en tres segundos y el mes se explica solo.</b><br />
  Finanzas personales en español (y en inglés), sin conectar el banco.
</p>

<p align="center">
  <a href="https://moneytrack.iagoestevez.com"><b>Probar la app →</b></a>
  &nbsp;·&nbsp;
  <a href="#cómo-se-usa">Cómo se usa</a>
  &nbsp;·&nbsp;
  <a href="#arquitectura">Arquitectura</a>
</p>

<p align="center">
  <img src="docs/screenshots/landing.png" alt="Portada de MoneyTrack: la hoja del mes colgada en una pared verde, con un calendario de gastos de ejemplo y una nota para apuntar el primer gasto" />
</p>

> Este repositorio es el escaparate del proyecto: producto, capturas y arquitectura. **El código fuente es privado** y está disponible bajo acuerdo de confidencialidad, a petición.
>
> Todas las capturas usan **datos de ejemplo**. Ninguna muestra cuentas reales.

---

## La idea

La mayoría de apps de finanzas te piden mucho antes de darte algo: conectar el banco, categorizar cientos de movimientos, configurar cuentas. MoneyTrack va al revés.

- **Tres segundos por apunte.** Importe, concepto y listo. La categoría se propone sola (la última que usaste) y la fecha es hoy.
- **Una hoja por mes.** La pantalla principal es lo que pegarías en la nevera: lo que te queda, qué días han costado y qué falta por pagar.
- **Avisos antes, no después.** Un límite te avisa al 80 % (o al porcentaje que elijas) con los días que quedan, cuando todavía puedes cambiar algo.
- **Tus datos, solo tuyos.** No hay conexión con el banco ni anuncios. Cada usuario solo puede leer lo suyo (Row Level Security en todas las tablas).

El mundo visual se llama **«el calendario de la cocina»**: una pared verde, una hoja blanca, dos tintas (negra y rojo rotulador) y el verde solo para lo que entra.

---

## Cómo se usa

### 1. Pruébala antes de crear la cuenta

La portada es la propia app con datos de ejemplo. Escribes tu primer gasto en la nota pegada a la hoja y, al registrarte, ya está apuntado. Nada de formularios vacíos.

<p align="center">
  <img src="docs/screenshots/landing-movil.png" alt="Portada en el móvil" width="300" />
</p>

### 2. El Resumen: tu mes en una hoja

Una cifra grande (lo que te queda), una tira de 30 días con el gasto de cada día y, debajo, lo que todavía queda por pagar y tus últimos apuntes. Pasa por un día para ver su detalle; púlsalo para filtrar.

<p align="center">
  <img src="docs/screenshots/resumen.png" alt="Resumen del mes: saldo, tira de gasto diario, aviso de presupuesto, recurrentes pendientes y últimos apuntes" />
</p>

### 3. Apuntar desde cualquier sitio

El botón **Apuntar** está siempre a mano: arriba a la derecha en el ordenador y en el centro de la barra inferior en el móvil. Se abre encima de lo que estés viendo, apuntas y sigues.

<p align="center">
  <img src="docs/screenshots/resumen-movil.png" alt="Resumen en el móvil con la barra inferior y el botón Apuntar en el centro" width="300" />
  &nbsp;&nbsp;
  <img src="docs/screenshots/apuntar-movil.png" alt="Formulario de apuntar un movimiento en el móvil: gasto o ingreso, importe, fecha, concepto y categoría" width="300" />
</p>

### 4. Límites que avisan a tiempo

Un tope mensual por categoría. Cada límite muestra cuánto queda, para cuántos días y, si vas rápido, en cuánto acabarías al ritmo actual. En la misma pantalla están los **recurrentes** (alquiler, Netflix, el gimnasio): se apuntan con un clic y nunca se duplican.

<p align="center">
  <img src="docs/screenshots/presupuestos.png" alt="Presupuestos: límites por categoría con barras de progreso, lo que queda y la proyección al ritmo actual" />
</p>

### 5. Movimientos, objetivos, inversiones y viajes

| | |
|---|---|
| <img src="docs/screenshots/movimientos.png" alt="Lista de movimientos agrupados por día con filtros" /> | <img src="docs/screenshots/objetivos.png" alt="Objetivos de ahorro con progreso y cuánto ahorrar al mes" /> |
| **Movimientos**: todo lo apuntado por día, con búsqueda, filtros y orden que viven en la URL (se pueden enlazar y compartir), y exportación a CSV. | **Objetivos**: lo que quieres juntar y para cuándo. Te dice cuánto ahorrar cada mes para llegar. |

- **Inversiones**: apuntas cada aportación y, de vez en cuando, el valor que ves en tu broker. Ves lo aportado frente a lo que vale de verdad, sin que cuente como gasto del mes.
- **Viajes**: agrupa gastos ya apuntados, con total, media por día y comparativa entre escapadas.

### 6. Análisis con IA sobre tu propio historial

Gemini lee tus apuntes (no promedios de nadie) y devuelve avisos con tipo e impacto, una predicción del mes que viene categoría a categoría con su nivel de confianza, y la evolución de los últimos seis meses. Pulsar una categoría lleva a sus movimientos. El análisis responde en el idioma de la app.

<p align="center">
  <img src="docs/screenshots/analisis.png" alt="Análisis IA: avisos con impacto, predicción del mes siguiente por categoría y gráficas de los últimos seis meses" />
</p>

---

## Tú decides cómo se ve

**Ajustes** está separado por secciones: Cuenta, Idioma y región, Apariencia, Apuntes y avisos, Categorías, Tus datos y Acerca de.

<p align="center">
  <img src="docs/screenshots/ajustes-oscuro.png" alt="Ajustes en modo oscuro, sección Apariencia: tema, tamaño del texto, reducir animaciones y ocultar importes" />
</p>

| Ajuste | Qué hace |
|---|---|
| **Idioma** | Español o inglés: textos, fechas, números y también las respuestas de la IA. |
| **Moneda** | El símbolo de los importes (euro, dólar, libra, pesos, real). |
| **Tema** | Claro, oscuro o el del sistema. El oscuro es gris verdoso, no negro: se lee bien de noche sin deslumbrar. |
| **Tamaño del texto** | Cuatro tamaños; escala toda la app. |
| **Reducir animaciones** | Quita transiciones y números que cuentan, aunque el sistema no lo pida. |
| **Ocultar importes** | Cambia todas las cifras por `•••` para abrir la app en público. También con el ojo de la barra superior. |
| **Al apuntar, empezar por** | Gasto o ingreso por defecto. |
| **Proponer la última categoría** | Si apuntaste en Alimentación, el siguiente empieza ahí. |
| **Aviso de los límites nuevos** | El porcentaje de aviso con el que nace cada límite. |
| **Pantalla al entrar** | Resumen, Movimientos, Presupuestos o Análisis. |

<p align="center">
  <img src="docs/screenshots/resumen-oscuro.png" alt="Resumen en modo oscuro" />
</p>

<p align="center">
  <img src="docs/screenshots/importes-ocultos.png" alt="Cabecera del resumen con los importes ocultos como puntos" />
</p>

---

## Decisiones de experiencia

Pequeñas reglas que se repiten en toda la app:

- **Estados vacíos que enseñan.** Cada pantalla vacía dice qué aparecerá ahí y ofrece el primer paso, nunca un «No hay datos».
- **Primer mes guiado.** Tres pasos con acciones reales (primer gasto, primer límite, primer recurrente) que desaparecen al completarse.
- **Borrar siempre pide confirmación** en la propia hoja y explica qué se conserva («los movimientos no se tocan»).
- **Errores que dicen qué hacer.** «No hay conexión. Comprueba tu red e inténtalo de nuevo», no un código.
- **Todo se puede enlazar.** Filtros, mes y sección de ajustes viven en la URL.
- **Accesible por teclado y lector de pantalla:** enlace para saltar al contenido, avisos anunciados al lector, interruptores accesibles, contraste AA en claro y oscuro.
- **Instalable (PWA).** Se añade a la pantalla de inicio del móvil y abre directamente en la app.

---

## Arquitectura

| Capa | Tecnología |
|---|---|
| Frontend | React 18, TypeScript estricto, Vite, CSS Modules sobre tokens de diseño, React Query, Zod |
| Backend | Vercel Serverless Functions en TypeScript |
| Datos y acceso | Supabase (PostgreSQL + Auth) con Row Level Security en todas las tablas |
| IA | Google Gemini con salida estructurada, caché por usuario e idioma y cupo diario |
| Idiomas | Español e inglés; los tests fallan si falta una traducción |
| Calidad | TypeScript estricto en todo el proyecto y tests con Vitest |

Las operaciones sensibles pasan por funciones serverless con validación en servidor. El resto va directo a Supabase desde el cliente, siempre protegido por RLS y validado con Zod. Las claves de servidor y de la IA nunca llegan al navegador.

---

## Código fuente

El código de MoneyTrack es privado. Si quieres revisarlo (por ejemplo, para una colaboración, una licencia o un proceso de selección), escríbeme y lo compartimos bajo acuerdo de confidencialidad.

---

## Autoría

Diseñada y desarrollada por **[Iago Estévez Pérez](https://github.com/iagoesteevezz)**: producto, diseño y código.
¿Algo no va bien en la app? Escríbeme a [iagoesteevezz@gmail.com](mailto:iagoesteevezz@gmail.com).

---

## Licencia

© 2026 Iago Estévez Pérez. Todos los derechos reservados.

MoneyTrack es software propietario. Este repositorio, sus textos, capturas y logotipo no pueden usarse, copiarse, modificarse ni distribuirse sin permiso escrito. Las condiciones completas están en [LICENSE](LICENSE).

Solicitudes de licencia: [iagoesteevezz@gmail.com](mailto:iagoesteevezz@gmail.com)
