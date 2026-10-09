# Apuntes FING

Apuntes de clase de la Facultad de Ingeniería (UdelaR), escritos en LaTeX.

## Estructura

```
apuntes-fing/
├── estilo/
│   └── apuntes.sty          # Estilo común a todos los apuntes
└── <MATERIA>/
    └── NN-tema/
        ├── tema.tex         # Fuente
        ├── tema.pdf         # PDF compilado
        └── codigo/          # Código asociado (si hay)
```

## Materias

### [GAL 1](GAL-1/) — Geometría y Álgebra Lineal 1

| # | Tema | PDF |
|---|------|-----|
| 01 | Números complejos | [PDF](GAL-1/01-numeros-complejos/numeros-complejos.pdf) |
| 02 | Sistemas, matrices y determinantes | [PDF](GAL-1/02-sistemas-matrices-determinantes/sistemas-matrices-determinantes.pdf) |

### [CDIV](CDIV/) — Cálculo Diferencial e Integral en una Variable

| # | Tema | PDF |
|---|------|-----|
| 01 | Integrales | [PDF](CDIV/01-integrales/integrales.pdf) |
| 02 | Límites y continuidad | [PDF](CDIV/02-limites-y-continuidad/limites-y-continuidad.pdf) |

## Compilar

Los `.tex` usan `\usepackage{apuntes}`. Para que LaTeX encuentre el estilo desde
cualquier carpeta, enlazalo una vez en tu árbol TeX personal:

```bash
mkdir -p "$(kpsewhich -var-value TEXMFHOME)/tex/latex/apuntes"
ln -sf "$PWD/estilo/apuntes.sty" "$(kpsewhich -var-value TEXMFHOME)/tex/latex/apuntes/apuntes.sty"
```

Después, dentro de la carpeta del tema:

```bash
latexmk -pdf tema.tex
```
