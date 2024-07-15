+++
archetype = "chapter"
title = "Consultas MySQL usando PHP"
weight = 27
+++

## Consultar

La función `mysqli_query` realiza la consulta. Sus parámetros son la conexión y la _query_. Retorna un objeto, por lo que la asignamos a `$result`

{{< highlight  type="php" wrap="true" >}}

$query = "SELECT * FROM users WHERE user = 'user2'";
$result = mysqli_query($conn, $query);

{{< /highlight >}}

## Imprimir resultados
La función `mysqli_num_rows` retorna el número de filas de la consulta. La función `mysqli_fetch_assoc` obtiene una fila resultante como un array asociativo.

{{< highlight  type="php" wrap="true" >}}

if(mysqli_num_rows($result) > 0){
    $row = mysqli_fetch_assoc($result);
    echo $row["id"] . "<br>";
    echo $row["user"] . "<br>";
    echo $row["password"] . "<br>";
}

{{< /highlight >}}

## Imprimir toda la tabla
Podemos dejar de especificar el usuario con el `WHERE` en la consulta. E imprimi englobando `mysqli_fetch_assoc` en un loop `while`.

{{< highlight  type="php" wrap="true" hl_lines="1 5">}}
$query = "SELECT * FROM users";
$result = mysqli_query($conn, $query);

if(mysqli_num_rows($result) > 0){
    while($row = mysqli_fetch_assoc($result)){
        echo $row["id"] . "<br>";
        echo $row["user"] . "<br>";
        echo $row["password"] . "<br><br>";
    };        
}
{{< /highlight >}}