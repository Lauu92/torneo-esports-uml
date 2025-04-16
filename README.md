# Sistema de Gestión de Torneos de eSport.

##
Autor: Laura Vinseiro Gutiérrez
Github: Lauu92

Link repositorio: https://github.com/Lauu92/torneo-esports-uml.git

Este proyecto implementa un sistema de gestión de torneos de eSports utilizando UML para el modelado. 

Diagrama de Casos de Uso: (diagrams/casos-uso.png)
Diagrama de Clases: (diagrams/clases.png)


##Justificación del diseño
¿Quiénes son los actores que interactúan con el sistema?
Los actores principales del sistema son los administradores, jugadores y el sistema. 

¿Cuáles son las acciones que cada actor puede realizar?
Las acciones por realizar según el actor son:
-	Administrador: el administrador es el encargado de generar las acciones referentes a los torneos; es decir, crea torneos, inscribe a los equipos en los torneos y genera emparejamientos de partidas. 
-	Jugador: como jugador vamos a entender aquel actor que pertenece al equipo, independientemente del rango que ostente. Al ser un equipo de eSports, sabemos que sus participantes básicamente son aquellos que juegan directamente en las competiciones. No cuentan normalmente con otras figuras como presidentes o delegados como los equipos deportivos “normales”. Es por ello por lo que ellos mismo se encargan de las gestiones propias relacionadas con las competiciones. Debido a todo esto, veremos que en los casos de uso ellos son los actores encargados de las gestiones referidas al equipo (registrar el equipo en los torneos, añadir jugadores a sus equipos y consultar las listas de equipos y jugadores). 
-	Sistema: el sistema se encarga de registrar los resultados de las partidas, actualizar la clasificación del sistema y asignar los premios a los ganadores. Son las acciones más “automáticas” de todo el entramado, ya que se generan “automáticamente” después de llevarse a cabo las partidas. 
¿Cómo se relacionan entre sí las entidades del sistema?
Las relaciones que se dan entre los elementos del sistema son todas de dependencia. Esto significa que los elementos no se contienen entre ellos, pero si que depende su existencia unos de otros. Por poner un ejemplo, para inscribir un equipo en un torneo, ese torneo debe existir previamente; en caso contrario, no se puede llevar a cabo la acción de inscribir. 

Hemos estructurado el proyecto en las siguientes clases:
-	Equipo
Tipo: clase
Atributos: idEquipo: String, nombre: String, numJugadores: int, puntos: int.
Métodos: getNombre(): String, setNombre(): Void, getIdEquipo(): String, setIdEquipo(): Void, getNumJugadores(): Int, setNumJugadores(): Void, getPuntos(): Int, setPuntos(): Void
-	Jugador
Tipo: clase.
Atributos: idJugador: String, nombre: String, apellidos: String, nacionalidad: String, equipo: String.
Métodos: getNombre(): String, setNombre(): Void, getEquipo(): String, setEquipo(): Void, getApellido(): String, setApellido(): Void, getNacionalidad(): String, setNacionalidad(): Void, getEquipo(): String, setEquipo(): Void


-	Torneo
Tipo: clase.
Atributos: -idTorneo: String, nombre: String, numEquiposParticipantes: Int, ganador: Equipo.
Métodos: getNombre(): String, setNombre(): Void, getIdTorneo(): String, setIdTorneo(): Void, getNumEquiposParticipantes(): Int, setNumEquiposParticipantes(): Void, getGanador(): Equipo, setGanador(): Void.
-	Partida
Tipo: clase.
Atributos: idPartida: String, nombre: String, equipo1: Equipo, equipo2: Equipo, ganador: Equipo
Métodos:  getNombre(): String, setNombre(): Void, getIdPartida(): String, setIdPartida(): Void, getEquipo1(): Equipo, setEquipo2(): Void, getEquipo1(): Equipo, setEquipo2(): Void, getGanador(): Equipo, setGanador(): Void


-	IDAO
Tipo: interfaz.
Atributos: List<Object>
Métodos:  insertarUno(J Objetc): int, eliminarUno(J Object): int, actualizarUno(J Object): int, borrarUno(J Object): int, mostrarTodos(List<Object>).
  
-	TorneoDaoImpl
Atributos: List<Torneo>
Métodos: añadirEquipo(Equipo equipo): int, actualizarClasificación(Equipo equipo, int posicion), asignarPremio(Equipo equipo).

-	PartidaDaoImpl
Atributos: List<Partida>
Métodos: generarEmparejamiento(Equipo eq1, Equipo eq2): int, registrarResultado(int resultado): boolean.

-	EquipoDaoImpl
Atributos: List<Equipo>
Métodos: añadirJugador(Jugador jugador): int
-	JugadorDaoImpl
Atributos: List<Jugador>

El diagrama UML se ha estructurado en tres partes. En la parte superior, tenemos las clases pertenecientes al modelo o javabean (Torneo, Partida, Equipo y Jugador). A continuación, tenemos la parte de control con las clases que implementan el interface IDAO, que podemos observar en la parte inferior del esquema. En cuanto a las relaciones, vemos como las clases de implementación evidentemente tienen una relación de implements, mientras que las clases principales están agregadas entre ellas de forma ordenada. 


##Conclusiones
Mediante este ejercicio sobre UML y casos de uso, he podido identificar algunos puntos clave sobre estas herramientas. Aún así, considero que la actividad no me ha ayudado a afianzar realmente esos conocimientos. 
He llegado a la conclusión de que UML permite representar visualmente los aspectos que consideremos más importantes de un sistema. Además, los casos de uso son indispensables para entender las interacciones entre los usuarios y el sistema. Esta primera aproximación me ha permitido poder familiarizarme tanto con la terminología como con la estructura de uso tanto de UML como de los casos de uso, aunque mi comprensión en general es limitada para aplicarlos con verdadera precisión y claridad.

