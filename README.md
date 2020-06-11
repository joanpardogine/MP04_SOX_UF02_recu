# Recuperacions Mòdul Professional 4: Sistemes Operatius en Xarxa (SOX)

## UF02 Sistemes operatius lliures en xarxa

Per poder recuperar qualsevol de les activitats que t'han quedat pendents durant el
curs d'enguany, cal que entreguis i aprovis la següent activitat.

### Situació
Per posasr-vos en situació, cal recordar l'activiat que es va realitzar a classe
[personalitzar-el-missatge-de-benvinguda-a-linux](http://joanpardo.home.blog/smx2/com-personalitzar-el-missatge-de-benvinguda-a-linux/)
> Per obrir a una finestra nova, clica sobre l'enllaç amb el botó dret del ratolí i pitja "**obrir a una nova finestra**"

Recordeu que la feiem sobre un servidor amb Ubuntu Server 16.04 LTS instal·lat.
Doncs un cop ja tenim el servidor, podeu fer servir qualsevol que tingueu, sempre i quan tingui Ubuntu Server 16.04 LTS instal·lat.
I pel que fa als discos durs i les particions, no cal que tinguin cap configuració especial.

[Installing Ubuntu Server 16.04 LTS](https://joanpardo.home.blog/inst-ubuntu-srv-16-04-lts/)
> Per obrir a una finestra nova, clica sobre l'enllaç amb el botó dret del ratolí i pitja "**obrir a una nova finestra**"

En una instl·lació estandars, per defecte, el fitxer ***```00-header```*** és el que fa que quan iniciem sessió a un servidor ens aparegui el següent.
> Recordeu que la ruta del fitxer ***```00-header```*** és ***```/etc/update-motd.d/00-header```***

```bahs
Welcome to Ubuntu 16.04.5 LTS (GNU/Linux 4.4.0-131-generic i686)

 * Documentation: https://help.ubuntu.com
 * Management: https://landscape.canonical.com
 * Support: https://ubuntu.com/advantage

186 packages can be updated.
129 updates are security updates.

New release '18.04.4 LTS' available.
Run 'do-release-upgrade' to upgrade to it.</pre>
```

Bé, de fet, el fitxer&nbsp; ***```00-header```*** només fa que surti la línia: 
```bash
Welcome to Ubuntu 16.04.5 LTS (GNU/Linux 4.4.0-131-generic i686)
```

El contingut del fitxer&nbsp; ***```00-header```*** , que per defecte és el següent:
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
## Objectiu 

Doncs bé, la pràctica consisteix en modificar el contingut del fitxer&nbsp; ***```00-header```*** perquè aparegui
el mateix text de benvinguda, però en català, en lloc de que aparegui en anglès.

Per tant cal que modifiqueu el contingut del fitxer&nbsp; ***```00-header```*** substituint
el ***Welcome to*** per **Benvinguts a**

Un cop hagueu modificat el fitxer, per veure si funciona o no, cal que reinicieu el servidor.
I el que haurà d'apareixer és:

```bahs
Benvinguts a Ubuntu 16.04.5 LTS (GNU/Linux 4.4.0-131-generic i686)

 * Documentation: https://help.ubuntu.com
 * Management: https://landscape.canonical.com
 * Support: https://ubuntu.com/advantage

186 packages can be updated.
129 updates are security updates.

New release '18.04.4 LTS' available.
Run 'do-release-upgrade' to upgrade to it.</pre>
```

Caldrà que em feu arribar el fitxer ***```00-header```*** modificat per correu, i un cop tingui lLa correcció,
us demanaré que fem una connexió remota per veure que us funciona en el vostre servidor.

