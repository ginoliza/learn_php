+++
archetype = "chapter"
title = "Server"
weight = 22
+++

Variable superglobal `$_SERVER` de pares `$key=>$value` que contiene cabeceras, ubicaciones de script y rutas. Las entradas de este array son creadas por el servidor web. Muestra casi todo lo que se necesita saber del entorno actual.

## Mostrar entradas

{{< highlight  type="phtml" wrap="true">}}
<?php
    foreach($_SERVER as $key=>$value){
        echo "$key = $value <br>";
    }
    
?>
{{< /highlight >}}

## PHP_SELF
En lugar de usar un valor estático a redirecciones o submits. Ej - al especificar el `action` en lugar de `index.html`

{{< highlight  type="phtml" wrap="true">}}
...
<body>
    <form action="<?php $_SERVER["PHP_SELF"] ?>" method="post">
    <input type="submit" value="Submit">
    </form>
    
</body>

</html>
<?php
    foreach($_SERVER as $key=>$value){
        echo "$key = $value <br>";
    }
    
?>
{{< /highlight >}}
Probar cambiando el nombre del archivo. 

Es buena práctica englobar el valor de `action` dentro de la función `htmlspecialchars` para mitigar vulnerabilidades cross site.

```phtml
<form action="<?php htmlspecialchars($_SERVER["PHP_SELF"]) ?>" method="post">
```

## REQUEST_METHOD
Es una forma preferida de detectar si algo ha sido `submitted`, en lugar de hacer 

```php
if(isset($_SESSION["submit"])){
    ...
}
```

Es conveniente:
```php
if($_SERVER["REQUEST_METHOD"] == "POST"){
    echo "Se hizo click <br>";
}
```