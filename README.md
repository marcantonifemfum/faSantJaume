# faSantJaume
Algorismes componedors, escrits en llenguatge PostScript, del llistat de reparació jurídica de les víctimes del franquisme / Parlament de Catalunya · LLEI 11/2017, del 4 de juliol.

Una iniciativa de la **Mesa de Catalunya d'Entitats Memorialistes**, per tal de confeccionar una gran pancarta (10x1,5m aprox) a exposar a les concentracions mesuals d'aquesta coordinadora «Veritat, Justícia i Reparació», a la plaça de Sant Jaume de Barcelona… https://mesadecatalunyanoticies.blogspot.com

En paral·lel, es genera un original en PDF (producte de l'algorisme principal), que anirem actualitzant en una adreça fixa, per mantenir al dia les successives reedicions que l'Arxiu Nacional de Catalunya vagi fent d'aquest *#opendataset*.

Expliquem el procés de generació, per ordre d'ús, dels fitxers de codi que en formen part:

  **20171101_actualitzat_llistat_Llei_11_2017_darrer010218.csv**
 
És el darrer *dataset* actualitzat aquest febrer, on ja hi hem corregit un seguit de petits errors que contradiuen la sintaxi del CSV (retorns de carro, dobles cometes i punts i comes, sobrers, fora de lloc, etc). En teniu detall a la capçalera del fitxer de codi que ve tot seguit. L'adreça a l'origen de l'arxiu original és aquí… http://anc.gencat.cat/ca/detall/noticia/La-llista-de-reparacio-juridica-de-victimes-del-franquisme-en-dades-obertes

 **llegeixCSVopenData_escriuArrays.ps**

Llegeix les dades del CSV, segons l'estructura de camps descrita per l'emisor, i en genera tres (3) fitxers a disc, en TXT (codificats en WinAnsi), categoritzats en persones físiques (dones i homes) i en persones jurídiques. Abans però, haurem purgat manualment els errors descrits al fitxer opriginal en CSV.

Es respecta l'ordre alfabètic original de les víctimes i se'n purguen les repeticions (persones amb diversos expedients), fent constar només el nom complet, un gatell d'execució i el seu codi, segons l'ANC, dins un únic paquet d'*arrays*. Vegeu personesJuridiquesRepresaliades_010218.txt, donesRepresaliades_010218.txt i homesRepresaliats_010218.txt

