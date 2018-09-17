---
layout: post
title: Esperanta klavaro por mia poŝtelefono (Google Nexus One)
created: 1279064940
---
Antaŭnelonge mi aĉetis novan poŝtelefonon, nome Google Nexus One.  Ĝis nun mankis la Esperantaj literoj en ĝia klavaro, sed mi sukcesis aldoni ilin.  Anstataŭ aldoni ilin al la operaciumo mem (kio estus sufiĉe malfacile), mi aldonis ilin al <a href="http://code.google.com/p/bulkey/">Bulkey</a>.  Bulkey estas bulgara klavaro por Android (la operaciumo de la poŝtelefono), kaj bonŝance ĝi estas malferma, kaj do tre facile modifebla.  Mi do senprobleme aldonis la Esperantajn literojn al la latina klavaro en Bulkey (unu el kelkaj elekteblaj).  Jen sekvas la ŝanĝoj, kiujn mi faris, por ke mi povu estonte refari ilin laŭbezone:

<pre>diff -r f8638a4e9fa5 res/values/strings.xml
--- a/res/values/strings.xml	Tue May 11 17:22:16 2010 +0300
+++ b/res/values/strings.xml	Tue Jul 13 23:26:59 2010 -0400
@@ -58,6 +58,12 @@
     &lt;string name="inputMethod"&gt;Input Method&lt;/string&gt;
     &lt;string name="prefs_kbd_type"&gt;which_bg_keyboard&lt;/string&gt;
     &lt;string name="alternates_for_short_i"&gt;ѝ&lt;/string&gt;
+    &lt;string name="alternates_for_c"&gt;ĉ&lt;/string&gt;
+    &lt;string name="alternates_for_g"&gt;ĝ&lt;/string&gt;
+    &lt;string name="alternates_for_h"&gt;ĥ&lt;/string&gt;
+    &lt;string name="alternates_for_j"&gt;ĵ&lt;/string&gt;
+    &lt;string name="alternates_for_s"&gt;ŝ&lt;/string&gt;
+    &lt;string name="alternates_for_u"&gt;ŭ&lt;/string&gt;
     &lt;string name="prefs_sound_on"&gt;sound_on&lt;/string&gt;
     &lt;string name="prefs_auto_switch"&gt;Switch to latin input&lt;/string&gt;
     &lt;string name="prefs_auto_switch_summary"&gt;Auto switch to latin input on URL and Email fields&lt;/string&gt;
diff -r f8638a4e9fa5 res/xml/qwerty.xml
--- a/res/xml/qwerty.xml	Tue May 11 17:22:16 2010 +0300
+++ b/res/xml/qwerty.xml	Tue Jul 13 23:26:59 2010 -0400
@@ -34,7 +34,7 @@
         &lt;Key android:codes="114" android:keyLabel="r"/&gt;
         &lt;Key android:codes="116" android:keyLabel="t"/&gt;
         &lt;Key android:codes="121" android:keyLabel="y"/&gt;
-        &lt;Key android:codes="117" android:keyLabel="u"/&gt;
+        &lt;Key android:codes="117" android:keyLabel="u" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_u"/&gt;
         &lt;Key android:codes="105" android:keyLabel="i"/&gt;
         &lt;Key android:codes="111" android:keyLabel="o"/&gt;
         &lt;Key android:codes="112" android:keyLabel="p" android:keyEdgeFlags="right"/&gt;
@@ -43,12 +43,12 @@
     &lt;Row&gt;
         &lt;Key android:codes="97" android:keyLabel="a" android:horizontalGap="5%p"
                 android:keyEdgeFlags="left"/&gt;
-        &lt;Key android:codes="115" android:keyLabel="s"/&gt;
+        &lt;Key android:codes="115" android:keyLabel="s" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_s"/&gt;
         &lt;Key android:codes="100" android:keyLabel="d"/&gt;
         &lt;Key android:codes="102" android:keyLabel="f"/&gt;
-        &lt;Key android:codes="103" android:keyLabel="g"/&gt;
-        &lt;Key android:codes="104" android:keyLabel="h"/&gt;
-        &lt;Key android:codes="106" android:keyLabel="j"/&gt;
+        &lt;Key android:codes="103" android:keyLabel="g" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_g"/&gt;
+        &lt;Key android:codes="104" android:keyLabel="h" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_h"/&gt;
+        &lt;Key android:codes="106" android:keyLabel="j" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_j"/&gt;
         &lt;Key android:codes="107" android:keyLabel="k"/&gt;
         &lt;Key android:codes="108" android:keyLabel="l" android:keyEdgeFlags="right"/&gt;
     &lt;/Row&gt;
@@ -60,7 +60,7 @@
                 android:isSticky="true" android:keyEdgeFlags="left"/&gt;
         &lt;Key android:codes="122" android:keyLabel="z"/&gt;
         &lt;Key android:codes="120" android:keyLabel="x"/&gt;
-        &lt;Key android:codes="99" android:keyLabel="c"/&gt;
+        &lt;Key android:codes="99" android:keyLabel="c" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_c"/&gt;
         &lt;Key android:codes="118" android:keyLabel="v"/&gt;
         &lt;Key android:codes="98" android:keyLabel="b"/&gt;
         &lt;Key android:codes="110" android:keyLabel="n"&gt;&lt;/Key&gt;</pre>
