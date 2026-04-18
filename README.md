# Git & GitHub — Guia Completa

---

## Tabla de Contenidos

1. [Que es Git](#que-es-git)
2. [Que es GitHub](#que-es-github)
3. [Relacion entre Git y GitHub](#relacion-entre-git-y-github)
4. [Diferencias clave](#diferencias-clave)
5. [Comandos de Git mas usados](#comandos-de-git-mas-usados)
   - [Configuracion inicial](#configuracion-inicial)
   - [Iniciar y clonar repositorios](#iniciar-y-clonar-repositorios)
   - [Estado y diferencias](#estado-y-diferencias)
   - [Staging y commits](#staging-y-commits)
   - [Ramas (Branches)](#ramas-branches)
   - [Fusionar y rebase](#fusionar-y-rebase)
   - [Repositorios remotos](#repositorios-remotos)
   - [Historial y logs](#historial-y-logs)
   - [Deshacer cambios](#deshacer-cambios)
   - [Stash](#stash)

---

## Que es Git

**Git** es un sistema de control de versiones distribuido, de codigo abierto, creado por **Linus Torvalds** en 2005. Permite a los desarrolladores registrar el historial completo de cambios de un proyecto, trabajar en paralelo mediante ramas y revertir el codigo a cualquier estado anterior.

### Caracteristicas principales

- **Distribuido:** cada desarrollador tiene una copia completa del repositorio con todo su historial.
- **Rapido:** la mayoria de operaciones son locales, sin necesidad de conexion a internet.
- **Integridad:** todo cambio queda identificado por un hash SHA-1, lo que garantiza que el historial no puede ser alterado sin que Git lo detecte.
- **Ramas baratas:** crear y fusionar ramas es una operacion liviana y muy eficiente.

> Git es una herramienta que corre en tu maquina local. No necesitas internet para usarlo.

---

## Que es GitHub

**GitHub** es una plataforma web de alojamiento de repositorios Git en la nube, adquirida por Microsoft en 2018. Agrega sobre Git una capa de colaboracion, visibilidad y herramientas de desarrollo como:

- **Pull Requests (PR):** propuestas de cambios que se revisan antes de fusionarse.
- **Issues:** sistema de seguimiento de tareas, bugs y mejoras.
- **GitHub Actions:** automatizacion de flujos de trabajo (CI/CD).
- **GitHub Pages:** publicacion de sitios web estaticos.
- **Code Review:** revision de codigo con comentarios en linea.
- **Forks:** copia personal de un repositorio ajeno para contribuir.

> GitHub es el servicio en la nube. Existen alternativas como GitLab, Bitbucket y Gitea.

---

## Relacion entre Git y GitHub

```
[ Tu maquina local ]          [ Nube ]

  Codigo fuente
       |
       v
  [ Git ]  ────── push ──────>  [ GitHub ]
           <───── pull/clone ──

  - Rastrea cambios            - Almacena el repo
  - Gestiona ramas             - Facilita colaboracion
  - Historial local            - Revision de codigo (PR)
                               - Automatizacion (Actions)
```

**Git** es el motor que registra y gestiona los cambios. **GitHub** es la plataforma que aloja esos repositorios y facilita el trabajo en equipo. Se usan juntos pero son independientes: puedes usar Git sin GitHub (repositorio solo local) y GitHub internamente usa Git como sistema de versionado.

---

## Diferencias clave

| Caracteristica   | Git                        | GitHub                       |
| ---------------- | -------------------------- | ---------------------------- |
| Tipo             | Software / herramienta CLI | Plataforma web (SaaS)        |
| Instalacion      | Se instala en tu maquina   | Se accede desde el navegador |
| Uso sin internet | Si                         | No                           |
| Repositorios     | Locales                    | Remotos (en la nube)         |
| Colaboracion     | No nativa                  | Pull Requests, Issues, Forks |
| Automatizacion   | No                         | GitHub Actions (CI/CD)       |
| Costo            | Gratuito y open-source     | Gratis con planes de pago    |
| Alternativas     | Mercurial, SVN             | GitLab, Bitbucket, Gitea     |

---

## Comandos de Git mas usados

### Configuracion inicial

```bash
# Establecer nombre de usuario global
git config --global user.name "Tu Nombre"

# Establecer email global
git config --global user.email "tu@email.com"

# Ver toda la configuracion actual
git config --list
```

---

### Iniciar y clonar repositorios

```bash
# Inicializar un repositorio Git en el directorio actual
git init

# Clonar un repositorio remoto en tu maquina
git clone <url-del-repositorio>

# Clonar en una carpeta con nombre especifico
git clone <url-del-repositorio> nombre-carpeta
```

---

### Estado y diferencias

```bash
# Ver el estado actual del repositorio (archivos modificados, en staging, etc.)
git status

# Ver cambios en archivos que AUN NO estan en staging
git diff

# Ver cambios en archivos que YA estan en staging
git diff --staged
```

---

### Staging y commits

```bash
# Agregar un archivo especifico al area de staging
git add archivo.txt

# Agregar todos los cambios del directorio actual
git add .

# Crear un commit con un mensaje descriptivo
git commit -m "Mensaje del commit"

# Agregar al staging y commitear en un solo paso (solo archivos ya rastreados)
git commit -am "Mensaje del commit"

# Modificar el ultimo commit (mensaje o archivos)
git commit --amend -m "Mensaje corregido"
```

---

### Ramas (Branches)

```bash
# Listar todas las ramas locales
git branch

# Listar ramas locales y remotas
git branch -a

# Crear una nueva rama
git branch nombre-rama

# Cambiar a una rama existente
git checkout nombre-rama

# Crear y cambiar a una nueva rama en un solo paso
git checkout -b nombre-rama
git switch -c nombre-rama   # forma moderna

# Eliminar una rama local (solo si ya fue fusionada)
git branch -d nombre-rama

# Forzar eliminacion de una rama local
git branch -D nombre-rama
```

---

### Fusionar y rebase

```bash
# Fusionar una rama dentro de la rama actual
git merge nombre-rama

# Rebase: reescribir la historia de la rama actual sobre otra
git rebase nombre-rama

# Abortar un merge en conflicto
git merge --abort

# Abortar un rebase en progreso
git rebase --abort
```

---

### Repositorios remotos

```bash
# Ver los remotos configurados
git remote -v

# Agregar un remoto con el alias "origin"
git remote add origin <url>

# Subir una rama al remoto por primera vez
git push -u origin nombre-rama

# Subir cambios al remoto (una vez configurado upstream)
git push

# Descargar y fusionar cambios del remoto en la rama actual
git pull

# Descargar cambios del remoto SIN fusionar
git fetch

# Eliminar una rama en el remoto
git push origin --delete nombre-rama
```

---

### Historial y logs

```bash
# Ver el historial de commits
git log

# Historial compacto (una linea por commit)
git log --oneline

# Historial con grafico de ramas
git log --oneline --graph --all

# Ver que cambios introdujo un commit especifico
git show <hash-del-commit>
```

---

### Deshacer cambios

```bash
# Descartar cambios no guardados de un archivo (peligroso: son irreversibles)
git checkout -- archivo.txt
git restore archivo.txt        # forma moderna

# Quitar un archivo del staging sin perder los cambios
git restore --staged archivo.txt

# Revertir un commit creando uno nuevo (seguro en ramas compartidas)
git revert <hash-del-commit>

# Mover HEAD a un commit anterior (peligroso en ramas compartidas)
git reset --hard <hash-del-commit>

# Reset suave: vuelve al commit pero conserva los cambios en staging
git reset --soft <hash-del-commit>
```

---

### Stash

El stash guarda temporalmente cambios sin necesidad de hacer un commit.

```bash
# Guardar cambios actuales en el stash
git stash

# Guardar con un mensaje descriptivo
git stash push -m "descripcion de los cambios"

# Ver todos los stashes guardados
git stash list

# Recuperar el ultimo stash y eliminarlo del stash
git stash pop

# Recuperar un stash especifico sin eliminarlo
git stash apply stash@{2}

# Eliminar un stash especifico
git stash drop stash@{0}

# Eliminar todos los stashes
git stash clear
```

---

## Flujo de trabajo tipico

```bash
# 1. Clonar el repositorio
git clone <url>

# 2. Crear una rama para tu feature o fix
git checkout -b feature/mi-nueva-funcionalidad

# 3. Hacer cambios en el codigo...

# 4. Ver que cambios realizaste
git status
git diff

# 5. Agregar y commitear
git add .
git commit -m "feat: agregar nueva funcionalidad"

# 6. Subir la rama al remoto
git push -u origin feature/mi-nueva-funcionalidad

# 7. Abrir un Pull Request en GitHub y solicitar revision

# 8. Tras aprobar y fusionar, actualizar main local
git checkout main
git pull
```

---

> Creado por **Facundo Cotto, Ignacio Correa , Pia Schiavone, Bruno Crizul**
