+++
archetype = "chapter"
title = "08. Switches"
weight = 8
+++

- Se usan en lugar de muchos `elseif`
- Mas eficiente
- Menos codigo

{{< highlight  type="php" wrap="true">}}
$nota = "A";

switch($nota){
    case "A":
        echo "Excelente";
        break;
    case "B":
        echo "Bien";
        break;
    case "C":
        echo "Mas o menos";
        break;
    case "D":
        echo "Mal";
        break;
    case "E":
        echo "Muy mal";
        break;
    case "F":
        echo "Pésimo";
        break;
    default:
        echo "Invalido";
}

{{< /highlight >}}

