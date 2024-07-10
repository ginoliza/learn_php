+++
archetype = "chapter"
title = "Variables GET & POST"
weight = 4
+++

Son variables que se pueden usar para obtener datos de la pagina web. Dentro de un formulario `form` se especifica:
- El archivo hacia donde van los datos (en este caso el mismo) `action="index.php"`
- El método: `method="get"` o `method="post"`. 

Se pueden observar los cambios al hacer click en el `submit`.

## _GET
- Los datos se añaden a la URL
- NO ES SEGURO
- Límite de caracteres
- Bookmark es posible con valores
- GET requests pueden ser cacheadas
- Mejor para páginas de búsqueda

{{< highlight  type="php" wrap="true" lineNos="true">}}
<body>
    <form action="index.php" method="get">
        <label>username</label><br>
        <input type="text" name="username"><br>
        
        <label>password</label><br>
        <input type="password" name="password"><br>

        <input type="submit" value="Log in">
    </form>
</body>
</html>
<?php
    echo "{$_GET["username"]} <br>";
    echo "{$_GET["password"]} <br>";
?>
{{< /highlight >}}

## _POST
- Los datos son empaquetados dentro del cuerpo del request HTTP
- MAS SEGURO
- Sin límite de caracteres
- Imposible crear un bookmark
- Requests no pueden ser cacheadas
- Mejor para enviar credenciales

{{< highlight  type="php" wrap="true" lineNos="true">}}
<body>
    <form action="index.php" method="get">
        <label>username</label><br>
        <input type="text" name="username"><br>
        
        <label>password</label><br>
        <input type="password" name="password"><br>

        <input type="submit" value="Log in">
    </form>
</body>
</html>
<?php
    echo "{$_POST["username"]} <br>";
    echo "{$_POST["password"]} <br>";
?>
{{< /highlight >}}

## Key => Value
Se puede acceder a los valores de `$_GET` y `$_POST` usando vares `$key=>$value`

Los `key` son `name` y los `value` son los valores ingresados, con excepcion del botón `submit` cuyo `value` se asigna directamente en la etiqueta.
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
foreach($_POST as $key=>$value){
    echo $key . "=" . $value . "<br>";
}
```

