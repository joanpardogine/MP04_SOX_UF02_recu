# Recuperacions Mòdul Professional 4: Sistemes Operatius en Xarxa (SOX)

## UF02 Sistemes operatius lliures en xarxa

Per poder recuperar qualsevol de les activitats que t'han quedat pendents durant el
curs d'enguany, cal que entreguis i aprovis la següent activitat.

Si seguiu l'activiat que es va realitzar a classe
[personalitzar-el-missatge-de-benvinguda-a-linux](http://joanpardo.home.blog/smx2/com-personalitzar-el-missatge-de-benvinguda-a-linux/)

Veureu que el contingut del fitxer&nbsp; ***```00-header```*** , que per defecte és el següent:

```bash
#!/bin/sh
#
#    00-header - create the header of the MOTD
#    Copyright (C) 2009-2010 Canonical Ltd.
#
#    Authors: Dustin Kirkland &lt;kirkland@canonical.com>
#
#    This program is free software; you can redistribute it and/or modify
#    it under the terms of the GNU General Public License as published by
#    the Free Software Foundation; either version 2 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
#    GNU General Public License for more details.
#
#    You should have received a copy of the GNU General Public License along
#    with this program; if not, write to the Free Software Foundation, Inc.,
#  51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.

[ -r /etc/lsb-release ] &amp;&amp; . /etc/lsb-release

if [ -z "$DISTRIB_DESCRIPTION" ] &amp;&amp;
[ -x /usr/bin/lsb_release ]; then
        # Fall back to using the very slow
lsb_release utility
        DISTRIB_DESCRIPTION=$(lsb_release -s -d)
fi

printf "Welcome to %s (%s %s %s)n" "$DISTRIB_DESCRIPTION"
"$(uname -o)" "$(uname -r)" "$(uname -m)"
```

I la seva sortida és la que apareix un cop s'iniica una sessió en el servidor.

```bahs
Welcome to Ubuntu 16.04.5 LTS (GNU/Linux 4.4.0-131-generic ...

 * Documentation: https://help.ubuntu.com
 * Management: https://landscape.canonical.com
 * Support: https://ubuntu.com/advantage

186 packages can be updated.
129 updates are security updates.

New release '18.04.4 LTS' available.
Run 'do-release-upgrade' to upgrade to it.</pre>
```

Per tant, el que vull és modifiqueu el contingut del fitxer&nbsp; ***```00-header```*** perquè aparegui
el mateix text personalitzat però en català en lloc de que aparegui en anglès.

Per tant cal que modifiqueu el contingut del fitxer&nbsp; ***```00-header```*** substituint
el ***Welcome to*** per **Benvinguts a**

Recordeu que la ruta del fitxer ***```00-header```*** és ***```/etc/update-motd.d/00-header```***

Caldrà que em feu arribar el fitxer ***```00-header```*** modificat per correu, i un cop tingui lLa correcció,
us demanaré que fem una connexió remota per veure que us funciona en el vostre servidor.

