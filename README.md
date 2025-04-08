# mb2g-depen-management
Repositorio para el curso de Entrerprise Dependency Management

## v01R00F00
Maven Bill of Materials

## v02R00F00
Se añaden al pom.xml las properties, que van a ser comunes a los micro servicios que van a usar el proyecto  
Estas properties sobreescriben lo que tengan en comun con las properties del pom del parent

## v03R00F00
Se añaden al pom.xml las dependencyManagement y las dependencies

- **dependencyManagement**.   
Este bloque se utiliza para definir versiones y configuraciones de dependencias que pueden ser heredadas por los módulos hijos del proyecto. 
No instala las dependencias directamente, sino que proporciona una forma centralizada de gestionar las versiones y configuraciones de las dependencias. 
Los módulos hijos pueden referirse a estas dependencias sin especificar la versión, ya que la versión se hereda del bloque dependencyManagement.

- **dependencies**.  
Este bloque se utiliza para declarar las dependencias que el proyecto necesita directamente. 
Las dependencias especificadas aquí se descargan e instalan cuando se construye el proyecto. 
Si una dependencia está definida en el bloque dependencyManagement del proyecto padre, los módulos hijos pueden incluirla en su propio bloque dependencies sin especificar la versión.

## v04R00F00
Se añaden al pom.xml el plugin *maven-enforcer-plugin*

El plugin se utiliza para ejecutar reglas que aseguran el cumplimiento de ciertas condiciones durante la fase de construcción del proyecto. Algunas de las reglas comunes incluyen:  

**Ban Duplicate Dependency:** Evita que haya dependencias duplicadas en el archivo pom.xml.  
**Require Maven Version:** Asegura que se esté utilizando una versión específica de Maven.  
**Require Java Version:** Verifica que se esté utilizando una versión específica de Java.  
**Ban Transitive Dependencies:** Prohíbe dependencias transitivas no deseada  
**Require Release Deps: ** Verifica que no haya ninguna dependencia con snapshot  