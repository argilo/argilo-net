---
layout: post
title: Esperanta klavaro en CyanogenMod 7
created: 1298220300
---
Por mia poŝtelefono (Google Nexus One) ekzistas kelkaj modifitaj versioj de la operaciumo.  Mia preferata estas CyanogenMod, kies plej lastan version (CyanogenMod 7) mi instalis antaŭnelonge.  Mi ĵus aldonis la Esperantajn literojn al ĝia klavaro per la ĉi-sekva modifo al packages/inputmethods/LatinIME:
<pre>diff --git a/java/res/values-en/donottranslate-altchars.xml b/java/res/values-en/donottranslate-altchars.xml
index 083befa..4edbeb5 100644
--- a/java/res/values-en/donottranslate-altchars.xml
+++ b/java/res/values-en/donottranslate-altchars.xml
@@ -22,6 +22,6 @@
     &lt;string name="alternates_for_e"&gt;3èéêëē&lt;/string&gt;
     &lt;string name="alternates_for_i"&gt;ìíîïī8&lt;/string&gt;
     &lt;string name="alternates_for_o"&gt;òóôõöōœø9&lt;/string&gt;
-    &lt;string name="alternates_for_u"&gt;ùúûüū7&lt;/string&gt;
+    &lt;string name="alternates_for_u"&gt;ùúûüūŭ7&lt;/string&gt;
     &lt;string name="alternates_for_y"&gt;ýÿ6&lt;/string&gt;
 &lt;/resources&gt;
diff --git a/java/res/values/donottranslate-altchars.xml b/java/res/values/donottranslate-altchars.xml
index 5038fd4..e30226a 100644
--- a/java/res/values/donottranslate-altchars.xml
+++ b/java/res/values/donottranslate-altchars.xml
@@ -20,13 +20,14 @@
 &lt;resources xmlns:xliff="urn:oasis:names:tc:xliff:document:1.2"&gt;
     &lt;string name="alternates_for_a"&gt;àáâãäåæ&lt;/string&gt;
     &lt;string name="alternates_for_e"&gt;èéêë&lt;/string&gt;
-    &lt;string name="alternates_for_h"&gt;&lt;/string&gt;
+    &lt;string name="alternates_for_h"&gt;ĥ&lt;/string&gt;
     &lt;string name="alternates_for_i"&gt;ìíîï&lt;/string&gt;
+    &lt;string name="alternates_for_j"&gt;ĵ&lt;/string&gt;
     &lt;string name="alternates_for_o"&gt;òóôõöœø&lt;/string&gt;
-    &lt;string name="alternates_for_u"&gt;ùúûü&lt;/string&gt;
-    &lt;string name="alternates_for_s"&gt;§ß&lt;/string&gt;
+    &lt;string name="alternates_for_u"&gt;ùúûüŭ&lt;/string&gt;
+    &lt;string name="alternates_for_s"&gt;§ŝß&lt;/string&gt;
     &lt;string name="alternates_for_n"&gt;ñ&lt;/string&gt;
-    &lt;string name="alternates_for_c"&gt;ç&lt;/string&gt;
+    &lt;string name="alternates_for_c"&gt;çĉ&lt;/string&gt;
     &lt;string name="alternates_for_y"&gt;ýÿ&lt;/string&gt;
     &lt;string name="alternates_for_q"&gt;1&lt;/string&gt;
     &lt;string name="alternates_for_w"&gt;2&lt;/string&gt;
@@ -35,7 +36,7 @@
     &lt;string name="alternates_for_t"&gt;5&lt;/string&gt;
     &lt;string name="alternates_for_z"&gt;&lt;/string&gt;
     &lt;string name="alternates_for_l"&gt;&lt;/string&gt;
-    &lt;string name="alternates_for_g"&gt;&lt;/string&gt;
+    &lt;string name="alternates_for_g"&gt;ĝ&lt;/string&gt;
     &lt;string name="alternates_for_p"&gt;0&lt;/string&gt;
     &lt;string name="alternates_for_v"&gt;&lt;/string&gt;
     &lt;string name="alternates_for_ae"&gt;&lt;/string&gt;
diff --git a/java/res/xml/kbd_qwerty.xml b/java/res/xml/kbd_qwerty.xml
index a4ab0f8..f706e67 100644
--- a/java/res/xml/kbd_qwerty.xml
+++ b/java/res/xml/kbd_qwerty.xml
@@ -93,9 +93,13 @@
             android:popupKeyboard="@xml/kbd_popup_template"
             android:popupCharacters="@string/alternates_for_g" /&gt;
         &lt;Key
-            android:keyLabel="h" /&gt;
+            android:keyLabel="h"
+            android:popupKeyboard="@xml/kbd_popup_template"
+            android:popupCharacters="@string/alternates_for_h" /&gt;
         &lt;Key
-            android:keyLabel="j" /&gt;
+            android:keyLabel="j"
+            android:popupKeyboard="@xml/kbd_popup_template"
+            android:popupCharacters="@string/alternates_for_j" /&gt;
         &lt;Key
             android:keyLabel="k" /&gt;
         &lt;Key
diff --git a/java/res/xml/kbd_qwerty_black.xml b/java/res/xml/kbd_qwerty_black.xml
index 787e4ef..687c1d0 100644
--- a/java/res/xml/kbd_qwerty_black.xml
+++ b/java/res/xml/kbd_qwerty_black.xml
@@ -93,9 +93,13 @@
             android:popupKeyboard="@xml/kbd_popup_template"
             android:popupCharacters="@string/alternates_for_g" /&gt;
         &lt;Key
-            android:keyLabel="h" /&gt;
+            android:keyLabel="h"
+            android:popupKeyboard="@xml/kbd_popup_template"
+            android:popupCharacters="@string/alternates_for_h" /&gt;
         &lt;Key
-            android:keyLabel="j" /&gt;
+            android:keyLabel="j"
+            android:popupKeyboard="@xml/kbd_popup_template"
+            android:popupCharacters="@string/alternates_for_j" /&gt;
         &lt;Key
             android:keyLabel="k" /&gt;
         &lt;Key</pre>
Se vi volas mem apliki la ĉi-supran flikaĵon, necesas fari tion dum vi sekvas la <a href="http://wiki.cyanogenmod.com/index.php?title=Compile_CyanogenMod_for_Passion">instrukcion</a> pri tradukado de CyanogenMod 7.
