+++
archetype = "chapter"
title = "26. Insertar a MySQL usando PHP"
weight = 26
+++

## Correr query y cerrar conexion
La función `mysqli_query` permite correr querys, sus parámetros son la conexion y la query

Cerramos la conexión con la función `mysqli_close`, su parametro es la conexión

{{< highlight type="php" wrap="true">}}
include("database.php");
$query = "INSERT INTO users (user, password) VALUES ('spongebob1', 'sb1')";
mysqli_query($conn, $query);
mysqli_close($conn);
{{< /highlight >}}

## Manejar excepciones
Englobar con un bloque `try catch`, el parámetro de `catch` es el error

```php
try{        
    mysqli_query($conn, $query);
}catch(mysqli_sql_exception){
    echo "No se pudo correr query";
}    
```

## Variables
Usar `$username` y `$password` dentro del query usando comillas simples `''` 

{{< highlight type="php" wrap="true" hl_lines="1-3">}}

$username = "user1";
$password = "password1";
$query = "INSERT INTO users (user, password) VALUES ('$username', '$password')";

try{        
    mysqli_query($conn, $query);
}catch(mysqli_sql_exception){
    echo "No se pudo correr query";
}    
mysqli_close($conn);
{{< /highlight >}}

## Encriptar
Con la función `password_hash`, su primer parámetro es el password y el segundo es el algoritmo
```php
$username = "user2";
$password = password_hash("password2", PASSWORD_DEFAULT);
```