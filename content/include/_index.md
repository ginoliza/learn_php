+++
archetype = "chapter"
title = "19. Include"
weight = 19
+++

La función `include()` permite incluir contenido de diferentes archivos 

{{< highlight  type="php" wrap="true" lineNos="true" title="header.html">}}
<h1>
    Esta es la web de Gino
</h1>
<a href="index.php">Home</a>
<a href="about.php">About</a>
<hr>
{{< /highlight >}}

{{< highlight  type="php" wrap="true" lineNos="true" title="footer.html">}}
<hr>
Autor: Gino Liza
<a href="mailto:gino@liza.com">mailto:gino@liza.com</a>
{{< /highlight >}}

Pueden ser incluidos en `index.php` y `about.php`

{{< highlight  type="html" wrap="true" lineNos="true" title="index.php">}}
<?php
    include("header.html");
?>
... html
<body>
    Esta es la homepage <br>
    Cosas sobre la homepage están aquí <br>
</body>
</html>
<?php
    include("footer.html");
?>
{{< /highlight >}}

{{< highlight  type="html" wrap="true" lineNos="true" title="about.php">}}
<?php
    include("header.html");
?>
... html
<body>
    Esta es la about page <br>
    Cosas sobre la about page están aquí <br>
</body>
</html>
<?php
    include("footer.html");
?>
{{< /highlight >}}