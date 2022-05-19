# Github - Buenas prácticas

## Accesos

Configurar la autenticación de github con Personal Token o SSH.

## Trabajando en un ticket

### Conceptos del ticket

- **feature**: Cuando incorporamos una nueva funcionalidad.
- **refactor**: Cuando no agregamos nuevas funcionalidades, ni arreglamos, ni testeamos, sino que buscamos escribir mejor lo que ya existe, quizás por una cuestión de performance, o solo mantenimiento.
- **spike**: Cuando vamos a crear esta branch solo para investigar, o testear un enfoque particular de una solución.
- **fix**: Cuando necesitamos arreglar la solución presentada e incorporada previamente al la main branch. Esto pasa cuando dimos merge a un código erróneo y debemos crear una nueva branch, para el mismo ticket por que aun no esta solucionado.

### Crear la branch

Siempre que comenzamos a trabajar en un nuevo ticket tenemos que mirar el nombre de la tarjeta en la que vamos a trabajar, para utilizarlo de identificador.

`<ticket_id>/<concepto>/<descripcion_con_guiones_bajos>`

**Ejemplo**:
Si la tarjeta es “[tutorial-001]- Estructura básica”, nosotros crearemos nuestra branch:

`git checkout -b tutorial-001/feature/crear_la_estructura_basica`.

### Commits

El mensaje de nuestros commits tiene que tener el identificador del ticket y el concepto al principio, para luego dejar un comentario completando la frase “Este nuevo commit va a…”

**Ejemplo**:

`git commit -m 'tutorial-001/feature Crear el índice del tutorial'`

## Subiendo un PR

Antes de subir una propuesta de código o “pull request” debemos siempre comprobar que estamos al día con la rama madre para evitar conflictos. Esto se hace haciendo un rebase de la main branch actualizada.

```sh
git checkout main # para volver a nuestra rama madre

git pull # para descargarnos actualizaciones

git checkout tutorial-001/feature/crear_la_estructura_basica # para volver a nuestra rama actual

git rebase main # para hacer un rebase de la rama madre actualizada

```

## Proceso de Merge

Colocamos como “reviewer” al colega que nos ayudará a comprobar nuestro código, y le enviamos el link por slack para que esté al tanto.

Luego que él lo revise, y esté correcto, procedemos a dar merge, y eliminar nuestra rama (branch).
