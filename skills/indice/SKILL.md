---
name: indice
description: "Índice de los 20 formularios de Traspasos de negocio, confidencialidad y acuerdos de empresa. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Traspasos de negocio, confidencialidad y acuerdos de empresa: índice de formularios

> Plugin `formularios-traspasos-y-acuerdos-de-empresa` · 20 formularios · normativa revisada el 25-11-2026.

## Qué es

Para operaciones y acuerdos sueltos de empresa: venta y arrendamiento de negocios o industrias, cartera de clientes, cartas de intenciones, acuerdos de confidencialidad (NDA), phantom shares, coworking, contrato estimatorio, requerimientos de pago por morosidad y otras cláusulas de empresa.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Acuerdo de confidencialidad (NDA) entre empresas»
- «Contrato de venta de un negocio en funcionamiento»
- «Carta de intenciones previa a una compraventa de empresa»

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-traspasos-y-acuerdos-de-empresa:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Contratos, pactos y cláusulas (18)

| Código | Formulario | Skill |
|---|---|---|
| MER-0815 | Contrato de venta de una rama de actividad | `contrato-venta-rama-actividad-mer-0815` |
| MER-0817 | Contrato de promoción inmobiliaria con financiación anticipada (forward funding) | `contrato-promocion-inmobiliaria-financiacion-mer-0817` |
| MER-0818 | Contrato de participaciones ficticias para directivos (phantom shares) | `contrato-participaciones-ficticias-directivos-phantom-mer-0818` |
| MER-0820 | Contrato de servicios de gestión de redes sociales (social media manager) | `contrato-servicios-gestion-redes-sociales-social-media-mer-0820` |
| MER-0821 | Contrato de servicios de marketing digital | `contrato-servicios-marketing-digital-mer-0821` |
| MER-0822 | Contrato de espacio de trabajo compartido (coworking) | `contrato-espacio-trabajo-compartido-coworking-mer-0822` |
| MER-0823 | Arrendamiento de empresa, negocio o industria (contrato) | `arrendamiento-empresa-negocio-industria-contrato-mer-0823` |
| MER-0824 | Acuerdo de confidencialidad (NDA) | `acuerdo-confidencialidad-nda-mer-0824` |
| MER-0825 | Cláusula que exonera de responsabilidad al suministrador | `clausula-exonera-responsabilidad-suministrador-mer-0825` |
| MER-0826 | Carta de intenciones (letter of intent) como preacuerdo contractual | `carta-intenciones-letter-of-intent-como-preacuerdo-mer-0826` |
| MER-0827 | Contrato de explotación de un negocio por tercero | `contrato-explotacion-negocio-tercero-mer-0827` |
| MER-0828 | Contrato de instalación, gestión y explotación de máquinas expendedoras | `contrato-instalacion-gestion-explotacion-maquinas-mer-0828` |
| MER-0829 | Acuerdo de confidencialidad entre empresas | `acuerdo-confidencialidad-entre-empresas-mer-0829` |
| MER-0830 | Compraventa de licencia de expendeduría de tabaco (contrato) | `compraventa-licencia-expendeduria-tabaco-contrato-mer-0830` |
| MER-0831 | Contrato de arrendamiento de un negocio o industria en funcionamiento | `contrato-arrendamiento-negocio-industria-funcionamiento-mer-0831` |
| MER-0832 | Contrato de venta de un negocio o industria | `contrato-venta-negocio-industria-mer-0832` |
| MER-0833 | Contrato de venta de una cartera de clientes | `contrato-venta-cartera-clientes-mer-0833` |
| MER-0834 | Contrato estimatorio de mercancías en consignación | `contrato-estimatorio-mercancias-consignacion-mer-0834` |

### Comunicaciones, requerimientos y cartas (2)

| Código | Formulario | Skill |
|---|---|---|
| MER-0816 | Carta de requerimiento de pago a deudores conforme a la Ley de morosidad | `carta-requerimiento-pago-deudores-conforme-ley-mer-0816` |
| MER-0819 | Burofax de requerimiento de pago al arrendatario de una industria | `burofax-requerimiento-pago-arrendatario-industria-mer-0819` |
