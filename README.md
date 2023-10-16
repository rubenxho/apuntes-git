## Índice

- [Índice](#índice)
  - [Comandos Basicos](#comandos-basicos)
    - [git config](#git-config)
    - [git pull](#git-pull)
    - [git status](#git-status)
  - [Casos De Uso](#casos-de-uso)
  - [Complementos](#complementos)
    - [diferencia entre git pull y git fetch](#diferencia-entre-git-pull-y-git-fetch)

---

### Comandos Basicos

---

#### **git config**

El comando `git config` se utiliza para configurar variables específicas de Git a nivel local o global.

**Ver la configuración actual:**
  ```bash
    git config --list
  ```

**Configurar el nombre de usuario:**
  ```bash
    git config --global user.name "Name"
  ```

**Configurar el correo electrónico:**
  ```bash
    git config --global user.email "example@email.com"
  ```

**Configurar alias:**
  ```bash
    git config --global alias.aliasName "command"
  ```

**Usar alias:**
  ```bash
    git aliasName 
  ```


`--global` se aplica a todos los repositorios, mientras que si se omite, la configuración es específica para el repositorio actual.


 
**Esta configuración se guarda en nuestra carpeta git/config y prodríamos ver algo como esto:**
 ```bash
    [user]
        name = Name
        email = example@email.com
    [alias]
        aliasName = command
  ```

**[⬆ Volver al Índice](#índice)**

---

#### **git pull**

El comando `git pull` es utilizado para combinar los cambios de un repositorio remoto en tu repositorio local. Es una forma rápida de actualizar tu repositorio local con los cambios más recientes del repositorio remoto.
  ```bash
    git pull
  ```

**Enlace de interes:**  **[git pull vs git fetch](#índice)**

**[⬆ Volver al Índice](#índice)**

---

#### **git status**

El comando `git status` te permite mostrar el estado actual del repositorio.
  ```bash
    git status
  ```

**[⬆ Volver al Índice](#índice)**

---

### Complementos

---

#### **Diferencia entre git pull y git fetch**

`git fetch` descarga las referencias (ramas, etiquetas, etc.) de un repositorio remoto a tu repositorio local. Sin embargo, no fusiona estos cambios con tu rama actual. Básicamente, actualiza tu conocimiento sobre lo que ha sucedido en el repositorio remoto, pero no hace cambios en tu código local.

`git pull` descarga las referencias (ramas, etiquetas, etc.) de un repositorio remoto a tu repositorio local, pero además, fusiona automáticamente los cambios de la rama remota en tu rama local. En otras palabras, `git pull` es básicamente un `git fetch` seguido de un `git merge`.

En resumen, `git fetch` trae los cambios del repositorio remoto a tu repositorio local sin hacer ninguna fusión, mientras que `git pull` hace lo mismo pero además fusiona los cambios automáticamente en tu rama local actual.