+++
archetype = "chapter"
title = "Sesión"
weight = 21
+++

Variable super global `$_SESSION` con pares `key=>value` para guardar información en mútliples páginas, se asigna un session id a un usuario. Ej - credenciales de login.

## Iniciar sesión

Para mantener las variables de `$_SESSION` se usa la función `session_start` antes del HTML

{{< highlight type="phtml" wrap="true" title="index.php">}}
<?php
    session_start();
?>

// HTML

<?php
    $_SESSION["username"] = "gino";
    $_SESSION["password"] = "liza";

    echo $_SESSION["username"];
    echo $_SESSION["password"];
?>
{{< /highlight >}}

{{< highlight type="phtml" wrap="true" title="home.php">}}

<?php
    session_start();
?>

// html

<?php
    echo $_SESSION["username"];
    echo $_SESSION["password"];
?>
{{< /highlight >}}

## Redireccionar usando php
`header("Location: ")` Permite redireccionar a otra página usando `php`

{{< highlight type="phtml" wrap="true" title="index.php">}}
<?php
    session_start();
?>

// HTML

<?php
    // Establecer username y password, redireccionar a home.php con esos datos
    $_SESSION["username"] = "gino";
    $_SESSION["password"] = "liza";

    header("Location: home.php");
?>
{{< /highlight >}}


## Destruir sesion
`session_destroy` destruye la sesión

{{< highlight type="phtml" wrap="true" title="home.php">}}
<?php
    session_start();
?>

// boton logout

<?php
    // destruir la sesión y redireccionar a index.php
    if(isset($_POST["logout"])){
        session_destroy();
        header("Location: index.php");
    }
?>
{{< /highlight >}}