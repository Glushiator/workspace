# Matriz de Trazabilidad CP-CPS-Procedimientos Operacionales

**Documento:** Matriz de Trazabilidad
**Versión:** 1.0
**Fecha:** 7 de noviembre de 2025
**PSC:** Microsystem S.A.
**Documentos relacionados:**
- ME-DG-PO01 Políticas de Certificación v16 (CP)
- ME-DG-PO02 Declaración de Prácticas de Certificación v15 (CPS)

---

## Propósito

Esta matriz demuestra la **trazabilidad completa** entre:
1. **Requisitos de política** establecidos en el CP (ME-DG-PO01)
2. **Prácticas de implementación** descritas en el CPS (ME-DG-PO02)
3. **Procedimientos operacionales** que ejecutan las prácticas
4. **Evidencias** que demuestran la implementación efectiva

---

## Instrucciones de Uso

### Para Auditores
1. Identifique el requisito de política que desea verificar en la columna "Requisito CP"
2. Revise la sección correspondiente del CP indicada
3. Verifique cómo se implementa en el CPS según la columna "Implementación CPS"
4. Solicite acceso al procedimiento operacional indicado
5. Revise las evidencias de implementación listadas

### Para Personal Interno
- Utilice esta matriz durante la gestión de cambios para identificar impactos
- Consulte al planificar auditorías internas
- Actualice cuando se modifiquen CP, CPS o procedimientos

---

## Matriz de Trazabilidad

### 1. IDENTIFICACIÓN Y GOBERNANZA

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Identificación del documento CP | 1.2 | Identificación del documento CPS | 1.2 | No aplica | N/A | Publicación en sitio web PSC | Actualización | Gerente I+D |
| Definición de roles de PKI | 1.5 | Detalle de responsabilidades operativas | 3 | Política de Seguridad de la Información | CG-MA-PSI | Organigrama, descripciones de cargo, matrices RACI | Anual | Gerente General |

---

### 2. PARTES INVOLUCRADAS

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Entidad Acreditadora | 3.1 | Relación con Entidad Acreditadora | 3.1 | Plan Auditoría Interna | CG-FR-PAI | Informes de inspecciones | Según inspecciones | Gerente I+D |
| Autoridad Certificadora (AC) | 3.2 | Operación de la AC | 3.2 | Plan Seguridad de Sistemas | ME-DG-PS04 | Certificado raíz AC, documentación HSM | Continuo | Gerente I+D |
| Autoridad de Registro (AR) | 3.3 | Procesos de AR | 3.3 | Plan Seguridad de Sistemas | ME-DG-PS04 | Registros de solicitudes procesadas | Continuo | Gerente Micro e-Doc |
| Solicitantes y Titulares | 3.4-3.5 | Derechos y obligaciones | 4.1-4.3 | No aplica | N/A | Contratos, T&C aceptados | Por solicitud | AR |

---

### 3. CICLO DE VIDA DEL CERTIFICADO

#### 3.1 Solicitud y Validación

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Proceso de solicitud de certificado | 4.1 | Procedimiento de solicitud y validación | 6.1 | Plan Seguridad de Sistemas | ME-DG-PS04 | Formularios de solicitud, logs de validación | Continuo | AR |
| Validación de identidad presencial | 4.1.2 | Métodos de validación de identidad | 6.1.2 | Plan Seguridad de Sistemas | ME-DG-PS04 | Registro fotográfico, cédulas verificadas, actas | Por solicitud | AR |

#### 3.2 Emisión

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Emisión de certificados | 4.2 | Generación y emisión | 6.2 | Descripción Medidas de Seguridad | OP-PR-MDS | Logs de HSM, certificados emitidos | Continuo | AC |
| Generación de par de claves en HSM | 5.2 | Generación segura de claves | 6.2.1 | Descripción Medidas de Seguridad | OP-PR-MDS | Logs HSM, ceremonias, FIPS 140-2 | Por ceremonia | Gerente I+D |
| Protección de claves privadas | 5.3 | Almacenamiento seguro en HSM | 6.2.2 | Descripción Medidas de Seguridad | OP-PR-MDS | Auditoría HSM, logs acceso criptográfico | Mensual | Gerente I+D |
| Entrega de certificados | 4.2.3 | Mecanismos de entrega segura | 6.3 | Plan Seguridad de Sistemas | ME-DG-PS04 | Acuses de recibo, logs de descarga | Por emisión | AR |
| Período de vigencia | 4.2.4 | Plazos de validez según tipo | 6.4 | No aplica | N/A | Certificados con período establecido | Por emisión | AC |

#### 3.3 Mantenimiento

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Proceso de renovación | 4.2.5 | Procedimiento de renovación | 6.5 | Plan Seguridad de Sistemas | ME-DG-PS04 | Solicitudes de renovación, validaciones | Continuo | AR |
| Suspensión temporal | 4.3.2 | Causales y procedimiento de suspensión | 6.6 | Procedimiento Continuidad Operacional | OP-PR-OP | Tickets, CRL actualizadas, notificaciones | Por evento | AC |

#### 3.4 Revocación

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Revocación de certificados | 4.3 | Causales y procedimiento | 6.7 | Procedimiento Continuidad Operacional | OP-PR-OP | Solicitudes, CRL/OCSP, tiempo < 24h | Continuo | AC |
| Publicación CRL/OCSP | 4.3.4 | Actualización y publicación | 6.7.3 | Procedimiento Continuidad Operacional | OP-PR-OP | CRL cada 24h, OCSP 24/7, logs | Diario | AC |
| Tiempo de revocación | 4.3.3 | Proceso expedito < 24h | 6.7.2 | Procedimiento Continuidad Operacional | OP-PR-OP | Estadísticas de tiempo, SLA | Mensual | AC |

---

### 4. ESTRUCTURA DE CERTIFICADOS Y CRL

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Perfil de certificados X.509v3 | 5 | Estructura detallada de certificados | 13 | No aplica | N/A | Ejemplos certificados, perfil documentado | Por cambio | Gerente I+D |
| Estructura de CRL | 5.4 | Formato y contenido de CRL | 13.3 | No aplica | N/A | CRL publicadas, RFC 5280 | Diario | AC |

---

### 5. USOS DEL CERTIFICADO

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Garantía de integridad y no repudio | 6.1 | Aplicaciones y casos de uso | 5.1 | No aplica | N/A | Casos de uso documentados, aplicaciones | Según evolución | Gerente Micro e-Doc |
| Autenticación de usuarios | 6.2 | Autenticación en servicios | 5.2 | No aplica | N/A | Integraciones, logs de uso | Según evolución | Gerente Micro e-Doc |
| Confidencialidad | 6.3 | Cifrado de datos | 5.3 | No aplica | N/A | Documentación de capacidades | Según evolución | Gerente Micro e-Doc |

---

### 6. OBLIGACIONES Y RESPONSABILIDADES

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Obligaciones del titular | 7.1 | Responsabilidades del titular | 4.2 | No aplica | N/A | T&C aceptados, cláusulas contractuales | Por solicitud | AR |
| Obligaciones de la AR | 7.2 | Responsabilidades de AR | 4.1.2 | Plan Seguridad de Sistemas | ME-DG-PS04 | Procedimientos AR, capacitación, auditorías | Trimestral | Gerente Micro e-Doc |
| Obligaciones de AC | 7.3 | Responsabilidades de AC | 4.1.1 | Plan Seguridad de Sistemas | ME-DG-PS04 | Procedimientos AC, controles, logs | Mensual | Gerente I+D |

---

### 7. LIMITACIONES Y PROHIBICIONES

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Usos no autorizados | 8 | Limitaciones de uso | 4.3 | No aplica | N/A | T&C, avisos legales en certificados | Por emisión | Gerente I+D |

---

### 8. RESPONSABILIDADES DEL PSC

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Mantener seguro RC | 9.1 | Cobertura de seguro vigente | 14.2.3 | No aplica | N/A | Póliza 5.000 UF sin deducibles, certificado | Anual | Gerente General |
| Limitación de responsabilidad | 9.2 | Límites de responsabilidad | 14.3 | No aplica | N/A | Cláusulas contractuales, T&C publicados | Anual | Gerente General |

---

### 9. PRIVACIDAD Y PROTECCIÓN DE DATOS

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Cumplimiento Ley 19.628 | 10 | Tratamiento de datos personales | 10 | Política Seguridad Información | CG-MA-PSI | Política privacidad, consentimientos, ARCO, PIA | Anual | Oficial Privacidad |
| Consentimiento informado | 10.2 | Obtención de consentimiento | 10.2 | Política Seguridad Información | CG-MA-PSI | Formularios con consentimiento, aceptación web | Por solicitud | AR |
| Derechos ARCO | 10.3 | Ejercicio de derechos | 10.3 | Política Seguridad Información | CG-MA-PSI | Procedimiento ARCO, tickets, respuestas en plazo | Por solicitud | Oficial Privacidad |

---

### 10. DERECHOS DE LOS TITULARES

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Derecho a revocar | 11.1 | Proceso de solicitud revocación | 6.7.1 | Procedimiento Continuidad Operacional | OP-PR-OP | Formulario, tickets, confirmaciones | Por solicitud | AR |
| Derecho a suspender | 11.2 | Proceso de solicitud suspensión | 6.6.1 | Procedimiento Continuidad Operacional | OP-PR-OP | Formulario, tickets, confirmaciones | Por solicitud | AR |
| Acceso a información | 11.3 | Transparencia y disponibilidad | 1.4 | No aplica | N/A | CP y CPS publicados 24/7 | Continuo | Gerente I+D |

---

### 11. GARANTÍAS Y SEGUROS

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Certificación ISO 9001 | 12.1 | Sistema gestión de calidad | 14.2.1 | Plan Auditoría Interna | CG-FR-PAI | Certificado vigente, informes auditoría, NC | Anual | Gerente General |
| Certificación ISO 27001 | 12.2 | Sistema gestión seguridad información | 14.2.2 | PS03, PS04, PS05, PS07 | ME-DG-PS03/04/05/07 | Certificado vigente, informes, análisis riesgos | Anual | Gerente I+D |
| Seguro RC | 12.3 | Características del seguro | 14.2.3 | No aplica | N/A | Póliza 5.000 UF, certificado vigencia | Anual | Gerente General |

---

### 12. POLÍTICAS DE SEGURIDAD

#### 12.1 Seguridad General

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Marco general de seguridad | 13 | Controles de seguridad | 7, 8, 9, 10, 11 | Plan Seguridad de Sistemas | ME-DG-PS04 | Documentación controles, auditorías, evaluaciones | Anual | Gerente I+D |

#### 12.2 Seguridad Física

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Seguridad física data center | 13.3 | Controles seguridad física | 10 | Plan Seguridad de Sistemas | ME-DG-PS04 | Tier III, biometría, vigilancia 24/7, logs, clima | Trimestral | Ger. Operaciones DC |

#### 12.3 Respaldos y Retención

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Política de respaldos | 13.4 | Procedimientos respaldo y retención | 7.3, 12 | Procedimiento de Respaldo | OP-PR-RESP | Logs automáticos, pruebas trimestrales, 6 años | Trimestral | Ger. Operaciones |
| Retención de información | 13.4 | Política retención 6 años | 12.1, 12.2 | Procedimiento de Respaldo | OP-PR-RESP | Política, registros antigüedad, almacenamiento | Anual | Ger. Operaciones |

#### 12.4 Auditorías

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Auditorías internas y externas | 13.5 | Programa de auditorías | 4.4 | Plan Auditoría Interna | CG-FR-PAI | Plan anual, informes interna/externa ISO/EA | Anual | Resp. Calidad |

#### 12.5 Gestión de Personal

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Gestión de personal | 13.6 | Controles de personal PSC | 9 | Plan Seguridad de Sistemas | ME-DG-PS04 | Expedientes, NDA, antecedentes, capacitación | Anual | Gerente RR.HH. |
| Capacitación de personal | 13.6 | Programa de capacitación | 9.2 | Plan Seguridad de Sistemas | ME-DG-PS04 | Plan anual, certificados, evaluaciones | Anual | Gerente RR.HH. |

#### 12.6 Gestión de Incidentes

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Gestión de incidentes | 13.7 | Sistema gestión incidentes | 7.5 | Gestión Incidentes SI | ME-DG-PS07 | Registro incidentes, análisis, métricas, reportes | Por incidente | Oficial Seguridad |

#### 12.7 Continuidad Operacional

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Plan continuidad | 13.8 | Plan contingencia y recuperación | 7.4 | Continuidad Operacional AC | ME-DG-PS03 | Plan actualizado, pruebas failover, RTO/RPO | Semestral | Gerente I+D |

#### 12.8 Control de Accesos Lógicos

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Control accesos lógicos | 13.9 | Gestión identidades y accesos | 11.3, 11.4 | Plan Seguridad de Sistemas | ME-DG-PS04 | Política accesos, matriz privilegios, MFA, logs | Trimestral | Gerente TI |

#### 12.9 Gestión Criptográfica

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Gestión claves criptográficas | 13.10 | Controles criptográficos | 11.1, 11.2 | Descripción Medidas Seguridad | OP-PR-MDS | FIPS 140-2, ceremonias, custodios, logs, backups | Por ceremonia | Gerente I+D |

#### 12.10 Logging y Monitoreo

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Registro de eventos | 13.11 | Políticas logging y monitoreo | 11.5 | Implementación Plan Seguridad | ME-DG-PS05 | Logs centralizados, 6 años, protección, alertas | Mensual | Gerente TI |
| Monitoreo de seguridad | 13.11 | Sistema monitoreo 24/7 | 11.5 | Implementación Plan Seguridad | ME-DG-PS05 | Dashboard, alertas real-time, reportes | Continuo | NOC/SOC |

#### 12.11 Gestión de Vulnerabilidades

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Gestión vulnerabilidades | 13.12 | Evaluaciones de seguridad | 8.4 | Implementación Plan Seguridad | ME-DG-PS05 | Escaneos mensuales, pentests anuales, remediación | Mensual | Gerente TI |

#### 12.12 Mantenimiento de Sistemas

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Actualización sistemas | 13.13 | Gestión cambios y parches | 8.2 | Implementación Plan Seguridad | ME-DG-PS05 | Procedimiento cambios, parches, mantenimientos | Mensual | Gerente TI |

#### 12.13 Gestión de Activos

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Gestión de activos | 13.14 | Inventario y clasificación | 11.6 | Plan Seguridad de Sistemas | ME-DG-PS04 | Inventario actualizado, clasificación, responsables | Semestral | Gerente TI |

---

### 13. INFORMACIÓN Y CONTACTO

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Datos de contacto PSC | 14 | Información de contacto | 15 | No aplica | N/A | Sitio web, correos monitoreados, teléfonos | Continuo | Recepción |
| Referencias documentales | 15 | Documentos relacionados | 16 | No aplica | N/A | Lista referencias actualizada | Por actualización | Gerente I+D |

---

### 14. ASPECTOS OPERACIONALES ADICIONALES

| Requisito CP | Sección CP | Implementación CPS | Sección CPS | Procedimiento | Código | Evidencia | Frecuencia | Responsable |
|--------------|------------|-------------------|-------------|---------------|--------|-----------|------------|-------------|
| Disponibilidad servicios 24/7 | Implícito | Objetivos de disponibilidad | 7.1 | Procedimiento Continuidad | OP-PR-OP | Métricas uptime 99.5%, reportes mensuales | Mensual | Ger. Operaciones |
| Notificaciones | Varias | Sistema de notificaciones | 6.3 | Plan Seguridad de Sistemas | ME-DG-PS04 | Correos automatizados, logs envíos | Continuo | Sistema |
| Portal usuario | 3.6 | Funcionalidades del portal | 3.6 | Plan Seguridad de Sistemas | ME-DG-PS04 | Portal 24/7, logs uso, SSL válido | Continuo | Ger. Micro e-Doc |
| Términos y condiciones | 8 | Aceptación de términos | 4.2.1 | No aplica | N/A | T&C publicados, aceptación en línea | Por solicitud | AR |

---

## Resumen Estadístico

### Procedimientos Operacionales Identificados

| Código | Nombre | Áreas que Implementa | Frecuencia Revisión |
|--------|--------|---------------------|---------------------|
| **CG-FR-PAI** | Plan Auditoría Interna | Auditorías internas/externas/EA | Anual |
| **CG-MA-PSI** | Política Seguridad de la Información | Privacidad, protección datos, roles | Anual |
| **ME-DG-PS03** | Continuidad Operacional AC | Contingencia, recuperación | Anual + pruebas semestrales |
| **ME-DG-PS04** | Plan Seguridad de Sistemas | Física, personal, lógica, activos, AR, AC | Anual |
| **ME-DG-PS05** | Implementación Plan Seguridad | Logging, monitoreo, vulnerabilidades, parches | Semestral |
| **ME-DG-PS07** | Gestión Incidentes SI | Incidentes de seguridad | Anual |
| **OP-PR-RESP** | Procedimiento de Respaldo | Respaldos, retención | Anual |
| **OP-PR-OP** | Procedimiento Continuidad Operacional | Revocación, suspensión, CRL/OCSP, disponibilidad | Anual |
| **OP-PR-MDS** | Descripción Medidas Seguridad | Criptografía, HSM, generación claves | Anual |

**Total de procedimientos operacionales:** 9

**Total de mapeos en la matriz:** 70+

---

## Gestión de la Matriz

### Control de Cambios

| Versión | Fecha | Cambios | Responsable |
|---------|-------|---------|-------------|
| 1.0 | 2025-11-07 | Creación inicial de la matriz | Gerente I+D |

### Proceso de Actualización

Esta matriz debe actualizarse cuando:
1. Se actualice el CP (ME-DG-PO01)
2. Se actualice el CPS (ME-DG-PO02)
3. Se creen, modifiquen o eliminen procedimientos operacionales
4. Se identifiquen nuevos requisitos normativos
5. La Entidad Acreditadora lo solicite
6. Durante auditorías internas anuales

**Responsable de mantener actualizada:** Gerente I+D
**Frecuencia de revisión:** Anual mínimo, o según cambios

---

## Uso en Auditorías

### Para Auditoría Interna
- Utilizar como checklist durante auditorías anuales
- Verificar que existan evidencias para cada mapeo
- Identificar gaps o inconsistencias

### Para Auditoría Externa (ISO 27001/9001)
- Proporcionar copia al auditor al inicio
- Facilita verificación de controles
- Demuestra trazabilidad del sistema de gestión

### Para Inspecciones de Entidad Acreditadora
- Incluir en paquete documental de auditoría
- Responde específicamente a observación sobre concordancia
- Facilita navegación entre documentos

---

## Contacto

**Responsable de la Matriz:**
Jaroslaw Marcin Iwanski
Gerente I+D
Microsystem S.A.

**Para consultas sobre procedimientos específicos:**
Consulte con el responsable indicado en cada fila de la matriz.

---

**Documento generado:** 7 de noviembre de 2025
**Próxima revisión:** Noviembre 2026 o según cambios