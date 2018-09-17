---
layout: post
title: Esperanta klavaro por mia poŝtelefono (Google Nexus One)
created: 1279064940
---
Antaŭnelonge mi aĉetis novan poŝtelefonon, nome Google Nexus One.  Ĝis nun mankis la Esperantaj literoj en ĝia klavaro, sed mi sukcesis aldoni ilin.  Anstataŭ aldoni ilin al la operaciumo mem (kio estus sufiĉe malfacile), mi aldonis ilin al <a href="http://code.google.com/p/bulkey/">Bulkey</a>.  Bulkey estas bulgara klavaro por Android (la operaciumo de la poŝtelefono), kaj bonŝance ĝi estas malferma, kaj do tre facile modifebla.  Mi do senprobleme aldonis la Esperantajn literojn al la latina klavaro en Bulkey (unu el kelkaj elekteblaj).  Jen sekvas la ŝanĝoj, kiujn mi faris, por ke mi povu estonte refari ilin laŭbezone:

```
diff -r f8638a4e9fa5 res/values/strings.xml
--- a/res/values/strings.xml	Tue May 11 17:22:16 2010 +0300
+++ b/res/values/strings.xml	Tue Jul 13 23:26:59 2010 -0400
@@ -58,6 +58,12 @@
     <string name="inputMethod">Input Method</string>
     <string name="prefs_kbd_type">which_bg_keyboard</string>
     <string name="alternates_for_short_i">ѝ</string>
+    <string name="alternates_for_c">ĉ</string>
+    <string name="alternates_for_g">ĝ</string>
+    <string name="alternates_for_h">ĥ</string>
+    <string name="alternates_for_j">ĵ</string>
+    <string name="alternates_for_s">ŝ</string>
+    <string name="alternates_for_u">ŭ</string>
     <string name="prefs_sound_on">sound_on</string>
     <string name="prefs_auto_switch">Switch to latin input</string>
     <string name="prefs_auto_switch_summary">Auto switch to latin input on URL and Email fields</string>
diff -r f8638a4e9fa5 res/xml/qwerty.xml
--- a/res/xml/qwerty.xml	Tue May 11 17:22:16 2010 +0300
+++ b/res/xml/qwerty.xml	Tue Jul 13 23:26:59 2010 -0400
@@ -34,7 +34,7 @@
         <Key android:codes="114" android:keyLabel="r"/>
         <Key android:codes="116" android:keyLabel="t"/>
         <Key android:codes="121" android:keyLabel="y"/>
-        <Key android:codes="117" android:keyLabel="u"/>
+        <Key android:codes="117" android:keyLabel="u" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_u"/>
         <Key android:codes="105" android:keyLabel="i"/>
         <Key android:codes="111" android:keyLabel="o"/>
         <Key android:codes="112" android:keyLabel="p" android:keyEdgeFlags="right"/>
@@ -43,12 +43,12 @@
     <Row>
         <Key android:codes="97" android:keyLabel="a" android:horizontalGap="5%p"
                 android:keyEdgeFlags="left"/>
-        <Key android:codes="115" android:keyLabel="s"/>
+        <Key android:codes="115" android:keyLabel="s" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_s"/>
         <Key android:codes="100" android:keyLabel="d"/>
         <Key android:codes="102" android:keyLabel="f"/>
-        <Key android:codes="103" android:keyLabel="g"/>
-        <Key android:codes="104" android:keyLabel="h"/>
-        <Key android:codes="106" android:keyLabel="j"/>
+        <Key android:codes="103" android:keyLabel="g" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_g"/>
+        <Key android:codes="104" android:keyLabel="h" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_h"/>
+        <Key android:codes="106" android:keyLabel="j" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_j"/>
         <Key android:codes="107" android:keyLabel="k"/>
         <Key android:codes="108" android:keyLabel="l" android:keyEdgeFlags="right"/>
     </Row>
@@ -60,7 +60,7 @@
                 android:isSticky="true" android:keyEdgeFlags="left"/>
         <Key android:codes="122" android:keyLabel="z"/>
         <Key android:codes="120" android:keyLabel="x"/>
-        <Key android:codes="99" android:keyLabel="c"/>
+        <Key android:codes="99" android:keyLabel="c" android:popupKeyboard="@xml/kbd_popup_template" android:popupCharacters="@string/alternates_for_c"/>
         <Key android:codes="118" android:keyLabel="v"/>
         <Key android:codes="98" android:keyLabel="b"/>
         <Key android:codes="110" android:keyLabel="n"></Key>
```
