# L-system
---
An implementation of [Lindenmayer system](https://en.wikipedia.org/wiki/L-system) with the [Anubis language](https://fr.wikipedia.org/wiki/Anubis_(langage)) which generate iteratively images of L-system by interpreting constants as [Logo-like](https://en.wikipedia.org/wiki/Logo_(programming_language)) commands.

>An L-system consists of an alphabet of symbols that can be used to make strings, a collection of production rules that expand each symbol into some larger string of symbols, an initial "axiom" string from which to begin construction, and a mechanism for translating the generated strings into geometric structures. L-systems were introduced and developed in 1968 by Aristid Lindenmayer, a Hungarian theoretical biologist and botanist at the University of Utrecht. Lindenmayer used L-systems to describe the behaviour of plant cells and to model the growth processes of plant development. L-systems have also been used to model the morphology of a variety of organisms[1] and can be used to generate self-similar fractals such as iterated function systems.

Arguments example with default value:
 - Number of iterations: `-i:3`
 - Move step (pixels unit): `-s:10`
 - Angle in degree: `-a:70`
 - Draw start X: `-start_x:0`
 - Draw start Y: `-start_y:0`
 - Draw start angle in degree: `-start_angle:0`
 - Draw opacity: `-opacity:255`
 - Axiom: `-axiom:"F"`
 - Rules: `-rule:""`
 - Draw color: `-r:0` `-g:255` `-b:0`

Some common rules:

`anbexec lsystem -s:4 -a:25 -start_x:200 -start_y:600 -start_angle:-75 -i:5 -opacity:192 -axiom:"X" -rule:"X=F-[[X]+X]+F[+FX]-X" -rule:"F=FF"`
![L-system plant](http://garzul.tonsite.biz/gif/plant.gif)

`anbexec lsystem -s:8 -a:90 -start_x:400 -start_y:300 -start_angle:270 -opacity:192 -i:10 -axiom:FX -rule:"X=X+YF+" -rule:"Y=-FX-Y"`
![Dragon Curve](http://garzul.tonsite.biz/gif/dragon_curve.gif)

`anbexec lsystem -s:8 -a:120 -start_x:400 -start_y:300 -start_angle:120 -i:5 -axiom:"F-G-G" -rule:"F=F-G+F+G-F" -rule:"G=GG"`
![Sierpinski](http://garzul.tonsite.biz/gif/sierpinski.gif)

`anbexec lsystem -s:8 -a:60 -start_x:400 -start_y:300 -start_angle:60 -i:5 -axiom:"F" -rule:"F=+G-F-G+" -rule:"G=-F+G+F-"`
![Sierpinski Arrowhead](http://garzul.tonsite.biz/gif/sierpinski_arrowhead.gif)

Note: This program show some problems relative to the Float implementation and drawing with opacity within the Anubis VM as demonstrated by the rendered animations above.
