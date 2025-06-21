**INFORMACIÓN:**
PaymentAPI v2.1 - Documentación Actualizada (Enero 2025)

Nuevos Endpoints:
- POST /api/v2/payments/instant - Pagos instantáneos (max $500)
- GET /api/v2/payments/{id}/status - Consultar estado de pago
- POST /api/v2/payments/recurring - Configurar pagos recurrentes

Cambios importantes:
- Campo "amount" ahora requiere formato decimal (ej: "150.00")
- Header "API-Version: 2.1" es obligatorio
- Timeout aumentado de 30s a 60s para pagos instantáneos
- Rate limit: 100 requests/minuto por API key

Ejemplo de request:
```json
{
  "amount": "25.50",
  "currency": "USD",
  "payment_method": "credit_card",
  "customer_id": "cust_123"
}
```

Códigos de respuesta:
- 200: Pago exitoso
- 202: Pago en procesamiento
- 400: Error en formato de request
- 429: Rate limit excedido

**ACTÚA COMO:** Senior Backend Developer especializado en APIs de pagos

**OBJETIVO:** Crear una guía de implementación para el equipo de desarrollo

**REGLAS:**
- Solo usa la información que te di
- Cita de dónde sale cada dato importante
- Si no tienes suficiente info, dilo

**QUIERO QUE:**
Expliques cómo implementar pagos instantáneos con la nueva API, incluyendo qué cambios necesitamos hacer desde la versión anterior

**FORMATO:**
Lista de pasos con ejemplos de código y consideraciones importantes