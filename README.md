# Istraživanje podataka
## Travel review Dataset
Korišćeni skup podataka predstavlja prosečne ocene različitih atrakcija sa Google reviews u .csv formatu. Sve ocene imaju realne vrednosti između 1 i 5.
Skup se može pronaći na [linku](https://archive.ics.uci.edu/dataset/485/tarvel+review+ratings).

Detaljna analiza skupa podataka nalazi se u okviru prve Jupyter sveske (klasterovanje).

## Modeli

### Klasterovanje
Za problem klasterovanja korišćena su dva modela: k-sredina i hijerarhijsko klasterovanje. Ova Jupyter sveska obuhvata analizu podataka i pretprocesiranje, nakon čega sledi određivanje optimalnog broja klastera za oba modela, treniranje i poređenje dobijenih rezultata. Kao deo pretprocesiranja korišćena je i tehnika PCA za smanjenje dimenzionalnosti ulaza, ali i kako bi podaci mogli biti predstavljeni grafički.

### Klasifikacija
Kako sam skup podataka ne sadrži ciljnu promenljivu i sve vrednosti su numeričke, za problem klasifikacije je izvršena transformacija jednog od atributa u kategoričke vrednosti na sledeći način:
- Ako je prosečna ocena za atrakciju manja od 1.7, označavamo je kao "niska."
- Ako je prosečna ocena za atrakciju veća od 1.7 i manja od 3.4, označavamo je kao "srednja."
- Ako je prosečna ocena za atrakciju veća od 3.4, označavamo je kao "visoka."

Na ovako transformisanom skupu podataka trenirana su tri modela: Logistička regresija, SVC i Random Forest. Za sve modele je prvo izvršeno podešavanje hiperparametara korišćenjem bibliotečke funkcije GridSearchCV, nakon čega su modeli sa najboljim parametrima evaluirani na validacionom skupu radi poređenja. Na kraju se nalazi detaljna evaluacija na test skupu za model Random Forest, koji se na validacionom skupu pokazao kao najbolji.

### Regresija
Zbog prirode podataka, pored klasifikacije primenjena je i regresija. Za ovaj problem korišćena su dva modela: Linearna regresija i SVR, pomoću kojih se pokušava predvideti vrednost jednog atributa, na osnovu vrednosti ostalih.

## Biblioteke
U okviru projekta korišćene su biblioteke pandas, numpy i sklearn

## Autor
Jelena Maksimović 193/2018.
