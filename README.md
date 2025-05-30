
## Analiza podataka OI 2020

Ovaj projekt obrađuje i analizira podatke vezane uz Olimpijske igre 2020, koristeći podatke iz nekoliko različitih izvora, uključujući i web scraping te interaktivnu pitalicu temeljenu na LLM modelu. Analize su implementirane u Jupyter Notebook-u `OI_Projekt.ipynb`.

---

### Podaci

Analiza uključuje sljedeće izvore podataka:

* **Athletes.xlsx**: Informacije o sportašima (ime, NOC, disciplina). Nema nedostajućih vrijednosti.
* **Coaches.xlsx**: Imena trenera, NOC, disciplina, događaj. Polje "Event" sadrži dosta nedostajućih vrijednosti.
* **EntriesGender.xlsx**: Broj muških, ženskih i ukupnih sudionika po disciplini. Nema nedostajućih vrijednosti.
* **gdp.csv**: Podaci o BDP-u zemalja kroz različite godine (neki nedostajući podaci).
* **Medals.xlsx**: Rangiranje timova po medaljama. Nema nedostajućih vrijednosti.
* **Teams.xlsx**: Informacije o timovima prema disciplini i događaju.
* **Podaci dobiveni web scrapingom**: Prikupljeni s internetskih izvora kako bi se omogućilo kreiranje interaktivnog kviza.

---

### LLM model (pitalica)

Kako projekt sadrži podatke samo za Olimpijske igre 2020., implementirana je i **LLM pitalica** koja korisnicima omogućuje da postave pitanja o bilo kojim Olimpijskim igrama ikad održanim (npr. “Koji sportaš je osvojio najviše medalja na OI u Riju 2016?”). Pitalica koristi LLM model za generiranje odgovora temeljenih na vanjskim izvorima i znanju modela.

---

###  Web scraping

Za potrebe kviza, projekt koristi **web scraping** za prikupljanje dodatnih podataka o Olimpijskim igrama (npr. popis sportaša, medalja, povijesne činjenice). Ti podaci nadopunjuju analizu i omogućuju korisnicima da postavljaju pitanja izvan okvira podataka iz 2020.

---

###  Ključne značajke

* Priprema i čišćenje podataka iz više izvora.
* Web scraping za proširenje baze podataka kviza.
* Interaktivna LLM pitalica za odgovaranje na pitanja o Olimpijskim igrama (neovisno o godini).
* Analiza i vizualizacija podataka za OI 2020.
* Integracija ekonomskih pokazatelja s rezultatima sportaša.

---

###  Kako koristiti

1. Klonirajte repozitorij:

   ```bash
   git clone <URL-repozitorija>
   cd <ime-repozitorija>
   ```
2. Instalirajte potrebne biblioteke:

3. Pokrenite Jupyter Notebook:

   ```bash
   jupyter notebook OI_Projekt.ipynb
   ```
4. Slijedite bilješke u notebooku za analizu podataka, vizualizaciju i korištenje pitalice.

---

### Tehnički zahtjevi

* Python 3.x
* Pandas
* Numpy
* BeautifulSoup / Requests (za web scraping)
* Matplotlib (ili drugi alati za vizualizaciju)
* LLM biblioteka (npr. OpenAI API ili lokalno trenirani model)
* Jupyter Notebook

---
