# LaTeX Шаблон за Македонски Јазик

Ова е професионален шаблон за пишување научни документи, семинарски работи, дипломски трудови и слични документи на македонски јазик користејќи LaTeX.

## Потребни алатки

### 1. LaTeX Дистрибуција

Треба да инсталирате LaTeX дистрибуција и дополнителни пакети (некои се опционални):

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get update
# Задолжителни пакети
sudo apt-get install \
  texlive-base \
  texlive-latex-base \
  texlive-latex-recommended \
  texlive-latex-extra \
  texlive-fonts-recommended \
  texlive-fonts-extra \
  texlive-luatex \
  texlive-lang-cyrillic \
  texlive-pictures \
  texlive-science

# Опционални пакети
sudo apt-get install \
  biber \
  latexmk
```

**Објаснување на пакетите:**

**Задолжителни (за основно компајлирање):**
- `texlive-base` - Основни LaTeX алатки и бинарни датотеки (вклучува lualatex, bibtex)
- `texlive-latex-base` - Основни LaTeX пакети
- `texlive-latex-recommended` - Препорачани LaTeX пакети (geometry, graphicx, xcolor, hyperref, итн.)
- `texlive-latex-extra` - Дополнителни пакети (fancyhdr, listings, microtype, booktabs, csquotes, parskip, caption) + **latexindent** (форматер)
- `texlive-fonts-recommended` - Препорачани фонтови
- `texlive-fonts-extra` - Дополнителни фонтови (за математички симболи)
- `texlive-luatex` - LuaLaTeX компајлер и fontspec пакет (за Unicode и модерни фонтови)
- `texlive-lang-cyrillic` - Поддршка за кирилица и македонски јазик (babel-macedonian)
- `texlive-pictures` - Пакети за графика (tikz, pgfplots)
- `texlive-science` - Математички пакети (amsmath, amssymb)

**Опционални (за подобро искуство):**
- `biber` - Модерна алатка за библиографија (алтернатива на bibtex)
- `latexmk` - Автоматизација на компајлирање (корисно за автоматско повторно компајлирање)

**Проценета големина:** ~350-400 MB задолжителни + ~20 MB опционални (вкупно ~370-420 MB наместо ~6 GB за texlive-full)

**Linux (Fedora):**
```bash
# Задолжителни пакети
sudo dnf install \
  texlive-collection-basic \
  texlive-collection-latex \
  texlive-collection-latexrecommended \
  texlive-collection-latexextra \
  texlive-collection-fontsrecommended \
  texlive-collection-fontsextra \
  texlive-collection-luatex \
  texlive-collection-langcyrillic \
  texlive-collection-pictures \
  texlive-collection-science

# Опционални пакети
sudo dnf install \
  biber \
  latexmk
```

**macOS:**
- Преземете и инсталирајте [MacTeX](https://www.tug.org/mactex/)

**Windows:**
- Преземете и инсталирајте [MiKTeX](https://miktex.org/download)

### 2. LaTeX пакети користени во овој шаблон

Овој шаблон користи следниве LaTeX пакети (сите се вклучени во горните инсталациони команди):

**Основни пакети:**
- `fontspec` - Управување со фонтови (вклучено во texlive-luatex)
- `babel` - Јазична поддршка (вклучено во texlive-latex-recommended)
- `geometry` - Подесување на димензии на страница (вклучено во texlive-latex-recommended)
- `graphicx` - Вклучување на слики (вклучено во texlive-latex-recommended)

**Дополнителни пакети:**
- `amsmath`, `amssymb` - Математички формули и символи (вклучено во texlive-science)
- `tikz`, `pgfplots` - Цртање на дијаграми и графикони (вклучено во texlive-pictures)
- `listings` - Форматирање на програмски код (вклучено во texlive-latex-extra)
- `booktabs` - Професионални табели (вклучено во texlive-latex-extra)
- `hyperref` - Хиперврски во PDF (вклучено во texlive-latex-recommended)
- `fancyhdr` - Прилагодливи хедери и футери (вклучено во texlive-latex-extra)
- `microtype` - Подобрена типографија (вклучено во texlive-latex-extra)
- `csquotes` - Правилни наводници (вклучено во texlive-latex-extra)
- `xcolor` - Боја на текст и позадина (вклучено во texlive-latex-recommended)

### 3. LuaLaTeX (вклучен во LaTeX дистрибуцијата)

Овој шаблон е спесифично конфигуриран за LuaLaTeX, модерен LaTeX компајлер кој поддржува Unicode и модерни фонтови. Го користиме за правилна поддршка на кирилица и македонски јазик.

**Зошто LuaLaTeX?**
- Нативна поддршка за Unicode (кирилица работи директно)
- Поддршка за модерни OpenType/TrueType фонтови (Liberation Serif)
- Подобра обработка на комплексни јазици

### 4. BibTeX (вклучен во LaTeX дистрибуцијата)

Овој шаблон е спесифично конфигуриран за BibTex, aлатка за управување со библиографија и референци. Се користи за автоматско форматирање на списокот на литература.

### 5. Liberation Фонтови

Liberation фонтот наликува на Times New Roman фонтот и поседува македонска подршка.

**Linux:**
```bash
sudo apt-get install fonts-liberation
```

**macOS/Windows:**
- Обично се инсталирани по стандард
- Ако недостасуваат, преземете од [Liberation Fonts](https://github.com/liberationfonts/liberation-fonts)

### 6. Едитор (опционално, но препорачано)

За едитор, препорачливо е да користите [VS Code](https://code.visualstudio.com/) со **LaTeX Workshop** екстензијата.

**Инсталација:**
1. Преземете и инсталирајте [VS Code](https://code.visualstudio.com/)
2. Инсталирајте ја екстензијата "LaTeX Workshop" (James Yu)

**Автоматски функции (веќе конфигурирани во `.vscode/settings.json`):**
- **Автоматско компајлирање при зачувување** - Секогаш кога зачувате `.tex` датотека, документот автоматски се компајлира
- **Автоматско форматирање** - Користи `latexindent` (од texlive-latex-extra) за форматирање на код
- **PDF преглед во табови** - PDF се отвора директно во VS Code
- **Синтакс highlighting** - Обојување на LaTeX синтакса за полесно читање
- **Autocomplete** - Автоматско довршување на LaTeX команди

**Корисни кратенки во VS Code:**
- `Ctrl + S` - Зачувај и автоматски компајлирај
- `Ctrl + Alt + B` - Рачно компајлирај
- `Ctrl + Alt + V` - Отвори PDF преглед
- `Shift + Alt + F` - Форматирај документ (latexindent)

## Брзо започнување

### Преку Visual Studio Code

Клонирајте го овој репизотирум преку Visual Studio Code со овој линк `https://github.com/DimitrijKrstev/LaTeX-Macedonian-Template`. Преку секое зачувување автоматски ќе се рекреира `main.pdf` со вашите најнови промени.

### Рачно

#### 1. Клонирајте или преземете го проектот

```bash
git clone <repository-url>
cd "LaTex Macedonian Template"
```

#### 2. Компајлирајте го документот

```bash
lualatex main.tex
bibtex main
lualatex main.tex
lualatex main.tex
```

**Зошто толку пати?**
- Прв пат: LaTeX ги процесира основните информации
- BibTeX: Ја креира библиографијата
- Втор пат: Се вметнува библиографијата
- Трет пат: Се ажурираат сите референци и содржината

### 3. Отворете го `main.pdf`


## Структура на проектот

```
.
├── main.tex                    # Главна датотека - започнете од тука
├── config/                     # Конфигурација
│   ├── preamble.tex            # Пакети и подесувања
│   └── commands.tex            # Ваши команди
├── sections/                   # Содржина на документот, секоја папка содржи секции и соодветни подсекции
│   ├── abstract.tex
│   ├── introduction/
│   ├── methodology/
│   ├── related-work/
│   └── conclusion/
├── tables/                     # Табели (одвоени датотеки)
│   ├── tools-comparison.tex
│   └── results-summary.tex
├── figures/                    # Слики и графикони, под-датотеки доколку се во голем број
├── references/                 # Библиографија
│   └── references.bib
└── back/                       # Завршен дел
    └──  bibliography.tex
```

## Како да работите со документот

### Уредување на содржина

1. **Отворете `main.tex`** - тука се вклучуваат сите секции
2. **Уредувајте ги датотеките во `sections/`** - тука пишувате ја содржината
3. **Компајлирајте** - за да видите промени

### Додавање на нова секција

**Едноставна секција (една датотека):**

```bash
# Креирајте нова датотека
nano sections/results.tex
```

Во `main.tex` додадете:
```latex
\input{sections/results}
```

**Комплексна секција (со подсекции):**

```bash
# Креирајте папка и датотека
mkdir sections/results
nano sections/results/results.tex
```

Во `main.tex` додадете:
```latex
\input{sections/results/results}
```

### Додавање на слики

1. **Ставете ја сликата** во `figures/` папката
2. **Вклучете ја** во вашата секција:

```latex
\begin{figure}[h]
  \centering
  \includegraphics[width=0.8\textwidth]{figures/my-image.png}
  \caption{Опис на сликата}
  \label{fig:my-image}
\end{figure}
```

3. **Референцирајте ја** во текстот:
```latex
Како што се гледа на Слика~\ref{fig:my-image}...
```

### Додавање на табели

**Опција 1: Директно во текст**
```latex
\begin{table}[h]
  \centering
  \caption{Наслов}
  \begin{tabular}{lcc}
    \toprule
    Колона 1 & Колона 2 & Колона 3 \\
    \midrule
    Податок  & 123      & 456      \\
    \bottomrule
  \end{tabular}
\end{table}
```

**Опција 2: Одвоена датотека (за комплексни табели)**
1. Креирајте `tables/my-table.tex`
2. Вклучете со `\input{tables/my-table}`

### Додавање на референци (цитирање)

1. **Отворете `references/references.bib`**
2. **Додадете нова референца:**

```bibtex
@article{авторпрезиме2024,
  author  = {Презиме, Име and Друг, Автор},
  title   = {Наслов на трудот},
  journal = {Име на списание},
  year    = {2024},
  volume  = {10},
  pages   = {123--145}
}
```

3. **Цитирајте во текстот:**
```latex
Според истражувањето \cite{авторпрезиме2024}...
```

**Референцирање:**
```latex
Од равенката~\ref{eq:einstein} следува...
```

## Чести проблеми

### "Command not found: lualatex"
- Инсталирајте LaTeX дистрибуција (види погоре)

### "Font not found: Liberation Serif"
- Инсталирајте Liberation фонтови (види погоре)

### "Undefined references"
- Компајлирајте повеќе пати (lualatex → bibtex → lualatex → lualatex)

### Сликата не се појавува
- Проверете дали патеката е точна
- Проверете дали сликата постои
- Користете поддржани формати: PNG, JPG, PDF

### Табелата излегува од страницата
- Намалете ја големината на текстот: `\small`
- Ротирајте ја табелата: користете `sidewaystable`
- Поделете ја на повеќе табели

## Совети за почетници

1. **Компајлирајте често** - За да видите промени веднаш
2. **Користете `\label` и `\ref`** - Никогаш не пишувајте броеви рачно
3. **Правете backup** - Користете Git или друг систем
4. **Читајте грешки** - LaTeX дава детални пораки за грешки
5. **Користете коментари** - Линии што почнуваат со `%` се игнорирани

## Дополнителни ресурси

- [Overleaf Tutorial](https://www.overleaf.com/learn) - Одлични LaTeX туторијали
- [LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX) - Сеопфатен водич
- [CTAN](https://ctan.org/) - LaTeX пакети и документација

## Лиценца

Овој шаблон е слободно достапен за користење и прилагодување.

## Прашања и проблеми

Ако имате прашања или проблеми, отворете issue на GitHub или консултирајте се со LaTeX заедницата.

---

**Среќно пишување!** 
