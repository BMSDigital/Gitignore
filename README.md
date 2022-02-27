# Una coleccion de `.gitignore` plantillas

Esta es la colección de GitHub de [`.gitignore`][man] plantillas de archivos.
Usamos esta lista para llenar el `.gitignore` selectores de plantilla disponiblesen la interfaz de GitHub.com al crear nuevos repositorios y archivos.

Para obtener más información sobre cómo `.gitignore` funcionan los archivos y cómo usarlos,
los siguientes recursos son un excelente lugar para comenzar:

- El [capítulo Ignorar archivos][chapter] del [Libro Pro Git][progit]
- El [Ignorar el artículo de archivos][help] en el sitio de ayuda de GitHub.
- El [gitignore(5)][man] manual pagina.

[man]: http://git-scm.com/docs/gitignore
[help]: https://help.github.com/articles/ignoring-files
[chapter]: https://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository#_ignoring
[progit]: http://git-scm.com/book

## Estructura de carpetas

Admitimos una colección de plantillas, organizadas de esta manera:

- La carpeta raíz contiene plantillas de uso común, para ayudar a las personas a comenzar
  con lenguajes de programación y tecnologías populares. Estos definen un sentido
  conjunto de reglas para ayudarlo a comenzar y asegurarse de que no se está comprometiendo
  archivos sin importancia en su repositorio.
- [`Global`](./Global) contiene plantillas para varios editores, herramientas y
  sistemas operativos que se pueden utilizar en diferentes situaciones. Es recomendado
  que usted [agregue estos a su plantilla global](https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files#configuring-ignored-files-for-all-repositories-on-your-computer)
  o combine estas reglas en las plantillas específicas de su proyecto si desea usar
  ellos permanentemente.
- [`community`](./community) contiene plantillas especializadas para otros populares
  lenguajes, herramientas y proyectos, que actualmente no pertenecen a la corriente principal
  plantillas. Estos deben agregarse a las plantillas específicas de su proyecto cuando
  decidir adoptar el marco o la herramienta.

## ¿Qué hace una buena plantilla?

Una plantilla debe contener un conjunto de reglas para ayudar a los repositorios de Git a trabajar con un
lenguaje de programación, framework, herramienta o entorno específico.

Si no es posible seleccionar un pequeño conjunto de reglas útiles para esta situación,
entonces la plantilla no es adecuada para esta colección.

Si una plantilla es principalmente una lista de archivos instalados por una versión particular de
algún software (por ejemplo, un marco PHP), podría vivir bajo el `community`
directorio. Ver [plantillas versionadas](#versioned-templates) para más detalles.

Si tiene un pequeño conjunto de reglas o desea admitir una tecnología que no es
ampliamente en uso, y todavía cree que esto será útil para otros, lea el
sección sobre [plantillas especializadas](#specialized-templates) para más detalles.

Incluya detalles al abrir la solicitud de extracción si la plantilla es importante y visible. Nosotros
es posible que no lo acepte de inmediato, pero podemos promoverlo a la raíz en una fecha posterior
basado en el interés.

Comprenda también que no podemos enumerar todas las herramientas que alguna vez existieron.
Nuestro objetivo es seleccionar una colección de las plantillas _más comunes y útiles_,
no para asegurarnos de cubrir todos los proyectos posibles. Si elegimos no hacerlo
incluya su idioma, herramienta o proyecto, no es porque no sea increíble.

## Pauta de contribución

Nos encantaría que nos ayudaras a mejorar este proyecto. Para ayudarnos a mantener esta colección
alta calidad, solicitamos que las contribuciones se adhieran a las siguientes pautas.

- **Proporcione un enlace a la página de inicio de la aplicación o del proyecto**. a menos que sea
  extremadamente popular, existe la posibilidad de que los mantenedores no conozcan o no utilicen
  el idioma, el marco, el editor, la aplicación o el proyecto al que se aplica el cambio.

- **Proporcione enlaces a la documentación** que respalde el cambio que está realizando.
  Lo mejor es la documentación actual y canónica que menciona los archivos que se ignoran.
  Si la documentación no está disponible para respaldar su cambio, haga lo mejor que pueda
  para explicar para qué sirven los archivos que se ignoran.

- **Explique por qué está haciendo un cambio**. Incluso si parece evidente, por favor
  tome una oración o dos para decirnos por qué debería ocurrir su cambio o adición.
  Es especialmente útil articular por qué este cambio se aplica a _todos_
  que trabaja con la tecnología aplicable, en lugar de solo usted o su equipo.

- **Por favor considere el alcance de su cambio**. Si su cambio es específico a un
  cierto lenguaje o marco, luego asegúrese de que el cambio se realice en el
  plantilla para ese lenguaje o marco, en lugar de la plantilla para un
  editor, herramienta o sistema operativo.

- **Por favor, solo modifique _una plantilla_ por solicitud de extracción**. Esto ayuda a mantener el tirón
  solicitudes y comentarios centrados en un proyecto o tecnología específica.

En general, cuanto más pueda hacer para ayudarnos a comprender el cambio que está realizando,
más probable será que aceptemos su contribución rápidamente.

## Plantillas versionadas

Algunas plantillas pueden cambiar mucho entre versiones, y si desea contribuir
a este repositorio necesitamos seguir este flujo específico:

- la plantilla en la raíz debe ser la versión compatible actual
- la plantilla en la raíz no debe tener una versión en el nombre del archivo (es decir,
  "hojas perennes")
- Las versiones anteriores de las plantillas deben vivir en `comunidad/`
- las versiones anteriores de la plantilla deben incrustar la versión en el nombre del archivo,
  para la legibilidad

Esto ayuda a garantizar que los usuarios obtengan la última versión (porque usarán lo que sea
en la raíz) pero ayuda a los mantenedores a admitir versiones anteriores que aún están en circulación.

## Plantillas especializadas

Si tiene una plantilla que le gustaría contribuir, pero no es del todo
mainstream, considere agregar esto al directorio `community` bajo un
carpeta que mejor se adapte a su lugar.

Las reglas en su plantilla especializada deben ser específicas para el marco o
herramienta, y cualquier plantilla adicional debe mencionarse en un comentario en el
encabezado de la plantilla.

Por ejemplo, esta plantilla podría vivir en `community/DotNet/InforCRM.gitignore`:

```
# gitignore template for InforCRM (formerly SalesLogix)
# website: https://www.infor.com/product-summary/cx/infor-crm/
#
# Recommended: VisualStudio.gitignore

# Ignore model files that are auto-generated
ModelIndex.xml
ExportedFiles.xml

# Ignore deployment files
[Mm]odel/[Dd]eployment

# Force include portal SupportFiles
!Model/Portal/*/SupportFiles/[Bb]in/
!Model/Portal/PortalTemplates/*/SupportFiles/[Bb]in
```

## Flujo de trabajo de contribución

Así es como te sugerimos que propongas un cambio en este proyecto:

1. [Bifurcar este proyecto][fork] a tu cuenta.
2. [crear una rama][branch] por el cambio que pretendes hacer.
3. Haz tus cambios en tu tenedor.
4. [Enviar una solicitud de extracción][pr] De la rama de tu tenedor a nuestro `main` rama.

Usar la interfaz basada en la web para hacer cambios también está bien y lo ayudará
bifurcando automáticamente el proyecto y solicitando que se envíe también una solicitud de extracción.

[fork]: https://help.github.com/articles/fork-a-repo/
[branch]: https://help.github.com/articles/creating-and-deleting-branches-within-your-repository
[pr]: https://help.github.com/articles/using-pull-requests/

## License

[CC0-1.0](./LICENSE).

