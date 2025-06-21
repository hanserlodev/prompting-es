# Ejemplo self-consistency

## Ejemplo Práctico - Arquitectura de Base de Datos

### ❌ Problema mal resuelto (sin autoconsistencia)
**Pregunta**:  
"¿SQL o NoSQL para un e-commerce con 100k usuarios?"  

**Respuesta única**:  
"Usa MongoDB porque es más escalable"  

### ✅ Problema bien resuelto (con autoconsistencia)
**Enfoque multicriterio**:
1. **Camino 1 (Análisis de consistencia)**:  
   E-commerce necesita ACID para transacciones financieras → PostgreSQL ✓  
   
2. **Camino 2 (Análisis de escalabilidad)**:  
   100k usuarios requiere sharding eventual → PostgreSQL con particionamiento ✓  
   
3. **Camino 3 (Análisis de complejidad)**:  
   Relaciones complejas (productos, usuarios, órdenes) → SQL es más apropiado ✓  

**Respuesta consensuada**:  
PostgreSQL con sharding horizontal ✅  

