# Checkout simple

Una acción de Gitea (o Github) muy sencilla para ejecutar en un contenedor que tenga git instalado y que haga checkout al directorio de trabajo.

**IMPORTANTE --> Es necesario que el runner tenga instalado GIT!!**

## Descripciones de las entradas y salidas

Se ha dejado todo lo más simple posible, solo repositorio del que se hace Checkout, referencia y toquen en caso de que este sea externo

Código directo de la definición de la acción

```yaml
inputs:
  repositorio:
    description: 'Nombre del repositorio. por ejemplo, actions/checkout. Valor por defecto ${{ github.repository }}'
    default: ${{ github.repository }}
  ref:
    descripcion: >
      Rama, tag o SHA para hacer checkout. Por defecto ira a master o main
    default: ${{ github.ref }}
  token:
    description: >
      Token de acceso personal. Se obtiene del entorno pero si se quiere hacer checkout de un repositiorio
      esterno es necesario fijarlo. Valor por defecto ${{ github.token }}
    default: ${{ github.token }}
outputs:
  ref:
    descripcion: 'Rama, tag o sha donde se ha hecho checkout'
  commit:
    description: 'SHA donde se ha hecho checkout'

```