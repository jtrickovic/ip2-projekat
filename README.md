# DeliciousMil — klasterovanje i pravila asocijacije

Projekat se bavi analizom skupa podataka DeliciousMil korišćenjem klasterovanja i pravila asocijacije.

## Sveske (koreni direktorijum)

1. **01_preprocessing** — osnovni podaci o skupu i učitavanje podataka.
2. **02_clustering** — klasterovanje po konvenciji oznaka (k = 20).
3. **03_association_rules** — pravila asocijacije.
4. **04_parameter_choice** — traženje boljeg k za svaki algoritam ponaosob, revizija parametara i poređenje klasterovanja bez i sa SVD redukcijom.
5. **05_raw_vs_svd** — spajanje csv-ova dva prolaza (SVD(100) vs sirovi TF-IDF) u tabele poređenja.

Redosled pokretanja: 01 → 02 → 03 → 04. Sveske 03 i 04 same učitavaju alate iz 01 i 02.

## Podaci

U korenu se nalaze `.dat` fajlovi (dokumenti, oznake i anotirane rečenice) i `vocabs.txt` — rečnik stemovanih reči; to je sam skup podataka.

## Ostali direktorijumi

- **raw/** — tri sveske, ali nad TF-IDF matricom (bez SVD redukcije). Kod je pretežno isti uz manje izmene.
- **figures/** — slike, **results/** — `.pkl` keš fajlovi, **csv/** — `.csv` tabele.

Keš fajlovi u `results/` su međurezultati: ako se obrišu, sveske ih automatski preračunaju pri sledećem pokretanju.

## Instalacija Python zavisnosti:

```bash
pip install numpy pandas scipy scikit-learn matplotlib networkx joblib nbformat
```

## Napomena 
- Radi sistematičnosti i zato što ima dosta reprezentacija algoritama koji ne mogu da nadju optimalno k, onda se pretraga za k produžava
da bismo videli šta bismo dobili, iako to nisu globalno optimalne vrednosti. Zbog toga je alternativa da se
smanji max k za pretragu pri ponovnom pokretanju, jer samo skeniranje traje dosta.

