# Análisis de Invariantes de Transición

Este script en Ruby implementa un análisis de invariantes de transición en una Red de Petri utilizando expresiones regulares y sustituciones para clasificar y contar las ocurrencias de grupos específicos de transiciones. Es una solución diseñada en el contexto del Trabajo Práctico Final de Programación Concurrente 2024.

## Propósito

El script tiene como objetivo:
- Leer un archivo de registro de transiciones (`transiciones.log`).
- Identificar y contar las ocurrencias de patrones de transiciones agrupados en **cuatro grupos** específicos (GRUPO1, GRUPO2, GRUPO3, GRUPO4).
- Imprimir el número de ocurrencias de cada grupo y la cadena resultante después de eliminar los patrones identificados.

## Requisitos

- Lenguaje: **Ruby** (versión 2.7 o superior).
- Sistema operativo: Windows (la ruta del archivo está configurada para este sistema, pero puede adaptarse).

## Configuración

1. **Archivo de entrada:**
    - El archivo `transiciones.log` debe estar ubicado en la ruta `D:\ProgCopncurrente\TPF_PC3\TPF_PC\`.
    - Este archivo debe contener las transiciones registradas en el formato especificado por el Trabajo Práctico Final.

2. **Dependencias:**
    - Ruby debe estar instalado en el sistema.

## Ejecución

1. Clona o descarga este repositorio en tu sistema local.
2. Asegúrate de que el archivo `transiciones.log` esté en la ruta configurada en el código.
3. Ejecuta el script desde la terminal o consola:
   ```bash
   ruby check_transition_invariants.rb
   ```

## Detalles del Código

### Funcionalidad Principal

1. **Leer el archivo de registro:**
   El script abre el archivo `transiciones.log` y lee su contenido completo.

2. **Definir la expresión regular:**
   Se utiliza una expresión regular compleja para identificar los patrones de transiciones definidos en el enunciado:
    - Ejemplo: `(T0)(.*?)(T1)(.*?)((T2)(.*?)(T5)|(T3)(.*?)(T4))(.*?)((T6)(.*?)(T9)(.*?)(T10)|(T7)(.*?)(T8))(.*?)(T11)`

3. **Clasificación de patrones:**
   Los patrones encontrados se clasifican en uno de los cuatro grupos según las transiciones involucradas:
    - GRUPO1: T0T1T3T4T7T8T11
    - GRUPO2: T0T1T3T4T6T9T10T11
    - GRUPO3: T0T1T2T5T7T8T11
    - GRUPO4: T0T1T2T5T6T9T10T11

4. **Conteo de ocurrencias:**
   Por cada patrón identificado, el script incrementa el contador correspondiente al grupo.

5. **Imprimir resultados:**
   Finalmente, imprime:
    - La cadena resultante después de eliminar los patrones identificados.
    - La cantidad de ocurrencias por grupo.

### Ejemplo de Salida

```plaintext
Remaining string: ''
GRUPO1: 15 occurrence(s)
GRUPO2: 10 occurrence(s)
GRUPO3: 8 occurrence(s)
GRUPO4: 12 occurrence(s)
```

## Posibles Mejoras

- **Compatibilidad multiplataforma:** Cambiar el manejo de rutas de archivos para soportar sistemas operativos distintos a Windows.
- **Manejo de errores:** Añadir verificaciones para asegurar que el archivo exista antes de intentar abrirlo.
- **Configuración dinámica:** Permitir al usuario especificar la ruta del archivo como argumento.

## Autor
Este script fue desarrollado como parte del Trabajo Práctico Final en el contexto de la asignatura de Programación Concurrente 2024.

## Referencias
- [Regex Debuggex](http://www.debuggex.com): Herramienta para probar y visualizar expresiones regulares.
- Enunciado del Trabajo Práctico Final 2024.
