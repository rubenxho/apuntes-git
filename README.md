## Índice

- [Índice](#índice)
  - [Áreas de trabajo](#áreas-de-trabajo)
    - [Stash](#stash)
    - [Working Directory](#working-directory)
    - [Staging Area](#staging-area)
    - [Local Repository](#local-repository)
    - [Remote Repository](#remote-repository)
  - [Comandos Basicos](#comandos-basicos)
    - [git branch](#git-branch)
    - [git clone](#git-clone)
    - [git config](#git-config)
    - [git diff](#git-diff)
    - [git fetch](#git-fetch)
    - [git log](#git-log)
    - [git merge](#git-merge)
    - [git pull](#git-pull)
    - [git remote](#git-remote)
    - [git stash](#git-stash)
    - [git status](#git-status)
    - [git switch](#git-switch)
    - [git tag](#git-tag)
  - [Casos De Uso](#casos-de-uso)
    - [Múltiples repositorios remotos](#Múltiples-repositorios-remotos)
    - [Trabajar con ramas remotas](#Trabajar-con-ramas-remotas)
  - [Complementos](#complementos)
    - [Comparación entre git pull y git fetch](#Comparación-entre-git-pull-y-git-fetch)
    - [Comparación entre git switch y git checkout](#Comparación-entre-git-switch-y-git-checkout)
    - [Fichero gitignore](#fichero-gitignore)

---

### Áreas de trabajo

---

### **Stash** 
Es el área donde se puede guardar temporalmente los cambios que no se han hecho commit. Esto permite cambiar de rama o realizar otras operaciones sin tener que hacer un commit de los cambios actuales. Puede almacenar n estados y funciona como una pila, colocando siempre de primero los últimos cambios que salvemos.

### **Working Directory**  
Es el lugar donde trabajas con los archivos de tu proyecto. Aquí es donde creas, modificas y eliminas archivos. Los cambios que haces en esta zona no se registran automáticamente en Git.

### **Staging Area** 
Es un área intermedia entre tu directorio de trabajo y tu repositorio local. Aquí colocas los archivos que quieres incluir en tu próximo commit. Puedes pensar en esta zona como un "escenario" donde preparas lo que se va a guardar en el siguiente commit.

### **Local Repository** 
Es donde Git almacena permanentemente la historia de tus commits. Es una carpeta oculta llamada .git dentro de tu directorio de trabajo. Aquí se encuentran todos los commits y las ramas de tu proyecto.

### **Remote Repository** 
Es una copia del repositorio local que se encuentra en un servidor remoto. Permite la colaboración entre diferentes desarrolladores al proporcionar un lugar centralizado donde se pueden cargar (push) y descargar (pull) los cambios.

**[⬆ Volver al Índice](#índice)**

---

### Comandos Basicos

---

#### **git branch**

El comando `git branch` es utilizado para gestionar ramas en un repositorio.
 
**Listar Ramas:**
  ```bash
    git branch
  ```

**Crear una Nueva Rama:**
  ```bash
    git branch <branch_name>
  ```

**Cambiar a una Rama Existente:**
  ```bash
    git checkout <branch_name>
  ```

**Crear y Cambiar a una Nueva Rama:**
  ```bash
    git checkout -b <branch_name>
  ```

**Eliminar una Rama:**
  ```bash
    git checkout -d <branch_name>
  ```

**Reenombrar una Rama:**
  ```bash
    git branch -m <old_name> <new_name>
  ```

**[⬆ Volver al Índice](#índice)**

---

#### **git clone**

El comando `git clone` se utiliza para crear una copia local de un repositorio Git existente. Básicamente, te permite descargar todo el historial de versiones, archivos y ramas de un repositorio remoto en tu máquina local.

  ```bash
    git clone REPOSITORY_URL
  ```

**[⬆ Volver al Índice](#índice)**

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

#### **git diff**

El comando `git diff` te permite ver las diferencias entre los cambios que has realizado en tu repositorio local y el estado actual del repositorio (ya sea el último commit o el estado en una rama específica). Es importante resaltar que solo muestra las diferencias; no realiza cambios en tu repositorio. Es una herramienta útil para entender qué cambios has realizado antes de confirmarlos con un commit.
 
**Diferencias entre el área de trabajo y el área de ensayo (staging area):**
  ```bash
    git diff
  ```

**Diferencias entre el área de ensayo (staging area) y el último commit:**
  ```bash
    git diff --staged
  ```

**Diferencias entre dos commits:**
  ```bash
    git diff <commit1> <commit2>
  ```

**Diferencias entre una rama y otra:**
  ```bash
    git diff <branch1>..<branch2>
  ```

**[⬆ Volver al Índice](#índice)**

---

#### **git fetch**

El comando `git fetch` es utilizado para obtener los últimos cambios de un repositorio remoto en tu repositorio local. Sin embargo, no fusiona estos cambios con tu rama actual.

  ```bash
    git fetch
  ```

**Enlaces de interés:**  
- **[Comando git pull](#git-pull)**
- **[Comparación entre git pull y git fetch](#Comparación-entre-git-pull-y-git-fetch)**

**[⬆ Volver al Índice](#índice)**

---

#### **git log**

El comando `git log` es utilizado para ver el historial de commits en un repositorio. Este comando muestra una lista de los commits en orden cronológico inverso, lo que significa que el commit más reciente aparece primero.

  ```bash
    git log
  ```

Cada entrada del registro (log entry) muestra información sobre un commit, incluyendo:

1- Commit Hash: Un identificador único para el commit, generalmente un conjunto de caracteres alfanuméricos.
2- Autor: El nombre del autor del commit.
3- Fecha y Hora: La fecha y hora en la que se realizó el commit.
4- Mensaje del Commit: El mensaje asociado con el commit, que proporciona información sobre los cambios realizados.

**Al ejecutar este comando veriamos algo como esto:**
```bash
    commit 6dcb09b8e12b4a1ae86f3398c8b04a67e2b2dc45 (HEAD -> main, origin/main)
    Author: author <example@email.com>
    Date:   Thu Sep 23 15:22:07 2021 -0700

        message

    commit 32a15e0cb64bfcbf00a07e845c071d9116717910
    Author: author <example@email.com>
    Date:   Wed Sep 22 09:18:54 2021 -0700

        message
  ```

Puedes usar varios argumentos y opciones con git log para personalizar la salida según tus necesidades. Por ejemplo, puedes limitar la cantidad de commits mostrados, filtrar por autor, buscar commits que contengan ciertas palabras clave, entre otras cosas. 

**Recomendado para verlo mejor:**
```bash
    git log —graph —pretty=oneline
```

**Al ejecutar este comando veriamos algo como esto:**
```bash
    * 42c31d1bb428d78d25251e855dcb0d06d0be2615 (HEAD -> main, origin/main) message
    * 8c6cec21ba4158998e4699259ad096bb4e6b9a20 message   
    * 5b8b9e5053a5e173e2806d9b4f883848232ee34c Merge pull request message
    |\  
    | * effba8cf48cf84a46f5894ec2b2529799cabfa2e (origin/branch) message
    |/  
    * 6a0ecb3fb75885d389c14e0a5549180897c4eedd message
```

**[⬆ Volver al Índice](#índice)**

---


#### **git merge**

El comando `git merge` se utiliza para combinar cambios de una rama a otra. Básicamente, toma los cambios de una rama fuente y los fusiona con otra rama objetivo. Esto puede ser útil cuando estás trabajando en un proyecto con múltiples ramas y deseas combinar el trabajo que has realizado en una rama específica con la rama principal o con otra rama.

  ```bash
    git merge <branch>
  ```

Cuando ejecutas `git merge`, Git intentará combinar los cambios automáticamente. Sin embargo, en algunos casos, si hay conflictos (es decir, cambios incompatibles en el mismo lugar del código), Git no podrá hacer la fusión automáticamente y te pedirá que resuelvas los conflictos manualmente.

**[⬆ Volver al Índice](#índice)**

---

#### **git pull**

El comando `git pull` es utilizado para combinar los cambios de un repositorio remoto en tu repositorio local. Es una forma rápida de actualizar tu repositorio local con los cambios más recientes del repositorio remoto.

  ```bash
    git pull
  ```

**Enlaces de interés:**  
- **[Comando git fetch](#git-fetch)**
- **[Comparación entre git pull y git fetch](#Comparación-entre-git-pull-y-git-fetch)**

**[⬆ Volver al Índice](#índice)**

---

#### **git remote**

El comando `git remote` es utilizado para administrar los repositorios remotos en Git. Puedes usarlo para ver, agregar y eliminar repositorios remotos asociados a tu proyecto. 

**Listar nombres de los repositorios remotos asociados con tu proyecto:**
  ```bash
    git remote
  ```

**Listar nombres y url de los repositorios remotos asociados con tu proyecto:**
  ```bash
    git remote -v
  ```

**Agregar un nuevo repositorio remoto:**
  ```bash
    git remote add <name> <url>
  ```

**Elimina un repositorio remoto:**
  ```bash
    git remote remove <name>
  ```

**Renombra un repositorio remoto:**
  ```bash
    git remote rename <name> <new_name>
  ```

**Cambia la URL de un repositorio remoto:**
  ```bash
    git remote set-url <name> <url>
  ```

**Traer cambios desde un repositorio remoto:**
  ```bash
    git fetch <name>
  ```

**Traer y fusionar cambios desde un repositorio remoto:**
  ```bash
    git pull <name> <branch>
  ```

**Enviar cambios a un repositorio remoto:**
  ```bash
    git push <name> <branch>
  ```

**Enlaces de interés:**  
- **[Múltiples repositorios remotos](#Múltiples-repositorios-remotos)**
- **[Trabajar con ramas remotas](#Trabajar-con-ramas-remotas)**

**[⬆ Volver al Índice](#índice)**

---

#### **git stash**

El comando `git stash` se utiliza para guardar temporalmente los cambios locales que no están listos para ser comprometidos en un área especial llamada "stash". Esto te permite cambiar de rama o realizar otras operaciones sin tener que comprometer tus cambios locales.


**Listar Stashes:**
  ```bash
    git stash list
  ```

**Guardar Cambios en el Stash:**
  ```bash
    git stash
  ```

**Guardar Cambios en el Stash con nombre:**
  ```bash
    git stash save <name>
  ```

**Aplicar y Eliminar un Stash:**
  ```bash
    git stash pop
  ```

**Aplicar un Cambio en especifico del Stash:**
  ```bash
    git stash apply N
  ```

**Eliminar un Stash Específico:**
  ```bash
    git stash drop N
  ```

**Limpiar Todos los Stashes:**
  ```bash
    git stash clear
  ```

**[⬆ Volver al Índice](#índice)**

---

#### **git status**

El comando `git status` te permite mostrar el estado actual del repositorio.

  ```bash
    git status
  ```

**[⬆ Volver al Índice](#índice)**

---

#### **git switch**

El comando `git switch` se utiliza para cambiar entre ramas en un repositorio.

**Cambiarme a una rama:**
  ```bash
    git switch <branch>
  ```

**Crear una rama y cambiarme a ella:**
  ```bash
    git switch -c <branch>
  ```

**Enlaces de interés:**  
- **[Comparación entre git switch y git checkout](#Comparación-entre-git-switch-y-git-checkout)**

**[⬆ Volver al Índice](#índice)**

---

#### **git tag**

El comando `git tag` se utiliza para etiquetar puntos específicos en la historia de un repositorio. Estas etiquetas se utilizan comúnmente para marcar versiones de software importantes (como versiones estables para producción) para que puedan ser fácilmente referenciadas en el futuro.

**Listar todas las etiquetas:**
  ```bash
    git tag
  ```

**Crear una etiqueta ligera (Lightweight Tags):**
  ```bash
    git tag <name>
  ```

**Crear una etiqueta anotada (Annotated Tags):**
  ```bash
    git tag -a <name> -m "message"
  ```

**Buscar etiquetas con un patron:**
  ```bash
    git tag -l <pattern>
  ```

**Eliminar una etiqueta:**
  ```bash
    git tag -d <name>
  ```

**Compartir una etiqueta al repositorio remoto:**
  ```bash
    git push origin <name>
  ```

**Compartir varias etiquetas al repositorio remoto:**
  ```bash
    git push origin --tags
  ```

**[⬆ Volver al Índice](#índice)**

---

### Casos de uso

---

#### **Múltiples repositorios remotos**

Para trabajar con múltiples repositorios remotos, podemos trabajar de la siguiente manera:

**Clonar un repositorio remoto que sera mi origin:**
  ```bash
    git clone <url> 
  ```

**Agregar otro repositorio remoto:**
  ```bash
    git remote add <name> <url>
  ```

**Listado de repositorios remotos con url:**
  ```bash
    git remote -v
  ```

Ya estamos trabajando con dos repositorios, todos los cambios sin indicar el repositorio se subiran al origin, 
ahora vamos a subir cambios a los repositorios:

**Subir cambios al repositorio origin:**
  ```bash
    git add .
    git commit -m "message"
    git push
  ```

**Subir cambios a otro repositorio:**
  ```bash
    git push <name> <branch>
  ```

En caso que necesite traer cambios de otro repositorio remoto a mi repositorio origin, debo hacer lo siguiente:

**Traer y fusionar cambios de otro repositorio:**
  ```bash
    git pull <name> <name>
  ```

**Subir cambios a mi repositorio origin:**
  ```bash
    git push origin <branch>
  ```

**Enlaces de interés:**  
- **[git remote](#git-remote)**

**[⬆ Volver al Índice](#índice)**

---

#### **Trabajar con ramas remotas**

Para trabajar en una rama remota que no tienes en tu repositorio local, necesitas seguir estos pasos:

**Descargar ultimos cambios del repositorio remoto:**
  ```bash
    git fetch
  ```

**Listar ramas locales y remotas del repositorio:**
  ```bash
    git branch -a
  ```

**Crear una copia local de la rama remota:**
  ```bash
    git checkout -b <remote_branch> origin/<remote_branch>
  ```

**Enlaces de interés:**  
- **[git remote](#git-remote)**

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

#### **Comparación entre git switch y git checkout**

`git switch` fue introducido  con el propósito específico de cambiar entre ramas. Su sintaxis es más concisa y se centra principalmente en el cambio de ramas.

`git checkout` es un comando más antiguo y versátil que puede utilizarse para muchas otras operaciones además de cambiar entre ramas. Su sintaxis es más amplia y puede utilizarse para una variedad de operaciones, como la creación de nuevas ramas, deshacer cambios o moverte a un commit específico.

En resumen, `git switch` está diseñado para hacer cambios entre ramas de manera más segura. No permite cambiar a una rama si hay cambios sin commitear que puedan entrar en conflicto con los cambios de la nueva rama. mientras que `git checkout` puede ser usado para cambiar entre ramas incluso si tienes cambios sin commitear. Esto puede llevar a la pérdida de cambios si no se maneja correctamente..

**[⬆ Volver al Índice](#índice)**

---

#### **Fichero gitignore**

El archivo `.gitignore` es un archivo especial en un repositorio que le indica a Git qué archivos o patrones de archivos debe ignorar al realizar operaciones como git add y git commit. Esto significa que los archivos y directorios listados en el `.gitignore` no serán rastreados por Git.

El propósito principal de usar `.gitignore` es evitar que se incluyan en el control de versiones archivos que no son relevantes para el desarrollo del proyecto o que pueden generarse automáticamente a partir de otros archivos.

**[⬆ Volver al Índice](#índice)**

---