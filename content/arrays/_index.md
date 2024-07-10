+++
archetype = "chapter"
title = "Arrays, foreach"
weight = 11
+++

Variable que puede contener mas de un valor.

## array()
Creación del array
```php
$frutas = array("manzana", "naranja", "platano", "coco");
```

## count()
Número de elementos del array
```php
echo count($frutas);
```
## foreach
Iterar por el array
```php
foreach ($frutas as $fruta) {
    echo $fruta . "<br>";
}
```

## $arr[x]
Acceder a los elementos
```php
echo $frutas[0] . "<br>";
```

## array_push()
Agregar valores al final
```php
array_push($frutas, "piña");
```

## array_pop()
Eliminar el último valor
```php
array_pop($frutas);
```

## array_shift()
Eliminar el primer valor
```php
array_shift($frutas);
```

## array_reverse()
Invertir array
```php
$frutas = array_reverse($frutas);
```
