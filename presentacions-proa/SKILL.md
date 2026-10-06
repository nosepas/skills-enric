---
name: "presentacions-proa"
description: "Crea presentacions de l'Escola Proa amb la seva identitat (colors, Poppins, logotip, separadors de subtema i notes). Pregunta si és per a PowerPoint o Google Slides."
---

# Presentacions de l'Escola Proa

Usa aquesta skill quan et demanin una presentació, un conjunt de diapositives o un material de classe per a PROA (Solsona). Escriu sempre en català, amb ortografia revisada, i amb llenguatge inclusiu.

## 0. Pregunta obligatòria abans de començar

Abans de construir res, pregunta (amb una pregunta de selecció si l'eina hi és, o en text): **«És per a PowerPoint o per a Google Slides?»** No cal preguntar-ho si l'usuari ja ho ha dit.

La resposta decideix com s'escriuen les fórmules matemàtiques (secció 7) i com es lliura el fitxer (secció 6). Si no hi ha ningú per respondre, tria PowerPoint (.pptx) i digues-ho al principi del lliurament.

## 1. Identitat visual (manual d'identitat corporativa de PROA)

Colors (usa'ls exactament):
- Fúcsia principal `#DC006B` (títols, formules, accents)
- Blau principal `#008CDC` (números, franges, icones)
- Secundaris: lila `#7B2182`, turquesa `#85C5CA`, groc `#E9CE2C`
- Fons de diapositiva: rosa molt clar `#FCEEF4` **amb un 60 % de transparència** (decisió de la mestra). Cercle decoratiu: groc clar `#F5E6A3`
- Text de cos: gairebé negre `#1D1D1B`. Blanc només sobre fúcsia, blau o lila
- Graduacions permeses dels colors principals: 100 %, 70 %, 40 % i 10 %

Panells de color (fórmules destacades, barres i etiquetes fúcsia, blau, lila, turquesa o groc): **farciment amb un 50 % de transparència i sense vora ni contorn** (decisió de la mestra). El text blanc queda més clar sobre un panell transparent: mira el renderitzat i, si no es llegeix bé, avisa l'usuari abans de canviar res. Les targetes blanques i els cercles dels números no es toquen.

Tipografia: **Poppins** a tot arreu (títols en negreta, text en regular). Si no està instal·lada al sistema, instal·la-la abans de renderitzar (`fc-list | grep -i poppins`). A Google Slides ja hi és.

Contrast: el blau `#008CDC` i el turquesa només per a text gran i en negreta, mai text petit. El text petit va en `#1D1D1B`. Mai text blanc sobre turquesa o groc.

Icones: cercle blau amb pictograma blanc (estil de l'imagotip). Números i avisos en cercles de color pla.

## 2. Regles dels títols (decisions de la mestra, tenen prioritat sobre el manual)

- Tots els títols comencen **amb majúscula** (frase normal, no tot en majúscules).
- Cada títol és **d'un sol color** (fúcsia). **Mai** canviïs el color d'una lletra concreta dins un títol: no s'usa el joc de lletres «a»/«o» blaves del manual.
- Títols que diuen la idea de la diapositiva (una frase curta), no només una etiqueta, llevat de portada, ruta, separadors i resum.
- Si un títol porta una fórmula, escriu-la com a text normal amb Unicode (P = ρ · g · h), mai com a equació ni LaTeX.

## 3. Estructura de la presentació

1. Portada.
2. Ruta de la sessió (targetes numerades amb els subtemes).
3. **A cada canvi de subtema, una pàgina separadora** amb el número del subtema, el títol del subtema i, sota, una línia curta (p. ex. la fórmula clau).
4. Diapositives de contingut, una idea per diapositiva, amb **poc text** (frases curtes, màxim 3 o 4 línies) i un element visual: esquema, targetes, taula, fórmula destacada.
5. Resum o xuleta final.

Les **explicacions llargues van a les notes del presentador** de cada diapositiva. Les notes han de dir què explicar, exemples, preguntes per comprovar la comprensió i errors típics. Mai hi posis exercicis resolts si l'usuari només vol teoria.

Varia les distribucions (targetes, dues columnes, esquema, taula, fórmula gran). No repeteixis tres diapositives seguides amb la mateixa forma. No posis línies decoratives sota els títols ni franges de color als marges.

## 4. Mides i marges (diapositiva 16:9 de 10 x 5,625 in)

- Marges de 0,5 in. Separació entre blocs de 0,3 in.
- Títol: 24 pt negreta, a (x 0,55; y 0,3; amplada 8,95; alçada 1,05), alineat a l'esquerra.
- Contingut a partir de y = 1,5. Text de cos entre 14 i 16 pt; res per sota de 12 pt (només peus de nota).
- Poppins és ample: calcula uns 0,55 em per caràcter i deixa marge als quadres.
- **Sense número de diapositiva** i sense la pestanya turquesa del número (decisió de la mestra): no hi posis `slideNumber` ni cap quadrat amb el número.
- Targetes blanques amb cantonades arrodonides i ombra suau sobre el fons rosa.

## 5. Capes de la diapositiva (layouts)

- **Portada:** fons rosa (60 % de transparència), decoració gran (cercle groc amb punter retallat) a l'esquerra, títol 36 pt fúcsia a l'esquerra, subtítol 16 pt, logotip a baix a la dreta (1,65 in d'ample).
- **Separador:** fons rosa (60 % de transparència), cercle decoratiu a baix a la dreta, cercle blau amb el número del subtema (0,75 in) a (0,7; 1,15), títol 36 pt fúcsia, subtítol 18 pt.
- **Contingut:** fons rosa (60 % de transparència) i títol. Sense número de diapositiva.
- **Tancament:** com el contingut, amb el logotip a baix a la dreta (1,6 in), sense tapar res.

Regla del logotip: no el deformis, no el recolorexis, no hi posis res a sobre ni a prop (deixa una zona lliure igual a l'alçada de la «p»). Sobre fons rosa o blanc, versió en color. Sobre fúcsia o blau, versió negativa (tot blanc).

## 6. Com construir-la

Per a fitxer `.pptx` (PowerPoint, i també base per a Google Slides): llegeix i segueix la skill `pptx` (pptxgenjs). Defineix el tema amb els colors de dalt i Poppins, i un `defineSlideMaster` per a portada, separador, contingut i tancament. Posa la decoració i el logotip als masters, mai copiats a cada diapositiva. Notes amb `slide.addNotes()`. Valida el fitxer, renderitza totes les diapositives a imatge i revisa desbordaments, contrast i alineacions abans de lliurar-lo.

Transparències amb pptxgenjs:
- Fons dels masters: `background: { color: 'FCEEF4', transparency: 60 }`.
- Panells de color: farciment `fill: { color, transparency: 50 }` i `line: { type: 'none' }`. Fes-ho amb una funció única (per exemple embolcallant `slide.addShape` per als `rect` i `roundRect` grans amb farciment de color) perquè tots els panells quedin iguals.

Per a Google Slides: si hi ha el connector de Drive i l'editor de Presentacions, crea el fitxer i edita'l allà. Si no, lliura el `.pptx` i explica que es pot pujar al Drive i obrir amb Presentacions de Google. A Google Slides **no s'usa mai LaTeX ni Auto-LaTeX Equations** (no ha funcionat) i tampoc equacions natives: les fórmules són text normal (secció 7).

## 7. Fórmules matemàtiques (depèn de la resposta a la pregunta inicial)

Un quadre de text per fórmula, amb nom d'objecte (per exemple «Fórmula pressió»), i espai suficient. Les fórmules de dins del text normal també segueixen aquestes regles; les dels títols, no (secció 2).

### Si és per a PowerPoint: equacions natives (llenguatge matemàtic de PowerPoint, OMML)

Les fórmules han de ser objectes d'equació de PowerPoint (editables des d'Insereix > Equació), no text pla. pptxgenjs no sap fer-ne: escriu el fitxer, descomprimeix-lo i substitueix el quadre de la fórmula amb aquest ajudant (el text pla queda com a versió de reserva).

```python
import re

def _r(t, sz=2400, color="1D1D1B", b=0):
    return (f'<m:r><a:rPr lang="ca-ES" sz="{sz}" b="{b}" i="1"><a:solidFill><a:srgbClr val="{color}"/></a:solidFill>'
            f'<a:latin typeface="Cambria Math"/></a:rPr><m:t>{t}</m:t></m:r>')

def frac(num, den, **k): return f'<m:f><m:num>{_r(num, **k)}</m:num><m:den>{_r(den, **k)}</m:den></m:f>'
def lin(num, den, **k):  return f'<m:f><m:fPr><m:type m:val="lin"/></m:fPr><m:num>{_r(num, **k)}</m:num><m:den>{_r(den, **k)}</m:den></m:f>'   # fracció lineal (a/b) per a quadres baixos
def sub(base, s, **k):   return f'<m:sSub><m:e>{_r(base, **k)}</m:e><m:sub>{_r(s, **k)}</m:sub></m:sSub>'
def sup(base, e, **k):   return f'<m:sSup><m:e>{_r(base, **k)}</m:e><m:sup>{_r(e, **k)}</m:sup></m:sSup>'
def txt(t, **k):         return _r(t, **k)

def set_equation(slide_xml, shape_name, omml_inner, plain):
    """Substitueix el quadre de text `shape_name` per una equacio nativa (amb el quadre original com a reserva)."""
    m = re.search(r'<p:sp>(?:(?!</p:sp>).)*?name="%s".*?</p:sp>' % re.escape(shape_name), slide_xml, re.S)
    sp = m.group(0)
    para = ('<a:p><a14:m><m:oMathPara><m:oMathParaPr><m:jc m:val="centerGroup"/></m:oMathParaPr><m:oMath>'
            + omml_inner + '</m:oMath></m:oMathPara></a14:m><a:endParaRPr lang="ca-ES"/></a:p>')
    sp_math = re.sub(r'<a:p>.*</a:p>', lambda _: para, sp, flags=re.S)
    ac = ('<mc:AlternateContent xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006">'
          '<mc:Choice xmlns:a14="http://schemas.microsoft.com/office/drawing/2010/main" Requires="a14">'
          + sp_math + '</mc:Choice><mc:Fallback>' + sp + '</mc:Fallback></mc:AlternateContent>')
    out = slide_xml.replace(sp, ac)
    if 'xmlns:m=' not in out[:600]:
        out = out.replace('<p:sld ', '<p:sld xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math" ', 1)
    return out

# P = F/A (blanc, 40 pt, sobre un panell fúcsia):
# set_equation(x, 'Fórmula pressió', txt('P=', sz=4000, color='FFFFFF', b=1) + frac('F', 'A', sz=4000, color='FFFFFF', b=1), 'P = F / A')
# P total = P atm + ρ·g·h:
# set_equation(x, 'Fórmula absoluta', sub('P','total') + txt('=') + sub('P','atm') + txt('+ρ·g·h'), 'P total = P atm + ρ · g · h')
```

Després: `zip` des de dins la carpeta (`[Content_Types].xml` primer), valida amb `validate.py` i renderitza. **LibreOffice mostra el text de reserva, no l'equació**: això és normal. Digues a l'usuari que l'equació només es veu en obrir el fitxer a PowerPoint i que ho comprovi. Si no s'hi veu bé, alternativa: deixar la fórmula en text lineal (P=F/A) i dir-li que la seleccioni i premi Alt+= per convertir-la en equació.

Consells comprovats: les equacions poden anar sobre fons de color (blanc sobre fúcsia, blau o lila). Una fracció apilada (`frac`) necessita un quadre d'uns 0,6 in d'alçada o més; en quadres baixos (etiquetes de 0,56 in o menys, com la diapositiva «Concepte per exercici») usa la fracció lineal `lin` (P=F/A). No posis text normal en negreta amb una fórmula dins la mateixa llista o columna: si una fila no necessita fórmula, escriu-hi només text sense fórmula. Les equacions surten en cursiva i amb tipus Cambria Math.

### Si és per a Google Slides: text normal, SENSE LaTeX

Auto-LaTeX Equations no ha funcionat: **no s'usa mai LaTeX**, ni `$$`, ni `\frac`, ni equacions natives. A Google Slides les fórmules són **text normal amb Unicode**, en un quadre de text propi i en Poppins:
- Fracció en línia amb barra: `P = F / A`, `ρ = m / V`, `A = F / P`
- Producte amb punt volat: `P = ρ · g · h`, `F = P · A`, `F = m · g`
- Potències amb ² i ³: `1 Pa = 1 N/m²`, `1 g/cm³ = 1 000 kg/m³`, `A = π · r²`
- Lletres gregues directes: ρ, π, Δ, ≈. Sense subíndexs: escriu `P total = P atm + ρ · g · h`

Fes-les destacades: negreta, 24–40 pt, en un panell (blanc sobre fúcsia, blau o lila, o fúcsia sobre targeta blanca), amb el quadre prou ample perquè càpiguen en una sola línia. Digues a l'usuari que, si vol equacions «de llibre» a Google Slides, les pot inserir a mà amb Insereix > Equació, però el lliurament estàndard és en text.

## 8. Recursos gràfics (generats amb codi, sense fitxers adjunts)

Aquesta skill és només text, així que el logotip i el punter van incrustats. Executa aquest bloc de Python per crear `logo_pos.png` (color), `logo_neg.png` (blanc), `imagotip(color)` i `deco(...)`.

```python
import base64, io, hashlib
import numpy as np
from PIL import Image, ImageDraw

LOGO_ALPHA = """
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
"""
LOGO_BLUE = """
iVBORw0KGgoAAAANSUhEUgAAAZAAAACfAQAAAAD/5bIAAAAB+UlEQVR42u1YO3KDMBB9EszYHZwg
4Qi5QTgapcscITcJRYocgyJFSsYVyRA2BbYTI620y9jJZEavMAzoef+7EkBCwh9iQ73nqQlRyPve
hoQA6HV63RPR5D7OApQOgDGtQkhGRESdRq+CiIgGjfl3AIBcQ6kZY3nzzdPh2iqt99jPK3Y0opRT
tourgFIupAkoFbfCRnzsyWXeySffLr3MSjGOuCiF19jGwvLtB0lVMrG0sUi6sbTS/5Yr9l474beR
4O86XXshGlE4TcaG8+VZbQvVsYZ6tvpQkQWRhjLNramRKWYAYO+NjxWkSi2nvOuibwHsdIMiO3bj
W6eTBRR78VZLiPJZKzM5x+va5F9DqZ1oWqjLkqcUKxTr9JQbpVsKImoPRdDLKaOfEnJy1qgVo0Et
BRvV5mo4H0vyhKl+JS1L3/uLS5mnUX81KeNaxXLPpu8qte/WGkeZ+LcxKVstxfiS0/KHCjXm7SsK
cmYlq1jz41dnfqmgtKcxSVeMfreIqlhKVblJzVJ6vWKD506kWOmRx1JGvWKzn7a1O5osonnZim1p
nBuZ+XnjloENH0YyN/jRw6vn+MpLGZhIBigjlzk8ZeJ2DCb4GcK7InqsVrWaFef9efGbhvIBAHi8
xBeSmDG9rvXtATyoN2UDEhISEhISEhISEv47vgAUia7mDm11XgAAAABJRU5ErkJggg==
"""
LOGO_SHA16 = "f27c27fdae7a875b"   # sha256 de LOGO_ALPHA+LOGO_BLUE (sense espais), primers 16 caràcters

def _clean(s): return "".join(s.split())
assert hashlib.sha256((_clean(LOGO_ALPHA) + _clean(LOGO_BLUE)).encode()).hexdigest()[:16] == LOGO_SHA16, "Logotip corromput: demana a l'usuari el fitxer del logotip"

def logo(path_color="logo_pos.png", path_neg="logo_neg.png"):
    a = np.asarray(Image.open(io.BytesIO(base64.b64decode(_clean(LOGO_ALPHA)))).convert("L"))
    b = np.asarray(Image.open(io.BytesIO(base64.b64decode(_clean(LOGO_BLUE)))).convert("L")) > 127
    rgb = np.zeros(a.shape + (3,), np.uint8); rgb[:] = (0xDC, 0x00, 0x6B); rgb[b] = (0x00, 0x8C, 0xDC)
    Image.fromarray(np.dstack([rgb, a]), "RGBA").save(path_color)          # 400 x 159 px, relació 2,52:1
    Image.fromarray(np.dstack([np.full_like(rgb, 255), a]), "RGBA").save(path_neg)

# Punter (imagotip): contorn de la fletxa en coordenades 0-1 dins del quadrat del cercle
ARROW = [[0.149,0.4],[0.143,0.411],[0.143,0.419],[0.149,0.43],[0.156,0.436],[0.455,0.524],[0.476,0.532],[0.484,0.546],[0.593,0.838],[0.601,0.849],[0.609,0.853],[0.621,0.853],[0.631,0.846],[0.636,0.833],[0.755,0.29],[0.755,0.281],[0.751,0.265],[0.738,0.249],[0.726,0.241],[0.717,0.239],[0.694,0.24],[0.163,0.392]]

def imagotip(path, color="008CDC", px=600):
    """Cercle de color amb el punter blanc (transparent)."""
    ss = 3; S = px * ss
    im = Image.new("RGBA", (S, S), (0, 0, 0, 0)); d = ImageDraw.Draw(im)
    d.ellipse((0, 0, S - 1, S - 1), fill="#" + color)
    d.polygon([(x * S, y * S) for x, y in ARROW], fill=(0, 0, 0, 0))
    im.resize((px, px), Image.LANCZOS).save(path)

def deco(path, cx, cy, diam, color="F5E6A3", W=2000, H=1125, ppi=200, ss=2):
    """Imatge de fons 10 x 5,625 in amb el cercle groc retallat pel punter. cx, cy, diam en polzades."""
    im = Image.new("RGBA", (W * ss, H * ss), (0, 0, 0, 0)); d = ImageDraw.Draw(im)
    r = diam * ppi * ss / 2; X = cx * ppi * ss; Y = cy * ppi * ss
    d.ellipse((X - r, Y - r, X + r, Y + r), fill="#" + color)
    d.polygon([(X - r + px * 2 * r, Y - r + py * 2 * r) for px, py in ARROW], fill=(0, 0, 0, 0))
    im.resize((W, H), Image.LANCZOS).save(path)

# Ús habitual
# logo(); deco("deco_cover.png", 2.2, 2.0, 6.8); deco("deco_divider.png", 7.3, 5.0, 6.6)
```

Posicions que han funcionat bé: portada `deco(…, 2.2, 2.0, 6.8)`; separadors `deco(…, 7.3, 5.0, 6.6)`. El text de portada i separadors va sobre el cercle i el retall: usa fúcsia per al títol i `#1D1D1B` per al subtítol.

Si l'usuari adjunta el manual d'identitat en PDF, el logotip original també es pot extreure de la pàgina 5 (`pdftoppm -r 400 -f 5 -l 5`), però amb el bloc de dalt normalment no cal.

## 9. Llenguatge (manual, apartat d'identitat verbal)

- Missatges clars i concisos, paraules simples i frases breus. To formal i informatiu amb famílies; més proper amb l'alumnat.
- Llenguatge inclusiu: «alumnat», «estudiants», «famílies», «equip docent», «personal d'administració». No usis «alumnes/professors/pares» en genèric, ni «@» ni «x».
- Valors de l'escola: inclusió, igualtat, transversalitat, excel·lència acadèmica, cura de cada persona.

## 10. Abans de lliurar

1. S'ha preguntat (o l'usuari ja havia dit) si és per a PowerPoint o Google Slides.
2. El fitxer es valida i s'obre sense errors.
3. Totes les diapositives renderitzades a imatge i revisades (res desbordat, res tallat, contrast correcte, logotip net).
4. Cada títol comença en majúscula i és d'un sol color.
5. Hi ha separador a cada canvi de subtema i notes a totes les diapositives de contingut.
6. Les fórmules segueixen la plataforma: equacions natives d'OMML per a PowerPoint (i has dit a l'usuari que les comprovi obrint-les a PowerPoint), o text normal amb Unicode per a Google Slides (mai LaTeX, mai `$$`).
7. El fons de les diapositives té un 60 % de transparència, els panells de color un 50 % i sense vora, i no hi ha número de diapositiva ni pestanya turquesa.
8. Lliura el fitxer amb una línia de context, i digues si cal instal·lar Poppins.