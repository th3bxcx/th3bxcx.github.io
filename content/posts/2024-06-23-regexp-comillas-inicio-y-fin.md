+++
title = "Añandiendo texto al inicio y al final de varias líneas."
author = ["BxCx"]
date = 2024-06-23T15:40:00-07:00
tags = ["emacs"]
categories = ["Emacs"]
draft = false
+++

¡Tenía un problema! Debía agregar comillas dobles '"' al inicio y al final de 120 líneas diferentes, por lo que no
debería ser una tarea manual. Para ello, tuve que utilizar las expresiones regulares (regexp).


## Para agregar texto al inicio de cada línea: {#para-agregar-texto-al-inicio-de-cada-línea}

Tenemos dos opciones:

-   Si se hace en un buffer:

Presiona `M-<` para ir al establecer una marca al inicio.

-   Si se hace en una región:

Presiona  `C-SPC` al principio de la primera línea.
Por último:
`M-x` replace-regexp RET ^ RET TuTexto RET"=, para agregar '**TuTexto**'.


## En una región, usando `string-insert-rectangle`. {#en-una-región-usando-string-insert-rectangle-dot}

Establecer la marca con `C-SPC` al inicio de la primer línea, mueve el cursor al final de la última línea, y usa `M-x
string-insert-rectangle RET` o `C-x r t`, luego ingresa el texto que deseas añadir y `RET`-


## En un buffer completo. {#en-un-buffer-completo-dot}

`C-x h` para seleccionar todo el buffer.
`M-x string-insert-rectangle RET` o `C-x r t`
Ingresa el texto que deseas añadir, y luego `RET`.
