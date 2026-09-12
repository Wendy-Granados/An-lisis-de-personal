# Análisis de Personal | Mapeo de Empleados

## 1. Descripción del proyecto

Dashboard desarrollado en Power BI para visualizar y analizar información de personal mediante indicadores de empleados, salarios, desempeño, distribución por departamento, edades y años de contratación.

El proyecto integra información de empleados con el catálogo de departamentos para facilitar la consulta y el seguimiento de indicadores relacionados con la gestión de personal.

---

## 2. Objetivo

Desarrollar un dashboard interactivo que permita visualizar la composición del personal y consultar indicadores relacionados con:

- Empleados activos.
- Salarios.
- Distribución de empleados por edad.
- Desempeño de los empleados.
- Distribución por departamento.
- Años de contratación.

---

## 3. Preguntas que responde el dashboard

El dashboard permite responder preguntas como:

- ¿Cuántos empleados activos hay?
- ¿Cuál es el total de salarios registrados?
- ¿Cómo se distribuyen los empleados por edad?
- ¿Cómo se encuentra distribuido el desempeño de los empleados?
- ¿Cuántos empleados pertenecen a cada departamento?
- ¿Cómo se distribuyen los empleados según su año de contratación?

---

## 4. Fuente de datos

El proyecto utiliza información estructurada en dos tablas:

### 4.1 Tabla `Departamentos`

Contiene el catálogo de departamentos y la información de sus responsables.

| Campo | Descripción |
|---|---|
| `Cod_departamento` | Código único del departamento |
| `Departamento` | Nombre del departamento |
| `Gerente` | Gerente responsable del departamento |

### 4.2 Tabla `Integrantes`

Contiene la información individual de los empleados.

| Campo | Descripción |
|---|---|
| `Nombre de los miembros` | Nombre del empleado |
| `ID` | Identificador del empleado |
| `Salario` | Salario registrado |
| `Cargo` | Puesto del empleado |
| `Fecha Nacimiento` | Fecha de nacimiento |
| `Edad` | Edad del empleado |
| `Sexo` | Sexo registrado |
| `Fecha de contratación` | Fecha de incorporación |
| `Departamento` | Departamento al que pertenece |
| `Reclutamiento de fuente` | Fuente de reclutamiento |
| `Registro de desempeño` | Registro de desempeño |
| `Índice de satisfacción` | Índice de satisfacción registrado |
| `Intervalo_edad` | Clasificación de edad |

---

## 5. Limpieza y preparación de datos

Antes de construir el modelo y las visualizaciones, se revisó la calidad de los datos para identificar inconsistencias que pudieran afectar los indicadores.

### 5.1 Validación de estructura

Se revisó que:

- Los nombres de las columnas fueran claros y consistentes.
- Cada columna tuviera el tipo de dato correspondiente.
- Los identificadores se utilizaran como valores únicos cuando correspondiera.
- Las fechas fueran reconocidas como tipo fecha.
- Los campos numéricos fueran reconocidos como números.
- Los campos categóricos conservaran valores consistentes.

### 5.2 Identificación de valores nulos

Los valores nulos deben analizarse de acuerdo con el significado de cada campo antes de eliminarlos.

Por ejemplo, que una columna contenga valores nulos no significa automáticamente que deban eliminarse todos los registros de esa columna.

Se debe determinar:

1. ¿El dato es obligatorio para el análisis?
2. ¿El registro puede utilizarse aunque ese campo esté vacío?
3. ¿El valor nulo representa información desconocida, no aplicable o un error de captura?
4. ¿La eliminación del registro afectaría la cantidad de empleados o algún KPI?

En Power Query, la revisión puede realizarse mediante la distribución y calidad de las columnas para identificar valores válidos, errores y vacíos.

### 5.3 Regla de limpieza

La limpieza debe realizarse considerando el propósito del dashboard y no únicamente buscando eliminar valores vacíos.

Como criterio general:

- No eliminar filas únicamente porque contienen un valor nulo.
- Identificar primero qué representa el valor faltante.
- Mantener registros cuando la ausencia del dato no impida el análisis.
- Corregir o excluir registros cuando el dato sea indispensable y exista evidencia de que se trata de un registro incorrecto.
- Evitar reemplazar valores nulos por valores arbitrarios que puedan alterar los indicadores.
- Verificar los cambios después de la limpieza para asegurar que no se haya reducido o alterado incorrectamente la población analizada.

### 5.4 Validación posterior

Después de la limpieza se verificó que:

- Los registros conservaran información coherente.
- Los tipos de datos fueran correctos.
- No existieran errores que afectaran las visualizaciones.
- Las relaciones entre tablas pudieran establecerse correctamente.
- Los indicadores utilizaran información consistente.

---

## 6. Modelo de datos

El modelo está compuesto por dos tablas relacionadas mediante el departamento.

<img width="825" height="397" alt="image" src="https://github.com/user-attachments/assets/82958426-31c0-40f7-bf1b-1fccbadccc26" />

### Relación

`Departamentos[Cod_departamento]` → `Integrantes[Departamento]`

- **Departamentos:** lado 1.
- **Integrantes:** lado muchos.
- **Cardinalidad:** 1:N.

Esta relación permite utilizar la información del catálogo de departamentos para segmentar y analizar los registros de empleados.

---

## 7. Indicadores y visualizaciones

### 7.1 Tarjetas KPI

Se utilizan tarjetas para mostrar:

- **Empleados activos**
- **Salarios**

### 7.2 Distribución de empleados por edad

**Visualización:** Embudo.

Muestra la distribución de los empleados de acuerdo con sus grupos de edad.

### 7.3 Desempeño de empleados

**Visualización:** Gráfico de barras.

Permite visualizar la distribución de los registros de desempeño de los empleados.

### 7.4 Empleados por departamento

**Visualización:** Tabla.

Presenta la distribución de empleados por departamento para facilitar la consulta de la estructura del personal.

### 7.5 Año de contratación

**Visualización:** Gráfico de barras.

Muestra la cantidad de empleados según su año de contratación.

---

## 8. Resultado

El resultado es un dashboard interactivo que integra información de empleados y departamentos para facilitar la consulta de indicadores de personal mediante diferentes visualizaciones.

### Vista del dashboard
<img width="877" height="487" alt="image" src="https://github.com/user-attachments/assets/97b0e619-26d6-48f4-89af-2fe0090cfc28" />
