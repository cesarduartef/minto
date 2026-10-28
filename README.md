# Minto

**Una skill para Claude que ordena tus ideas con el Principio de la Pirámide de Barbara Minto: la conclusión primero y los argumentos agrupados con lógica.**

🇬🇧 [Read in English](README.en.md)

---

## Qué hace

Le pasas un correo, una propuesta, un informe o una idea suelta, y Minto te ayuda a que el lector entienda lo importante en la primera línea.

**No necesitas conocer el método: la skill lo aplica por ti.** Le hablas de tu texto como le hablarías a un colega, y ella te responde sobre tu texto, no sobre teoría.

Tiene cuatro modos, y Claude elige el adecuado según lo que le pidas:

| Modo | Cuándo | Qué recibes |
|---|---|---|
| **Aclarar** | Tienes una intención pero no sabes cómo plantearla | Hasta cuatro preguntas y una ficha con tu idea principal y sus argumentos |
| **Estructurar** | Tienes notas, datos o un borrador para reordenar | El texto con la conclusión primero, sin perder ni inventar datos |
| **Revisar** | Quieres saber si tu texto se entiende | Un diagnóstico con veredicto, hallazgos citando tu texto y las tres correcciones que más rinden. No te reescribe nada sin permiso |
| **Definir el problema** | Antes de una propuesta o una investigación | Una ficha con la situación, el resultado que no quieres, el que sí quieres y la pregunta que tu documento debe responder |

## Un ejemplo

**Antes**
> Hola Ana. Ayer nos reunimos con el equipo para revisar el avance de la campaña. Revisamos los indicadores de las tres primeras semanas, conversamos con el área de ventas y también vimos los costos de pauta. Ventas comentó que los leads llegan con poca información. El costo por lead subió 30% respecto al plan. El formulario actual pide solo nombre y correo. Creemos que habría que hacer algunos ajustes. ¿Podemos conversarlo?

**Después**
> **Asunto: ¿Apruebas cambiar el formulario de la campaña esta semana?**
> Hola Ana. Te pido aprobar un cambio en el formulario de la campaña esta semana, para atacar dos problemas que vimos ayer:
> 1. El costo por lead está 30% por encima del plan.
> 2. Ventas recibe leads con solo nombre y correo, sin datos para calificarlos.
>
> La propuesta es agregar empresa y cargo. Si me confirmas hoy, coordino el cambio.

No se agregó ni un dato. Solo cambió el orden y quedó claro el pedido.

## Para quién es

Para cualquiera que escriba para que otros decidan o actúen: correos, propuestas, cotizaciones, informes, resúmenes ejecutivos, presentaciones, tesis, artículos académicos y clases.

No sirve para todo, y la skill lo sabe: no reordena cronologías de incidentes, manuales ni relatos, porque ahí el orden temporal es el contenido.

## Instalación

Hay dos versiones de la misma skill. **Instala solo una.** Las dos funcionan igual y responden en el idioma de tu texto; lo único que cambia es el idioma de las instrucciones.

### En Claude (web, escritorio o móvil)

1. Descarga [`minto-es.zip`](dist/minto-es.zip) (o [`minto-en.zip`](dist/minto-en.zip) para la versión en inglés).
2. En Claude, ve a **Customize > Skills**.
3. Haz clic en **+**, luego en **Create skill** y elige **Upload a skill**.
4. Sube el zip y activa la skill.

Necesitas tener activada la ejecución de código en **Settings > Capabilities**. Funciona también en el plan gratuito. Si tienes dudas, revisa la [guía oficial de skills](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

### En Claude Code

```bash
claude plugin marketplace add cesarduartef/minto
claude plugin install minto-es@minto
```

Para la versión en inglés, usa `minto-en@minto`.

## Cómo usarla

No necesitas escribir ningún comando. Claude la activa solo cuando le pides algo como:

- "Revisa este correo antes de que lo mande"
- "Ordena estas notas para un informe al directorio"
- "¿Se entiende mi idea principal?"
- "Tengo que convencer a mi jefe de X y no sé cómo plantearlo"
- "Ayúdame a definir el problema de este cliente antes de la propuesta"

También puedes llamarla directamente con `/minto`.

## Qué la hace distinta

Existen otras skills del Principio de la Pirámide, todas en inglés. Esta:

- **Está en español** (y tiene versión en inglés), y responde en el idioma de tu texto.
- **Está hecha desde el libro.** Además de las reglas de la pirámide, incluye dos partes del libro que casi nadie usa: cómo **definir un problema** antes de escribir y **siete patrones** para los documentos más frecuentes (pedir aprobación de un gasto, propuesta a un cliente nuevo, informe de avance, elegir entre alternativas y otros).
- **Cubre textos académicos y clases**, no solo documentos de negocio.
- **No inventa datos.** Lo que falta lo marca como `[falta dato: ...]`.
- **Pide permiso.** Si solo le muestras tu borrador, te dice qué ve y te ofrece reescribirlo, pero no lo cambia sin que se lo pidas.

## Cómo se probó

La skill se probó con 8 casos (correo con la conclusión enterrada, cronología de incidente, resumen académico vacío, texto en inglés, definición del problema de un cliente, entre otros), resueltos por agentes que no participaron en escribirla. Los casos y los resultados están en [`evals/`](evals/).

## Estructura del repositorio

```
minto/
├── plugins/
│   ├── minto-es/skills/minto/   ← versión en español (original)
│   └── minto-en/skills/minto/   ← versión en inglés (traducción)
├── dist/                        ← zips para instalar en Claude
├── evals/                       ← casos de prueba y resultados
└── .claude-plugin/              ← para instalar desde Claude Code
```

## Créditos

- Basada en *The Pyramid Principle: Logic in Writing and Thinking*, de **Barbara Minto**. Los principios están explicados con palabras propias. Es un homenaje: este proyecto no está afiliado a la autora. Si te sirve la skill, lee el libro.
- Algunas ideas de diseño se inspiran en otras skills abiertas sobre el mismo tema: [millwright-labs/minto-pyramid-skill](https://github.com/millwright-labs/minto-pyramid-skill) (pedir permiso antes de reescribir), [welltraum/minto](https://github.com/welltraum/minto) (prueba de mecanismo frente a razón) y [tyroneross/pyramid-principle](https://github.com/tyroneross/pyramid-principle) (veredicto de revisión). Gracias a sus autores.

## Licencia

[MIT](LICENSE). Puedes usarla, modificarla y compartirla citando la fuente.

## Autor

**César Duarte** · [LinkedIn](https://www.linkedin.com/in/cesarduartef)

¿Ideas o problemas? Abre un [issue](../../issues).
