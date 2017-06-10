# docker
Comandos de Docker

He aquí un resumen actual (versión 0.7.1) de los comandos de Docker:
attach Adjunta a un contenedor corriendo
build Construye un contenedor de un archivo Docker
commit Crea una nueva imagen de los cambios del contenedor
cp Copia archivos/carpetas de los contenedores del sistema de archivos a la ruta de host
diff Inspecciona los cambios en el sistema de archivos de un contenedor
events Obtiene eventos en tiempo real desde el servidor
export Transmite el contenido de un contenedor como un archivo tar
history Muestra el historial de una imagen
images Lista las imágenes
import Crea una nueva imagen del sistema de archivos de los contenidos a partir de un archivo tar
info Muestra el sistema de información de la pantalla
insert Inserta un archivo en una imagen
inspect Regresa información de bajo nivel en un contenedor
kill Mata a un contenedor en ejecución (corriendo)
load Carga una imagen desde un archivo tar
login Registra la sesión para el servidor de registro de Docker
logs Obtiene los registros de un contenedor
port Busca el puerto público el cual está NAT-eado y lo hace privado (PRIVATE_PORT)
ps Lista los Contenedores
pull Descarga una imagen o un repositorio del servidor de registros Docker
push Empuja una imagen o un repositorio del servidor de registro Docker
restart Reinicia un contenedor en ejecución (corriendo)
rm Elimina uno o más contenedores
rmi Elimina una o más imágenes
run Ejecuta un comando en un contenedor
save Guarda una imagen en un archivo tar
search Busca una imagen en el índice de Docker
start Inicia un contenedor detenido
stop Detiene un contenedor en ejecución (corriendo)
tag Etiqueta una imagen en un repositorio
top Busca los procesos en ejecución de un contenedor
versión Muestra la información de versión de Docker

#Dockerfile:
Formato

FROM busybox
ENV foo /bar
WORKDIR ${foo}   # WORKDIR /bar
ADD . $foo       # ADD . /bar
COPY \$foo /quux # COPY $foo /quux

Instructions

    FROM Sets the Base Image for subsequent instructions.
    MAINTAINER (deprecated - use LABEL instead) Set the Author field of the generated images.
    RUN execute any commands in a new layer on top of the current image and commit the results.
    CMD provide defaults for an executing container.
    EXPOSE informs Docker that the container listens on the specified network ports at runtime. NOTE: does not actually make ports accessible.
    ENV sets environment variable.
    ADD copies new files, directories or remote file to container. Invalidates caches. Avoid ADD and use COPY instead.
    COPY copies new files or directories to container. Note that this only copies as root, so you have to chown manually regardless of your USER / WORKDIR setting. See https://github.com/moby/moby/issues/30110
    ENTRYPOINT configures a container that will run as an executable.
    VOLUME creates a mount point for externally mounted volumes or other containers.
    USER sets the user name for following RUN / CMD / ENTRYPOINT commands.
    WORKDIR sets the working directory.
    ARG defines a build-time variable.
    ONBUILD adds a trigger instruction when the image is used as the base for another build.
    STOPSIGNAL sets the system call signal that will be sent to the container to exit.
    LABEL apply key/value metadata to your images, containers, or daemons.

