+++
archetype = "chapter"
title = "Arrays asociativos"
weight = 12
+++

Son valores key=>value

## Creación
`array("key" => "value");`
```php
$capitales = array(
    "Peru" => "Lima", 
    "Colombia" => "Bogota", 
    "Argentina" => "Buenos Aires", 
    "Brasil" => "Brasilia");

```
## Numero de elementos
```php
echo count($capitales);
```

## Acceso a los valores
Mediante el `key`
```php
echo $capitales["Peru"];
```

## Cambiar valores
Mediante el `key`
```php
$capitales["Peru"] = "Arequipa";
```

## Agregar elementos
Agregar un `key` que no existe en el array
```php
$capitales["Chile"] = "Santiago";
```

## Eliminar elemento final
`array_pop`
```php
array_pop($capitales);
```

## Eliminar elemento inicial
`array_shift`
```php
array_shift($capitales);
```

## Obtener llaves
`array_keys`, retorna un nuevo array
```php
$keys = array_keys($capitales);

foreach ($keys as $key) {
    echo $key . "<br>";
}
```

## Obtener valores
`array_values`, retorna un nuevo array
```php
$values = array_values($capitales);

foreach ($values as $value) {
    echo $value . "<br>";
}
```

## Invertir valores por llaves
`array_flip`, retorna un nuevo array
```php
$capitales = array_flip($capitales);
```

## Invertir
`array_reverse`, retorna un nuevo array
```php
$capitales = array_reverse($capitales);
```

## Ejercicio
Usando web, que un usuario escriba un pais y al presionar `Submit` se imprima la capital.
{{% expand title="Solución" %}}
```html
<body>
    <form action="index.php" method="post">
        <label>Ingrese pais:</label>
        <input type="text" name="pais"><br>
        <input type="submit" value="Submit">        
    </form>
</body>
```
```php
<?php
$country = $_POST["pais"];

$capitales = array(
    "Peru" => "Lima",
    "Colombia" => "Bogota",
    "Argentina" => "Buenos Aires",
    "Brasil" => "Brasilia"
);

echo "La capital de $country es $capitales[$country]";

?>
```
{{% /expand %}}