+++
archetype = "chapter"
title = "01. Lo básico"
weight = 1
+++

## Tips
1. Instalar xampp
2. Linkear la dirección del ejecutable PHP en VSCode en `settings.json`
{{< highlight  type="json" wrap="true" title="settings.json">}}
"php.validate.executablePath" : "C:/xampp/php/php.exe"
{{< /highlight >}}
3. Poner la pagina web `website` en la carpeta `htdocs`
4. Instalar las extensiones para VSCode:
    - Live Server
    - PHP Inteliphense
    - PHP Server

## PHP
Todo dentro de un archivo `index.php`
### Imprimir
{{< highlight type="php" wrap="true">}}
echo "Hello world";
{{< /highlight>}}
### Comentarios
{{< highlight type="php" wrap="true">}}
// comentario de una sola linea
{{< /highlight>}}

{{< highlight type="php" wrap="true">}}
/*
comentario
multi
linea
*/
{{< /highlight>}}
### HTML
Los archivos **php** pueden contener:
- HTML
- CSS
- JavaScript
- PHP

{{< highlight type="phtml">}}
...html

<body>
    <h1>titulo</h1>
</body>
</html>

<?php
    // codigo php
?>
{{< /highlight >}}