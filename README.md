<!--

author:   André Dietrich
email:    LiaScript@web.de
version:  0.0.1
language: en
narrator: US English Male

logo:     https://liascript.github.io/img/bg-showcase-1.jpg

import:   https://raw.githubusercontent.com/liaTemplates/AVR8js/main/README.md

import:   https://github.com/LiaTemplates/Pyodide/blob/0.1.4/README.md


-->



# LiaScript at the OEB 2021


> **Shiny New e-Learning Platforms: Great for Business, a Dead-end for Online Education?**
>
> Do centralised platforms really support the distribution of knowledge and
> might fancy but restrictive educator interfaces actually be a threat to
> creativity? As an alternative we developed LiaScript, an extendable language
> for creating interactive online courses. Content can be created, edited,
> stored everywhere and shared freely. It even works offline, no back-end
> required. You will learn how to create quizzes with brackets, how to
> articulate and create animations with braces, and much more.
>
> ~~Learning outcomes:~~
>
> - What are the problems of centralized platforms
> - How can online education work on a decentralized web and infrastructure...
> - How to use LiaScript to create open educational resources (OER)


## LiaScript, it's not a Platform

### Single-Source of Truth

### Storage & Distribution

### Classrooms?




## Demos




### Quizzes


What's the name of the Markdown-dialect that
was developed to create educational content?

    [[LiaScript]]

---

Just add as many points as you wish:

    [[X]] Only the **X** marks the correct point.
    [[ ]] Empty ones are wrong.
    [[X]] ...

---

A single-choice with a solution

    [( )] ...
    [(X)] <-- Only the **X** is allowed.
    [( )] ...
*************************************************

__That was the correct answer, you can now play Prince of Persion!__

??[Prince of Persia 4D](https://archive.org/details/msdos_4D_Prince_of_Persia_1994)

*************************************************




### Programming




#### Arduino

<div id="example">
<wokwi-led color="red"   pin="13" label="13"></wokwi-led>
<wokwi-led color="green" pin="12" label="12"></wokwi-led>
<wokwi-led color="blue"  pin="11" label="11"></wokwi-led>
<wokwi-led color="blue"  pin="10" label="10"></wokwi-led>
<span id="simulation-time"></span>
</div>

``` cpp
byte leds[] = {13, 12, 11, 10};
void setup() {
  Serial.begin(115200);
  for (byte i = 0; i < sizeof(leds); i++) {
    pinMode(leds[i], OUTPUT);
  }
}

int i = 0;
void loop() {
  Serial.print("LED: ");
  Serial.println(i);
  digitalWrite(leds[i], HIGH);
  delay(250);
  digitalWrite(leds[i], LOW);
  i = (i + 1) % sizeof(leds);
}
```
@AVR8js.sketch(example)




#### Python

``` python
import numpy as np
import matplotlib.pyplot as plt

t = np.arange(0.0, 2.0, 0.01)
s = np.sin(2 * np.pi * t)

fig, ax = plt.subplots()
ax.plot(t, s)

ax.grid(True, linestyle='-.')
ax.tick_params(labelcolor='r', labelsize='medium', width=3)

plt.show()

plot(fig) # <- this is required to plot the fig also on the LiaScript canvas
```
@Pyodide.eval


### Classrooms



#### Single-Choice

How do you like LiaScript?

    [(1)] its ok ...
    [(2)] I will use it
    [(3)] Probably something to think about
    [(4)] No way, this will replace platforms



#### Text-clouds?

Add some random words ...

    [[___]]



#### More complex surveys

    [[1][2][3][4][5][6][7]]
    [                     ] option 1
    [                     ] option 2
    [                     ] option 3
    [                     ] option 4



### Language & Animations

    --{{0}}--
Everything that is related to animations, is associated to braces. Double braces
at the beginning of a block indicate the point in time when something should
appear or disappear. Braces surrounded by dashes can be interpreted as the
explanation for a specific point. That's it, if you change the representation of
the course, these elements will be treated differently.

    --{{1}}--
See this important table.

     {{1-2}}
| I   | appear    | at  | first |
| --- | --------- | --- | ----- |
| and | disappear | at  | two   |


      {{2}}
* I will remain till the end
* and do have some {3}{__inline animations__}
* inline effects can also {3-4}{disappear} ...

    --{{2}}--
The bullet point list is also quite important, it contains some sub effects

    --{{3 Russian Female}}--
Первоначально создан в 2004 году Джоном Грубером (англ. John Gruber) и Аароном
Шварцем. Многие идеи языка были позаимствованы из существующих соглашений по
разметке текста в электронных письмах...

    --{{4}}--
If you try out the experimental Google translation, you will find out that
everything gets translated and also the voice will change, except for the
Russian text, this will remain.



### Data & Tables

     {{0-1}}
<!--
data-title="Government expenditure on education"
data-xlabel="year"
data-ylabel="% of GDP"
-->
| Year | Finland |     USA | Germany |   China |
| ---- | -------:| -------:| -------:| -------:|
| 1995 | 6.80942 |         | 4.42079 | 1.84192 |
| 1996 | 6.86052 |         | 4.48319 | 1.85338 |
| 1997 |         |         |         |         |
| 1998 |         |         | 4.45345 | 1.84432 |
| 1999 | 5.86960 |         |         | 1.88803 |
| 2000 | 5.71687 |         |         |         |
| 2001 | 5.84797 |         |         |         |
| 2002 | 6.02477 |         |         |         |
| 2003 | 6.17476 |         |         |         |
| 2004 | 6.16849 |         |         |         |
| 2005 | 6.03605 |         |         |         |
| 2006 | 5.93809 |         | 4.27930 |         |
| 2007 | 5.68608 |         | 4.34302 |         |
| 2008 | 5.84676 |         | 4.40954 |         |
| 2009 | 6.48517 |         | 4.88047 |         |
| 2010 | 6.54070 | 5.42001 | 4.91368 |         |
| 2011 | 6.48200 | 5.22389 | 4.80779 |         |
| 2012 | 7.19254 | 5.19485 | 4.93331 |         |
| 2013 | 7.15848 | 4.94378 | 4.93496 |         |
| 2014 | 7.15155 | 4.98948 | 4.93112 |         |


     {{1-2}}
| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |              2 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |
| Sheep           |           90 |             12 |      95 |
| Human           |           68 |             70 |      10 |


      {{2}}
| Music-Style {2-3}{1994} {3}{2014} |           Classic |           Country | Reggae |             Hip-Hop |           Hard-Rock |               Samba |
|:--------------------------------- | -----------------:| -----------------:| ------:| -------------------:| -------------------:| -------------------:|
| Student rating                    | {2-3}{50} {3}{20} | {2-3}{50} {3}{30} |    100 | {2-3}{200} {3}{220} | {2-3}{350} {3}{150} | {2-3}{250} {3}{230} |


### Multimedia

__Image !__

__Audio ?__

__Video !?__

__Anything else ??__


??[SketchFab human eye model](https://sketchfab.com/3d-models/the-human-eye-extrinsic-muscle-contraction-20-dc9c88630b6c42a8b242fd6024d0697f)

### Misc


                                    Title
    1.9 | DOTS
        |                  *
      y |               *     *
      - | r r r r r r r*r r r r*r r r r r r r
      a |             *         *
      x |            *           *
      i | B B B B B * B B B B B B * B B B B B
      s |         *                 *
        | *  * *                       * *  *
     -1 +------------------------------------
        0.1              x-axis             1


---



````````` A typical workflow for generation courses with LiaScript
Generation                     Publication          Usage

                                                           .-----------.           Modes:
    | LiaScript Plugin A                            ╔══════| Browser   |══════╗
    |  | Plugin B                           native  ║      '-----------'      ║"- Textbook        "
    v  v                                  +-------> ║ Digital Systems         ║"- Presentation    "
+---------------------+                   |         ║ (Sprint 2021)           ║"- Slides          "
| # Digital Systems   |\          .-,(  ),-.        ╚═════════════════════════╝
| (Sprint 2021)       +-+      .-(          )-.            .-----------.
|                       | --> (     Cloud      )    ╔══════| LMS       |══════╗
|"##"Introduction       |      '-(         ).-'     ║      '-----------'      ║
| + ...                 |         '-.( ).-' SCORM   ║ Digital Systems         ║
+-----------------------+                 +-------> ║ (Sprint 2021)           ║
                                          |         ╚═════════════════════════╝
                                          |                .-----------.
                                          |         ╔══════| pdfViewer |══════╗
                                          | export  ║      '-----------'      ║
                                          +-------> ║ Digital Systems         ║
                                                    ║ (Sprint 2021)           ║
                                                    ╚═════════════════════════╝

"- Atom Editor with LiaScript Extention           "|"- [Github](https://github.io)         "
"- [CodiLia](https://github.com/liascript/codilia)"|"- [Dropbox](https://www.dropbox.com)  "
"  Online Editor @TUBAF                           "|"- [IPFS](https://ipfs.io), ...        "
                                                   |
                                                   |
`````````


## Appendix

### Resources

* __Project-Website:__ https://LiaScript.github.io
* __Open-Source:__ https://github.com/liascript
* __YouTube:__ https://www.youtube.com/channel/UCyiTe2GkW_u05HSdvUblGYg
* __Additional resources:__

  - Documentation: https://github.com/LiaScript/docs
  - Free books: https://github.com/LiaBooks
  - Templates: https://github.com/LiaTemplates
  - Talks & ...: https://github.com/LiaPlayground
  - Blog: https://aizac.herokuapp.com

* __Editor:__ https://atom.io

  - Liascript-Preview: https://atom.io/packages/liascript-preview
  - Liascript-Snippets: https://atom.io/packages/liascript-snippets

* __Development-Server:__ https://www.npmjs.com/package/@liascript/devserver


### Contact

> ![Pic: André Dietrich](https://oeb.global/sites/default/files/images/speakers/imported/2021-08-1311%25253A32%25253A48477724-me.jpg)
> __André Dietrich__ is originally a robotics and embedded software developer,
> now working as a researcher at the TU Bergakademie Freiberg. Due to struggles
> with common Learning-Management-Systems and authoring-systems, he started the
> development on LiaScript, a language-based approach for creating interactive
> and open online-courses. His current research interests are language design,
> new web technologies and online education with focus on open educational
> resources.
>
> **Contact: [Andre.Dietrich@informatik.tu-freiberg.de](mailto:Andre.Dietrich@informatik.tu-freiberg.de)**
