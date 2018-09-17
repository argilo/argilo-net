---
layout: page
title: Anagramoj
created: 1137266998
permalink: /anagramoj/
---
<?php
	function kodigu($nova, $strekoj)
	{
		if ($strekoj) {
			$nova = str_replace(" ", "|", $nova);
		} else {
			$nova = str_replace(" ", "", $nova);
		}
		$nova = str_replace("CX", "Q", $nova);
		$nova = str_replace("Cx", "Q", $nova);
		$nova = str_replace("cx", "q", $nova);
		$nova = str_replace("Ĉ", "Q", $nova);
		$nova = str_replace("ĉ", "q", $nova);
		$nova = str_replace("GX", "W", $nova);
		$nova = str_replace("Gx", "W", $nova);
		$nova = str_replace("gx", "w", $nova);
		$nova = str_replace("Ĝ", "W", $nova);
		$nova = str_replace("ĝ", "w", $nova);
		$nova = str_replace("HX", "[", $nova);
		$nova = str_replace("Hx", "[", $nova);
		$nova = str_replace("hx", "[", $nova);
		$nova = str_replace("Ĥ", "[", $nova);
		$nova = str_replace("ĥ", "[", $nova);
		$nova = str_replace("JX", "\\", $nova);
		$nova = str_replace("Jx", "\\", $nova);
		$nova = str_replace("jx", "\\", $nova);
		$nova = str_replace("Ĵ", "\\", $nova);
		$nova = str_replace("ĵ", "\\", $nova);
		$nova = str_replace("UX", "Y", $nova);
		$nova = str_replace("Ux", "Y", $nova);
		$nova = str_replace("ux", "y", $nova);
		$nova = str_replace("Ŭ", "Y", $nova);
		$nova = str_replace("ŭ", "y", $nova);
		$nova = str_replace("SX", "X", $nova);
		$nova = str_replace("Sx", "X", $nova);
		$nova = str_replace("sx", "x", $nova);
		$nova = str_replace("Ŝ", "X", $nova);
		$nova = str_replace("ŝ", "x", $nova);
		return $nova;
	}
?>

Laŭ la [Reta Vortaro](http://purl.org/NET/voko/revo/), anagramo estas "ŝanĝaranĝo de la literoj de vorto, por fari alian vorton: nomo - mono, resano - ansero".

Per tiu ĉi paĝo vi povas trovi anagramojn.  La anagramojn trovas la programo "[Wordplay](http://hsvmovies.com/static_subpages/personal_orig/wordplay/index.html)" de Evans A Criswell.  Mi mem adaptis ĝin al Esperanto.  La modifita fontokodo de la programo troviĝas en [Github](https://github.com/argilo/anagramoj).

Entajpu du-tri vortojn **Unikode** aŭ **x-sisteme** por trovi anagramojn de ili.

<p><a href="anagramoj<?php echo isset($_GET["detale"]) ? "" : "?detale" ?>"><?php echo isset($_GET["detale"]) ? "Simpla" : "Detala" ?> serĉo.</a></p>
<form method="post" action="anagramoj<?php echo isset($_GET["detale"]) ? "?detale" : "" ?>"><p>
<?php
	if (isset($_GET["detale"])) {
?>
Serĉvortoj: <input type="text" name="vorto" value="<?php echo $_POST["vorto"] ?>" size="25" />
<br />Ĉiam inkluzivu tiun ĉi vorton: <input type="text" name="inkluzivu" value="<?php echo $_POST["inkluzivu"] ?>" size="15" />
<br />Ĉiam ekskluzivu tiun ĉi vorton: <input type="text" name="ekskluzivu" value="<?php echo $_POST["ekskluzivu"] ?>" size="15" />
<br />Maksimuma nombro da vortoj en ĉiu anagramo: <input type="text" name="maksvortoj" value="<?php echo $_POST["maksvortoj"] ?>" size="5" />
<br />Maksimuma nombro da literoj en ĉiu vorto: <input type="text" name="maksliteroj" value="<?php echo $_POST["maksliteroj"] ?>" size="5" />
<br />Minimuma nombro da literoj en ĉiu vorto: <input type="text" name="minliteroj" value="<?php echo $_POST["minliteroj"] ?>" size="5" />
<br /><input name="kandidatoj" type="radio" value="ne" <?php echo $_POST["kandidatoj"] != "jes" ? "checked=\"checked\"" : "" ?> />Listigu anagramojn
<input name="kandidatoj" type="radio" value="jes" <?php echo $_POST["kandidatoj"] == "jes" ? "checked=\"checked\"" : "" ?> />Listigu kandidatajn vortojn
<br /><br /><input type="submit" value="Trovu" />
<?php
	} else {
?>
<input type="text" name="vorto" value="<?php echo $_POST["vorto"] ?>" size="25" />
<input type="submit" value="Trovu" />
<?php
	}
?>
</p></form>
<?php
	if (isset($_POST["vorto"])) {
		$novavorto = kodigu($_POST["vorto"], 0);
		$novainkluzivu = kodigu($_POST["inkluzivu"], 0);

		if (strlen($novavorto) - strlen($novainkluzivu) <= 25) {

		echo "<p>Jen la listo de trovitaj " . ($_POST["kandidatoj"] == "jes" ? "kandidataj vortoj" : "anagramoj") . " por <b>" . $_POST["vorto"] . "</b> (maksimume 10000):</p>";
		echo "<p>";

		$parametroj = "";
		if ($_POST["maksvortoj"]) {
			$parametroj .= " -d" . ($_POST["maksvortoj"] + 1);
		}
        if ($_POST["maksliteroj"]) {
			$parametroj .= " -m" . $_POST["maksliteroj"];
		}
        if ($_POST["minliteroj"]) {
			$parametroj .= " -n" . $_POST["minliteroj"];
		}
		if ($_POST["kandidatoj"] == "jes") {
			$parametroj .= " -l -x";
		}
        if (isset($_POST["inkluzivu"])) {
			$parametroj .= " -w \"$novainkluzivu\"";
		}
		if ($_POST["ekskluzivu"]) {
			$novaekskluzivu = "| grep -i -w -v -E \"(" . kodigu($_POST["ekskluzivu"],1) . ")\"";
		}

		$rezulto = shell_exec("/home/ec2-user/anagramoj/wordplay \"$novavorto\" -s $parametroj -f /home/ec2-user/anagramoj/vortoj.txt $novaekskluzivu $novaekskluzivu");

		$rezulto = strtolower($rezulto);
		$rezulto = str_replace("\n", "<br />", $rezulto);
        $rezulto = str_replace("q", "\xC4\x89", $rezulto);
        $rezulto = str_replace("w", "\xC4\x9D", $rezulto);
        $rezulto = str_replace("[", "\xC4\xA5", $rezulto);
        $rezulto = str_replace("\\", "\xC4\xB5", $rezulto);
        $rezulto = str_replace("y", "\xC5\xAD", $rezulto);
        $rezulto = str_replace("x", "\xC5\x9D", $rezulto);

		echo $rezulto;

		echo "</p>";

		} else {
			echo "<p>Pardonon!  Viaj serĉvortoj estas tro longaj.  Bonvolu mallongigi ilin, kaj reprovu.</p>";
		}
	}
?>
