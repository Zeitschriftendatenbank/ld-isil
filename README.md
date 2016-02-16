# Neumodellierung ISIL-Verzeichnis

## Übersicht

* (Tw) Adressdatensatz
    * (035E$a = H | N) Organisation
        * (035E$f = 11) Nationalbibliothek
        * (035E$f = 15) Zentrale Fachbibliothek
        * (035E$f = 21) Regionalbibliothek
        * (035E$f = 33) Öffentliche Bibliothek
        * (035E$f = 34) Mediathek
        * (035E$f = 36) Öffentliche Bibliothek für besondere Benutzergruppen
        * (035E$f = 39) Fahrbibliothek
        * (035E$f = 51) Archiv (staatlich)
        * (035E$f = 52) Archiv (kommunal)
        * (035E$f = 53) Archiv (kirchlich)
        * (035E$f = 54) Archiv (Herrschafts-/Familienarchiv)
        * (035E$f = 55) Archiv (Wirtschaft)
        * (035E$f = 56) Archiv (Parlament, Partei, Stiftung oder Verband)
        * (035E$f = 57) Archiv (Medienarchiv)
        * (035E$f = 58) Archiv (Hochschule, Wissenschaft)
        * (035E$f = 59) Archiv (Sonstiges)
        * (035E$f = 60) Zentrale Universitätsbibliothek
        * (035E$f = 65) Abteilungsbibliothek, Institutsbibliothek, Fachbereichsbibliothek (Universität)
        * (035E$f = 70) Zentrale Hochschulbibliothek, nicht Universität
        * (035E$f = 73) Abteilungsbibliothek, Fachbereichsbibliothek (Hochschule, nicht Universität)
        * (035E$f = 81) Wissenschaftliche Spezialbibliothek
        * (035E$f = 82) Einrichtung der Denkmalpflege
        * (035E$f = 84) Forschungseinrichtung
        * (035E$f = 86) Museum (nicht Museumsbibliothek)
        * (035E$f = 87) Verlag
        * (035E$f = 88) Sonstige Einrichtung
        * (035E$f = 91) Fachstelle für Bibliotheken
        * (035E$f = 94) Regionaler Zentralkatalog / Leihverkehrszentrale
        * (035E$f = 95) Virtuelle Bibliothek / Portal
        * (035E$f = 96) Verbundsystem/ -katalog
        * (035E$f = 98) Serviceeinrichtung
    * (035E$a = P) Produkt oder Service
        * (035E$f = 89) Paket elektronischer Ressourcen
    * (035E$a = I) Informationssatz

    
    
## Namspaces

- org:          http://www.w3.org/ns/org#
- skos:         http://www.w3.org/2004/02/skos/core#
- v:            http://www.w3.org/2006/vcard/ns#
- dct:          http://purl.org/dc/terms/
- dc:           http://purl.org/dc/elements/1.1/
- xsd:          http://www.w3.org/2001/XMLSchema#
- ico:          http://ontology.eil.utoronto.ca/icontact.owl#
- locn:         http://www.w3.org/ns/locn#
- rdfs:         http://www.w3.org/2000/01/rdf-schema#
- rdf:          http://www.w3.org/1999/02/22-rdf-syntax-ns#
- wgs84_pos:    http://www.w3.org/2003/01/geo/wgs84_pos#
- placeaccess:  http://waisvm-cd8e10.ecs.soton.ac.uk/2014/2/ontology/placeaccess.owl#
- dbp:          http://dbpedia.org/property/
- holding:      http://purl.org/ontology/holding#
- bibo:         http://purl.org/ontology/bibo/
- lobid:        http://purl.org/lobid/lv#
- gbv:          http://purl.org/ontology/gbv#
- zdb:          https://w3id.org/zdb/v#
- service:      http://purl.org/ontology/service#
- dso:          http://purl.org/ontology/dso#
- schema:       http://schema.org/
- gr:           http://purl.org/goodrelations/v1#
- dcmitype:     http://purl.org/dc/dcmitype/
- cld:          http://purl.org/cld/terms/
- marcrel:      http://id.loc.gov/vocabulary/relators/

## Organisation

Jede Organisation (wenn 035E$a = H oder N) ist Graph vom Typ org:Organization.

### Identifier

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|008H $a |ZDB-Bibliothekskennung (BIK)|N|zdb:bik|rdfs:Literal^^xsd:string|
|008H $b|Identifikationsnummer der DBS|N|-|-|
|008H $c|Regionales Bibliothekskennzeichen|N|dct:identifier|rdfs:Literal^^xsd:string|
|008H $d|Sigel|N|lobid:sigel|rdfs:Literal^^xsd:string|
|008H $e|ISIL|N|lobid:isil|rdfs:Literal^^xsd:string|
|008H $f|Bibliotheks-ID der EZB|N|-|-|
|008H $g|OCLC Registry ID|N|foaf:page|http://www.worldcat.org/webservices/registry/Institutions/<Registry-ID>|
|008H $h|Weitere ISIL|N|lobid:isil|rdfs:Literal^^xsd:string|
|035E $k|früheres Sigel|N|zdb:formerSigel|rdfs:Literal^^xsd:string|
|035D@ $a|ehem. Sigel der übernommenen Einrichtung|N|zdb:formerSigel|rdfs:Literal^^xsd:string|

### Name

```skos:prefLabel``` für den Organisationnamen wird von der Organization Ontology vorgeschlagen (siehe auch http://patterns.dataincubator.org/book/preferred-label.html).

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|029A $a|Name der Einrichtung|N|skos:prefLabel|rdfs:Literal@de|

Abhängig vom Inhalt von 029@ $4 werden weitere Namensformen mit unterschiedlichen Properties ausgeueichnet:

    029@ $4 = a oder b

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|029@ $a|weiterer Name / offizielle oder weitere Abkürzung des Namens|N|skos:altLabel|rdfs:Literal@de|

    029@ $4 = c 

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|029@ $a|normierte Kurzbezeichnung für die ZDB|N|dbp:shortName|rdfs:Literal@de|

    029@ $4 = d 

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|029@ $a|Englische Anzeigeform des Namens|N|skos:prefLabel|rdfs:Literal@en|

### Ort

*Ort wird nur angezeigt, wenn 032P $p != n*

Jeder Ort ist ein Graph von Typ org:Site, der mit folgender Property verknüpft ist:

    org:hasPrimarySite wenn 032P $2 = S
    org:hasSite wenn 032P $2 = P
    org:hasSite wenn 032P $2 = R
    org:hasSite wenn 032P $2 = W

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|032P $k|$k|Geografische Länge|N|wgs84_pos:longitude|rdfs:Literal^^xsd:string|
|032P $l|Geografische Breite|wgs84_pos:latitude|rdfs:Literal^^xsd:string|
|032P $d|Ländercode (ISO 3166)|N|ico:hasCountry|http://ontologi.es/place/<Ländercode>|
|032P $o|$o|Informationen für Menschen mit Behinderungen|N|placeaccess:isWheelchairAccessible|rdfs:Literal@de|
|032P $z|$z|Bemerkungen zur Anschrift allgemein|N||v:comment|rdfs:Literal@de|

#### Subgraph Adresse

Adresse des Ortes ist ein Graph vom Typ ```v:Address```, der mit folgender Property ausgezeichnet wird:

    v:hasAddress

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|032P $a|Straße und Hausnummer|N|v:street-address|rdfs:Literal^^xsd:string|
|032P $b|Ort|N|v:locality|rdfs:Literal^^xsd:string|
|032P $e|Postleitzahl|N|v:postal-code|rdfs:Literal^^xsd:string|
|032P $f|Bundesland/Provinz|N|v:region|rdfs:Literal^^xsd:string|
|032P $g|Postfach|N|locn:poBox|rdfs:Literal^^xsd:string|
|032P $h|Gebäude, Gebäudeteil, Zustellanweisung|N|v:note|rdfs:Literal^^xsd:string|
|032P $2|Code Adresse|N|v:role|rdfs:Literal@de|
|032P $3|Bezeichnung Adresse|N|skos:prefLabel|rdfs:Literal@de|

Für 032P $2 sollen die Codes als Klartext dargestellt werden:

|032P $2|rdfs:Literal@de|
|---|---|
|S|Sitz-/Besuchsadresse/Hauptanschrift|
|P|Postanschrift|
|R|Rechnunganschrift|
|W|weitere Anschrift|

#### Subgraph Öffnungszeiten

Öffnungszeiten des Ortes ist ein Graph vom Typ ```ico:HoursOfOperation```, der mit folgender Property ausgezeichnet wird

    ico:hasOperatingHours

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|032P $i|Öffnungszeiten (allgemein)|N|rdf:value|rdfs:Literal@de|
|032P $j|Öffnungszeiten (Anmerkungen)|N|v:note|rdfs:Literal@de|

### Telefon

*Telefon wird nur angezeigt, wenn 035B $c != n*

Telfon ist ein Graph, der mit folgender Property ausgewertet wird:

    v:hasTelephone

und folgenden Typ hat, der explizit ausgezeichnet werden muss:

    rdf:type v:Voice

Die Telefonnummer wird ohne Formatierung aber mit einem vorangestellten "tel:+" aus mehreren Unterfelden erzeugt:

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035B $d + $e + $f|Telefonnummer|N|v:hasValue|IRI|
|035B $a|Code Kommunikationsbereich|N|v:role|rdfs:Literal@de|
|035B $b|Bezeichnung Kommunikationsbereich|N|skos:prefLabel|rdfs:Literal@de|

### Fax

*Fax wird nur angezeigt, wenn 035B $c != n*

Fax ist ein Graph, der mit folgender Property ausgewertet wird:

    v:hasTelephone

und folgenden Typ hat, der explizit ausgezeichnet werden muss:

    rdf:type v:Fax

Die Faxnummer wird ohne Formatierung aber mit einem vorangestellten "tel:+" aus mehreren Unterfelden erzeugt:

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035B $g + $h + $i|Telefaxnummer|N|v:hasValue|IRI|
|035B $a|Code Kommunikationsbereich|N|v:role|rdfs:Literal@de|
|035B $b|Bezeichnung Kommunikationsbereich|N|skos:prefLabel|rdfs:Literal@de|

### Email

*Email wird nur angezeigt, wenn 035B $c != n*

Email ist ein Graph vom Typ v:Email, der mit folgender Property ausgewertet wird:

    v:hasTelephone

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035B $k|E-Mail-Adresse|N|v:hasValue|IRI|
|035B $a|Code Kommunikationsbereich|N|v:role|rdfs:Literal@de|
|035B $b|Bezeichnung Kommunikationsbereich|N|skos:prefLabel|rdfs:Literal@de|

### Sammelschwerpunkte

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035G $a|Schlagwörter der Sammelschwerpunkte|W|dc:subject|rdfs:Literal@de|

### SSG

Jedes genannte Sondersammelgebiet ist ein Graph, der mit folgender Property auszeichnet wird

    holding:collects

und folgenden Typ hat, der explizit ausgezeichnet werden muss:

    bibo:Collection 

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035H $a|Betreute Sondersammelgebiete der DFG|W|dc:subject|rdfs:Literal@de|

### ILN

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035E $c|ZDB-Melderkennung (ILN)|N|gbv:iln|rdfs:Literal^^xsd:nonNegativeInteger|

TODO: ILN als Klasse mit Rollen/Skopes

### Typ der Einrichtung

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035E $f|Typ der Einrichtung|N|lobid:libtype|http://purl.org/lobid/libtype#n<035E $f>|

Alternative:

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035E $f|Typ der Einrichtung|N|org:classification|http://purl.org/lobid/libtype#n<035E $f>|


### Unterhaltsträger

Der Unterhaltsträger wird als URI aus dem Feld 035E $g mit dem Prefix http://purl.org/lobid/fundertype#n gebildet.

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035E $g|Unterhaltsträger|N|lobid:fundertype|http://purl.org/lobid/fundertype#n<035E $g>|

### Bestandsgrößenklasse

Die Bestandsgrößenklasse wird als URI aus dem Feld 035E $h mit dem Prefix http://purl.org/lobid/stocksize#n gebildet.

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035E $h|Bestandsgrößenklasse|N|lobid:stocksize|http://purl.org/lobid/stocksize#n<035E $h>|

### Fernleihe

Fernleihe ist ein Graph. Abhängig vom Inhalt von 035I $e wird er mit folgender Property ausgezeichnet:

    035I $e = n -> service:excludes
    035I $e = a, e, k, l -> service:provides

und folgenden Typ hat:

    dso:Interloan

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035I $a|Leihverkehrsregion|N|dct:spatial|https://w3id.org/zdb/v#<035I $a>|
|035J $a|Allgemeine Anmerkungen zur Fernleihe (öffentlich)|N|dct:description|rdfs:Literal@de|

#### Fernleihindikator

Der Fernleihindikator wird aus den folgendermaßen gebildet:

    035I $e + $g + $f

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035I $e / $f / $g|Fernleihindikator|N|zdb:illcode|https://w3id.org/zdb/illcode#<035I $e + $g + $f>|

### Zuständiges Verbundsystem

Folgende Mappingtabelle liegt zugrunde:

|035I $c|Objekt-URI|
|---|---|
|GBV|http://viaf.org/viaf/262029867|
|HBZ|http://viaf.org/viaf/233744054|
|HeBIS|http://viaf.org/viaf/132237927|
|SWB|http://viaf.org/viaf/127281670|
|BVB|http://viaf.org/viaf/151796786|
|KOBV|http://viaf.org/viaf/155764903|
|ÖBV|http://viaf.org/viaf/171259670|
|ZDB|http://viaf.org/viaf/213141461|

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035I $c|Zuständiges Verbundsystem|N|org:memberOf|VIAF-URI siehe Tabelle|

### Dokumentenliefersystem

Wird nur angezeigt, wenn 035K $a = S

Dokumentenliefersystem ist ein Graph, der mit folgender Property ausgezeichnet wird:

    service:provides

und folgenden Typ hat:

    dso:DocumentService

|Pica+|Inhalt|Property|Object|
|---|---|---|---|
|035K $a|Dokumentenliefersystem|skos:prefLabel|"Subito"^^xsd:string|

### Kontakt-E-Mails für die Fernleihe

*Kontakt-E-Mails für die Fernleihe wird nur angezeigt, wenn 035L $a einen Wert enthält*.

Email ist ein Graph vom Typ v:Email, der mit folgender Property ausgewertet wird:

    v:hasTelephone

Mapping Tabelle für Code für Inhalt:

|035L $a|rdfs:Literal@de|
|---|---|
|a|Verlängerungen|
|b|Vormerkungen|
|c|Internationaler Leihverkehr (IFLA Voucher)|
|d|Mahnfrist|
|e|passive Fernleihe|
|f|aktive Fernleihe|

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035L $d|Kontakt-E-Mail|N|v:hasValue|IRI|
|035L $a|Code für Inhalt|N|v:role|rdfs:Literal@de (siehe Tabelle)|

### Endnutzer Service-URLs

Abhängig vom Inhalt von 009Q $z wird eine Endnutzer Service-URL durch folgende Properties ausgezeichnet:

    009Q $z = A -> foaf:homepage

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|009Q $u|URL|N|foaf:homepage|IRI|

    009Q $z = B, C, D oder W -> service:provides

in diesem Fall ist Endnutzer Service-URL ist ein Graph. Der Typ dieses Graphs ist abhängig vom Inhalt von 009Q $z:

|009Q $z|Bedeutung|Typ|
|---|---|---|
|B|OPAC/Katalog|http://purl.org/cld/cdtype/CatalogueOrIndex|
|C|Fernleihe|http://purl.org/ontology/dso#Interloan|
|D|Kontaktformular|http://purl.org/openorg/contactForm|
|E|Wifi-Zugang|http://linkedgeodata.org/page/ontology/Wifi|
|W|Service in Unterfeld $x definiert|http://purl.org/ontology/service#Service|

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|009Q $u|URL|N|dct:identifier|IRI|
|009Q $x|Art der URL|N|dct:description|rdfs:Literal@de|

### Allgemeine Bemerkungen zum gesamten Eintrag

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|047A $a|Allgemeine Bemerkungen zum gesamten Eintrag|J|dct:description|rdfs:Literal@de|

### TODO

Dieses Unterfeld kann zu jeder Komminikationsverbindung existieren und sich entwerder auf jede, auf eine einzelne oder eine zusätzliche Kommnunikationsart beziehen.

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035B $l|Bemerkungen zu den Kommunikationsverbindungen|N|-|-|

---

|035I $b|$b|Leihverkehrsart|N

---

|035I $d|$d|Weitere(s) Verbundsystem(e)|N

---

|035E $j|ILN anderer Systeme|W|-|-|

---

|Neu: 035E $l|$l|Lizenzinformation Bestandsdaten ZDB|N

---

|035K $b|$b|Teilnahme am Altbestandszertifikat|N
|035K $c|$c|Altbestandsgrenze|N
|035K $d|$d|URL Altbestandausstattung|N
|035K $e|$e|Art das Lokalsystems (Protokoll FL-System)|N
|035K $f|$f|Automatisierte FL (Online FL regional)|N
|035K $g|$g|Bestandslücken Verbunddatenbank|N
|035K $h|$h|Materielcodes|N

---

## Produkt

Jedes Produkt (wenn 035E$a = P) ist sowohl vom Typ: gr:ProductOrService als auch vom Typ dcmitype:Dataset

### Identifier
### Name
### Ort
### Telefon
### Email
### Sammelschwerpunkte
### Endnutzer Service-URLs
### Allgemeine Bemerkungen zum gesamten Eintrag

siehe Organisation

### Art des Pakets

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035P $a|Art des Pakets|N|cld:itemFormat|rdfs:Literal@de|

### Enthaltene Titel

Enthaltene Titel ist ein Graph, der mit folgender Property ausgezeichnet wird:

    dct:extend

und von Typ 

    dct:SizeOrDuration

ist.

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035P $e|Enthaltene Titel (Anbieter)|N|rdf:value|rdfs:Literal^^xsd:nonNegativeInteger|

### Anbieter

Anbieter ist ein Graph, der mit folgender Property ausgezeichnet wird:

    dcterms:publisher

und vom Typ

    dcterms:Agent

ist.

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035P $g|$g|Anbieter|N|skos:prefLabel|rdfs:Literal^^xsd:string|

### Verhandlungsrunde

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035P $c|Verhandlungsrunde|N|dct:issued|xsd:gYear|

### URL im CMS "Datenbankinfo"

|Pica+|Inhalt|wdh.|Property|Object|
|---|---|---|---|---|
|035P $h|URL im CMS "Datenbankinfo"|N|foaf:page|IRI|

|035P $i|$i|Finanzierungsmodell|N

|009Q $u|$u|URL|N
|009Q $x|$x|Art der URL / Text|N
|009Q $z|$z|Art der URL / Code|N

