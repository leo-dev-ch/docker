#Ejecutar container postgres
$docker pull postgres:9.4


$docker run -p 5432:5432 --name postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres

#Environment Variables

POSTGRES_PASSWORD  variable de entorno establece la contraseña del superusuario para PostgreSQL

POSTGRES_USER se utiliza junto con POSTGRES_PASSWORD para establecer un usuario y su contraseña

PGDATA variable de entorno opcional se puede utilizar para definir otra ubicación, como un subdirectorio, para los archivos de base de datos. El valor predeterminado es /var/lib/postgresql/data, pero si el volumen de datos que está utilizando es un punto de montaje, Postgres initdb recomienda un subdirectorio (por ejemplo /var/lib/postgresql/data/Pgdata) para contener los datos.

POSTGRES_DB variable de entorno opcional se puede utilizar para definir un nombre diferente para la base de datos predeterminada que se crea cuando se inicia la imagen. Si no se especifica, se utilizará el valor de POSTGRES_USER.

POSTGRES_INITDB_ARGS variable de entorno opcional se puede utilizar para enviar argumentos a postgres initdb. El valor es una cadena de argumentos separada por el espacio como postgres initdb les esperaría. Esto es útil para agregar funcionalidad como sumas de comprobación de páginas de datos: -e POSTGRES_INITDB_ARGS = "- checksums de datos".

POSTGRES_INITDB_XLOGDIR variable de entorno opcional se puede utilizar para definir otra ubicación para el registro de transacciones de Postgres. De forma predeterminada, el registro de transacciones se almacena en un subdirectorio de la carpeta principal de datos de Postgres (PGDATA). A veces puede ser deseable almacenar el registro de transacciones en un directorio diferente que puede ser respaldado por almacenamiento con diferentes características de rendimiento o fiabilidad.

# Conectarse via psql

$ docker run -it --rm --link some-postgres:postgres postgres psql -h postgres -U postgres