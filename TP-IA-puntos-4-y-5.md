# 4. Integración de Inteligencia Artificial

> Nota: los tiempos y la cantidad de clases están marcados como ajustables. Adaptarlos al cronograma real del eje 2.

La propuesta integra dos herramientas de Inteligencia Artificial en dos momentos
distintos de la secuencia didáctica, cada uno con una función cognitiva diferente:
**Stitch** en la fase de ideación previa al código, y **Claude** en la fase de
revisión posterior a la producción. La decisión central del diseño es que la IA
no produce el contenido que se evalúa, sino que opera en los extremos del
proceso —la ideación y la auditoría—, dejando la construcción del conocimiento
en manos del estudiante.

## Fundamento desde el modelo TPACK

- **Conocimiento del contenido (CK):** estructura semántica de HTML5, jerarquía de
  etiquetas, separación entre estructura y presentación, validación normativa.
- **Conocimiento pedagógico (PK):** diseño previo a la implementación, trabajo en
  parejas, revisión crítica de la propia producción y verificación contra fuente
  normativa.
- **Conocimiento tecnológico (TK):** Stitch como generador de interfaces a partir
  de descripciones en lenguaje natural; Claude como analizador de código.
- **Intersección (TPACK):** la tecnología se incorpora solo donde aporta algo que
  el estudiante no puede obtener por otro medio con la misma economía de tiempo:
  variantes de diseño inmediatas y una revisión técnica sistemática. En ningún
  momento reemplaza la escritura del código, que es el objeto de aprendizaje del
  eje.

## 4.1 Stitch — fase de ideación

**¿Para qué se utilizará la IA?**
Para generar rápidamente variantes de diseño de interfaz a partir de una
descripción en lenguaje natural, de modo que cada pareja pueda *decidir* la
estructura del documento antes de escribir la primera etiqueta. La estructura de
un documento HTML es una decisión de diseño, no un resultado accidental del
proceso de maquetado.

**¿Qué deberá hacer el estudiante con la respuesta generada?**
No podrá copiarla ni utilizar el código que la herramienta exporta. Deberá
traducir el boceto a un **mapa de estructura semántica**: un esquema en el que
cada región visual del diseño se asocia a la etiqueta HTML que corresponde
(`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`), con una
justificación breve de cada elección. Además deberá indicar qué elementos del
boceto descarta y por qué.

**¿Qué aprendizaje se espera favorecer?**
La capacidad de leer un diseño visual y traducirlo a una jerarquía semántica
correcta; la comprensión de que las etiquetas de HTML5 expresan significado y no
apariencia; y el hábito de planificar la estructura antes de implementarla.

**¿Qué intervención tendrá el docente?**

1. Entrega un prompt base común, para que los bocetos de todas las parejas sean
   comparables entre sí.
2. Establece la restricción explícita de que el código exportado por Stitch no
   puede formar parte de la entrega.
3. Valida el mapa de estructura semántica de cada pareja **antes** de autorizar
   el inicio del maquetado.

## 4.2 Claude — fase de auditoría

**¿Para qué se utilizará la IA?**
Para auditar el trabajo práctico final ya terminado: detectar errores de
estructura, problemas de semántica, omisiones de accesibilidad y desvíos
respecto de las buenas prácticas de HTML5.

**¿Qué deberá hacer el estudiante con la respuesta generada?**
No aplicará las recomendaciones de forma automática. Deberá clasificar cada
hallazgo del informe en una de tres categorías —error real, mejora pertinente o
falso positivo—, emitir un veredicto propio con fundamento técnico y verificar
los puntos estructurales contra una fuente normativa (documentación de MDN y el
validador del W3C). Solo después aplicará las correcciones que haya aceptado.

**¿Qué aprendizaje se espera favorecer?**
El desarrollo de criterio para evaluar una respuesta generada por IA y el hábito
de verificarla contra la especificación. Es el nivel cognitivo más alto de la
secuencia: el estudiante pasa de producir código a juzgar afirmaciones técnicas
sobre su propio código.

**¿Qué intervención tendrá el docente?**

1. Entrega el prompt de auditoría estandarizado (incluido en el punto 5), de modo
   que la calidad del informe no dependa de la habilidad de cada pareja para
   formular preguntas.
2. Evalúa el **acta de auditoría**, no el código corregido: lo que se califica es
   la capacidad de discriminar, no la obediencia al informe.
3. Acompaña la verificación en el validador del W3C y contrasta los veredictos de
   cada pareja con los errores y falsos positivos que ya conoce como habituales
   en este tipo de revisión.

## 4.3 Encuadre común de uso de IA

- Toda interacción con IA debe quedar registrada: se entregan las capturas o la
  transcripción de las consultas realizadas.
- Está prohibido presentar como propio código generado o exportado por una
  herramienta de IA.
- Cada entrega incluye una declaración breve de uso de IA: qué herramienta se
  usó, en qué momento y con qué finalidad.

---

# 5. Actividad con IA: "Acta de auditoría del TP final"

**Modalidad:** en parejas. **Duración estimada:** una clase de trabajo más la
entrega del acta *(ajustable)*.

## Consigna para el estudiante

Una vez finalizado el trabajo práctico del eje 2, cada pareja realizará una
auditoría técnica de su propio código utilizando el prompt provisto por el
docente. El producto de la actividad **no es el código corregido**: es un acta de
auditoría en la que el equipo toma posición frente a cada observación de la IA y
la respalda con evidencia. Un acta que acepta el cien por ciento de las
observaciones sin verificar ninguna vale menos que un acta con tres rechazos bien
fundamentados.

## Herramienta de IA

Claude, utilizado con el prompt de auditoría estandarizado que entrega el
docente (sección "Prompt de auditoría"). El prompt es idéntico para todas las
parejas.

## Interacción con la IA

1. Ejecutar el prompt de auditoría sobre el archivo HTML del trabajo práctico.
2. Obtener el informe de hallazgos.
3. Formular al menos **dos contra-preguntas** sobre hallazgos específicos, por
   ejemplo: "¿por qué esto constituye un error y no una preferencia de estilo?"
   o "¿en qué punto de la especificación de HTML5 se basa esta afirmación?".
4. Registrar las respuestas obtenidas en esas contra-preguntas.

## Producción del estudiante

Un documento con tres secciones:

**a) Acta de auditoría** — una tabla con una fila por hallazgo:

| Hallazgo (según la IA) | Ubicación | Categoría asignada por el equipo | Veredicto y fundamento | Evidencia | Acción tomada |
|---|---|---|---|---|---|
|  | línea / etiqueta | Error real · Mejora · Falso positivo | justificación técnica propia | enlace a MDN o captura del validador del W3C | Aplicada · No aplicada |

**b) Código antes y después**, con las correcciones aceptadas aplicadas.

**c) Registro de interacción:** transcripción o capturas del intercambio con la
IA, incluidas las dos contra-preguntas.

## Análisis crítico

El equipo deberá obligatoriamente:

- **Rechazar con fundamento al menos un hallazgo.** Si considera que el informe
  fue íntegramente correcto, deberá demostrarlo verificando cada punto en el
  validador del W3C.
- **Verificar en el validador del W3C** todos los hallazgos de carácter
  estructural, y adjuntar el resultado.
- **Identificar lo que la IA no dijo:** señalar al menos un aspecto del trabajo
  práctico que el informe no revisó y que el equipo considera relevante.
- **Detectar afirmaciones sin respaldo:** marcar todo hallazgo que la IA no haya
  podido fundamentar en la especificación cuando se lo repreguntó.

## Criterios de evaluación sugeridos

| Criterio | Peso |
|---|---|
| Calidad del fundamento técnico en los veredictos | 35 % |
| Verificación efectiva contra fuente normativa | 25 % |
| Detección de falsos positivos y omisiones de la IA | 25 % |
| Coherencia entre los veredictos y las correcciones aplicadas | 15 % |

---

## Prompt de auditoría (entrega el docente)

```text
Actúa como revisor de código HTML5, con criterio de semántica y accesibilidad.

CONTEXTO
El siguiente código corresponde a un trabajo práctico de un curso introductorio
de HTML. No fue escrito por un profesional: espera errores propios de quien
está aprendiendo.

TAREA
Revisa el código en estos cuatro ejes:
1. Validez estructural (anidamiento, etiquetas sin cerrar, atributos obligatorios).
2. Semántica (uso correcto de las etiquetas de HTML5 según su significado).
3. Accesibilidad (textos alternativos, jerarquía de encabezados, etiquetado de
   formularios, idioma del documento).
4. Buenas prácticas de escritura del documento.

FORMATO DE SALIDA
Una tabla con estas columnas: Hallazgo | Ubicación (línea o etiqueta) |
Categoría (Error / Mejora / Observación) | Fundamento normativo |
Corrección sugerida | ¿Verificable en el validador del W3C? (Sí/No)

RESTRICCIONES
- No reescribas el documento completo ni devuelvas el archivo corregido.
- Máximo 10 hallazgos, ordenados de mayor a menor severidad.
- No sugieras CSS ni JavaScript: la auditoría es exclusivamente de HTML.
- Si no tienes certeza de que algo sea un error, indícalo explícitamente como
  "Requiere verificación" en la columna de categoría.
- Para cada hallazgo, cita la referencia concreta (MDN o especificación de HTML)
  en la que te basas.

CÓDIGO A AUDITAR:
[pegar aquí el archivo HTML]
```

## Prompt base para Stitch (entrega el docente)

```text
Diseña la interfaz de [tipo de sitio del TP: por ejemplo, una página de
presentación personal] para visualización en escritorio.

Debe incluir, como regiones claramente diferenciadas:
- un encabezado con el título del sitio y la navegación principal;
- un área de contenido principal dividida en [cantidad] secciones temáticas;
- un bloque de contenido complementario o lateral;
- un pie de página con información de contacto.

Estilo visual: limpio y sobrio, sin imágenes decorativas. Prioriza que la
separación entre las regiones sea evidente a simple vista.

Genera 3 variantes de distribución.
```

**Recordatorio para el estudiante:** el resultado de Stitch es un punto de
partida para decidir la estructura, no un diseño a reproducir. El código que la
herramienta exporta no puede utilizarse en la entrega.
