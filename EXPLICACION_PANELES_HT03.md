# Explicacion de paneles del dashboard - Tarea HT03

## Contexto general

El dashboard `firewall-dashboard.html` representa un sistema de administracion de cortafuegos orientado a la tarea HT03: **Implementa politicas de cortafuegos** del curso **PICD-713 Aseguramiento de Entornos Virtuales**.

La tarea HT03 se enfoca en dos operaciones principales:

1. Identificar los componentes de las politicas de firewall.
2. Identificar el trafico con las politicas de firewall.

El caso practico plantea una empresa con infraestructura virtualizada basada en VMware vSphere y maquinas Linux, donde servidores web y base de datos comparten una misma red virtual. Esto genera riesgo de ataques laterales y escalamiento de privilegios, por lo que se implementa un firewall virtual, como pfSense o FortiGate-VM, para controlar el trafico entre zonas.

---

## Panel: Resumen

El panel **Resumen** funciona como vista principal del estado del firewall.

Contiene:

- Indicadores generales de seguridad.
- Politicas activas.
- Amenazas bloqueadas.
- Uptime del firewall.
- Sesiones activas.
- Paquetes por segundo.
- Topologia de red segmentada por zonas.
- Alertas recientes.
- Mapa de amenazas.
- Eventos de politica en tiempo real.
- Acceso directo al contenido HT03.

Relacion con HT03:

Este panel resume el objetivo de la practica: controlar el trafico entre zonas como WAN, LAN, DMZ, VPN e invitados. Tambien permite observar si las politicas estan permitiendo, bloqueando o registrando conexiones, lo cual corresponde a la segunda operacion de la tarea.

---

## Panel: HT03 Tarea

El panel **HT03 Tarea** contiene directamente el desarrollo de la actividad solicitada en el documento.

Contiene:

- Nombre de la tarea: HT-03 - Implementa politicas de cortafuegos.
- Curso: PICD-713 Aseguramiento de Entornos Virtuales.
- Objetivo de la tarea.
- Caso practico.
- Operaciones principales.
- Validacion por CLI pfSense.
- Materiales, equipos y herramientas.
- Componentes de una politica efectiva.
- Actividades de retroalimentacion.

Relacion con HT03:

Este panel es la adaptacion directa del documento HT03 al dashboard. Convierte la tarea en una vista visual e interactiva donde se puede revisar el objetivo, el entorno virtualizado, los recursos requeridos y los criterios tecnicos para evaluar las politicas de firewall.

---

## Panel: Politicas

El panel **Politicas** muestra la administracion de reglas de firewall.

Contiene:

- Politicas de cortafuegos activas.
- Reglas de permitir y denegar trafico.
- Orden de prioridad.
- Concepto de Deny-All.
- Detalles por politica.
- Origen.
- Destino.
- Servicio o puerto.
- Accion.
- Horario.
- Logging.

Relacion con HT03:

Este panel corresponde principalmente a la operacion 01 de la tarea: **identificar los componentes de las politicas de firewall**. Permite reconocer que una politica efectiva debe incluir interfaz, origen, destino, protocolo, puerto, accion, registro y orden de evaluacion.

---

## Panel: Reglas ACL

El panel **Reglas ACL** representa listas de control de acceso a nivel de red y transporte.

Contiene:

- Reglas L3/L4.
- Filtrado por direccion IP.
- Filtrado por protocolo.
- Filtrado por puerto.
- Acciones de permitir o denegar.
- Procesamiento secuencial de reglas.

Relacion con HT03:

Este panel ayuda a comprender como el firewall decide si un paquete puede pasar o debe bloquearse. Refuerza el analisis de trafico entre maquinas virtuales, especialmente cuando se necesita separar servidores web, base de datos y administracion.

---

## Panel: Objetos

El panel **Objetos** administra elementos reutilizables de red.

Contiene:

- Hosts.
- Subredes.
- Rangos IP.
- Grupos de servicios.
- Objetos usados por multiples politicas.

Relacion con HT03:

En la practica, los objetos permiten representar servidores virtuales, redes internas, DMZ y servicios como HTTP, HTTPS, SSH o MySQL. Esto facilita crear reglas mas ordenadas y comprensibles.

---

## Panel: Redes / Zonas

El panel **Redes / Zonas** muestra la segmentacion de la infraestructura.

Contiene:

- Zona WAN.
- Zona LAN.
- Zona DMZ.
- Zona VPN.
- Zona de invitados.
- Niveles de confianza.
- Politicas inter-zona.

Relacion con HT03:

Este panel es clave para la tarea porque el documento pide identificar interfaces de red como WAN, LAN y DMZ. La segmentacion permite separar servidores web y bases de datos para reducir riesgos de ataques laterales.

---

## Panel: NAT

El panel **NAT** muestra la traduccion de direcciones.

Contiene:

- SNAT.
- DNAT.
- Port Forwarding.
- Publicacion de servicios internos.
- Traduccion de trafico entrante y saliente.

Relacion con HT03:

En un entorno virtualizado, NAT puede usarse para permitir que servidores internos salgan a Internet o para publicar un servidor web de la DMZ sin exponer directamente toda la red interna.

---

## Panel: VPN

El panel **VPN** muestra accesos remotos seguros.

Contiene:

- Tuneles IPSec.
- Acceso SSL/TLS.
- Usuarios remotos.
- MFA.
- Trafico VPN inspeccionado por politicas.

Relacion con HT03:

La VPN representa otro origen de trafico que debe ser controlado. Las politicas deben definir si un usuario remoto puede acceder a servidores web, bases de datos o solo a servicios administrativos.

---

## Panel: IPS / IDS

El panel **IPS / IDS** muestra deteccion y prevencion de intrusiones.

Contiene:

- Alertas de seguridad.
- Firmas de ataques.
- Bloqueo de amenazas.
- Eventos criticos.
- Deteccion de malware, escaneos y exploits.

Relacion con HT03:

Este panel complementa la tarea porque ayuda a detectar trafico sospechoso. No solo se verifica si una regla permite o bloquea trafico, sino tambien si existe comportamiento malicioso entre maquinas virtuales.

---

## Panel: Control Apps

El panel **Control Apps** representa inspeccion de aplicaciones.

Contiene:

- Control de aplicaciones L7.
- Inspeccion profunda de paquetes.
- Bloqueo de aplicaciones no autorizadas.
- Politicas por tipo de aplicacion.

Relacion con HT03:

Aunque la tarea se centra en capa 3 y capa 4, este panel amplia el analisis mostrando que los firewalls modernos tambien pueden controlar trafico por aplicacion, no solo por IP y puerto.

---

## Panel: Usuarios

El panel **Usuarios** muestra autenticacion y control de acceso.

Contiene:

- Usuarios.
- Roles.
- RBAC.
- Integracion LDAP/Active Directory.
- MFA.

Relacion con HT03:

Este panel ayuda a entender que las politicas tambien pueden depender de identidades. Por ejemplo, un administrador puede tener acceso SSH, mientras que un usuario comun no debe tener acceso a la base de datos.

---

## Panel: Reportes

El panel **Reportes** muestra informes y cumplimiento.

Contiene:

- Reportes diarios.
- Reportes semanales.
- Reportes mensuales.
- Cumplimiento normativo.
- Estadisticas de amenazas y trafico.

Relacion con HT03:

La tarea pide verificar si las politicas funcionan correctamente. Los reportes sirven como evidencia para demostrar trafico permitido, trafico bloqueado y eventos registrados durante la practica.

---

## Panel: Monitoreo

El panel **Monitoreo** muestra supervision en tiempo real.

Contiene:

- CPU.
- Memoria RAM.
- Interfaces.
- Sesiones activas.
- Paquetes por segundo.
- Log del sistema.

Relacion con HT03:

Este panel se relaciona con el comando `pfctl -ss`, porque permite observar sesiones activas que atraviesan el firewall. Tambien permite verificar que las politicas no afecten negativamente el rendimiento del entorno virtualizado.

---

## Panel: Sistema

El panel **Sistema** muestra configuracion general del firewall.

Contiene:

- Version de firmware.
- Modelo.
- Licencia.
- Alta disponibilidad.
- Backups.
- Uso de recursos.
- Actualizaciones.

Relacion con HT03:

Este panel representa la plataforma donde se ejecutan las politicas. En la practica, el firewall virtual debe estar correctamente configurado, actualizado y funcionando antes de validar reglas y trafico.

---

## Comandos usados en HT03

### `pfctl -sr`

Muestra la lista de reglas activas del firewall con su orden de evaluacion.

Uso en la tarea:

- Verificar que las politicas existen.
- Revisar el orden top-down.
- Confirmar acciones de permitir, denegar o registrar.

### `pfctl -ss`

Muestra el estado actual de las sesiones que atraviesan el firewall.

Uso en la tarea:

- Identificar conexiones activas.
- Revisar IP origen y destino.
- Ver protocolos y puertos.
- Confirmar si el trafico coincide con las politicas configuradas.

---

## Conclusiones para la tarea HT03

El dashboard refleja la tarea HT03 porque organiza el contenido tecnico en paneles de gestion de firewall. Cada seccion permite observar un aspecto distinto del proceso:

- Las politicas definen las reglas.
- Las redes y zonas representan la segmentacion.
- Las ACL filtran trafico por IP, protocolo y puerto.
- Los logs y sesiones validan el trafico real.
- Los reportes documentan evidencia.
- El monitoreo confirma rendimiento y conectividad.

En conjunto, el dashboard demuestra como implementar, revisar y validar politicas de cortafuegos en un entorno virtualizado sin comprometer la conectividad ni el rendimiento de los servicios.
