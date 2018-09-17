---
layout: page
title: Pri Argilo
created: 1138463631
permalink: /pri-argilo/
---
<?php
        $dato = getdate();
        $agxo = $dato["year"] - 1980;
        if ($dato["mon"] < 7) {
                $agxo--;
        } elseif ($dato["mon"] == 7) {
                if ($dato["mday"] < 15) {
                        $agxo--;
                }
        }
        if (isset($_GET['foto'])) {
?>
<div style="text-align: center"><a href="pri-argilo"><img src="/files/argilo_nova.jpg" alt="foto de Argilo" /><br />(reen)</a></div>
<?php
        } else {
?>
<div style="float: right; text-align: center; margin-top: 25px;"><a href="pri-argilo?foto"><img src="/files/argilo_nova_mg.jpg" alt="foto de Argilo" /><br />(pligrandigi)</a></div>
<ul>
<li>Aĝo: <?php echo $agxo ?></li>
<li>Vera nomo: Clayton Smith</li>
<li>Loĝloko: Otavo, Kanado</li>
<li>Ŝatokupoj: muziko, <a href="sxatokupoj#matematiko">matematiko</a>, <a href="sxatokupoj#jxonglado">ĵonglado</a>, unuciklado, kegloludado</li>
<li>Mezlernejo: Lambton-Kent Composite School</li>
<li>Universitato: <a href="https://uwaterloo.ca/">University of Waterloo</a></li>
<li>Edzino: Teodora Alexandrova</li>
</ul>

<h2>Por kontakti min</h2>
<ul>
<li>Retpoŝto: argilo ĉe gmail.com</li>
</ul>
<?php
        }
?>
