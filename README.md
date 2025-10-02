<div align="center">
  <img width="172" height="173" alt="Frutas" src="img/frutas.png" style="display: inline-block; vertical-align: middle;"/>
  <img src="img/titulo.png" alt="Titulo" width="600" style="display: inline-block; vertical-align: middle;"/>
  <img width="172" height="173" alt="Verduras" src="img/verduras.png" style="display: inline-block; vertical-align: middle;"/>
</div>

---

## <img width="455" height="401" alt="Descripción" src="img/descripcion.png"/>

Este proyecto consiste en un sistema de gestión de inventario desarrollado en Java que permite administrar productos perecederos y crear combos promocionales con descuentos personalizados. El sistema calcula automáticamente el precio de los combos sumando el costo por kilogramo de cada producto incluido y aplicando el descuento correspondiente.

Cuenta con una interfaz gráfica desarrollada con Java Swing y persistencia de datos mediante archivos de texto. Este proyecto fue desarrollado como parte del curso de Pruebas de Software, implementando pruebas unitarias con JUnit 5 y alcanzando un 98% de cobertura de código verificado con JaCoCo.

---

<a name="indice"></a>
## <img width="155" height="101" alt="Indice" src="img/indice.png"/>

1. [Objetivos](#objetivos)
2. [Tecnologías Utilizadas](#tecnologias-utilizadas)
3. [Requisitos Técnicos](#requisitos-tecnicos)
4. [Instalación](#instalacion)
5. [Estructura del Proyecto](#estructura-del-proyecto)
6. [Funcionalidades](#funcionalidades)
7. [Ejecución de Pruebas](#ejecucion-de-pruebas)
8. [Reportes de Cobertura](#reportes-de-cobertura)
9. [Plan de Pruebas](#plan-de-pruebas)
10. [Evidencias](#evidencias)
11. [Conclusiones](#conclusiones)
12. [Recomendaciones](#recomendaciones)
13. [Desarrolladores](#desarrolladores)
14. [Licencia](#licencia)
15. [Contacto](#contacto)

---

<a name="objetivos"></a>
## <img width="205" height="111" alt="Objetivos" src="img/objetivos.png"/>

- Aplicar técnicas de pruebas unitarias en un proyecto Java
- Implementar pruebas que cubran al menos el 90% de la lógica de negocio
- Generar y analizar informes de cobertura de código
- Diseñar un plan de pruebas completo que valide la funcionalidad del sistema

[🔼 Volver al índice](#indice)

---

<a name="tecnologias-utilizadas"></a>
## <img width="405" height="401" alt="Tecnologias Usadas" src="img/tecnologias.png"/>

- **Lenguaje:** Java 17
- **Framework de Pruebas:** JUnit 5
- **Herramienta de Cobertura:** JaCoCo
- **Gestor de Dependencias:** Maven
- **IDE:** IntelliJ IDEA 
- **Interfaz Gráfica:** Java Swing

[🔼 Volver al índice](#indice)

---

<a name="requisitos-tecnicos"></a>
## <img width="405" height="401" alt="Requisitos Tecnicos" src="img/requisitos.png"/>

- Java Development Kit (JDK) 17 o superior
- Maven 3.6 o superior
- IntelliJ IDEA (Community o Ultimate Edition)
- Git instalado en el sistema

[🔼 Volver al índice](#indice)

---

<a name="instalacion"></a>
## <img width="225" height="251" alt="Instalacion" src="img/instalacion.png"/>

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/Inventario-Combos.git
cd Inventario-Combos
```

### 2. Compilar el proyecto

```bash
mvn clean install
```

### 3. Ejecutar la aplicación

**Opción A - Desde Maven:**
```bash
mvn exec:java -Dexec.mainClass="sistemagestioncombos.VentanaPrincipal"
```

**Opción B - Desde IntelliJ IDEA:**
1. Abrir IntelliJ IDEA y seleccionar "Open"
2. Seleccionar el archivo `pom.xml` del proyecto
3. IntelliJ detectará automáticamente que es un proyecto Maven
4. Ejecutar la clase `VentanaPrincipal.java` ubicada en `src/main/java/sistemagestioncombos/`

[🔼 Volver al índice](#indice)

---

<a name="estructura-del-proyecto"></a>
## <img width="405" height="451" alt="Estructura" src="img/estructura.png"/>

```
## Estructura del Proyecto
<table><tr><td>

sistemagestioncombos/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── sistemagestioncombos/
│   │   │       ├── Producto.java              # Clase modelo de productos
│   │   │       ├── Combo.java                 # Clase modelo de combos
│   │   │       ├── Inventario.java            # Gestor de inventario
│   │   │       ├── GestorCombos.java          # Lógica de negocio para combos
│   │   │       ├── ArchivoProducto.java       # Persistencia de productos
│   │   │       ├── ArchivoCombo.java          # Persistencia de combos
│   │   │       ├── Main.java                  # Interfaz de consola
│   │   │       ├── VentanaPrincipal.java      # Menú principal GUI
│   │   │       ├── VentanaInventario.java     # Vista de productos
│   │   │       └── VentanaCombos.java         # Vista de combos
│   │   └── resources/                         # Recursos del proyecto
│   └── test/
│       └── java/
│           └── sistemagestioncombos/
│               ├── ProductoTest.java          # Pruebas de Producto
│               ├── ComboTest.java             # Pruebas de Combo
│               ├── InventarioTest.java        # Pruebas de Inventario
│               ├── GestorCombosTest.java      # Pruebas de GestorCombos
│               ├── ArchivoProductoTest.java   # Pruebas de persistencia
│               └── ArchivoComboTest.java      # Pruebas de persistencia
├── target/                                    # Archivos compilados (generado)
├── pom.xml                                    # Configuración de Maven
├── .gitignore                                 # Archivos ignorados por Git
├── combos.txt                                 # Archivo de datos (generado)
├── productos.txt                              # Archivo de datos (generado)
└── README.md                                  # Este archivo
```
</td></tr></table>

[🔼 Volver al índice](#indice)

---

<a name="funcionalidades"></a>
## <img width="315" height="311" alt="Funcionalidades" src="img/funcionalidades.png"/>

## Gestión de Productos
- **Agregar productos:** Registro de nuevos productos con todos sus atributos (nombre, precio, tipo, temporada, días para vencer, cantidad en kg)
- **Modificar productos:** Actualización de cualquier atributo de productos existentes
- **Eliminar productos:** Eliminación de productos del inventario
- **Listar productos:** Visualización de todos los productos en formato tabla con cálculo de valor total

## Gestión de Combos
- **Crear combos:** Definición de nuevos combos con nombre, temporada, descuento (%) y unidades disponibles
- **Agregar productos a combos:** Asociación de múltiples productos a un combo
- **Modificar combos:** Actualización de temporada, descuento o unidades
- **Eliminar productos de combos:** Remoción de productos específicos de un combo
- **Eliminar combos:** Eliminación completa de combos del sistema
- **Cálculo automático de precios:** El sistema calcula automáticamente el precio original sumando el precio de 1 kg de cada producto que compone el combo, y luego aplica el descuento para obtener el precio final

## Persistencia de Datos
- **Guardado automático:** Los datos se guardan automáticamente en archivos de texto al realizar cambios
- **Carga al inicio:** Los datos se cargan automáticamente al iniciar la aplicación
- **Formato de almacenamiento:** Archivos de texto plano con formato delimitado por punto y coma (;)

## Cálculos y Reportes
- **Valor total por producto:** Precio × cantidad en kg
- **Precio original de combo:** Suma del precio por kg de cada producto incluido en el combo (sin considerar la cantidad total en inventario)
- **Precio final de combo:** Precio original × (1 - descuento/100)
- **Valor total del inventario:** Suma de todos los productos individuales y el valor de todos los combos (precio final × unidades)

[🔼 Volver al índice](#indice)

---

<a name="ejecucion-de-pruebas"></a>
## <img width="405" height="401" alt="Ejecucion de pruebas" src="img/ejecucion.png"/>

## Ejecutar todas las pruebas

```bash
mvn test
```

## Ejecutar pruebas con reporte de cobertura

```bash
mvn clean test jacoco:report
```

## Ver el reporte de cobertura en el navegador

El reporte HTML se genera automáticamente en:
```
target/site/jacoco/index.html
```

Abre este archivo en tu navegador para ver el reporte detallado con cobertura por clase, método y línea.

## Ejecutar una clase de prueba específica

```bash
mvn test -Dtest=ProductoTest
```

[🔼 Volver al índice](#indice)

---

<a name="reportes-de-cobertura"></a>
## <img width="415" height="411" alt="Reportes cobertura" src="img/reportes.png"/>

Según el análisis de JaCoCo, el proyecto alcanza los siguientes niveles de cobertura:

| Clase | Cobertura de Instrucciones | Cobertura de Ramas | Instrucciones Perdidas | Ramas Perdidas | Líneas Perdidas | Métodos Perdidos |
|-------|---------------------------|-------------------|----------------------|---------------|----------------|------------------|
| ArchivoCombo | 95% | 100% | 14 de 314 | 0 de 2 | 1 de 52 | 1 de 6 |
| ArchivoProducto | 95% | 100% | 9 de 178 | 0 de 2 | 2 de 41 | 0 de 4 |
| Inventario | 98% | 91% | 34 de 1,848 | 1 de 6 | 2 de 66 | 0 de 22 |
| Combo | 100% | 97% | 41 de 1,388 | 0 de 6 | 1 de 68 | 0 de 19 |
| Producto | 100% | 100% | 40 de 1,000 | 0 de 0 | 0 de 59 | 0 de 17 |
| GestorCombos | 100% | 100% | 12 de 197 | 0 de 0 | 0 de 29 | 0 de 7 |
| **Total** | **98%** | **98%** | **150 de 4,925** | **5 de 16** | **4 de 315** | **1 de 75** |

### Análisis de Cobertura

- **Cobertura General:** 98% de instrucciones y 98% de ramas cubiertas
- **Cumplimiento del Objetivo:** Se supera ampliamente el requisito de 90% de cobertura establecido en la Etapa 2
- **Clases con Cobertura Perfecta:** Producto (100%/100%) y GestorCombos (100%/100%) alcanzan cobertura completa
- **Áreas de Mejora:** Las clases de persistencia (ArchivoCombo y ArchivoProducto) tienen 95% de cobertura, principalmente debido a casos excepcionales de manejo de archivos que son difíciles de simular en pruebas unitarias

[🔼 Volver al índice](#indice)

---

<a name="plan-de-pruebas"></a>
## <img width="315" height="311" alt="Plan pruebas" src="img/plan.png"/>

## Estrategia de Pruebas

El proyecto implementa una estrategia de pruebas exhaustiva que incluye:

1. **Pruebas Unitarias:** Cada clase de lógica de negocio tiene su archivo de pruebas correspondiente
2. **Cobertura de Casos Límite:** Se prueban valores límite, nulos e inválidos
3. **Cobertura de Ramas:** Se validan tanto flujos exitosos como casos de error
4. **Pruebas de Integración:** Se verifica la interacción correcta entre clases
5. **Pruebas de Persistencia:** Se valida el guardado y recuperación de datos

## Casos de Prueba por Módulo

#### 1. Pruebas de Producto (ProductoTest.java)

-  Creación válida de productos
-  Validación de nombre obligatorio y no vacío
-  Validación de precio no negativo
-  Validación de tipo obligatorio
-  Validación de temporada obligatoria
-  Validación de días para vencer no negativos
-  Validación de cantidad mayor a cero
-  Cálculo correcto del valor total (precio × cantidad)
-  Modificación de atributos (setters)
-  Comparación de productos (equals y hashCode)

#### 2. Pruebas de Combo (ComboTest.java)

-  Creación válida de combos
-  Validación de nombre obligatorio
-  Validación de temporada obligatoria
-  Validación de descuento entre 0 y 100
-  Validación de unidades no negativas
-  Agregar productos al combo
-  Eliminar productos del combo
-  Recálculo automático de precios al agregar/eliminar productos
-  Recálculo automático de precios al modificar descuento
-  Cálculo del valor total en inventario (precio final × unidades)
-  Protección de encapsulamiento (getProductos devuelve copia)

#### 3. Pruebas de Inventario (InventarioTest.java)

-  Agregar productos al inventario
-  Prevenir productos duplicados (mismo nombre)
-  Buscar productos por nombre (case-insensitive)
-  Eliminar productos por nombre
-  Listar todos los productos (con protección de encapsulamiento)
-  Agregar combos al inventario
-  Prevenir combos duplicados (mismo nombre)
-  Buscar combos por nombre (case-insensitive)
-  Eliminar combos por nombre
-  Listar todos los combos
-  Calcular valor total del inventario (productos + combos)

#### 4. Pruebas de GestorCombos (GestorCombosTest.java)

-  Crear combo a través del gestor
-  Agregar producto existente a combo existente
-  Manejo de error al agregar producto inexistente a combo
-  Manejo de error al agregar producto a combo inexistente
-  Eliminar producto de combo
-  Calcular valor de combo específico
-  Obtener total de combos disponibles

#### 5. Pruebas de ArchivoProducto (ArchivoProductoTest.java)

-  Guardar lista de productos en archivo
-  Cargar productos desde archivo existente
-  Manejo de archivo inexistente (retorna lista vacía)
-  Verificación de formato de archivo (campos correctos)
-  Parseo correcto de datos numéricos
-  Limpieza de espacios en blanco (trim)

#### 6. Pruebas de ArchivoCombo (ArchivoComboTest.java)

-  Guardar lista de combos en archivo
-  Cargar combos desde archivo existente
-  Reconstrucción de relaciones combo-productos
-  Manejo de archivo inexistente (retorna lista vacía)
-  Verificación de formato de archivo
-  Manejo de combos sin productos

## Tipos de Validaciones Implementadas

1. **Validaciones de Entrada:**
   - Campos obligatorios no nulos ni vacíos
   - Rangos numéricos válidos
   - Formatos de datos correctos

2. **Validaciones de Negocio:**
   - Prevención de duplicados
   - Integridad referencial (productos en combos)
   - Cálculos matemáticos correctos

3. **Validaciones de Persistencia:**
   - Formato de archivo correcto
   - Manejo de archivos inexistentes
   - Recuperación de datos consistente

[🔼 Volver al índice](#indice)

---

<a name="evidencias"></a>
## <img width="255" height="251" alt="Evidencias" src="img/evidencias.png"/>

## Evidencias de Funcionamiento de la Aplicación

### Interfaz de Consola (Main.java)
Ejecución del sistema a través de la interfaz de consola con menú de opciones:

<div align="center">
  <img src="evidencias/main.png" alt="Interfaz de Consola" width="350"/>
</div>

### Interfaz Gráfica - Ventana Principal
<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="evidencias/ventanap1.png" alt="Menú Principal" width="400"/>
        <br>
        <strong>Menú principal del sistema</strong>
      </td>
      <td align="center">
        <img src="evidencias/ventanap4.png" alt="Agregar Producto" width="400"/>
        <br>
        <strong>Formulario de captura de datos</strong>
      </td>
    </tr>
  </table>
</div>

### Gestión de Inventario de Productos
Vista de la tabla de productos con sus características, precios y cantidades:

<div align="center">
  <img src="evidencias/ventanap2.png" alt="Inventario de Productos" width="650"/>
</div>

### Gestión de Combos
Vista de la tabla de combos con productos asociados, descuentos y precios calculados:

<div align="center">
  <img src="evidencias/ventanap3.png" alt="Lista de Combos" width="650"/>
</div>


## Evidencias de Pruebas Unitarias

Ejecución exitosa de todas las clases de prueba implementadas:

### ArchivoComboTest
<div align="center">
  <img src="evidencias/ArchivoComboTest.png" alt="Pruebas ArchivoCombo" width="420"/>
</div>

### ArchivoProductoTest
<div align="center">
  <img src="evidencias/ArchivoProductoTest.png" alt="Pruebas ArchivoProducto" width="500"/>
</div>

### ComboTest
<div align="center">
  <img src="evidencias/ComboTest.png" alt="Pruebas Combo" width="450"/>
</div>

### GestorCombosTest
<div align="center">
  <img src="evidencias/GestorCombosTest.png" alt="Pruebas GestorCombos" width="450"/>
</div>

### InventarioTest
<div align="center">
  <img src="evidencias/InventarioTest.png" alt="Pruebas Inventario" width="450"/>
</div>

### ProductoTest
<div align="center">
  <img src="evidencias/ProductoTest.png" alt="Pruebas Producto" width="450"/>
</div>


## Reporte de Cobertura JaCoCo

Reporte completo de cobertura de código mostrando 98% de cobertura en instrucciones y ramas:

<div align="center">
  <img src="evidencias/JacocoTest.png" alt="Reporte de Cobertura JaCoCo" width="800"/>
</div>

*El reporte detallado en formato HTML se encuentra en `target/site/jacoco/index.html` después de ejecutar `mvn clean test jacoco:report`*

[🔼 Volver al índice](#indice)

---

<a name="conclusiones"></a>
## <img width="285" height="281" alt="Conclusiones" src="img/conclusiones.png"/>

## Logros Alcanzados

1. **Cumplimiento de Objetivos:** Se desarrolló una aplicación completa y funcional que cumple con todos los requisitos establecidos en la Etapa 2 del proyecto
2. **Alta Cobertura de Pruebas:** Se alcanzó un 98% de cobertura de código, superando ampliamente el objetivo del 90%
3. **Código de Calidad:** Se aplicaron principios SOLID y buenas prácticas de programación orientada a objetos
4. **Persistencia Exitosa:** Se implementó un sistema de almacenamiento en archivos que mantiene la integridad de los datos
5. **Interfaz Amigable:** Se desarrolló una GUI intuitiva y funcional con paleta de colores organizada
6. **Documentación Completa:** Se documentó el código, las pruebas y el proceso de desarrollo

## Aprendizajes Obtenidos

1. **Importancia de las Pruebas:** Las pruebas unitarias son fundamentales para detectar errores tempranamente y garantizar la calidad del software
2. **Uso de Herramientas:** JUnit y JaCoCo son herramientas esenciales para automatizar pruebas y medir cobertura
3. **Validación Exhaustiva:** Es necesario probar tanto casos exitosos como casos de error y valores límite
4. **Cobertura como Métrica:** La cobertura de código es un buen indicador de calidad, pero debe complementarse con pruebas significativas
5. **Diseño de Software:** Una buena arquitectura facilita la creación de pruebas y el mantenimiento del código

## Desafíos Enfrentados

1. **Persistencia de Relaciones:** Guardar y recuperar las relaciones entre combos y productos requirió un diseño cuidadoso
2. **Cobertura de Excepciones:** Alcanzar alta cobertura en el manejo de excepciones de I/O fue un reto
3. **Validaciones Consistentes:** Asegurar que todas las validaciones funcionaran correctamente en diferentes escenarios
4. **Sincronización de Datos:** Mantener la consistencia entre la interfaz gráfica y los archivos de persistencia

## Reflexión Final

Este proyecto nos permitió comprender la importancia de las pruebas de software en el ciclo de desarrollo. La implementación de pruebas unitarias exhaustivas no solo nos ayudó a detectar errores tempranamente, sino que también nos dio confianza en la calidad y estabilidad del código. El uso de herramientas profesionales como JUnit, JaCoCo y Maven nos preparó para enfrentar proyectos reales en la industria del software.

El uso de herramientas profesionales como JUnit, JaCoCo y Maven nos preparó para enfrentar proyectos reales en la industria del software. Además, el proceso de documentación nos enseñó la importancia de comunicar claramente el funcionamiento y las capacidades de un sistema.

[🔼 Volver al índice](#indice)

---

<a name="recomendaciones"></a>
## <img width="355" height="351" alt="Recomendaciones" src="img/recomendaciones.png"/> 

1. **Base de Datos:** Migrar de archivos de texto a una base de datos relacional (MySQL, PostgreSQL) para mayor robustez
2. **Pruebas de GUI:** Implementar pruebas automatizadas de la interfaz gráfica usando frameworks como AssertJ Swing
3. **API REST:** Desarrollar una API REST para permitir acceso remoto al sistema
4. **Autenticación:** Implementar un sistema de usuarios con diferentes roles y permisos
5. **Reportes Avanzados:** Agregar generación de reportes en PDF o Excel con estadísticas del inventario
6. **Validaciones en Tiempo Real:** Mejorar la experiencia de usuario con validaciones inmediatas en los formularios
7. **Búsqueda y Filtros:** Implementar funcionalidades de búsqueda avanzada y filtros en las tablas
8. **Historial de Cambios:** Mantener un registro de modificaciones para auditoría
9. **Notificaciones:** Alertas automáticas para productos próximos a vencer
10. **Internacionalización:** Soporte para múltiples idiomas

[🔼 Volver al índice](#indice)

---

<a name="desarrolladores"></a>
## <img width="355" height="351" alt="Desarrolladores" src="img/desarrolladores.png"/> 

Este proyecto fue desarrollado por Dafne Julieth Cortés, Johana Jazmín Saavedra y Michael Duvan Gómez Peña, estudiantes de cuarto semestre en Técnica profesional en programación de aplicaciones de software de la Fundación Universitaria Compensar; con una participación activa en la creación del juego y presentación del proyecto final.

<div align="center">
  <table>
    <tr>
      <td align="center" style="padding: 0 30px;">
        <img src="img/Dafne.jpg" width="120" style="border: none;"><br/>
        <strong>Dafne Julieth Cortés</strong>
        <br>
        <em>(Desarrollador Backend)</em>
      </td>
      <td align="center" style="padding: 0 30px;">
        <img src="img/johana.png" width="80" style="border: none;"><br/>
        <strong>Johana Jazmín Saavedra</strong>
        <br>
        <em>(QA Tester)</em>
      </td>
      <td align="center" style="padding: 0 30px;">
        <img src="img/Michael.png" width="120" style="border: none;"><br/>
        <strong>Michael Duvan Gómez Peña</strong>
        <br>
        <em>(Desarrollador Frontend)</em>
      </td>
    </tr>
  </table>
</div>

[🔼 Volver al índice](#indice)

---

<a name="licencia"></a>
## <img width="185" height="181" alt="Licencia" src="img/licencia.png"/> 

Este proyecto fue desarrollado con fines académicos para el curso de Pruebas de Software.

[🔼 Volver al índice](#indice)

---

<a name="contacto"></a>
## <img width="185" height="181" alt="Contacto" src="img/contacto.png"/> 

Para cualquier consulta sobre el proyecto, puede contactar a través del repositorio de GitHub.

[🔼 Volver al índice](#indice)

---

**Fecha de Última Actualización:** Octubre 2024  
**Versión:** 1.0.0
