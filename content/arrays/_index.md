+++
archetype = "chapter"
title = "11. Arrays, foreach"
weight = 11
+++

Variable que puede contener mas de un valor.

## Creación
`array()`

```php
$frutas = array("manzana", "naranja", "platano", "coco");
```

## Número de elementos
`count()`

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

## Acceder a los elementos
`[]`

```php
echo $frutas[0] . "<br>";
```

## Agregar valores al final
`array_push()`
```php
array_push($frutas, "piña");
```

## Eliminar el último valor
`array_pop()`

```php
array_pop($frutas);
```

## Eliminar el primer valor
`array_shift()`
```php
array_shift($frutas);
```

## Invertir array
`array_reverse()`, , retorna un nuevo array

```php
$frutas = array_reverse($frutas);
```
