# Návrh projektu  
**Predmet:** Neurónové siete
**Autori:** Andrej Gáfrik, Martin Grega
**Téma:** Detekcia urážok v komentároch v anglickom jazyku

## Motivácia
V posledných rokoch bol zaznamenaný vysoký nárast frekvencie výskytu urážlivých komentárov na webových stránkach. Zodpovedná zaň je najmä mladšia generácia používateľov. Saturácia komentárov urážlivými vyjadreniami má za následok zníženie dôveryhodnosti danej stránky, poprípade aj značný úbytok jej návštevníkov, nehovoriac o tom, že je pozitívnym faktorom v náraste extrémizmu v súčasnej spoločnosti. Tento jav má nemalé následky, preto je žiadané vytvorenie určitého systému moderácie používateľských prejavov v komentároch.  Množstvo používateľmi generovaného obsahu je ale príliš veľké na to, aby bolo možné ho manuálne filtrovať, preto sa ponúka možnosť oprieť sa o existujúci výskum v doméne umelej inteligencie, ktorá sa v poslednej dobe výrazne zaoberá oblasťou spracovávania prirodzených jazykov pomocou neurónových sietí. Ako prvý krok je nevyhnutné zadefinovať a implementovať model, ktorého úlohou bude efektívna detekcia urážlivého obsahu v poskytnutých dátach.

## Súvisiace práce v danej oblasti

  Na základe prečítaných prameňov sme zisliti, že na detekciu urážok v texte sa dajú použiť napríklad viac-vrstvový perceptrón, pri ktorom ako aktivačná funckia bola použitá ReLu a back-propagation pre trénovanie.
Použitá tiež môže byť 1D konvolučná neurónová sieť. Zostava: 4 konvolučné vrstvy s výstupom o veľkosti 128 a kernel veľkosť 5, potom Max Pooling, ďalej 3 konvolučné vrstvy s výstupom veľkosti 128 a kernel veľkostou 5 a nakoniec Average Pooling. 
Ako ďalší príklad uvádzame LSTM (Long Short Term Memory). Je to typ RNN siete, ktorá je schopná učiť sa dlhotrvajúce vzťahy. Použitá bola jedna vrstva s 128 jednotkami LSTM. MLP malo najlepší výsledok vzhľadom na F1 score. Autori v práci ďalej uvádzajú ďalšie
metódy trénovania, ktoré zlepšujú výkonnosť LSTM, ktoré je schopné brať do úvahy celé vety. Ako dataset väčeina autorov používalo verejný dataset z twiteru, ktorý zverejňuje 1% tweetov alebo dataset, ktorý chceme použiť v našom zadaní.

// Zdroj http://cs229.stanford.edu/proj2017/final-reports/5242067.pdf
	
## Dataset
  Dataset k našemu projektu sme našli ans tránke kaggle. Obsahuje trénovací aj validačný dataset s komentármi, ktoré sú útočné alebo nie. V trénovacom datasete sú jednotlivé komentáre označené či obsahujú urážlivé slovo/ urážku ale nie. Jeden riadok
datasetu obsahuje boolean hodnotu, či v komentári je urážka alebo nie, dátum komentáru a samotný komentár. Trénovací dataset obsahuje 3945 riadkov a testovací dataset 2233 riadkov. K testovaciemu datasetu máme zhodný dataset, ktorý obsahuje aj boolean	hodnoty či v komentári je urážka alebo nie. 

## High-Level Solution Proposal

Riešenie ešte nemáme úplne premyslené. Je pravdepodobné, že sa chztíme nejakého postupu z daného článku.
