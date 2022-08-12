# Kubernetes / K8s

Kubernetes es la plataforma de orquestación que mayor éxito tiene en el mercado.

## Contenedores

Un contenedor es un concepto abstracto que se conforma de diferentes tecnologias:

* Control groups: Un contenedor o preceso tenga aislado los recursos de memória, I/O, red, procesador.
* Namespaces: Aislar un proceso en un sandbox para que no pueda ver el sistema operativo que hay debajo u otros contenedores.
  * mount: Visibilidad reducida de los directorios donde trabaja.
  * network: Permite que cada contenedor tenga su interfaz de red, dirección IP, tabla de rutas.
  * build: Namespaces de procesos.
* chroot: Nos permite que nuestro sistema tenga visibilidad de estos archivos donde se está trabajando y no se pueda acceder a otros recursos del sistema.

### Contenedores vs VM

Los contenedores comparten el mismo sistema operativo, mintras que las máquinas virtuales necesitan hablar con un sistema operativo invitado.

### Diferencias entre Docker y Kubernetes

Docker se encarga de gestionar los contenedores, mientras que K8s hace worklog placement; es decir, si se tienen que relacionar una gran cantidad de contenedores donde se tienen que relacionar.

Este es una evolución de los proyectos de Google Borg & Omega.

Docker nació como una empresa que ofrece determinados servicios, k8s nace como un proyecto que es recibido por la comunicad, donde pertenece a la CNCF (Cloud Native Computer Foundation).

Todos los servicios de Cloud ofrecen un servicio de k8s utilizando Docker como su container runtime.

### Kubernetes

Nos permite correr diferentes replicas y asegurarse que todas estas se encuentren funcionando.

Internamente tiene un balanceador de carga, no se necesita instalar otros recursos.

Define diferenrtes mecanismos para hacer roll-outs de código.

Políticas de escalado automáticos.

Correr Jobs batch, o procesos, donde tiene un tiempo de vida definido.

CRDs: Custom Recourse Defenition.
Service Catalog. Puedo saber que está descargado y conectame a ello.
RBAC: Añadir poíticas de roles.

### Que es un Pod?

Un Pod es un grupo de contenedores que trabajan uno al lado del otro. Podemos tener un Pod de uno o varios contenedores en el mismo host.

Todos los contenedores que viven dentro de un Pod, comparten el mismo segmento o namespace de red. Todos tienen la misma dirección IP.

Cuando se escala algo, se escala el Pod entero.