# Viaje Digital: Servicio de Mantención — Análisis de Oportunidades
## Grupo Kaufmann · Digital Hub · Marzo 2026

Este documento analiza en detalle los 14 pasos del "Primer Viaje: Servicio de Mantención" del cliente Kaufmann, identificando el estado actual del proceso y las oportunidades digitales a desarrollar en los canales:

- **App Kaufmann** — canal digital cliente (iOS / Android)
- **Portal Web Cliente** (cliente.kaufmann.cl o equivalente)
- **Eleva** — software interno orientado a dar superpoderes a los asesores de venta y servicio

---

## Contexto: ¿Qué es el Convenio de Mantenimiento Kaufmann?

El Convenio de Mantenimiento (o "Eleva") es un programa de prepago de mantenciones que permite al cliente Kaufmann suscribirse a un paquete de servicios programados para su vehículo, a precio fijo. El cliente paga por adelantado y usa ese crédito a medida que agenda sus mantenciones. El propósito del viaje digital es que toda la experiencia —desde el onboarding hasta el post-servicio— sea fluida, digital y proactiva.

---

## FASE 1: ANTES DEL SERVICIO

### Paso 1 — Onboarding Simple
**Descripción del proceso actual:**
El cliente descarga la App Kaufmann y se registra. El CRM se actualiza con sus datos. Este es un proceso optativo que puede ocurrir antes de suscribir el convenio.

**Estado actual:**
- Registro básico en App
- CRM se actualiza manualmente o mediante integración básica

**Oportunidades digitales:**

**App Kaufmann:**
- Onboarding progresivo (progressive disclosure): no pedir todos los datos de golpe. Paso 1: email/teléfono. Paso 2: datos del vehículo (patente → autocompletar desde Registro Civil o ANAC). Paso 3: preferencias de notificación.
- Login social (Google / Apple ID) para reducir fricción de creación de cuenta.
- Pantalla de bienvenida contextualizada según el perfil del vehículo del cliente (marca, modelo, año) que muestre los beneficios del convenio de mantención específico para ese auto.
- Vinculación de múltiples vehículos desde el inicio (familias con varios autos).
- Deeplinks desde SMS/email de invitación para llevar directo a la activación de cuenta.

**Portal Web:**
- Landing de activación de cuenta simplificada con QR para continuar en App.

**Eleva (Asesor):**
- Vista del asesor que muestra qué clientes han descargado la App pero no han completado el onboarding → oportunidad de seguimiento proactivo.
- Botón "Invitar al cliente" que genera un link de registro personalizado (con patente y nombre pre-cargados).

---

### Paso 2 — Suscripción al Convenio de Mantenimiento
**Descripción del proceso actual:**
El cliente suscribe el convenio de mantenimiento (Eleva). Esto implica un prepago de mantenciones y opcionalmente la contratación de MyService. Actualmente se integra con Dimo/Wicar/Copiloto y API de Contrato.

**Estado actual:**
- Proceso mayormente presencial o asistido por asesor
- Integración con sistemas de contrato

**Oportunidades digitales:**

**App Kaufmann / Portal Web:**
- Cotizador de convenio en App: el cliente selecciona su vehículo, el plan de mantención recomendado aparece basado en kilometraje actual y proyección anual, con precio total y cuotas.
- Firma digital del convenio directamente en la App (DocuSign / firma biométrica nativa de iOS/Android).
- Pago del prepago desde la App: Webpay, tarjeta, transferencia, cuotas con tarjeta.
- Resumen visual del convenio: "Tienes 3 mantenciones incluidas. La próxima vence a los 10.000 km o en octubre 2026."
- Notificación push de bienvenida post-contratación con próximos pasos.

**Eleva (Asesor):**
- Panel de "Propuestas Pendientes": clientes que han cotizado pero no contratado. Con datos de cuándo cotizaron y qué plan eligieron.
- Asistente de oferta: el asesor ve en Eleva qué paquete se adapta mejor al perfil de uso del vehículo del cliente, con argumentos de venta ("tu cliente maneja ~1.500 km/mes, este plan le ahorra $X al año").
- Generación del contrato pre-llenado con datos del CRM para que el cliente solo firme.

---

### Paso 3 — Follow-Up Digital (MyService)
**Descripción del proceso actual:**
El cliente recibe un pop-up en la App y un correo invitándolo a contratar MyService (si no lo hizo al inicio). Canal: Eleva.

**Estado actual:**
- Comunicación vía Bloomreach (email/push)
- Proceso de compra de MyService aún requiere mejora

**Oportunidades digitales:**

**App Kaufmann:**
- In-app banner contextual que aparece cuando el cliente abre la App después de la suscripción, mostrando el beneficio de MyService.
- Compra de MyService con un tap (one-click purchase) si el cliente ya tiene un método de pago registrado.
- Video corto (<60s) explicando qué es MyService y por qué vale la pena.
- Contador visual: "Te quedan 5 días para añadir MyService con descuento de suscriptor."

**Eleva (Asesor):**
- Alerta automática en Eleva cuando un cliente con convenio activo no tiene MyService → tarea de seguimiento generada automáticamente para el asesor.
- Script sugerido de conversación para el asesor cuando contacta al cliente.

---

### Paso 4 — Anticipación Proactiva del Servicio
**Descripción del proceso actual:**
El cliente recibe un recordatorio de su próxima mantención y desde ahí mismo puede iniciar el agendamiento. Habilitadores: Dimo/Wicar/Copiloto, API Contrato, Bloomreach.

**Estado actual:**
- Recordatorio básico por email/push
- No siempre integrado con datos reales de kilometraje

**Oportunidades digitales:**

**App Kaufmann:**
- Widget de "Mi próxima mantención" en la pantalla de inicio de la App, con barra de progreso de km restantes.
- Notificación push inteligente: disparada por km (si el auto tiene telemetría) o por fecha estimada según perfil de uso declarado.
- Notificación accionable: el botón de la push lleva directo al paso 1 del agendamiento (sin abrir la App por separado).
- Selector de "¿Cuánto km tiene tu auto hoy?" para recalibrar la estimación cuando no hay telemetría.
- Recordatorio escalonado: 30 días antes → 15 días → 7 días → 3 días (ajustable por el cliente en preferencias).

**Portal Web:**
- Banner en el área de cliente: "Tu mantención se acerca. Agenda en 2 minutos."

**Eleva (Asesor):**
- Lista de clientes "próximos a mantención" ordenada por urgencia (km restantes, días restantes).
- Para clientes sin agenda confirmada a X días de su fecha estimada → alerta al asesor para contacto proactivo.
- Historial de comunicaciones enviadas a ese cliente (qué push, qué email, cuándo abrió).
- Integración con datos de telemetría vehicular (cuando disponible) para anticipación basada en km reales.

---

### Paso 5 — Agendamiento Self-Service
**Descripción del proceso actual:**
En la App (o web), el cliente elige sucursal y horario. Canal: App Kaufmann.

**Estado actual:**
- Agendamiento en App disponible pero con limitaciones de disponibilidad en tiempo real

**Oportunidades digitales:**

**App Kaufmann / Portal Web:**
- Calendario de disponibilidad en tiempo real integrado con Outlook/SAP: el cliente ve exactamente los slots disponibles en cada sucursal.
- Filtros de búsqueda: por sucursal, por hora del día (mañana/tarde), por proximidad geográfica.
- Selección de tipo de mantención pre-cargada según el convenio del cliente (no tiene que elegir qué servicio — ya está determinado por el contrato).
- Estimación de tiempo de servicio visible antes de confirmar ("Esta mantención dura ~2 horas").
- Opción de servicio a domicilio o en el trabajo (si aplica en esa sucursal).
- Guardar preferencias: "Siempre quiero Kaufmann Las Condes, mañanas entre 8 y 10."
- Integración con calendarios del teléfono: botón "Agregar a Google Calendar / Apple Calendar".

**Eleva (Asesor):**
- Vista del calendario de la sucursal en tiempo real para apoyar el agendamiento asistido por teléfono.
- Bloqueo de slots para clientes VIP o de flota.
- Capacidad de agendar desde Eleva en nombre del cliente.

---

### Paso 6 — Confirmación y Acompañamiento Previo
**Descripción del proceso actual:**
El cliente recibe un recordatorio y confirmación del agendamiento. Canal: Bloomreach.

**Estado actual:**
- Email de confirmación automático
- Push de recordatorio antes del turno

**Oportunidades digitales:**

**App Kaufmann:**
- Pantalla de "Mi cita" en la App: con dirección exacta de la sucursal, horario, nombre del asesor asignado, y número de orden de trabajo.
- Mapa integrado con ruta desde la ubicación actual del cliente hasta la sucursal.
- Checklist pre-visita: "¿Qué traer? Cédula de identidad, llaves del auto." (reducir fricciones en la llegada).
- Notificación push el día anterior (con opción de reagendar o cancelar con 1 tap).
- Notificación el día de la cita con 2 horas de anticipación.
- Opción de compartir la cita con otra persona (cónyuge, secretaria) desde la App.

**Eleva (Asesor):**
- Vista de agenda del día con todos los clientes que llegan: con nombre, vehículo, tipo de mantención y si hay servicios adicionales pendientes de cotizar.
- Alerta de clientes que no han confirmado su asistencia a 24h de la cita.

---

## FASE 2: DURANTE EL SERVICIO

### Paso 7 — Llegada e Ingreso Sin Fricción
**Descripción del proceso actual:**
El cliente llega a la sucursal. Habilitadores: Control de Acceso, Selling Speech, Asesor Móvil (Fiori).

**Estado actual:**
- Check-in mayormente presencial
- Asesor usa Fiori en tablet/desktop para registrar el ingreso

**Oportunidades digitales:**

**App Kaufmann:**
- Check-in digital desde el auto: el cliente confirma su llegada desde la App cuando está en el estacionamiento → aviso automático al asesor.
- QR de ingreso: el cliente muestra el QR de su cita en la App para registro rápido en recepción.
- Formulario pre-llenado: el cliente puede completar desde la App antes de llegar (km actuales, observaciones, servicios adicionales solicitados).
- Indicador de "turno en espera": el cliente ve cuántas personas están antes que él.

**Eleva (Asesor):**
- Alerta en tiempo real cuando el cliente hace check-in digital → el asesor sabe que el cliente ya llegó.
- Ficha completa del cliente en pantalla: vehículo, historial de servicios, convenio activo, alertas de servicios pendientes.
- Selling speech dinámico: Eleva sugiere qué servicios adicionales ofrecer según el historial del vehículo y las campañas activas (ej: "Este auto no ha hecho cambio de frenos en 2 años — ofrecer revisión de frenos").
- Script de bienvenida personalizado: "Buenos días [Nombre], su [Marca Modelo] viene por su mantención de los [km] km."

---

### Paso 8 — Seguimiento en Tiempo Real
**Descripción del proceso actual:**
El cliente recibe notificaciones y aprobaciones cuando son necesarias. Canal: App Kaufmann, Bloomreach.

**Estado actual:**
- Notificaciones básicas de estado
- Aprobación de presupuestos por teléfono o presencialmente

**Oportunidades digitales:**

**App Kaufmann:**
- Tracker visual de estado del servicio: "Recibido → En diagnóstico → En trabajo → Listo para retirar" (como el tracker de un delivery).
- Notificaciones push en cada cambio de estado.
- Aprobación digital de trabajos adicionales: el asesor envía una solicitud desde Eleva, el cliente la recibe en la App con descripción del trabajo, costo y fotos del problema. El cliente aprueba o rechaza con un tap.
- Chat en tiempo real entre cliente y asesor desde la App.
- Video corto del diagnóstico (30-60 seg) enviado por el asesor directamente al cliente.
- Estimación de hora de término actualizada en tiempo real.

**Eleva (Asesor):**
- Panel de estado de todos los vehículos en taller en tiempo real.
- Botón "Enviar presupuesto adicional" que genera automáticamente la solicitud en la App del cliente.
- Registro de tiempo de aprobación (SLA): si el cliente no responde en X minutos → alerta al asesor.
- Historial de comunicaciones del día con ese cliente.

---

### Paso 9 — Recepción y Aviso de Término de Servicio
**Descripción del proceso actual:**
El cliente recibe en la App una recepción clara del presupuesto y recibo de finalización del trabajo. Canal: App Kaufmann, Bloomreach.

**Estado actual:**
- Notificación de término básica
- Presupuesto en formato PDF por correo

**Oportunidades digitales:**

**App Kaufmann:**
- Notificación push de "Tu auto está listo" con detalle del resumen de trabajos realizados.
- Vista del "Resumen de servicio": qué se hizo, qué se reemplazó, próxima recomendación.
- Fotos del estado del vehículo post-servicio (ej: foto del aceite nuevo, filtros cambiados).
- Acuse de recibo digital del trabajo realizado.
- Visualización del saldo restante del convenio: "Te quedan 2 mantenciones en tu Eleva."

**Eleva (Asesor):**
- Generación del resumen de servicio con un click, que se envía automáticamente a la App del cliente.
- Checklist de calidad pre-entrega: el técnico o asesor marca cada ítem (presión neumáticos, nivel líquidos, etc.) en Eleva antes de notificar al cliente.

---

### Paso 10 — Pago Digital
**Descripción del proceso actual:**
El cliente paga el servicio de forma digital antes de ir a la sucursal. Habilitadores: Pasarela de Pago, Eleva.

**Estado actual:**
- Pago digital disponible pero no siempre utilizado
- Integración con pasarela de pago existente

**Oportunidades digitales:**

**App Kaufmann / Portal Web:**
- Pago en 1 tap desde la App: el cliente recibe la boleta, la revisa y paga con el método guardado (Webpay, tarjeta débito/crédito, Apple Pay, Google Pay).
- Pago fraccionado: opción de pagar en cuotas directo desde la App.
- Descuento del saldo del convenio automático: si el servicio está cubierto por Eleva, se descuenta sin necesidad de pago adicional.
- Recibo digital instantáneo en la App.
- Opción de donación de vuelto (redondeo para causa social de Kaufmann).

**Eleva (Asesor):**
- Vista de pagos pendientes vs. pagados antes de autorizar el retiro.
- Registro de pago en tiempo real integrado con SAP.

---

### Paso 11 — Retiro Ágil en Sucursal
**Descripción del proceso actual:**
El cliente retira su vehículo. Control de Acceso gestiona la salida. Canal: App Kaufmann (pasiva).

**Estado actual:**
- Proceso presencial con validación del pago antes de entregar llaves

**Oportunidades digitales:**

**App Kaufmann:**
- QR de retiro: el cliente muestra el QR de la App para retirar el vehículo sin presentar documentos físicos.
- Confirmación de retiro desde la App (firma digital o selfie).
- Instrucciones post-servicio en la App: "Recuerda rodar suavemente los primeros 500 km después del cambio de frenos."
- Ubicación del vehículo en el estacionamiento del taller (si hay sistema de tracking de autos en patio).

**Eleva (Asesor):**
- Autorización de salida del vehículo desde Eleva con un click (confirma que el pago está OK y el trabajo está completo).
- Integración con Control de Acceso para apertura automática de barrera.

---

### Paso 12 — Revisión Clara de Factura en App
**Descripción del proceso actual:**
El cliente puede revisar todos los cargos explicados fácilmente desde la App. Canal: App Kaufmann, Bloomreach.

**Estado actual:**
- Factura enviada por email en PDF
- Sin visualización nativa en la App

**Oportunidades digitales:**

**App Kaufmann:**
- Sección "Mis Facturas" en la App: todas las boletas/facturas en formato legible (no solo PDF), con cada ítem desglosado.
- Explicación en lenguaje simple de cada cobro: "Cambio de aceite: $X — cada 5.000 km o 6 meses."
- Gráfico de evolución del gasto en servicio a lo largo del tiempo.
- Comparación con valor de mercado: "Con tu convenio Eleva ahorraste $X en esta mantención."
- Descarga o reenvío de la boleta para rendiciones de gastos.
- Factura electrónica con RUT de empresa para clientes empresa.

---

## FASE 3: POST SERVICIO

### Paso 13 — Evaluación del Servicio
**Descripción del proceso actual:**
El cliente evalúa el servicio recibido. Canal: App Kaufmann.

**Estado actual:**
- Encuesta de satisfacción básica (NPS o CSAT)
- Resultados no siempre visibles para el asesor en tiempo real

**Oportunidades digitales:**

**App Kaufmann:**
- Encuesta en App con formato conversacional (no formulario estático): máximo 3 preguntas, con emojis y respuestas rápidas.
- NPS inmediato + seguimiento: si el cliente da nota baja, se activa un flujo de recuperación.
- Posibilidad de dejar una reseña pública (Google Maps, Trustpilot) con 1 tap si la nota es alta.
- Campo de texto libre para comentarios específicos.
- Gamificación: el cliente acumula puntos o beneficios por completar la encuesta.

**Eleva (Asesor):**
- Dashboard de NPS en tiempo real por sucursal y por asesor.
- Alertas instantáneas cuando un cliente da nota baja (Detractor): tarea automática de recuperación asignada al asesor con prioridad alta.
- Vista del historial de evaluaciones de cada cliente para personalizar el trato en próximas visitas.

---

### Paso 14 — Mantiene Relación
**Descripción del proceso actual:**
Post-servicio, el cliente recibe certificados de mantención e historial de trabajos. Canal: App Kaufmann.

**Estado actual:**
- Entrega de certificados básica (PDF por email)
- Historial disponible en App con funcionalidad limitada

**Oportunidades digitales:**

**App Kaufmann:**
- Sección "Mi Historial": timeline visual de todos los servicios realizados al vehículo, con fechas, km, trabajos, fotos y facturas asociadas.
- Certificado digital de mantención descargable (PDF sellado digitalmente) — útil para venta del vehículo.
- "Pasaporte del Vehículo": resumen completo del vehículo (historial, neumáticos, próximas revisiones técnicas).
- Recordatorio de Revisión Técnica (RTV) y SOAP: notificación proactiva antes del vencimiento.
- Contenido de valor: tips de conducción eficiente, alertas de recalls del fabricante, noticias sobre el modelo del cliente.
- Programa de lealtad: puntos por cada mantención realizada, canjeables por descuentos en servicios o accesorios.
- Referidos: el cliente invita a un conocido → ambos ganan un beneficio.
- Notificación de campaña: "Revisión de baterías gratis este mes para tu modelo."

**Eleva (Asesor):**
- Vista 360° del cliente: todas las interacciones, servicios, comunicaciones, evaluaciones y contratos en un solo lugar.
- Propensión de renovación del convenio: alerta cuando el convenio está próximo a vencer o a consumirse → tarea de renovación asignada.
- Segmentación para campañas: Eleva permite etiquetar clientes por perfil (flota, particular, VIP, en riesgo de abandono) para acciones diferenciadas.
- Predicción de churn: clientes que no han respondido comunicaciones en X meses → intervención proactiva.

---

## Resumen de Oportunidades por Canal

### App Kaufmann — Prioridades
1. Tracker de estado del vehículo en tiempo real (Paso 8)
2. Aprobación digital de trabajos adicionales (Paso 8)
3. Agendamiento self-service con disponibilidad real (Paso 5)
4. Historial y pasaporte del vehículo (Paso 14)
5. Pago digital con 1 tap (Paso 10)
6. Onboarding con autocompletado de patente (Paso 1)
7. Notificaciones inteligentes escalonadas (Paso 4)

### Portal Web Cliente — Prioridades
1. Agendamiento responsive (espejo de la App para usuarios sin smartphone)
2. Pago digital y revisión de factura
3. Historial de servicios con descarga de certificados

### Eleva (Asesor) — Prioridades
1. Dashboard de clientes próximos a mantención (Paso 4)
2. Selling speech dinámico en ingreso (Paso 7)
3. Vista 360° del cliente (Paso 14)
4. Alertas de NPS bajo con tarea de recuperación (Paso 13)
5. Panel de aprobaciones pendientes del cliente (Paso 8)
6. Generación de contratos y cotizaciones desde Eleva (Paso 2)
