# PROJEKT POWER BI  
## Analýza přidělování obecních bytů v Brně (2017–2023)

**Autor:** Lucie Mendlíková  
**Studium:** Datová akademie  

---

## Cíl projektu
Tento Power BI projekt se zaměřuje na analýzu a vizualizaci dat o obecním bydlení ve městě Brně v letech 2017–2023. Cílem projektu je přehledně zobrazit vývoj počtu žadatelů o obecní byty, počet přidělených bytů a strukturu bytového fondu podle jednotlivých městských částí.

---

## Zdroje dat
Data pocházejí z volně dostupných datasetů zveřejněných na webových stránkách města Brna. Fotografie města Brna byla vytvořena pomocí nástroje Copilot. Logo města Brna bylo převzato z oficiálních webových stránek města Brna a odkazuje na přehled obecního bydlení v Brně.

- **Obecní bydlení – běžné obecní byty podle městských částí:**  
  https://data.brno.cz/datasets/9551b6096c404c98b3a2cc1dde8b8786_0/explore

- **Obecní bydlení – počty bytů jednotlivých typů podle městských částí:**  
  https://data.brno.cz/datasets/a83243db63c641529aede621830b610f_0/explore

---

## Použité nástroje
Datové tabulky byly získány ve formátu `.csv` a následně převedeny do Excelu, kde došlo k základní úpravě dat, konkrétně k rozdělení hodnot do jednotlivých sloupců. Takto připravené tabulky byly následně importovány do Power BI, ve kterém probíhaly veškeré další úpravy a analýzy.

---

## Popis a struktura dat
Projekt pracuje se dvěma hlavními datovými tabulkami:

### `obecni_byty_statistiky`
Tabulka obsahuje časové údaje o počtu žadatelů, přidělených bytů a dalších ukazatelích v jednotlivých letech. Důležité je rozlišovat mezi sloupci `zaevid_zadatele_celkem` a `zaevid_zadatele`. První z nich uvádí celkový počet osob evidovaných v databázích městských částí, přičemž ne všichni tito žadatelé jsou aktivní a skutečně se ucházejí o volné byty, a proto nejsou pro další analýzy relevantní. Sloupec `zaevid_zadatele` naopak zachycuje pouze aktivní žadatele, se kterými je v analýzách pracováno.

Dále byla v tabulce odstraněna data nerelevantní pro projekt a pro účely analýzy byl vytvořen nový sloupec `Rok`, který zjednodušuje práci s časovým filtrováním. Tato tabulka zahrnuje pouze běžný typ obecních bytů.

### `obecni_byty_typy`
Tabulka obsahuje přehled typů obecních bytů (běžné, bezbariérové, sociální, startovací apod.) podle městských částí. Data pocházejí z roku 2022 a neobsahují časové rozlišení, proto nejsou využívána pro časové analýzy. Vzhledem k tomu, že hlavní časová tabulka pracuje pouze s kategorií běžných bytů, slouží tato tabulka pouze k orientačnímu přehledu struktury obecního bytového fondu v Brně a k přibližnému vyčíslení zastoupení jednotlivých typů bytů.

Tabulky jsou propojeny pomocí vytvořené pomocné tabulky `Mestska_cast`, která slouží k filtrování a členění dat napříč celým reportem.

---

## Vytvořené metriky a kalkulovaný sloupec
- **celkem_pridelenych_bytu** – celkový počet přidělených běžných bytů ve všech městských částech za sledované období  
- **celkem_zadatelu** – celkový počet aktivních žadatelů o běžný byt ve všech městských částech za sledované období  
- **uspesnost_prideleni** – procentuální vyjádření podílu přidělených bytů z počtu aktivních žadatelů  
- **rozdil_zadatelu_a_pridelenych** *(kalkulovaný sloupec)* – počet neúspěšných žadatelů, tedy rozdíl mezi celkovým počtem aktivních žadatelů a přidělených bytů  

**Poznámka:** Ve vizualizaci mapy nejsou správně rozpoznány městské části Sever, Střed a Jih, a jejich body se proto zobrazují uprostřed Brna, což snižuje přehlednost mapy. Vzhledem k tomu, že se jedná o oficiální názvy městských částí, není možné je upravovat, aby nedošlo ke zkreslení dat.

Typ bytu **„V DPS“** označuje byt v domě s pečovatelskou službou.

---

## Závěr
Projekt poskytuje přehledný pohled na problematiku obecního bydlení v Brně a umožňuje porovnávat jak vývoj v čase, tak rozdíly mezi jednotlivými městskými částmi. Důraz byl kladen na jednoduchost, čitelnost a správné využití vizualizačních nástrojů Power BI.

Z celkového počtu přibližně 19 tisíc žadatelů bylo v letech 2017–2023 přiděleno zhruba 3 tisíce bytů, což ukazuje, že nabídka obecního bydlení dlouhodobě nestačí pokrýt poptávku. Úspěšnost přidělení ve výši 17 % tak naznačuje, že většina žadatelů na běžný obecní byt v Brně nedosáhne.

---

## Odevzdané soubory
- `PBI_PROJEKT.pbix` – projekt zpracovaný v Power BI  
- `Obecni_byty1.xlsx` – zdrojová tabulka pro tabulku `obecni_byty_statistiky`  
- `Obecni_byty2.xlsx` – zdrojová tabulka pro tabulku `obecni_byty_typy`  
