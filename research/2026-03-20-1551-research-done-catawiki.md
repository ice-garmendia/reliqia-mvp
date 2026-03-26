# Research Competidor: Catawiki
**Fecha de análisis:** 2026-03-20 15:51
**Analizado por:** Claude (Reliqia Research)
**Contexto:** Análisis desde la perspectiva de Reliqia — comunidad global de coleccionistas impulsada por IA

---

## 1. Modelo de negocio y estructura de comisiones

### Origen y escala actual
Catawiki fue fundada en 2008 por René Schoenmakers (coleccionista de cómics) y Marco Jansen (desarrollador), ambos holandeses. El nombre es un portmanteau de "catalogue" + "wiki". Originalmente era una wiki de catálogos de coleccionistas; desde 2011 pivotó al modelo de subastas online. Tiene sede en Amsterdam, 733 empleados y ha levantado $285M de inversores como Accel, Permira y Lead Edge Capital. Reporta ~14 millones de visitantes mensuales y más de 75.000 objetos en subasta cada semana.

### Estructura de fees — dual-sided commission
El modelo de ingresos es simple: cobran a ambos lados de cada transacción.

**Seller fee:** 12,5% del precio final de adjudicación (excluyendo IVA). El vendedor no paga por listar — solo paga si vende.

**Buyer Protection Fee:** 9% del precio final de adjudicación + €3 fijos. Se presenta como garantía de seguridad del pago, no como "comisión", aunque funcionalmente lo es.

**Comisión total efectiva sobre la transacción:** ~21,5% sobre el precio de adjudicación, distribuida entre ambas partes. Para contexto: eBay cobra ~10% solo al vendedor. Catawiki es significativamente más caro en términos de costo total del ecosistema.

**Ingreso mínimo:** Solo se puede listar ítems con valor estimado de €75 o más. Esto excluye gran parte del catálogo de un coleccionista promedio de CDs o vinilos de precio moderado.

**Servicios adicionales:** Existen opciones de visibilidad premium para vendedores (listings destacados, mayor exposición), a costo adicional.

**Sin swap, sin venta directa entre usuarios:** El único mecanismo de transacción es la subasta. No existe venta a precio fijo peer-to-peer ni intercambio entre usuarios.

---

## 2. Sistema de subastas — cómo funciona

### Flujo completo
1. El vendedor sube el ítem con fotos y descripción.
2. Un experto interno de Catawiki lo revisa virtualmente (solo fotos y descripción, sin inspección física).
3. Si es aprobado, el experto asigna un valor estimado no vinculante y lo incluye en una subasta semanal temática.
4. La subasta dura típicamente 7 a 10 días.
5. Las ofertas son visibles para todos en tiempo real.
6. Catawiki controla el horario de cierre — el vendedor no puede elegirlo.
7. Al cierre, cada nueva oferta extiende automáticamente la subasta 1 minuto adicional (anti-sniping), lo que elimina la estrategia de puja en el último segundo.
8. El ganador paga mediante el sistema de pagos de Catawiki (escrow); el pago se libera al vendedor hasta 3 días después de que el comprador confirma recepción.

### Bidding automático
El sistema permite "automatic bid": el comprador ingresa su máximo y el sistema puja automáticamente por el incremento mínimo necesario hasta ese tope.

### "No Reserve Day"
Catawiki organiza eventos periódicos de subastas sin precio de reserva donde todo sale al precio que sea. Es atractivo para compradores pero reportado como problemático para vendedores que terminan vendiendo ítems valiosos por precios muy bajos.

### Problema documentado con la UI de bidding
Usuarios reportan confusión entre el botón "Bid directly" y el botón "Quick bid". Al ser visualmente iguales y sin texto aclaratorio, usuarios accidentalmente han pujado sumas mucho mayores de lo deseado. Ejemplo real: un usuario pujó €162 creyendo hacer una puja incremental; el segundo más alto era €60. Otro pujó £470 cuando el segundo era £110 — €350 de sobrepago involuntario. La empresa no ofrece cancelación.

---

## 3. Categorías — especialmente música

### Categorías generales (80+)
Arte, antigüedades, joyería, relojes, libros, cómics, sellos, monedas, vinos y whiskies, coches clásicos, diseño, moda, instrumentos musicales, objetos militares, deportes, memorabilia, fuentes estilográficas, entre otros.

### Música — lo que existe y lo que no
- **Vinilos:** Categoría activa. Acepta vinilos en condición mínima VG+ (Very Good Plus). Orientado a prensados raros y ediciones especiales con valor de mercado relevante (Beatles, Bowie, Rolling Stones, Michael Jackson, Queen, etc.).
- **CDs:** Mencionados en las guidelines pero con presencia muy secundaria. El umbral de €75 elimina prácticamente todos los CDs que no sean rarezas o lotes de alto valor.
- **Cassettes:** Presencia marginal. Solo cassettes con valor coleccionable muy alto calificarían.
- **Lo rechazado:** Más de 1 millón de ítems son rechazados anualmente. En música, ítems de condición inferior a VG+, precio estimado bajo €75, o sin suficiente rareza no son aceptados. Un CD común de los 90s casi con certeza no entraría.

**Conclusión:** Catawiki sirve al coleccionista de vinilos raros de alto valor. No sirve al coleccionista promedio de CDs, cassettes o vinilos de precio moderado — que es exactamente el público central de Reliqia.

---

## 4. Experiencia de usuario (UX)

### Web
- Tiempo de carga promedio: 2,02 segundos (desktop).
- Filtros de búsqueda avanzada: precio, fecha de cierre, marca, material, ubicación geográfica.
- Diseño limpio y moderno comparado con Discogs.

### App móvil (iOS / Android)
- Disponible en ambas plataformas.
- **Reviews mayoritariamente negativas:**
  - Crashes frecuentes.
  - Notificaciones que no llegan o llegan tarde.
  - Actualizaciones recientes eliminaron el contador de "tiempo restante" visible.
  - Dificultad para seguir múltiples subastas simultáneamente.
  - Mensajes entre usuarios que no se muestran correctamente.

### Proceso de onboarding de vendedor
- Registro gratuito + verificación de identidad (documentos, dirección).
- Subida de fotos + descripción → espera de revisión experta → aprobación o rechazo sin feedback detallado.
- El vendedor no controla cuándo se lista ni cuándo cierra la subasta.

---

## 5. Sistema de autenticidad y verificación

### El modelo declarado
240+ expertos internos revisando virtualmente todos los ítems antes de publicarlos. Ningún ítem se lista sin aprobación experta. Se rechaza más de 1 millón de ítems por año.

### La realidad según investigaciones periodísticas
Una investigación de EenVandaag (junio 2025) — programa periodístico holandés de referencia — es devastadora:

- Revisión de ~20.000 ítems listados: fakes y ítems mal etiquetados aprobados de forma rutinaria.
- 60 de 170 "expertos" tienen backgrounds cuestionables. 9 no pueden ser identificados en ninguna fuente online.
- Ningún tasador certificado empleado. Las evaluaciones se basan exclusivamente en fotos y descripciones textuales del vendedor.
- Cita directa de un tasador de arte profesional (Willem de Winter): *"Las fotos pueden ser manipuladas. Te perdés detalles críticos."*
- Cita de un anticuario (Rob de Boer): *"Ves algo etiquetado como 'vidrio de Murano auténtico' listado por cientos de euros, cuando está disponible en el webshop chino Temu por unos pocos euros."*
- Ex-empleados describieron una cultura interna que prioriza velocidad y volumen sobre precisión.
- Catawiki rechaza ofrecer devoluciones por ítems mal descritos, a diferencia de casas de subasta tradicionales.
- Potencial violación de los requisitos del Digital Services Act de la UE.

---

## 6. Comunidad y reputación

### Lo que existe
- Sistema de feedback básico con ratings y reseñas.
- Sin perfiles ricos de coleccionista — solo comprador/vendedor anónimo con rating numérico.
- Sin colección digital, sin estados de ítem (intocable / open to trade / spare), sin wishlist social.
- Foros de comunidad abandonados desde ~2014.

### Dato significativo — thread de intercambio (2014)
Coleccionistas de sellos pidieron una función de intercambio en los foros. El moderador de Catawiki respondió: *"Catawiki no ofrece funcionalidades prácticas en su sistema para el intercambio"* — reconociendo el gap — y nunca lo desarrollaron.

### Reputación en la comunidad de coleccionistas
Muy polarizada. Bien vista para encontrar rarezas de alto valor; cuestionada para vendedores que esperan precios justos y para compradores que esperan autenticidad garantizada.

---

## 7. Alertas y notificaciones

### Sistema actual
- **Auction alerts por email:** se envía **solo UN email por semana** con todos los ítems que coincidan con keywords del usuario. No es en tiempo real.
- **Watchlist/Favoritos:** seguimiento de subastas específicas con notificaciones de cierre próximo o cuando alguien te supera.
- **Notificaciones in-app:** reportadas como poco confiables.

### Limitaciones frente a lo que Reliqia propone
- La alerta semanal agrupa todos los ítems — no distingue nuevos de listings ya vistos.
- No hay alertas instantáneas al momento en que aparece exactamente lo que el usuario busca.
- No hay contexto en las alertas (pressing, condición, precio estimado, reputación del vendedor, score de autenticidad).
- La periodicidad semanal hace que ítems muy buscados puedan adjudicarse antes de que el usuario sea notificado.

---

## 8. Swap / intercambio entre usuarios

**No existe.** Catawiki es exclusivamente un marketplace de subastas. No tiene ningún mecanismo de swap, trade, o intercambio peer-to-peer entre coleccionistas.

El moderador oficial de Catawiki reconoció en 2014 que una plataforma moderna de coleccionistas solo es completa si tiene función de exchange. No hay indicios de desarrollo posterior.

---

## 9. Presencia geográfica y limitaciones

### Alcance
- Disponible en 60 países, soporte en 17 idiomas.
- Sede en Amsterdam; oficinas en Madrid.
- ~70% de las ventas son internacionales.
- Primariamente europeo en su base de usuarios activa.

### Limitaciones para vendedores
- No disponible para vendedores desde todos los países (LATAM tiene acceso limitado).
- Shipping coordinado por vendedor y comprador directamente; Catawiki no interviene.
- Partnership con Eurosender para tarifas negociadas. Seguro de envío vía XCover.

---

## 10. Críticas y quejas frecuentes

### Ratings consolidados
- **Trustpilot:** +129.000 reseñas; rating ~3,5-4/5 con alta varianza.
- **ComplaintsBoard:** 1/5 estrellas, 0% de resolución reportada.
- **BritainReviews:** 3,8/5 — 30% cinco estrellas, 11% una estrella.

### Quejas más frecuentes

**1. Fakes y autenticidad deficiente**
La queja más grave y estructural, confirmada por investigación periodística de 2025.

**2. Atención al cliente inexistente**
> *"Zero customer service, all automated responses, no chance to get in touch with a representative. Once they have your money, their 'support' is non-existent."*

Caso documentado: reseñas negativas editadas sin consentimiento del usuario para volverse neutras.

**3. Precios de realización bajos para vendedores**
- Caso documentado: dos lámparas de aceite compradas a ~€200 cada una, vendidas a €1 cada una en Catawiki.
- Una artista plástica reportó un promedio de €120 por pintura a lo largo de 260 subastas en dos años.

**4. UI de bidding confusa**
Usuarios que pujaron sumas mucho mayores de las deseadas sin posibilidad de cancelación. Reportado como "estafa" por múltiples usuarios.

**5. Sellers que no envían**
Catawiki relista lotes vendidos sin despachar cuando el precio fue demasiado bajo. Solo ofrece reembolso al comprador — sin penalización severa al vendedor.

**6. App con problemas crónicos**
Crashes, notificaciones que no llegan, eliminación de features útiles, actualizaciones que empeoran la experiencia.

---

## Síntesis estratégica para Reliqia

| Dimensión | Catawiki | Oportunidad para Reliqia |
|---|---|---|
| Modelo de transacción | Solo subastas | Swap + subasta + venta directa |
| Swap entre usuarios | Inexistente | Diferenciador central |
| Música: CDs y cassettes | Marginal (solo alto valor, +€75) | Categoría core desde el día 1 |
| Threshold de entrada | €75 mínimo | Accesible para cualquier coleccionista |
| Alertas | Semanal, sin contexto, sin novedades distinguidas | Tiempo real, con contexto completo |
| Autenticidad | Expertos con credibilidad cuestionada, sin inspección física | Fotos en tiempo real + señales físicas + comunidad |
| Comunidad y reputación | Rating numérico básico, foros abandonados | Reputación como identidad, historial trato a trato |
| Perfiles de colección | No existe | Estados por ítem, wishlist, historial |
| UX mobile | App con problemas crónicos reportados | Oportunidad mobile-first bien ejecutado |
| Atención al cliente | Críticas masivas, respuestas automatizadas | Punto de diferenciación real |
| Precio para sellers | Comisión 12,5% + resultados bajos por no-reserve | Modelo que protege al vendedor sin contexto |
| Identidad de plataforma | Marketplace de subastas de alto valor | Comunidad de coleccionistas — la transacción es la consecuencia |
| Acceso LATAM | Muy limitado | Mercado desatendido con alta oportunidad |

---

## Qué podemos aprender de ellos

**Lo que funciona en Catawiki y Reliqia puede replicar:**
- El sistema anti-sniping (extensión de 1 minuto por oferta tardía) es inteligente y protege la integridad de la subasta — Reliqia debería adoptarlo.
- El escrow vía Stripe antes de liberar el pago al vendedor es el estándar correcto — Reliqia ya lo tiene en su flujo.
- La idea de subastas temáticas semanales por categoría crea momentos de comunidad y genera FOMO útil.
- El modelo "solo se cobra si hay venta" (no fee de listado) reduce la fricción para el vendedor.

**Lo que NO hacer:**
- No construir autenticidad solo sobre revisión fotográfica de expertos. La credibilidad del sistema colapsa sin inspección física + señales verificables + validación comunitaria.
- No bloquear el mercado con un threshold mínimo de valor — excluye al coleccionista promedio que es el corazón de la comunidad.
- No ignorar el swap. El propio Catawiki reconoció en 2014 que era un gap — y nunca lo resolvió.
- No descuidar la app. La experiencia mobile es donde vive el coleccionista activo.
- No automatizar la atención al cliente en disputas. La reputación de Reliqia como árbitro confiable es parte del producto.

---

## Conclusión

La falla más grande de Catawiki para el perfil de Reliqia no es técnica — es conceptual: **Catawiki trata al coleccionista como un vendedor o un comprador de objetos de alto valor.** Reliqia propone tratarlo como el protagonista de una comunidad donde colección, reputación y conocimiento compartido son el producto.

Catawiki no es el competidor directo de Reliqia para CDs, cassettes o vinilos de precio medio. Pero sí compite por el coleccionista serio de vinilos raros — y ahí la diferencia es el swap inteligente, las alertas en tiempo real, la comunidad real y una autenticidad construida desde abajo (señales físicas + comunidad) en lugar de desde arriba (expertos opacos).

El espacio que ocupa Reliqia — coleccionistas de música de todos los niveles, swap proactivo, comunidad con reputación, alertas instantáneas — **Catawiki lo dejó vacío por diseño.**

---

*Fuentes: Wikipedia, Catawiki Help Centre, EenVandaag (NL Times, junio 2025), Trustpilot, ComplaintsBoard, BritainReviews, Numis Forums, LastDodo Community, BidAmount Forum, Eurosender, Silicon Canals, Crunchbase, Vizologi, E-Commerce Nation.*
