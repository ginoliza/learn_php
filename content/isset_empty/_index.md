+++
archetype = "chapter"
title = "isset, empty"
weight = 13
+++

## isset()
Retorna True si una variable:
- Esta declarada
- No es `null`

```php
// true
$x = ""; 
$x = 1;
$x = "";
$x = "gino";

// false
$x;
$x = null;
```

## empty()
Retorna True si una variable:
- No esta declarada 
- `false`
- `null`
- `""`

```php
// true
$x;
$x = null;
$x = false;
$x = "";
// false
$x = "g";
$x = 1;
$x = true;
```

## Ejercicio
Ingresar nombre de usuario y contraseña. Al hacer click en el boton `Log In` validar si los valores estan establecidos.

Se puede detectar que el botón ha sido presionado si su `value` ha sido establecido.

{{% expand %}}

```html
<form action="index.php" method="post">
    <label>Username:</label>
    <input type="text" name="username"><br>

    <label>Password:</label>
    <input type="password" name="password"><br>

    <input type="submit" name="login" value="Log In">
</form>
```


```php
 if(isset($_POST["login"])){
    $username = $_POST["username"];
    $password = $_POST["password"];    

    if(empty($username)){
        echo "Debe ingresar nombre de usuario <br>";
    }
    elseif(empty($password)){
        echo "Debe ingresar contraseña <br>";
    }else{
        echo "Hola $username";
    }
}
```

{{% /expand %}}