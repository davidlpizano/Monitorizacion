# Procesos

En Linux, cada proceso en ejecución tiene un identificador (**PID**) y un estado.
Los comandos `ps` y `top` permiten consultar los procesos y su actividad.

## Consultar procesos con `ps`

`ps` muestra una instantánea de los procesos en el momento de ejecutar el comando.
Estas variantes usan la sintaxis BSD de `ps`:

| Comando | Qué muestra |
| --- | --- |
| `ps a` | Procesos asociados a una terminal. |
| `ps au` | Procesos asociados a una terminal con un formato orientado al usuario. |
| `ps aux` | Procesos de todos los usuarios, incluidos los que no tienen terminal. |

En la columna `STAT`, algunos estados habituales son:

| Estado | Significado |
| --- | --- |
| `R` | En ejecución o listo para ejecutarse (*running/runnable*). |
| `S` | En espera interrumpible (*interruptible sleep*). |

### Ejemplos

`ps a` muestra procesos asociados a terminales:

![Ejemplo de salida de ps a](../img/1a.png)

`ps au` añade columnas como el usuario y el porcentaje de CPU y memoria:

![Ejemplo de salida de ps au](../img/1b.png)

`ps aux` también incluye procesos sin terminal, como servicios del sistema:

![Ejemplo de salida de ps aux](../img/1c.png)

Se puede filtrar la consulta por nombre de comando o usuario:

```bash
ps u -C nano
ps -u alumno
```

![Ejemplos de filtros de ps](../img/1d.png)

## Supervisar procesos con `top`

`top` actualiza continuamente la información de procesos y del uso de recursos.
Pulsa estas teclas mientras está abierto para ordenar la lista:

| Tecla | Orden |
| --- | --- |
| `M` | Por porcentaje de memoria (`%MEM`). |
| `P` | Por porcentaje de CPU (`%CPU`). |
| `T` | Por tiempo acumulado de CPU. |

![Ejemplo de salida de top](../img/1e.png)