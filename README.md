# Analitika i vizualizacija podataka

Statističke analize i vizualizacija podataka rađene u okviru predmeta Analitika i vizualizacija podataka (Računarski fakultet, 2026). Analize su rađene u R-u (R Markdown) i u alatu Orange Data Mining.

**Tehnologije:** R, dplyr, tidyverse, ggplot2, FSA, R Markdown, Orange Data Mining

---

## Domaći 1 – Da li se isplati čekati? Veza između godina iskustva i plate profesora

**Pitanje:** Da li se plate profesora razlikuju u zavisnosti od godina radnog iskustva?

**Podaci:** `Salaries` skup podataka iz R paketa `carData`. Godine iskustva su podeljene u tri grupe: 0–10, 10–25 i 25+.

**Pristup:**
- deskriptivna statistika i vizualizacija (box plot, histogrami, scatter plot sa trend linijom)
- provera normalnosti: QQ plot i Shapiro-Wilk test
- normalnost nije ispunjena u svim grupama, pa je umesto ANOVA testa korišćen neparametarski **Kruskal-Wallis test**

**Zaključak:** Razlika u platama između grupa je statistički značajna (H = 97.86, p < 0.001), ali odnos nije linearan. Plate najbrže rastu u ranoj fazi karijere, a nakon 15–20 godina se stabilizuju.

👉 [Pogledaj celu analizu sa graficima](domaci-1-plate-profesora/aivp_domaci1.md)

---

## Domaći 2 – Povezanost akademskih faktora i mentalnog zdravlja kod studenata

**Podaci:** Bangladeshi University Students Mental Health Dataset (Kaggle), anketa iz 2023. sa 1977 ispitanika i skorovima za stres, anksioznost i depresiju. Podaci nisu uključeni u repozitorijum.

**Istraživačka pitanja i pristup:**
1. *Da li se nivo stresa razlikuje između akademskih oblasti?* Provera normalnosti (Shapiro-Wilk, QQ plot), zatim **Kruskal-Wallis** i **Dunn post-hoc** test.
2. *Da li studenti sa višim stresom imaju i viši nivo depresije?* **Spearman korelacija**.
3. *Da li je kategorija depresije povezana sa godinom studija?* **Hi-kvadrat test** sa proverom očekivanih frekvencija i analizom reziduala.

**Zaključak:**
- Nivo stresa se značajno razlikuje između akademskih oblasti (p < 0.001). Studenti EEE/ECE prijavljuju više stresa od studenata CS/CSE i Mechanical.
- Između stresa i depresije postoji umereno jaka pozitivna veza (ρ = 0.591, p < 0.001).
- Kategorija depresije je povezana sa godinom studija (χ² = 41.73, p = 0.003). Najnepovoljnija slika javlja se sredinom studija.
- Ograničenje: analiza pokazuje povezanost, ali ne i uzročnost.

👉 [Pogledaj celu analizu sa graficima](domaci-2-mentalno-zdravlje-studenata/aivp_domaci2.md)

---

## Domaći 3 – Vizualizacija i eksploracija podataka u Orange-u

**Podaci:** [Nutritional Facts for Most Common Foods](https://www.kaggle.com/datasets/niharika41298/nutrition-details-for-most-common-foods) (Kaggle), 335 namirnica i 10 varijabli.

**Pristup:**
- čišćenje podataka: vrednosti „t“ (količine u tragovima) zamenjene su nulama, a ispravljena je greška nastala Excel formatiranjem
- eksploracija u Orange-u: Data Table, Feature Statistics, Distributions, Box Plot i Scatter Plot
- analiza raspodela, varijabilnosti po kategorijama, autlajera i veza između nutritivnih vrednosti

**Zaključak:** Raspodela kalorija je pozitivno iskošena, a autlajeri su uglavnom realne vrednosti, a ne greške. Između kalorija i proteina postoji blaga pozitivna veza. Kategorije hrane se delimično razlikuju: meso i riba imaju više proteina.

📄 [Izveštaj (PDF)](domaci-3-orange-nutritivne-vrednosti/aivp_domaci3.pdf) · ⚙️ [Orange workflow](domaci-3-orange-nutritivne-vrednosti/dom3.ows)

---

## Struktura repozitorijuma

```
├── domaci-1-plate-profesora/                 R Markdown analiza (.Rmd, .md, .html)
├── domaci-2-mentalno-zdravlje-studenata/     R Markdown analiza (.Rmd, .md, .html)
└── domaci-3-orange-nutritivne-vrednosti/     izveštaj (PDF) i Orange workflow (.ows)
```
