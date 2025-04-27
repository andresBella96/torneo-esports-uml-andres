# ⚽ **Sistema de Gestión de Torneos de eSports**

## 👤 Autor  

**Andrés Bella Canet**  
  
**GitHub:** `andresBella98`

## 📚 Descripción del Proyecto  

Este proyecto implementa un sistema de gestión de torneos de **eSports**
utilizando **UML** para el modelado y **Java** para la implementación.  
  
🔗*Link del repo:* https://github.com/andresBella96/torneo-esports-uml-andres.git

## 🧩 Diagramas UML

### Diagrama de Casos de Uso  

<picture>
  <source srcset="diagrams/theme/casos-uso-dark.png" media="(prefers-color-scheme: dark)">
  <source srcset="diagrams/casos-uso.png" media="(prefers-color-scheme: light)">
  <img src="diagrams/casos-uso.png" alt="Diagrama de casos de uso">
</picture>

### Diagrama de Clases  
  
<picture>
  <source srcset="diagrams/theme/clases-dark.png" media="(prefers-color-scheme: dark)">
  <source srcset="diagrams/clases.png" media="(prefers-color-scheme: light)">
  <img src="diagrams/clases.png" alt="Diagrama de clases">
</picture>

## 🗄️ Estructura del Proyecto  

```
torneo-esports-uml/ ├── src/
│ ├── es/empresa/torneo/
│ │ ├── modelo/
│ │ ├── control/
│ │ ├── vista/
│ │ ├── Main.java
├── diagrams/
│ ├── casos-uso.png
│ ├── clases.png
├── README.md
├── .gitignore
```
## 🔧 Instalación y Ejecución

1️⃣ Clonar el repositorio:
`git clone https://github.com/usuario/torneo-esports-uml.git`  
  
2️⃣ Compilar y ejecutar el proyecto:
`cd src javac es/empresa/torneo/Main.java java es.empresa.torneo.Main`

## 📝 Justificación del diseño
Primero, se van a responder a las preguntas planteadas en el pdf de la actividad. Después, se ampliará la justificación con 
conceptos importantes respecto al diseño UML.  

#### ▶️ *¿Quiénes son los actores que interactúan con el sistema?*  
  
Los actores que interactuan en el sistema serían el **Administrador** y el **Usuario**.  

#### ▶️ *¿Cuáles son las acciones que cada actor puede realizar?*  
  
- **Administrador**: Registrar equipos y añadir jugadores.  
- **Usuario**: Consultar jugadores y equipos.  

#### ▶️ *¿Cómo se relacionan entre sí las entidades del sistema?*  
  
Como entidades definimos aquellas entes que son únicas y se definen a partir de atributos, 
con lo que en este sistema se decide establecer como entidades a **Jugador** y **Equipo**.  
  
Estas entidades además tienen una relación de **1:n**, pues pueden haber muchos jugadores pertenecientes
a un equipo y un jugador solo pertenece a un equipo.

#### ▶️ *Casos de uso y arquitectura*
Los caso de uso generales para el apartado requerido en esta actividad son: *Registrar equipo, Añadir jugadores a un equipo y Consultar lista de equipos y jugadores*.  
  
Al registro se le ha añadido un nuevo caso de uso para la comprobación de la existencia de equipos ya registrados que se relaciona con el registro de jugadores y equipos con un <include>, pues
ambos casos de uso incluyen esa comprobación.  
  
También, se ha realizado un <extend> de la consulta de listas de equipos y jugadores para ofrecer la posibilidad de filtrar estas consultas por parte del usuario. 

#### ▶️ *Clases y sus relaciones*  
  
De acuerdo al modelo **MVC**, aunque utilizado de forma muy simplificada simplificado, se ha divido el proyecto en las siguientes clases:  
  
- `Equipo`: representan el **Modelo de datos**. 
- `Jugador`: representan el **Modelo de datos**.
- `GestorTorneos`: maneja toda la **lógica de negocio**. Actua como **Control**.
- `VistaPrincipal`: actúa como **Vista**.
- `Main`: ejecuta el proyecto. 
  
La relaciones entre ellas son claras, pues hay asociaciones entre `Jugador` y `Equipo`, puesto que Jugador contiene en sus atributos a 'Equipo' y entre estas clases entidad y el `GestorTorneos`. Esto último, se debe al hecho de utilizar listas de `Jugador` y `Equipo` en `GestorTorneos` como medida para poder realizar pruebas del sistema sin tener que conectarse a ninguna base de datos o archivo/s.  
  
Por otro lado, existe una dependencia entre las clases `GestorTorneos` y `VistaPrincipal`, pues la vista necesita instanciar un objeto de tipo `GestorTorneos` para usar sus métodos y lo mismo ocurre entre la clase `Main` y `VistaPrincipal`.

## 🏁 Conclusiones
En este proyecto, se ha podido profundizar en modelado **UML** que, aunque ha sido de forma muy reducida y superficial en ciertos aspectos, ha permitido la compresión de algunos factores clave en el diseño de aplicaciones.  
  
✔️ Por un lado, se ha visto uno de los patrones de arquitectura de software más utilizados en el desarrollo de aplicaciones.  
  
✔️ También, debido a la realización de la memoria en un *README.md*, se ha podido practicar la maquetación y diseño en lenguaje markdown. Por ejemplo, aunque esto es html, se han incluído los diagramas como imágenes adaptativas al tema del navegador/github. 
  
✔️ Aunque solo la estructura está creada, no sería complicado implementar este proyecto en java con un pequeño menu en consola para hacer las primeras pruebas con **JUnit**.  
  
✔️ Y por último, pero no menos importante, nos ha forzado a pensar de forma holística, visualizando el desarrollo de software en su conjunto y no solo desde el punto de vista de la programación.

