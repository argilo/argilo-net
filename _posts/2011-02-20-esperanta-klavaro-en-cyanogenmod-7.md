---
layout: post
title: Esperanta klavaro en CyanogenMod 7
created: 1298220300
---
Por mia poŝtelefono (Google Nexus One) ekzistas kelkaj modifitaj versioj de la operaciumo.  Mia preferata estas CyanogenMod, kies plej lastan version (CyanogenMod 7) mi instalis antaŭnelonge.  Mi ĵus aldonis la Esperantajn literojn al ĝia klavaro per la ĉi-sekva modifo al packages/inputmethods/LatinIME:

```
diff --git a/java/res/values-en/donottranslate-altchars.xml b/java/res/values-en/donottranslate-altchars.xml
index 083befa..4edbeb5 100644
--- a/java/res/values-en/donottranslate-altchars.xml
+++ b/java/res/values-en/donottranslate-altchars.xml
@@ -22,6 +22,6 @@
     <string name="alternates_for_e">3èéêëē</string>
     <string name="alternates_for_i">ìíîïī8</string>
     <string name="alternates_for_o">òóôõöōœø9</string>
-    <string name="alternates_for_u">ùúûüū7</string>
+    <string name="alternates_for_u">ùúûüūŭ7</string>
     <string name="alternates_for_y">ýÿ6</string>
 </resources>
diff --git a/java/res/values/donottranslate-altchars.xml b/java/res/values/donottranslate-altchars.xml
index 5038fd4..e30226a 100644
--- a/java/res/values/donottranslate-altchars.xml
+++ b/java/res/values/donottranslate-altchars.xml
@@ -20,13 +20,14 @@
 <resources xmlns:xliff="urn:oasis:names:tc:xliff:document:1.2">
     <string name="alternates_for_a">àáâãäåæ</string>
     <string name="alternates_for_e">èéêë</string>
-    <string name="alternates_for_h"></string>
+    <string name="alternates_for_h">ĥ</string>
     <string name="alternates_for_i">ìíîï</string>
+    <string name="alternates_for_j">ĵ</string>
     <string name="alternates_for_o">òóôõöœø</string>
-    <string name="alternates_for_u">ùúûü</string>
-    <string name="alternates_for_s">§ß</string>
+    <string name="alternates_for_u">ùúûüŭ</string>
+    <string name="alternates_for_s">§ŝß</string>
     <string name="alternates_for_n">ñ</string>
-    <string name="alternates_for_c">ç</string>
+    <string name="alternates_for_c">çĉ</string>
     <string name="alternates_for_y">ýÿ</string>
     <string name="alternates_for_q">1</string>
     <string name="alternates_for_w">2</string>
@@ -35,7 +36,7 @@
     <string name="alternates_for_t">5</string>
     <string name="alternates_for_z"></string>
     <string name="alternates_for_l"></string>
-    <string name="alternates_for_g"></string>
+    <string name="alternates_for_g">ĝ</string>
     <string name="alternates_for_p">0</string>
     <string name="alternates_for_v"></string>
     <string name="alternates_for_ae"></string>
diff --git a/java/res/xml/kbd_qwerty.xml b/java/res/xml/kbd_qwerty.xml
index a4ab0f8..f706e67 100644
--- a/java/res/xml/kbd_qwerty.xml
+++ b/java/res/xml/kbd_qwerty.xml
@@ -93,9 +93,13 @@
             android:popupKeyboard="@xml/kbd_popup_template"
             android:popupCharacters="@string/alternates_for_g" />
         <Key
-            android:keyLabel="h" />
+            android:keyLabel="h"
+            android:popupKeyboard="@xml/kbd_popup_template"
+            android:popupCharacters="@string/alternates_for_h" />
         <Key
-            android:keyLabel="j" />
+            android:keyLabel="j"
+            android:popupKeyboard="@xml/kbd_popup_template"
+            android:popupCharacters="@string/alternates_for_j" />
         <Key
             android:keyLabel="k" />
         <Key
diff --git a/java/res/xml/kbd_qwerty_black.xml b/java/res/xml/kbd_qwerty_black.xml
index 787e4ef..687c1d0 100644
--- a/java/res/xml/kbd_qwerty_black.xml
+++ b/java/res/xml/kbd_qwerty_black.xml
@@ -93,9 +93,13 @@
             android:popupKeyboard="@xml/kbd_popup_template"
             android:popupCharacters="@string/alternates_for_g" />
         <Key
-            android:keyLabel="h" />
+            android:keyLabel="h"
+            android:popupKeyboard="@xml/kbd_popup_template"
+            android:popupCharacters="@string/alternates_for_h" />
         <Key
-            android:keyLabel="j" />
+            android:keyLabel="j"
+            android:popupKeyboard="@xml/kbd_popup_template"
+            android:popupCharacters="@string/alternates_for_j" />
         <Key
             android:keyLabel="k" />
         <Key
```

Se vi volas mem apliki la ĉi-supran flikaĵon, necesas fari tion dum vi sekvas la [instrukcion](http://wiki.cyanogenmod.com/index.php?title=Compile_CyanogenMod_for_Passion) pri tradukado de CyanogenMod 7.
