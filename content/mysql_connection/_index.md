+++
archetype = "chapter"
title = "Conexión con MySQL"
weight = 24
+++

Se puede conectar de dos maneras:
1. Extension mySQLi
2. PDO (PHP Data Objects)

Usaremos la primera: se puede acceder al GUI `phpMyAdmin` desde XAMPP o en la dirección `http://localhost/phpmyadmin/`

## Crear una base de datos
Desde `phpMyAdmin` ir a la pestaña `Databases`, ingresar el nombre de la base de datos (ej - `businessdb`), y presionar `Create`

Verificar que esté creada desde la pestaña `Databases`

## Conexion a mysql
Crear `database.php` para establecer la conexion con la base de datos; e incluirlo en `index.php`

La función `mysqli_connect()` permite hacerlo, retorna un objeto. 

Parámetros: el nombre del servidor, nombre de usuario, password, y nombre de la base de datos. Podemos obtener estos desde `phpMyAdmin` en `User accounts`
{{< highlight type="php" title="database.php" wrap="true" hl_lines="6">}}

$db_server = "localhost";
$db_user = "root";
$db_pass = "";
$db_name = "businessdb";

$conn = mysqli_connect(
    $db_server,
    $db_user,
    $db_pass,
    $db_name
);

if($conn){
    echo "Estas conectado a la DB";
}
else{
    echo "NO estas conectado a la DB";
}
{{< /highlight >}}
Probar con exito, luego apagar MySQL desde XAMPP y probar con error

## try, catch
No es buena idea mostrar el error a un usuario, es mejor englobar la conexión en un bloque `try, catch`

{{< highlight  type="php" wrap="true" title="database.php" hl_lines="6 16">}}

$db_server = "localhost";
$db_user = "root";
$db_pass = "";
$db_name = "businessdb";

try{
    $conn = mysqli_connect(
        $db_server,
        $db_user,
        $db_pass,
        $db_name
    );

    echo "Conectado a la BD";
}
catch(mysqli_sql_exception){
    echo "Error al conectar a la BD";
}

{{< /highlight >}}
Probar con exito, luego apagar MySQL desde XAMPP y probar con error