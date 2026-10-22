<div align="center">

# ⚡ Neovim para Ciberseguridad y Scripting

### Guía práctica de atajos para Termux en Android

![Neovim](https://img.shields.io/badge/Editor-Neovim-57A143?logo=neovim&logoColor=white)
![Termux](https://img.shields.io/badge/Terminal-Termux-000000?logo=android&logoColor=white)
![Licencia](https://img.shields.io/badge/Licencia-MIT-blue)

**Edita scripts, trabaja con herramientas de pentesting y compila código desde tu móvil.**

</div>

Fuente: configuración de Neovim del laboratorio [i-HakLab](https://github.com/ivam3/i-haklab) (menú de ayuda).

---


Guía rápida de atajos de **Neovim**, pensada para usarse desde el móvil con **Termux**. Teclas a la izquierda, lo que hacen a la derecha.

Solo incluye lo que más se usa para **editar scripts, trabajar con herramientas de pentesting y compilar código**.

Fuente: configuración de Neovim del laboratorio [i-HakLab](https://github.com/ivam3/i-haklab) (menú de ayuda).

---

## 🧭 Índice de contenidos

1. [Cómo leer esta guía](#cómo-leer-esta-guía)
2. [Abrir, guardar y salir](#1-abrir-guardar-y-salir)
3. [Modos](#2-modos)
4. [Moverse por el código](#3-moverse-por-el-código)
5. [Editar](#4-editar)
6. [Objetos de texto](#5-objetos-de-texto)
7. [Modo Visual](#6-modo-visual-selección)
8. [Modo Insertar](#7-modo-insertar)
9. [Buscar y reemplazar](#8-buscar-y-reemplazar)
10. [Ventanas, buffers y pestañas](#9-ventanas-buffers-y-pestañas)
11. [Buscar archivos y texto (Telescope)](#10-buscar-archivos-y-texto-telescope)
12. [Explorador de archivos (Nvim Tree)](#11-explorador-de-archivos-nvim-tree)
13. [LSP y autocompletado](#12-programar-lsp-y-autocompletado)
14. [Ejecutar y compilar](#13-ejecutar-y-compilar-sin-salir-de-neovim)
15. [Macros y registros](#14-macros-y-registros)
16. [Marcas](#15-marcas)
17. [Plegar código](#16-plegar-código)
18. [Asistentes de IA](#17-asistentes-de-ia)
19. [Los 10 atajos que debes dominar primero](#los-10-atajos-que-debes-dominar-primero)

---

## Cómo leer esta guía

| Símbolo | Significa |
|---|---|
| `<leader>` | La tecla **coma** (`,`) en esta configuración |
| `<C-x>` | Mantén **Ctrl** y pulsa `x` |
| `<A-x>` | Mantén **Alt** y pulsa `x` |
| `Esc` | Volver al modo Normal |
| `{n}` | Un número (por ejemplo `25G`) |

**Idea clave:** Neovim funciona por **modos**. En modo **Normal** las teclas son comandos; en modo **Insertar** escribes texto. Si algo raro pasa, pulsa `Esc` dos veces.

> En Termux, `Esc` y `Ctrl` están en la barra extra de teclas. Si no te funciona `Esc`, esta configuración también permite `jk` para volver a Normal.

**Atajos nativos vs. atajos de esta configuración:** los que usan `<leader>`, `<F3>`, `<F4>`, `<A-,>` y `<C-b>` son propios de la configuración de i-HakLab. El resto funcionan en cualquier Neovim o Vim.

---

## 1. Abrir, guardar y salir

| Tecla | Acción |
|---|---|
| `nvim archivo.py` | Abrir (o crear) un archivo desde la terminal |
| `<leader>w` | Guardar |
| `<leader>x` | Guardar y salir |
| `<C-c>` | Salir **sin guardar** |
| `:w` | Guardar |
| `:q` | Salir |
| `:q!` | Salir sin guardar |
| `:wq` o `:x` | Guardar y salir |
| `:e!` | Recargar el archivo y descartar los cambios |
| `:e archivo` | Abrir otro archivo |
| `:help tema` | Ayuda de Neovim sobre un tema |

---

## 2. Modos

| Tecla | Acción |
|---|---|
| `Esc` o `jk` | Volver a modo Normal |
| `i` | Insertar antes del cursor |
| `a` | Insertar después del cursor |
| `I` | Insertar al inicio de la línea |
| `A` | Insertar al final de la línea |
| `o` | Nueva línea debajo y escribir |
| `O` | Nueva línea arriba y escribir |
| `v` | Modo Visual (seleccionar texto) |
| `V` | Seleccionar líneas completas |
| `<C-v>` | Seleccionar en bloque (columnas) |
| `R` | Modo Reemplazar (sobrescribe lo que hay) |

---

## 3. Moverse por el código

| Tecla | Acción |
|---|---|
| `h` `j` `k` `l` | Izquierda, abajo, arriba, derecha |
| `w` / `b` | Palabra siguiente / anterior |
| `e` | Final de la palabra |
| `W` / `B` / `E` | Igual, pero separando solo por espacios |
| `0` | Inicio de la línea |
| `^` | Primer carácter que no es espacio |
| `$` | Final de la línea |
| `gg` | Inicio del archivo |
| `G` | Final del archivo |
| `{n}G` | Ir a la línea `n` (por ejemplo `25G`) |
| `H` / `M` / `L` | Parte alta / media / baja de la pantalla |
| `{` / `}` | Párrafo anterior / siguiente |
| `%` | Saltar al paréntesis, llave o corchete que cierra |
| `f{c}` | Saltar al carácter `c` hacia adelante en la línea |
| `F{c}` | Saltar al carácter `c` hacia atrás en la línea |
| `t{c}` | Saltar justo antes del carácter `c` |
| `;` | Repetir el último `f` `t` `F` `T` |
| `<C-u>` / `<C-d>` | Media página arriba / abajo |
| `<C-b>` / `<C-f>` | Página completa arriba / abajo |
| `zz` | Centrar la pantalla en el cursor |
| `<C-o>` / `<C-i>` | Volver / avanzar en el historial de saltos |
| `gf` | Abrir el archivo cuyo nombre está bajo el cursor |
| `g;` | Ir al lugar del último cambio |

> En esta configuración la coma es la tecla `<leader>`, así que la coma sola ya no repite `f`/`t` en sentido inverso. Usa `;` para repetir.

---

## 4. Editar

| Tecla | Acción |
|---|---|
| `x` | Borrar el carácter bajo el cursor |
| `dd` | Cortar la línea |
| `D` | Borrar desde el cursor hasta el final de la línea |
| `yy` | Copiar la línea |
| `p` / `P` | Pegar después / antes del cursor |
| `u` | Deshacer |
| `<C-r>` | Rehacer |
| `.` | Repetir el último cambio |
| `cw` | Cambiar la palabra (borra y entra en Insertar) |
| `C` | Cambiar desde el cursor hasta el final de la línea |
| `cc` | Cambiar la línea entera |
| `r{c}` | Reemplazar un solo carácter por `c` |
| `J` | Unir la línea con la siguiente |
| `~` | Cambiar mayúscula / minúscula del carácter |
| `>>` / `<<` | Indentar / desindentar la línea |
| `==` | Auto-indentar la línea |
| `<C-a>` / `<C-x>` | Sumar / restar 1 al número bajo el cursor |
| `gcc` | Comentar / descomentar la línea (Neovim 0.10 o superior) |

**Truco:** los comandos se combinan. `d` + `w` borra una palabra. `3dd` borra 3 líneas. `y` + `$` copia hasta el final de la línea.

---

## 5. Objetos de texto

Se combinan con un operador: `d` (borrar), `c` (cambiar), `y` (copiar) o `v` (seleccionar). Aquí los ejemplos usan `d` y `c`.

| Tecla | Acción |
|---|---|
| `diw` | Borrar la palabra bajo el cursor |
| `daw` | Borrar la palabra y su espacio |
| `ci"` | Cambiar lo que hay entre comillas dobles |
| `ci'` | Cambiar lo que hay entre comillas simples |
| `di(` | Borrar lo que hay entre paréntesis |
| `da(` | Borrar los paréntesis y su contenido |
| `ci[` | Cambiar lo que hay entre corchetes |
| `di{` | Borrar lo que hay entre llaves |
| `cit` | Cambiar el contenido de una etiqueta HTML/XML |
| `dip` | Borrar el párrafo |

> Regla fácil: `i` = "dentro de", `a` = "alrededor de" (incluye los símbolos).

---

## 6. Modo Visual (selección)

| Tecla | Acción |
|---|---|
| `v` / `V` / `<C-v>` | Seleccionar por caracteres / líneas / bloque |
| `o` | Saltar al otro extremo de la selección |
| `gv` | Volver a seleccionar la selección anterior |
| `y` | Copiar la selección |
| `d` | Cortar la selección |
| `c` | Cambiar la selección |
| `>` / `<` | Indentar / desindentar la selección |
| `J` | Unir las líneas seleccionadas |
| `u` / `U` | Pasar a minúsculas / mayúsculas |
| `gc` | Comentar / descomentar la selección (Neovim 0.10 o superior) |

---

## 7. Modo Insertar

| Tecla | Acción |
|---|---|
| `<C-w>` | Borrar la palabra anterior |
| `<C-u>` | Borrar desde el inicio de la línea hasta el cursor |
| `<C-h>` | Borrar el carácter anterior (retroceso) |
| `<C-t>` / `<C-d>` | Indentar / desindentar la línea |
| `<C-r>"` | Pegar lo último copiado o borrado |
| `<C-o>` | Ejecutar un comando Normal y volver a Insertar |
| `<C-v>` | Insertar un carácter literal (por ejemplo, de control) |
| `<C-k>` | Insertar un carácter especial (ñ, á, ü) |

---

## 8. Buscar y reemplazar

| Tecla | Acción |
|---|---|
| `/texto` | Buscar hacia adelante |
| `?texto` | Buscar hacia atrás |
| `n` / `N` | Siguiente / anterior resultado |
| `*` / `#` | Buscar la palabra bajo el cursor hacia adelante / atrás |
| `:s/viejo/nuevo/g` | Reemplazar en la línea actual |
| `:%s/viejo/nuevo/g` | Reemplazar en todo el archivo |
| `:%s/viejo/nuevo/gc` | Igual, pidiendo confirmación en cada uno |
| `:noh` | Quitar el resaltado de la búsqueda |

---

## 9. Ventanas, buffers y pestañas

| Tecla | Acción |
|---|---|
| `<C-h>` `<C-j>` `<C-k>` `<C-l>` | Moverse entre ventanas |
| `:sp` o `<C-w>s` | Dividir ventana horizontalmente |
| `:vsp` o `<C-w>v` | Dividir ventana verticalmente |
| `<C-w>c` | Cerrar la ventana actual |
| `<C-w>o` | Cerrar todas las demás ventanas |
| `<C-w>=` | Igualar el tamaño de las ventanas |
| `<C-b>n` | Siguiente buffer |
| `<C-b>p` | Buffer anterior |
| `<C-b>q` | Cerrar el buffer actual |
| `:ls` | Listar los buffers abiertos |
| `:tabnew` | Nueva pestaña |
| `gt` / `gT` | Pestaña siguiente / anterior |
| `<leader>ei` | Abrir la configuración `init.lua` |

---

## 10. Buscar archivos y texto (Telescope)

| Tecla | Acción |
|---|---|
| `<leader>ff` | Buscar archivos por nombre |
| `<leader>fa` | Buscar en todos los archivos, incluidos los ocultos |
| `<leader>fw` | Buscar texto en todo el proyecto (grep) |
| `<leader>fz` | Buscar texto en el archivo actual |
| `<leader>fo` | Archivos abiertos recientemente |
| `<leader>fb` | Lista de buffers abiertos |
| `<leader>fh` | Buscar en la ayuda |
| `<leader>ma` | Buscar marcas |
| `<leader>gt` | Estado de Git |
| `<leader>cm` | Historial de commits |
| `<leader>pt` | Elegir entre terminales ocultas |

> `<leader>fw` es de lo más útil en pentesting: encuentra credenciales, rutas, IPs o funciones en un proyecto entero.

---

## 11. Explorador de archivos (Nvim Tree)

| Tecla | Acción |
|---|---|
| `<leader>e` | Abrir / cerrar el explorador |
| `Enter` | Abrir archivo o entrar en carpeta |
| `a` | Crear archivo o carpeta |
| `r` | Renombrar |
| `d` | Borrar (pide confirmación) |
| `c` / `x` / `p` | Copiar / cortar / pegar |
| `g?` | Ver todos los comandos del árbol |

---

## 12. Programar: LSP y autocompletado

Funcionan en archivos con servidor de lenguaje activo (Python, Bash, C/C++, Lua...).

| Tecla | Acción |
|---|---|
| `K` | Ver la documentación de lo que hay bajo el cursor |
| `gd` | Ir a la definición |
| `gD` | Ir a la declaración |
| `gi` | Ir a la implementación |
| `gr` | Ver todas las referencias |
| `gs` | Ver los argumentos de la función |
| `<F3>` | Renombrar el símbolo en todo el proyecto |
| `<F4>` | Acciones de código disponibles |
| `gl` | Ver el error o aviso de la línea actual |
| `[d` / `]d` | Error anterior / siguiente |
| `<leader>fm` | Formatear el código |

**Autocompletado** (con el menú abierto):

| Tecla | Acción |
|---|---|
| `<C-n>` / `<C-p>` | Siguiente / anterior sugerencia |
| `Enter` | Confirmar sugerencia |
| `<C-d>` / `<C-u>` | Desplazar la documentación abajo / arriba |

---

## 13. Ejecutar y compilar sin salir de Neovim

Comandos nativos, muy útiles para probar scripts rápido.

| Comando | Acción |
|---|---|
| `:!python3 %` | Ejecutar el archivo actual con Python |
| `:!bash %` | Ejecutar el archivo actual con Bash |
| `:!gcc % -o salida && ./salida` | Compilar un archivo C y ejecutarlo |
| `:!comando` | Ejecutar cualquier comando de terminal |
| `:r !comando` | Insertar en el archivo la salida de un comando |
| `:r archivo` | Insertar el contenido de otro archivo |
| `:%!comando` | Pasar todo el archivo por un comando externo |
| `:terminal` | Abrir una terminal dentro de Neovim |
| `:ToggleTerm` | Abrir / ocultar la terminal integrada (Toggleterm) |
| `:ToggleTerm direction=float` | Terminal flotante sobre el código |
| `:ToggleTermToggleAll` | Abrir / ocultar todas las terminales |
| `<leader>pt` | Elegir entre las terminales ocultas |
| `<C-\><C-n>` | Salir del modo terminal y volver a Normal |
| `:%!xxd` | Ver el archivo en hexadecimal |
| `:%!xxd -r` | Volver del hexadecimal al formato normal |
| `ga` | Ver el código ASCII/Unicode del carácter bajo el cursor |

> `%` significa "el archivo actual". Guarda antes de ejecutar (`<leader>w`).

---

## 14. Macros y registros

Una macro graba las teclas que pulsas y las repite después. Sirve para aplicar el mismo cambio a muchas líneas.

| Tecla | Acción |
|---|---|
| `qa` | Empezar a grabar una macro en el registro `a` |
| `q` | Dejar de grabar |
| `@a` | Reproducir la macro del registro `a` |
| `@@` | Repetir la última macro |
| `5@a` | Reproducir la macro 5 veces |
| `:g/patrón/normal @a` | Aplicar la macro a todas las líneas que coincidan |
| `:reg` | Ver el contenido de todos los registros |
| `"+y` | Copiar al portapapeles del sistema |
| `"+p` | Pegar desde el portapapeles del sistema |

**Receta para repetir un cambio en muchas líneas:**

1. Colócate en la primera línea.
2. Graba con `qa`, haz el cambio en esa línea y termina con `j` (bajar una línea).
3. Pulsa `q` para parar.
4. Reproduce con `20@a` para aplicarlo a las 20 líneas siguientes.

**Notas:**
- Mientras grabas, la barra de estado muestra `[a]` en rojo.
- Si un comando falla (por ejemplo, una búsqueda sin resultados), la macro se detiene en ese punto.
- Los comandos `"+y` y `"+p` necesitan el paquete `termux-api` instalado para funcionar en Termux.
- No compartas macros para arreglar archivos de otras personas: dependen del cursor y del contenido exacto del archivo, y pueden corromperlo sin avisar. Para eso es mejor un parche (`git diff > fix.patch` y `git apply fix.patch`) o un `sed -i`.

---

## 15. Marcas

Las marcas son marcadores para volver rápido a un punto del código.

| Tecla | Acción |
|---|---|
| `ma` | Poner la marca `a` en la posición actual |
| `'a` | Saltar a la línea de la marca `a` |
| `` `a `` | Saltar a la posición exacta de la marca `a` |
| `mA` | Poner una marca global (funciona entre archivos) |
| `'A` | Saltar a la marca global `A` |
| `` `. `` | Ir al último cambio |
| `:marks` | Listar todas las marcas |

---

## 16. Plegar código

Útil para scripts largos: oculta bloques para ver solo la estructura.

| Tecla | Acción |
|---|---|
| `za` | Abrir / cerrar el bloque bajo el cursor |
| `zc` | Cerrar bloque |
| `zo` | Abrir bloque |
| `zM` | Cerrar todos los bloques |
| `zR` | Abrir todos los bloques |
| `zp` | Ver las líneas plegadas sin abrirlas |

---

## 17. Asistentes de IA

| Tecla | Acción |
|---|---|
| `<A-,>cc` | Abrir el chat de CodeCompanion |
| `<A-,>ca` | Acciones de CodeCompanion |
| `<A-,>ci` | CodeCompanion en línea (genera código en el sitio) |
| `<A-,>ce` | Explicar el código seleccionado |
| `,lm` (en modo Visual) | Enviar la selección a Ollama (IA local) |

**Ollama local** (opcional): instálalo con `pkg install ollama`, arráncalo con `ollama serve` y descarga el modelo con `ollama pull deepseek-coder:1.3b`.

---

## Los 10 atajos que debes dominar primero

1. `i` y `Esc`: insertar y volver a Normal
2. `<leader>w`: guardar
3. `dd`, `yy`, `p`: cortar, copiar y pegar líneas
4. `u`: deshacer
5. `/texto` y `n`: buscar
6. `ciw` y `ci"`: cambiar rápido
7. `gg` y `G`: inicio y final del archivo
8. `<leader>ff` y `<leader>fw`: buscar archivos y texto
9. `gd` y `K`: entender el código
10. `:!python3 %`: ejecutar tu script

---

## 👨‍💻 Sobre el autor

Soy **M3ilan**, estudiante autodidacta de ciberseguridad, interesado en el hacking ético, el pentesting, Linux y la inteligencia artificial aplicada a la seguridad.

Aprendo mediante formación especializada, práctica en laboratorios y documentación técnica. Trabajo principalmente desde un smartphone Android con Termux.

He creado este repositorio como proyecto personal para organizar y documentar en español los atajos de Neovim y facilitar su consulta desde el móvil.

---

## 📚 Fuente y créditos

Este repositorio es un proyecto personal creado por mí, **M3ilan**. Para elaborar esta guía he utilizado como fuente de referencia la información del menú de ayuda de Neovim incluido en mi laboratorio i-HakLab.

- **Iván (Ivam3):** https://github.com/ivam3 — perfil de GitHub donde publica sus repositorios y proyectos.
- **i-HakLab:** https://github.com/ivam3/i-haklab — repositorio del laboratorio utilizado como referencia para consultar la configuración y la ayuda de Neovim.

Mi agradecimiento a Iván y a la comunidad **Ivam3byCinderella**, de la que formo parte a través de Telegram y YouTube, por compartir herramientas y recursos que contribuyen al aprendizaje técnico.

La elaboración, organización y documentación de esta guía son mi aportación personal. Los enlaces anteriores reconocen la procedencia de la herramienta y de la información utilizada como referencia.

---

## 🎯 Objetivo

Seguir aprendiendo y especializándome en ciberseguridad, hacking ético, pentesting e inteligencia artificial aplicada a la ciberseguridad, explorando cómo utilizar la IA para desarrollar herramientas y recursos prácticos que ayuden a otras personas a aprender, mejorar su seguridad digital y protegerse frente a las amenazas.

---

## Licencia

MIT. Úsalo, cópialo y compártelo libremente.
