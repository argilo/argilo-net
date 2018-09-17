---
layout: post
title: Esperanta Dvoraka klavarfasono
created: 1178325602
---
<p>Kiam mi unuafoje isntalis Ubuntu en mian porteblan komputilon, mi kreis Esperantan Dvorakan klavarfasonon.  Ĝi estis tute sama kiel la Usona Dvoraka klavaro, krom ke per AltGr eblis aldoni supersignon.  Ekzemple, mi tajpis AltGr+C por skribi "ĉ", AltGr+G por "ĝ", ktp.<p>

<p>Antaŭ du semajnoj mi instalis la plej lastan version de Ubuntu.  Mi decidis rezervkopii miajn dosierojn, forviŝi mian durdiskon kaj instali ĝin de nulo.  Bedaŭrinde mi forgesis kopii la dosieron kiu enhavis mian klavarfasonon, do mi devis rekrei ĝin.  Nun mi afiŝas ĝin ĉi tie por ke mi ne perdu ĝin estonte.  Kaj eble ĝi povas esti utila al iu alia.  Do jen ĝi:</p>

<pre>default partial alphanumeric_keys
xkb_symbols "basic" {

  name[Group1]= "Esperanto";

    key &lt;TLDE&gt; { [       grave,	asciitilde	]	};

    key &lt;AE01&gt; { [	    1,	exclam 		]	};
    key &lt;AE02&gt; { [	    2,	at		]	};
    key &lt;AE03&gt; { [	    3,	numbersign	]	};
    key &lt;AE04&gt; { [	    4,	dollar		]	};
    key &lt;AE05&gt; { [	    5,	percent		]	};
    key &lt;AE06&gt; { [	    6,	asciicircum	]	};
    key &lt;AE07&gt; { [	    7,	ampersand	]	};
    key &lt;AE08&gt; { [	    8,	asterisk	]	};
    key &lt;AE09&gt; { [	    9,	parenleft	]	};
    key &lt;AE10&gt; { [	    0,	parenright	]	};
    key &lt;AE11&gt; { [ bracketleft,	braceleft	]	};
    key &lt;AE12&gt; { [ bracketright, braceright	]	};

    key &lt;AD01&gt; { [  apostrophe,	quotedbl	]	};
    key &lt;AD02&gt; { [	comma,	less		]	};
    key &lt;AD03&gt; { [      period,	greater		]	};
    key &lt;AD04&gt; { [	    p,	P		]	};
    key &lt;AD05&gt; { [	    y,	Y		]	};
    key &lt;AD06&gt; { [	    f,	F		]	};
    key &lt;AD07&gt; { [	    g,	G, gcircumflex, Gcircumflex	]	};
    key &lt;AD08&gt; { [	    c,	C, ccircumflex, Ccircumflex	]	};
    key &lt;AD09&gt; { [	    r,	R		]	};
    key &lt;AD10&gt; { [	    l,	L		]	};
    key &lt;AD11&gt; { [	slash,	question	]	};
    key &lt;AD12&gt; { [	equal,	plus		]	};

    key &lt;AC01&gt; { [	    a,	A 		]	};
    key &lt;AC02&gt; { [	    o,	O		]	};
    key &lt;AC03&gt; { [	    e,	E		]	};
    key &lt;AC04&gt; { [	    u,	U, ubreve, Ubreve	]	};
    key &lt;AC05&gt; { [	    i,	I		]	};
    key &lt;AC06&gt; { [	    d,	D		]	};
    key &lt;AC07&gt; { [	    h,	H, hcircumflex, Hcircumflex	]	};
    key &lt;AC08&gt; { [	    t,	T		]	};
    key &lt;AC09&gt; { [	    n,	N		]	};
    key &lt;AC10&gt; { [	    s,	S, scircumflex, Scircumflex	]	};
    key &lt;AC11&gt; { [	minus,	underscore	]	};

    key &lt;AB01&gt; { [   semicolon,	colon		]	};
    key &lt;AB02&gt; { [	    q,	Q		]	};
    key &lt;AB03&gt; { [	    j,	J, jcircumflex, Jcircumflex	]	};
    key &lt;AB04&gt; { [	    k,	K		]	};
    key &lt;AB05&gt; { [	    x,	X		]	};
    key &lt;AB06&gt; { [	    b,	B		]	};
    key &lt;AB07&gt; { [	    m,	M		]	};
    key &lt;AB08&gt; { [	    w,	W		]	};
    key &lt;AB09&gt; { [	    v,	V		]	};
    key &lt;AB10&gt; { [	    z,	Z		]	};

  include "level3(ralt_switch)"
};</pre>

<p>Tion mi metis en la dosieron <code>/usr/share/X11/xkb/symbols/epo</code>.</p>
