+++
archetype = "chapter"
title = "Proyecto registrar"
weight = 28
+++

Crear un formulario para poder registrar un usuario en la base de datos con todo lo aprendido

{{< highlight  type="phtml" wrap="true" title="index.php">}}
<?php
// 0. Conectar con la base de datos
include("database.php");
?>

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Register</title>
</head>

<body>
    <h1>Registrar</h1>
    <!-- 1. Crear formulario -->
    <form action="<?php $_SERVER["PHP_SELF"] ?>" method="post">
        <label>username</label><br>
        <input type="text" name="username" id=""><br>

        <label>password</label><br>
        <input type="password" name="password" id=""><br>

        <input type="submit" name="submit" value="Register">

    </form>
</body>

</html>

<?php
// 2. Detectar si algo ha sido enviado
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // 3. Validar si algun campo está vacio
    if (empty($_POST["username"])) {
        echo "Ingrese usuario";
    } elseif (empty($_POST["password"])) {
        echo "Ingrese contraseña";
    } else {
        // 4. Filtrar codigo malicioso
        $username = filter_input(
            INPUT_POST,
            "username",
            FILTER_SANITIZE_SPECIAL_CHARS
        );

        $password = filter_input(
            INPUT_POST,
            "password",
            FILTER_SANITIZE_SPECIAL_CHARS
        );

        // 5. Encriptar password
        $hashed_password = password_hash($_POST["password"], PASSWORD_DEFAULT);

        echo "$username -> $password -> $hashed_password <br>";

        // 5. Manejo de excepciones
        try {
            $query = "INSERT INTO users (user, password) VALUES ('$username','$hashed_password')";
            mysqli_query($conn, $query);
            echo "inserción correcta";
        } catch (mysqli_sql_exception) {
            echo "error al insertar";
        }
    }
}
// 0. Cerrar la base de datos
mysqli_close($conn);
?>
{{< /highlight >}}

{{< highlight  type="php" wrap="true" title="database.php">}}
<?php
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
}
catch(mysqli_sql_exception){
    echo "Error al conectar a la BD";
}
?>
{{< /highlight >}}
