---
layout: post
title: Esperanta Dvoraka klavarfasono
created: 1178325602
---
Kiam mi unuafoje isntalis Ubuntu en mian porteblan komputilon, mi kreis Esperantan Dvorakan klavarfasonon.  Ĝi estis tute sama kiel la Usona Dvoraka klavaro, krom ke per AltGr eblis aldoni supersignon.  Ekzemple, mi tajpis AltGr+C por skribi "ĉ", AltGr+G por "ĝ", ktp.

Antaŭ du semajnoj mi instalis la plej lastan version de Ubuntu.  Mi decidis rezervkopii miajn dosierojn, forviŝi mian durdiskon kaj instali ĝin de nulo.  Bedaŭrinde mi forgesis kopii la dosieron kiu enhavis mian klavarfasonon, do mi devis rekrei ĝin.  Nun mi afiŝas ĝin ĉi tie por ke mi ne perdu ĝin estonte.  Kaj eble ĝi povas esti utila al iu alia.  Do jen ĝi:

```
default partial alphanumeric_keys
xkb_symbols "basic" {

  name[Group1]= "Esperanto";

    key <TLDE> { [       grave,	asciitilde	]	};

    key <AE01> { [	    1,	exclam 		]	};
    key <AE02> { [	    2,	at		]	};
    key <AE03> { [	    3,	numbersign	]	};
    key <AE04> { [	    4,	dollar		]	};
    key <AE05> { [	    5,	percent		]	};
    key <AE06> { [	    6,	asciicircum	]	};
    key <AE07> { [	    7,	ampersand	]	};
    key <AE08> { [	    8,	asterisk	]	};
    key <AE09> { [	    9,	parenleft	]	};
    key <AE10> { [	    0,	parenright	]	};
    key <AE11> { [ bracketleft,	braceleft	]	};
    key <AE12> { [ bracketright, braceright	]	};

    key <AD01> { [  apostrophe,	quotedbl	]	};
    key <AD02> { [	comma,	less		]	};
    key <AD03> { [      period,	greater		]	};
    key <AD04> { [	    p,	P		]	};
    key <AD05> { [	    y,	Y		]	};
    key <AD06> { [	    f,	F		]	};
    key <AD07> { [	    g,	G, gcircumflex, Gcircumflex	]	};
    key <AD08> { [	    c,	C, ccircumflex, Ccircumflex	]	};
    key <AD09> { [	    r,	R		]	};
    key <AD10> { [	    l,	L		]	};
    key <AD11> { [	slash,	question	]	};
    key <AD12> { [	equal,	plus		]	};

    key <AC01> { [	    a,	A 		]	};
    key <AC02> { [	    o,	O		]	};
    key <AC03> { [	    e,	E		]	};
    key <AC04> { [	    u,	U, ubreve, Ubreve	]	};
    key <AC05> { [	    i,	I		]	};
    key <AC06> { [	    d,	D		]	};
    key <AC07> { [	    h,	H, hcircumflex, Hcircumflex	]	};
    key <AC08> { [	    t,	T		]	};
    key <AC09> { [	    n,	N		]	};
    key <AC10> { [	    s,	S, scircumflex, Scircumflex	]	};
    key <AC11> { [	minus,	underscore	]	};

    key <AB01> { [   semicolon,	colon		]	};
    key <AB02> { [	    q,	Q		]	};
    key <AB03> { [	    j,	J, jcircumflex, Jcircumflex	]	};
    key <AB04> { [	    k,	K		]	};
    key <AB05> { [	    x,	X		]	};
    key <AB06> { [	    b,	B		]	};
    key <AB07> { [	    m,	M		]	};
    key <AB08> { [	    w,	W		]	};
    key <AB09> { [	    v,	V		]	};
    key <AB10> { [	    z,	Z		]	};

  include "level3(ralt_switch)"
};
```

Tion mi metis en la dosieron `/usr/share/X11/xkb/symbols/epo`.
