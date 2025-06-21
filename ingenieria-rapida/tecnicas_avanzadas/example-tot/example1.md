```markdown
Problema: Arquitectura para plataforma de streaming con 1M usuarios activos

Rama A: Arquitectura de Microservicios
├── Ventajas:
│   ├── Escalabilidad independiente por servicio
│   ├── Tecnologías heterogéneas (Node.js para API, Go para streaming)
│   ├── Equipos pueden trabajar independientemente
│   └── Resiliencia (fallo aislado)
├── Desventajas:
│   ├── Complejidad de deployment y monitoreo
│   ├── Latencia de red entre servicios
│   ├── Consistencia eventual (problema para pagos)
│   └── Overhead de infraestructura
├── Complejidad de implementación: 8/10
├── Escalabilidad: 10/10
├── Mantenibilidad: 7/10
└── Evaluación: Prometedor

Rama B: Monolito Modular
├── Ventajas:
│   ├── Simplicidad de desarrollo inicial
│   ├── Transacciones ACID nativas
│   ├── Menor latencia (no hay red)
│   └── Debugging más simple
├── Desventajas:
│   ├── Acoplamiento entre módulos
│   ├── Escalabilidad limitada
│   ├── Stack tecnológico único
│   └── Riesgo de punto único de falla
├── Complejidad de implementación: 4/10
├── Escalabilidad: 5/10
├── Mantenibilidad: 6/10
└── Evaluación: Posible

Rama C: Arquitectura Hexagonal + Event Sourcing
├── Ventajas:
│   ├── Auditabilidad completa (crucial para streaming)
│   ├── Flexibilidad para cambios de lógica de negocio
│   ├── Posibilidad de replay de eventos
│   └── Desacoplamiento entre dominio e infraestructura
├── Desventajas:
│   ├── Curva de aprendizaje elevada
│   ├── Complejidad de consultas (CQRS necesario)
│   ├── Storage de eventos puede crecer mucho
│   └── Eventual consistency
├── Complejidad de implementación: 9/10
├── Escalabilidad: 9/10
├── Mantenibilidad: 8/10
└── Evaluación: Descartado (demasiado complejo para MVP)

Decisión Final: Monolito Modular → Microservicios

Justificación:
1. Comenzar con monolito modular para MVP (6 meses)
2. Identificar bounded contexts durante desarrollo
3. Extraer microservicios críticos (streaming, payments)
4. Migración gradual basada en métricas de performance

Roadmap:
- Mes 1-6: Monolito con Clean Architecture
- Mes 7-12: Extraer servicio de streaming
- Mes 13-18: Extraer servicio de pagos
- Mes 19+: Evaluación continua de nuevas extracciones
```