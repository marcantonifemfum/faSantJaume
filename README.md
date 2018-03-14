# faSantJaume [ca]
Algorismes componedors, escrits en llenguatge *PostScript*, del **llistat de reparació jurídica de les víctimes del franquisme / Parlament de Catalunya · Llei 11/2017, del 4 de juliol**… http://dogc.gencat.cat/ca/pdogc_canals_interns/pdogc_resultats_fitxa/?action=fitxa&documentId=791945

Una iniciativa de la **Mesa de Catalunya d'Entitats Memorialistes**, per tal de confeccionar una gran pancarta (10x1,5m aprox.) a exposar a les concentracions mensuals d'aquesta coordinadora «Veritat, Justícia i Reparació», a la plaça de Sant Jaume de Barcelona… https://mesadecatalunyanoticies.blogspot.com

En paral·lel, es genera un original en PDF (producte de l'algorisme principal), que anirem actualitzant en una adreça fixa, per mantenir al dia les successives reedicions que l'Arxiu Nacional de Catalunya vagi fent d'aquest *#opendataset*.

Expliquem el procés de generació, per ordre d'ús, dels fitxers de codi que en formen part:

**20171101_actualitzat_llistat_Llei_11_2017_darrer010218.csv**
 
És el darrer *dataset* actualitzat aquest febrer, on ja hi hem corregit un seguit de petits errors que contradiuen la sintaxi del CSV (retorns de carro, dobles cometes i punts i comes, sobrers, fora de lloc, etc). En teniu detall a la capçalera del fitxer de codi que ve tot seguit. L'adreça a l'origen de l'arxiu original és aquí… http://anc.gencat.cat/ca/detall/noticia/La-llista-de-reparacio-juridica-de-victimes-del-franquisme-en-dades-obertes

**llegeixCSVopenData_escriuArrays.ps**

Llegeix les dades del CSV, segons l'estructura de camps descrita per l'emissor, i en genera tres (3) fitxers a disc, en TXT —codificats en WinAnsi—, categoritzats en persones físiques (dones i homes) i en persones jurídiques. Abans però, haurem purgat manualment els errors descrits al fitxer original en CSV.

Es respecta l'ordre alfabètic original de les víctimes i se'n purguen les repeticions (persones amb sumaríssims diversos), fent constar només el nom complet, un gatell d'execució i el seu codi, segons l'ANC, dins un únic paquet d'*arrays*. Vegeu personesJuridiquesRepresaliades_010218.txt, donesRepresaliades_010218.txt i homesRepresaliats_010218.txt

El *prompt* d'execució, documenta la feina feta i si es donen possibles errors.

Necessita executar-se amb un algorismes més, de suport, dins el mateix directori:

> **espiapaq_fura4_.ps**
> Reescriu una *array* per a tota mena d'objectes inclosos i recursivitats.

**personesJuridiquesRepresaliades_010218.txt**

Paquet `[ … ]` d'*arrays* (escrit per llegeixCSVopenData_escriuArrays.ps) seguint el mateix ordre alfabètic original, amb la sintaxi `[ (nom, nom) true/false (#Codi) ]`

**donesRepresaliades_010218.txt**
 
Paquet `[ … ]` d'*arrays* (escrit per llegeixCSVopenData_escriuArrays.ps) seguint el mateix ordre alfabètic original, amb la sintaxi `[ (cognoms, nom) true/false (#Codi) ]`

**homesRepresaliats_010218.txt**

Paquet `[ … ]` d'*arrays* (escrit per llegeixCSVopenData_escriuArrays.ps) seguint el mateix ordre alfabètic original, amb la sintaxi `[ (cognoms, nom) true/false (#Codi) ]`

**componStJaume.ps**

Llegeix les dades endreçades en *arrays* que hem generat prèviament en TXT, via llegeixCSVopenData_escriuArrays.ps, provinents del CSV de la Llista de Reparació Jurídica de Víctimes del Franquisme (1938-1978), publicades per l'Arxiu Nacional de Catalunya.

Compon dinàmicament, en columnes i per categories, amb caplletres alfabètiques i ressaltant-ne les execucions sumaríssimes, amb valors totals i unes capçaleres fixes, per a confeccionar una gran pancarta. Pensat per a ser reproduïda en quadricromia al doble del seu format actual… 10x1,5m aprox. …doncs es superen els màxim permesos, en un fitxer PDF, implementats al format.

El *prompt* d'execució, documenta la feina feta i si es donen possibles errors.

Treballa amb tipografies *MultipleMaster* (Myriad MM Italic) i *OpenType* (Myriad Pro Bold), però no s'inclouen en aquest repositori pel fet de ser propietàries. Els formats admesos són: TrueType, PFB, OTF1 i MM.

Necessita executar-se amb dos algorismes més, dins el mateix directori, que us descriurem tot seguit:

> **aplanatCaixaBaixa.ps**
> *Array* aplanadora d'accents, a caixa baixa, per facilitar l'ordre alfabètic de les caplletres.

> **P7upCap.ps**
> Inicialitza el format de pàgina (*MediaBox*), amb les seves àrees normatives de treball (*TrimBox, BleedBox* i també pot activar *ArtBox* i *CropBox*). Genera les creus de tall (*PrinterMarks*) de forma especial com anotacions i, activa o no, la sobreimpressió en CMYK.

Teniu un exemple del resultat final (work in progress) a…
**reparacioJuridicaVictimesFranquisme_pancarta140318.pdf**

NOTA IMPORTANT PER A LA CERCA DE NOMS DINS EL PDF: amb *viewers* tipus *AdobeReader* (almenys en darreres versions a MacOSX), degut segurament a l'alta densitat de text dins d'una sola pàgina (més de seixanta-sis mil resgistres), el Find/Search no funciona correctament (localitza noms erronis).


Documentació d'errors, suggeriments i tota mena de col·laboracions, seran benvingudes!
