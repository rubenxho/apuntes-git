## Índice

- [Índice](#índice)
  - [Comandos Basicos](#comandos-basicos)
    - [git config](#git-config)
    - [git pull](#git-pull)
    - [git status](#git-status)
  - [Casos De Uso](#casos-de-uso)
  - [Complementos](#complementos)
    - [Comparación entre git pull y git fetch](#Comparación-entre-git-pull-y-git-fetch)
    - [Fichero gitignore](#fichero-gitignore)

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

**Enlace de interes:**  
**[Comparación entre git pull y git fetch](#Comparación-entre-git-pull-y-git-fetch)**

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

#### **Comparación entre git pull y git fetch**

`git fetch` descarga las referencias (ramas, etiquetas, etc.) de un repositorio remoto a tu repositorio local. Sin embargo, no fusiona estos cambios con tu rama actual. Básicamente, actualiza tu conocimiento sobre lo que ha sucedido en el repositorio remoto, pero no hace cambios en tu código local.

`git pull` descarga las referencias (ramas, etiquetas, etc.) de un repositorio remoto a tu repositorio local, pero además, fusiona automáticamente los cambios de la rama remota en tu rama local. En otras palabras, `git pull` es básicamente un `git fetch` seguido de un `git merge`.

En resumen, `git fetch` trae los cambios del repositorio remoto a tu repositorio local sin hacer ninguna fusión, mientras que `git pull` hace lo mismo pero además fusiona los cambios automáticamente en tu rama local actual.

**[⬆ Volver al Índice](#índice)**

---

#### **Fichero gitignore**

El archivo `.gitignore` es un archivo especial en un repositorio que le indica a Git qué archivos o patrones de archivos debe ignorar al realizar operaciones como git add y git commit. Esto significa que los archivos y directorios listados en el `.gitignore` no serán rastreados por Git.

El propósito principal de usar `.gitignore` es evitar que se incluyan en el control de versiones archivos que no son relevantes para el desarrollo del proyecto o que pueden generarse automáticamente a partir de otros archivos.

**[⬆ Volver al Índice](#índice)**

---