+++
archetype = "chapter"
title = "20. Cookies"
weight = 20
+++

Se establecen con la función `setcookie()`, al hacerlo se guarda en la supervariable `$_COOKIE` que contiene valores `key=>value`. 

Parámetros:
1. nombre de la cookie
2. valor de la cookie
3. tiempo a ser guardado
4. ubicación de almacenamiento

Para eliminar la cookie se establece el tercer parámetro: `time()-0`

```php
setcookie("fav_food", "pollo", time() + 86400, "/");
setcookie("fav_drink", "guarana", time() + 86400, "/");
setcookie("fav_dessert", "doughnuts", time() - 0, "/");

echo $_COOKIE["fav_food"] . "<br>";

foreach ($_COOKIE as $key => $value) {
    echo "$key = $value <br>";
}

if (isset($_COOKIE["fav_dessert"])) {
    echo "Tu postre favorito es {$_COOKIE["fav_dessert"]}";
} else {
    echo "No sé tu postre favorito";
}
```