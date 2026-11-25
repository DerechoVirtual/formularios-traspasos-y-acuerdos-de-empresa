# Traspasos de negocio, confidencialidad y acuerdos de empresa

> Plugin de Claude Code `formularios-traspasos-y-acuerdos-de-empresa` · **20 formularios** · Mercantil · normativa revisada el 25-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Para operaciones y acuerdos sueltos de empresa: venta y arrendamiento de negocios o industrias, cartera de clientes, cartas de intenciones, acuerdos de confidencialidad (NDA), phantom shares, coworking, contrato estimatorio, requerimientos de pago por morosidad y otras cláusulas de empresa.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el documento en Word, con las normas comprobadas en el BOE. Cada skill explica en su `SKILL.md` qué es el formulario, para qué sirve, cómo se usa, qué datos necesita y qué avisos normativos lleva; el formulario seco, listo para rellenar, está en `assets/formulario.md` dentro de la carpeta de la skill.

## Qué puedes hacer con él

Estos son los tipos de documento que trae, con algunos ejemplos (la lista completa de los 20 está al final):

- **Contratos, pactos y cláusulas** (18). Por ejemplo: Contrato de venta de una rama de actividad; Contrato de promoción inmobiliaria con financiación anticipada (forward funding); Contrato de participaciones ficticias para directivos (phantom shares).
- **Comunicaciones, requerimientos y cartas** (2). Por ejemplo: Carta de requerimiento de pago a deudores conforme a la Ley de morosidad; Burofax de requerimiento de pago al arrendatario de una industria.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué documento necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Acuerdo de confidencialidad (NDA) entre empresas»
   - «Contrato de venta de un negocio en funcionamiento»
   - «Carta de intenciones previa a una compraventa de empresa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/formularios-traspasos-y-acuerdos-de-empresa:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/formularios-traspasos-y-acuerdos-de-empresa:contrato-venta-rama-actividad-mer-0815`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él. Todos los datos jurídicos del documento (artículos vigentes, sentencias con su ECLI, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las notas de actualización de la revisión del 25-11-2026 (reformas legales, órganos judiciales de la LO 1/2025, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el documento; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te entrega el documento en Word **tal cual es el formulario**: empieza por su primera línea, sin títulos, notas ni explicaciones añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. En el chat te dice lo que queda pendiente y, si es un escrito, el plazo y ante quién se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork). Se instala desde este repositorio de GitHub o subiendo el ZIP del plugin.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 1.156 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable formularios-traspasos-y-acuerdos-de-empresa@formularios-traspasos-y-acuerdos-de-empresa`).

## Instalación

En Claude Code, añade el catálogo (solo la primera vez) e instala el plugin:

```
/plugin marketplace add DerechoVirtual/formularios-traspasos-y-acuerdos-de-empresa
/plugin install formularios-traspasos-y-acuerdos-de-empresa@formularios-traspasos-y-acuerdos-de-empresa
```

En Claude (web, escritorio o Cowork): **Personalizar → Plugins → Añadir marketplace** con la dirección `https://github.com/DerechoVirtual/formularios-traspasos-y-acuerdos-de-empresa`, o sube el ZIP del plugin ([descargar ZIP](https://github.com/DerechoVirtual/formularios-traspasos-y-acuerdos-de-empresa/releases/latest/download/formularios-traspasos-y-acuerdos-de-empresa.zip)).

Para comprobar que está instalado: `claude plugin list`.

## Lista completa de formularios (20)

| Código | Formulario | Skill |
|---|---|---|
| MER-0815 | Contrato de venta de una rama de actividad | `contrato-venta-rama-actividad-mer-0815` |
| MER-0816 | Carta de requerimiento de pago a deudores conforme a la Ley de morosidad | `carta-requerimiento-pago-deudores-conforme-ley-mer-0816` |
| MER-0817 | Contrato de promoción inmobiliaria con financiación anticipada (forward funding) | `contrato-promocion-inmobiliaria-financiacion-mer-0817` |
| MER-0818 | Contrato de participaciones ficticias para directivos (phantom shares) | `contrato-participaciones-ficticias-directivos-phantom-mer-0818` |
| MER-0819 | Burofax de requerimiento de pago al arrendatario de una industria | `burofax-requerimiento-pago-arrendatario-industria-mer-0819` |
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

## Privacidad

Ver `PRIVACY.md`.
