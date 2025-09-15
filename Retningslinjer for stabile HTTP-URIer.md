# Retningslinjer for stabile HTTP-URIer

## 1\. Formål

Det http-baserede internet, også blot kaldet web’et, er i dag en de facto platform for interoperabilitet mellem it-systemer og vil fremover i stigende grad være den platform, det offentliges data og dokumenter vil blive udstillet og udvekslet ved hjælp af.

Web’et er i sin natur et decentraliseret netværk af data og dokumenter, der er entydigt identificeret ved hjælp af HTTP-URIer.

INFO

URI = ’Uniform Resource Identifier’.

En URI er en entydig identifikator der bruges til, på en ensartet måde, at identificerer digitale (virtuelle) eller fysiske ressourcer (objekter).

En URI kan fungere enten som et entydigt og unikt navn eller som en entydig og unik adresse. Når URIer bruges som navne kaldes de for Uniform Resource Name (URN) og når de bruges som adresse kaldes for Uniform Resource Locator (URL). En URI kan have funktion som et navn og en adresse samtidigt eller som enten et navn eller en adresse.

Specifikationen RFC 3986 [\[1\]](#Fodnote 1) definerer syntaksen for URIer. URIer defineres med en tilknyttet protokol, eksempelvis HTTP (HyperText Transfer Protocol).

En URI baseret på HTTP-protokollen kaldes en HTTP-URI. Disse URIer er nok bedst kendt som de adresser (URLer) der bruges i browsere til navigering på internettet.

Web’et er også en platform, hvor ændringer af identifikatorer (HTTP-URIer) i et it-system vil kunne påvirke andre it-systemer negativt.

En URI, og dermed også en HTTP-URI, kan fungere både som en unik og entydig identifikator i sig selv og den kan fungere som en adresse til en ressource. Den mest udbredte anvendelse er at lade en HTTP-URI samtidigt være både entydig identifikator og entydig adresse til den ressourcen den identificerer. Dette er eksempelvis tilfældet når HTTP-URIer anvendes til definition af datamodeller beskrevet ved hjælp af ’Resource Description Framework’ (RDF) [\[2\]](#Fodnote 2).

Hvis potentialet og værdien af web’et skal udnyttes, er der derfor behov for at sikre, at HTTP-URIerne holdes stabile og vedvarende, så de, når de anvendes til opslag, altid peger på samme ressource.

De efterfølgende retningslinjer for udformning og anvendelse af stabile HTTP-URIer er skabt med henblik på digitaliseringsinitiativer, hvor permanent, uforanderlig identifikation af digitale ressourcer ønskes i et fællesoffentligt regi.

Retningslinjerne er blevet til på baggrund af tilsvarende arbejde i regi af EU og W3C.

ISAs rapport _”D7.1.3 - Study on persistent URIs, with identification of best practices and recommendations on the topic for the MSs and the EC”_ [\[3\]](#Fodnote 3), har været det primære grundlag og fra W3Cs specifikation _”Data on the Web Best Practices”_ [\[4\]](#Fodnote 4) er der hentet yderligere råd. Under udarbejdelsen er der desuden blevet set på følgende internationale specifikationer:

RFC 3986, Uniform Resource Identifier (URI): Generic Syntax

Internet Engineering Task Force, januar 2005

Tilgængelig på: `https://www.rfc-editor.org/info/rfc3986`

Spatial Data on the Web Best Practices

W3C Working Group Note & OGC Best Practice, 28 september 2017

Tilgængelig på: `https://www.w3.org/TR/sdw-bp/`

Cool URIs for the Semantic Web

W3C Interest Group Note. 2008.

Tilgængelig på: `http://www.w3.org/TR/cooluris/`

Linked identifier schemes: Best practice guide, Version 0.3

Geospatial Commision,. oktober 2019.

Tilgængelig på: `https://www.gov.uk/government/publications/linked-identifier-schemes-best-practice-guide`

Som et resultat af erfaringsindsamlingen til ISAs rapport definerede rapportens forfattere ti regler, _“10 rules for persistent URIs”_, hvis formål er at formidle ’best practice’ for design og publicering af stabile URIer. De ti regler er opdelt i fem punkter, der tilrådes, og fem punkter, der frarådes:

ISAs 10 regler er i dansk regi blevet til 10 retningslinjer.

| ISA-regel                                      | Dansk retningslinje                                                      |
| ---------------------------------------------- | ------------------------------------------------------------------------ |
| Follow the pattern                             | URIer bør overholde det fastlagte mønster                                |
| Re-use existing identifiers                    | Eksisterende identifikatorer bør i videst muligt omfang genbruges.       |
| Link to multiple representations               | Link mellem repræsentationer af en ressource med flere repræsentationer. |
| Implement 303 redirects for real-world objects | Anvend 303-omdirigering for fysiske objekter                             |
| Use dedicated service                          | Dedikerede services bør bruges                                           |
| Avoid stating ownership                        | URIer bør ikke udtrykke ejerskab                                         |
| Avoid version numbers                          | URIer bør ikke versioneres                                               |
| Avoid using auto-increment                     | URIers referencedel bør ikke have fortløbende automatisk opdatering      |
| Avoid query strings                            | URIer bør ikke indeholde søgestrenge                                     |
| Avoid file extensions                          | En URI bør ikke afsluttes med filendelse                                 |

INFO

I dette dokument følges følgende konventioner:

* ’skal’ indikerer, at noget er påkrævet
* ’må ikke’ indikerer, at noget ikke er tilladt
* ’må kun’ eller ’må kun... hvis’ indikerer, at noget er tilladt i tilfælde af en fremsat betingelse
* ’må (godt)’ eller ’kan (godt)’ indikerer, at noget er tilladt
* ’behøver ikke at’ eller ’behøves ikke’ indikerer, at noget ikke er påkrævet
* ’bør’ indikerer, at noget er anbefalet men ikke påkrævet

Da formålet er at hjælpe og lette arbejdet med at sikre varige identifikatorer til de behov offentlige organisationer møder, er der søgt skabt et stabilt grundlag uden unødvendigt restriktive regler. Der er derfor ikke tale om rigide regler, men om retningslinjer, der skal give mere fleksibilitet og mindst muligt administrativt arbejde. Alle 10 regler er derfor videreført som retningslinjer.

Retningslinjerne søger at sikre, at de URIer, der defineres til brug i fællesoffentligt regi får den nødvendige stabilitet.

Retningslinjernes fokus er på data, datasæt, webAPIer, datamodeller og modelelementer, mens de ikke anses for nødvendige for adresser for websider i almindelighed.

Retningslinjernes fokus er altså på data i et maskinlæsbart format, forstået som et format, der er struktureret, så software let kan identificere, genkende og udtrække givne oplysninger.

OBS

Retningslinjerne stiller ikke krav til at en myndighed ændrer praksis på de områder hvor myndigheden er forpligtet til at anvende andre internetrettede identifikatorer defineret af internationale standardorganisationer. Eksempelvis på områder hvor anvendelse af OID eller HL7 FHIR er påkrævet.

## 2\. Retningslinjerne

Det er måske værd indledningsvis at understrege nogle nøglepunkter om URI'er i den nuværende sammenhæng.

1. URI'er er 'dumme strenge', dvs. de bærer ingen semantik. Deres funktion er udelukkende at identificere en ressource.
2. Selvom det foregående punkt er korrekt, ville det være ikke-intuitivt hvis en URI som `https://example.com/dataset` returnerer andet end netop et datasæt. Menneskelig læsbarhed er nyttigt.
3. Når en URI anvendes til opslag, kan en enkelt URI principielt tilbyde den samme ressource i mere end et format. `https://example.com/dataset` kan tilbyde de samme data i f.eks. CSV, JSON og XML. Serveren returnerer det mest passende format baseret på indholdsforhandling eller på hvad der er forespurgt at det anvendende program.
4. En URI kan omdirigere til en anden. Dette bruges blandt andet for at kunne tilbyde stabile, permanente links til brugere, samtidigt med at man bevarer en fleksibilitet i et bagvedliggende serverlandskab. Eksempelvis kan URIen `https://example.com/dataset` være en URI brugeren anvender, mens indholdet i praksis hentes fra adressen `https://min.server.dk/minedata/`.

De nævnte funktionaliteter kan kombineres eller anvendes enkeltvis.

### 2.1 URIer bør overholde det fastlagte URI-mønster

§

URIer bør overholde det fastlagte mønster

_Opfylder ISA-regel:_ Follow the pattern

Retningslinjen har til hensigt både at skabe basis for definition af stabile URIer og for at give en hjælp til opbygning af de tekststrenge der udgør URIerne, på en måde der sikrer en vis grad af genkendelighed og ensartethed.

ISAs regel ”Follow the pattern” handler om opbygning af URIer. ISAs forslag er, at URIer skal have følgende mønster:

`http://{domain}/{type}/{concept}/{reference}`

I nærværende retningslinjer er dette blevet til følgende mønster:

`https://data.gov.dk/{type}/{emne}/{reference}/`

#### Domændelen

Det første der bemærkes er at domænedelen i retningslinjerne er gjort til et specifikt domæne, `https://data.gov.dk/`, hvor HTTPS-protokollen anvendes frem for den i ISA anvendte HTTP-protokol.

En HTTP-URI identificerer entydigt en ressource. En HTTP-URI kan også fungere som en adresse, der kan åbnes for at hente yderligere information om ressourcen.

HTTPS-URIer har samme mulighed og giver samme fordele, men når URIen bruges til opslag krypteres kommunikationen, og dermed forøges sikkerheden.

Derfor anvendes HTTPS-URIer.

Selve domænedelen, `data.gov.dk`, er et domæne der kan forventes at være stabilt. Det vil sige det kan forventes at domænet vil eksistere og være under staten Danmarks rådighed så langt frem i tiden som der vil være behov for domænet. Domænet `gov.dk` er dags dato registreret under Statens IT der har givet Digitaliseringsstyrelsen lov til at anvende underdomænet ’`data`.’. Det betyder at Digitaliseringsstyrelsen kan gøre brug af domænet `[https://data.gov.dk](https://data.gov.dk)`. Denne brug kan på ethvert tidspunkt flyttes til anden myndighed hvis det ønskes.

Alle URIer, der følger retningslinjerne, forventes derfor at starte med tekststrengen `https://data.gov.dk/`.

Det er muligt at oprette andre domæner under gov.dk-domænet lige som det er muligt at oprette yderligere underdomæner under domænet data.gov.dk-domænet. I begge tilfælde vil det være muligt at opnå en tilsvarende stabilitet som den der søges opnået ved at benytte `https://data.gov.dk`. Nærværende retningslinjer fokuserer udelukkende på HTTP-URIer der er baseret på `https://data.gov.dk`. Oprettes et underdomæne skal det sikres at underdomænedelens betegnelse er neutral i forhold organisationsnavne således at underdomænet stadigt vil være meningsgivende ved ressortomlægning eller reorganisering.

På tidspunktet for retningslinjernes offentliggørelse er to underdomæneudvidelser taget i brug. Det drejer sig om `https://geo.data.gov.dk/` og `https://envi.data.gov.dk/` der anvendes af henholdsvis ’Styrelsen for Dataforsyning og Effektivisering’ (SDFE) og ’Miljøstyrelsen’ (MST).

Den organisation, som er ansvarlig for et sådant underdomæne, opfordres til også at lade retningslinjerne gælde for disse i videst muligt omfang.

Bemærk at retningslinjen ikke er ensbetydende med, at alle ressourcer, alle data, skal have en konkret ’fysisk’ placering under domænet. Det er muligt at lade ressourcer være placeret under andre, oftest allerede etablerede, domæner, hvortil der kan omstilles ved hjælp af en 303-omdirigering [\[5\]](#Fodnote 5) (’URL redirection’). De domæner der omstilles til skal dog – for at bevare den sikkerhed der signaleres med brugen af HTTPS-protokollen – også anvende HTTPS-protokollen.

OBS

Ved 303-omdirigering skal der omdirigeres til en URL der anvender HTTPS-protokollen hvis den oprindelige URL anvender HTTPS-protokollen.

#### Brug af {type} og {emne}

Der er intet der i princippet forhindrer at URIer opbygges alene med domænedelen `https://data.gov.dk/` tilføjet en unik tekststreng. Et eksempel kunne være:

`https://data.gov.dk/46448b04-42ba-4e0e-8939-5e2d775f513b`

I vid udstrækning vil brugen af URIer være overladt til maskiner, til software. Et softwareprogram vil ikke have problemer med konstruktionen af ovenstående URI, men det vil de fleste mennesker have.

Det  kan være praktisk, dels at denne type URIer har en form, der gør dem lettere at se hensigten med, dels gør dem lettere at huske. Den ovenstående URI ville både være svær at huske og vil heller ikke ville give nogen form for information om den ressource, den identificerer. Hvis URIens tekststreng derimod ser ud som denne:

`https://data.gov.dk/**dataset/ener**/46448b04-42ba-4e0e-8939-5e2d775f513b`

vil et menneske kunne nogenlunde stole på at URIen identificerer et datasæt med energirelaterede informationer.

I ovenstående eksempel udgør ’dataset/’ type-delen af URIen, ’ener/’ udgør emne-delen af URIen og ’46448b04-42ba-4e0e-8939-5e2d775f513b’ er URIens referencedel. Type- og emne-dele behandles her. Referencedelen efterfølgende.

For at skabe en grad af genkendelighed i URIer udformet efter retningslinjerne, er der fastlagt et antal termer til anvendelse i henholdsvis type-delen og i emne-delen af en URI. Termerne er skabt i relation til arbejdet med retningslinjernes udformning og skal ikke betragtes som et endeligt og begrænset sæt. De vil kunne udvides efter behov.

Type-delen har som udgangspunkt disse termer der bruges til beskrive den overordnede, genelle type af ressourcen.

| URI-mønster                                                    | {type}        | Forklaring                                                                                                                                                                                                                     |
| -------------------------------------------------------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [https://data.gov.dk/](https://data.gov.dk/)**id**/...         | ’id’          | ’id’ angiver, at URIen er en identifikator for et fysisk objekt. Objektet selv kan med andre ord ikke tilgås direkte via internettet.                                                                                          |
| [https://data.gov.dk/](https://data.gov.dk/)**eid**/...        | ’eid’         | {eid} angiver at URIen er en identifikator for et konkret objekt anvendt i sammenhæng med digitale signaturer og elektronisk identifikaion (eID).                                                                              |
| [https://data.gov.dk/](https://data.gov.dk/)**dataset**/...    | ’dataset’     | {dataset} bruges, når URIen skal anvendes til identifikation af en samling af data, udgivet eller udvalgt og arrangeret af en enkelt kilde og som er til rådighed for adgang eller download i en eller flere repræsentationer. |
| [https://data.gov.dk/](https://data.gov.dk/)**api**/...        | ’api’         | {api} bruges når URIen anvendes til at identificere et http-baseret api (eller webservice).                                                                                                                                    |
| [https://data.gov.dk/](https://data.gov.dk/)**model**/...      | ’model’       | {model} bruges, når URIen skal anvendes til identifikation af databeskrivende modeller, eksempelvis kernemodeller, vokabularer, anvendelsesmodeller og –profiler.                                                              |
| [https://data.gov.dk/](https://data.gov.dk/)**concept**/...    | ’concept’     | {concept} bruges, når URIen skal anvendes til identifikation af begrebsmodeller. Eksempelvis et klassifikationssystem, en taksonomi eller anden form for begrebssystem.                                                        |
| [https://data.gov.dk/](https://data.gov.dk/)**catalogue**/     | _’catalogue’_ | {catalogue} bruges, når URIen skal anvendes til identifikation af digitale  kataloger der indeholder information om digitale ressourcer..                                                                                      |
| [https://data.gov.dk/](https://data.gov.dk/document/)**document** | _’document’_  | {document} benyttes til angivlse af at ressourcen er et webdocument, oftest i HTML-form.                                                                                                                                       |

Emnedelen kan benyttes til at indsnævre beskrivelsen af ressourcen til et mere specifikt emneområde. Med brug af emne-delen er der med de før listede termer for type-delen, dannet et antal mønstre der anbefales anvendt på URIer hvor nedenstående beskrivelse passer.

##### Kombinationer hvor typen er ’model’

På nuværende tidspunkt er emnedelsordene ’`core`’ og ’`profile`’ taget i anvendelse til at identificere logiske modeller i form af kernemodeller og vokabularer samt anvendelsesmodeller og -profiler.

Kernemodeller og vokabularer er datamodeller der er udformet med henblik på at indgå i - oftest mange – forskellige sammenhæng via anvendelsesmodeller eller anvendelsesprofiler. Kernemodeller og vokabularer er genbrugelige modeller der typisk har et centralt forretningsobjekt i fokus,

Anvendelsesmodeller og –profiler er rettede mod specifikke anvendelsessituationer. De afspejler og afgrænses af behovet for information i en bestemt anvendelsessituation (dvs. i et bestemt system eller dataintegration) og sammensættes af elementer fra kernemodeller og/eller vokabularer.

| URI-mønster                              | {emne}      | Beskrivelse                                                                                                         |
| ---------------------------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------- |
| `https://data.gov.dk/**model/core/**`    | _’core’_    | Bruges til URIer der identificerer en kernemodel eller et vokabular – en model som beskriver et snævert emneområde. |
| `https://data.gov.dk/**model/profile/**` | _’profile’_ | Bruges til URIer der identificerer en anvendelsesmodel eller en anvendelsesprofil.                                  |

##### Kombinationer hvor typen er ’concept’’

Også her kan emnedelsordene ’`core`’ og ’`profile`’ anvendes til begrebs- og klassifikationsmodeller. Emneordsdelen ’`core`’ bruges til modeller der indeholde de enkelte klassifikationselementer eller begreber. Emneorddelen ’`profile`’ bruges når der er tale om en samlet klassifikation eller begrebsmodel.

Hvis klassifikationssystemet FORM skulle identificeres med retningslinjerne ville det anbefalede mønster være: `https://data.gov.dk/concept/profile/` med efterfølgende angivelse af relevant referencedel.

Hvis de forvaltningsopgaver FORM beskriver var samlet i en kerne begrebsmodel ville det anbefalede mønster være `https://data.gov.dk/concept/core/`.

| URI-mønster                                | {emne}      | Beskrivelse                                                                                                                                                   |
| ------------------------------------------ | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `https://data.gov.dk/**concept/core/**`    | _’core’_    | Bruges til URIer der identificerer, en kerne begrebsmodel der beskriver de enkelte begreber der kan indgå i enten en anvendelsesmodel eller et begrebssystem. |
| `https://data.gov.dk/**concept/profile/**` | _’profile’_ | Bruges til URIer der identificerer et anvendelsesorienteret klassifikations- eller begrebssystem oftest sammensat af elementer fra en kerne begrebsmodel.     |

##### Kombinationer hvor typen er ’dataset’’

Til URIen hvor typen er ’`dataset`’, det vil sige til identifikation af datasæt, anbefales det at emnedelen give en overordnet beskrivelse af datasættet. På nuværende tidspunkt er emneordet ’`lang`’ taget i brug til datasæt der indeholder sprogrelaterede informationer.

Det anbefales at overveje brug af EUs klassifikation for temaer til datasæt, listet i kapitel ’4 EUs dataportals temaer for datasæt’.

| URI-mønster                             | {emne}   | Beskrivelse                                                                                                                      |
| --------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `https://data.gov.dk/**dataset/lang/**` | _’lang’_ | Bruges til URIer der identificerer et sæt eller en samling af data hvor emnet – i bred forstand – er sprog eller sprogteknologi. |

##### Kombinationer hvor typen er ’id’

Typen ’`id`’ anvendes til identifikation af konkrete fysiske objekter. På nuværende tidspunkt er der fastlagt et antal emnedele der vurderes at ville være de oftest anvendte.

| URI-mønster                                | {emne}           | Beskrivelse                                                                                      |
| ------------------------------------------ | ---------------- | ------------------------------------------------------------------------------------------------ |
| `https://data.gov.dk/**id/thing/**`        | _’thing’_        | Angiver at URIen er en identifikator for et fysisk objekt uden indikation af objektets karakter. |
| `https://data.gov.dk/**id/person/**`       | _’person’_       | Angiver at URIen er en identifikator for en person.                                              |
| `https://data.gov.dk/**id/place/**`        | _’place’_        | Angiver at URIen er en identifikator for et fysisk sted eller en fysisk lokation,                |
| `https://data.gov.dk/**id/organization/**` | _’organization’_ | Angiver at URIen er en identifikator for en organisation i bred forstand.                        |
| `https://data.gov.dk/**id/doc/**`          | _’doc’_          | Angiver at URIen er en identifikator for et dokument.                                            |
| `https://data.gov.dk/**id/event/**`        | _’event’_        | Angiver at URIen er en identifikator for en hændelse eller en begivenhed..                       |

##### Kombinationer hvor typen er ’catalogue’

Der er på nuværende tidspunkt fastlagt og ibrugtaget tre emnedele til brug i kombination med typen ’`catalogue`’.

| URI-mønster                                         | {emne}             | Beskrivelse                                                                  |
| --------------------------------------------------- | ------------------ | ---------------------------------------------------------------------------- |
| `https://data.gov.dk/**catalogue/models**/`         | _’models’_         | Bruges til URIer der identificerer et digitalt katalog over datamodeller.    |
| `https://data.gov.dk/**catalogue/datasets**/`       | _’datasets’_       | Bruges til URIer der identificerer et digitalt katalog over datasæt.         |
| `https://data.gov.dk/**catalogue/lang-resources/**` | _’lang-resources’_ | Bruges til URIer der identificerer et digitalt katalog over sprogressourcer. |

Bemærk at ovenstående liste vil kunne udvides, men ikke reduceres efter retningslinjernes offentliggørelse.

Retningslinjerne er forsøgt udformet så fleksibelt at myndigheder kan udforme URIer der passer myndighedens behov.

#### Brug af {reference}

Reference-delen er den sidste del af URIen, den del der angiver et specifikt begreb, en model, en id, et datasæt eller anden form for ressource.

Referencedelen kan bestå af flere led. Eksempelvis:

`https://data.gov.dk/model/core/itsystem/`

`https://data.gov.dk/model/core/itsystem/SystemComponent`

hvor `/itsystem` og `/itsystem/SystemComponent` udgør referencedelen for henholdsvis it-system-vokabularet i sin helhed og for et enkelt element i vokabularet, idette tilfælde klassen SystemComponent. Noter at det anbefales kun at anvende små bogstaver når der indgår bogstaver i URIer. Dog er det en accepteret konvention at lade URIer der identificerer klasser og egenskaber i vokabularer og kernemodeller, anvende CamelCase.

#### Menneskeligt læseligt og brug af danske og engelske termer

Som tidligere nævnt vil det være en fordel for den menneskelige bruger af URIer, hvis de har en udformning der gør dem lette for mennesker at huske og at tolke, men det er ingen betingelse, det er en anbefaling. Det er altså muligt at bruge maskingenererede kombinationer af tal og bogstaver der ikke umiddelbart er hverken forståelige eller nemme at huske for en person. Så længe de myndighed der har ansvaret for URIens dannelse er sikker på at URIen er unik, så længe strider det ikke mod retningslinjerne.

Det anbefales dog som minimum at holde type-delen som umiddelbart forståelig for mennesker og også gerne emne-delen.

Alle dele af URIen, type-, emne- og referencedelen kan udtrykkes i danske ord. Beslutninger om udformning af konkrete URIer styres ikke centralt, men tages af de enkelte myndigheder. Det er op til den enkelte URI-definerende myndighed at beslutte om ordene skal være danske eller engelske. Når det er rimeligt at antage at URIer vil skulle håndteres af ikke-dansktalende, eksempelvis ved projekter hvor data forventes udveksles internationalt, anbefales det at anvende engelske termer. Brugen af et sprog internationalt gør det lettere at dele data og metadata globalt

Bemærk at der med udtrykket ’engelsksprogede’ ikke er taget stilling til, om de anvendte termer skal være britisk-engelsk, amerikansk-engelsk eller anden form for engelsk. Det overlades til den URI-definerende aktør at foretage det valg, der giver den bedste formidling.

### 2.2 Genbrug i videst muligt omfang eksisterende identifikatorer

§

Genbrug i videst muligt omfang eksisterende identifikatorer

_Opfylder ISA-regel:_ Re-use existing identifiers

I de tilfælde hvor der eksisterer en etableret og anvendt unik og entydig identifikator, der ikke allerede har en anvendelig og stabil HTTP-URI-form bør denne gives en HTTP-URI-form efter retningslinjerne.

En URN i form af en UUID (Universal Unique Identifier), der eksempelvis har været anvendt til at identificerer fakturaer kan omdannes fra denne URN:

`urn:uuid:91aa87da-9f06-11e7-abc4-cec278b6b50a`

til følgende HTTP-URI:

`https://data.gov.dk/id/thing/91aa87da-9f06-11e7-abc4-cec278b6b50a/`

Hvor en eksisterende identifikator ikke ønskes anvendt direkte i den nuværende form, kan URI-repræsentationen eksempelvis anvende en hash-værdi af identifikatoren.  Eksempelvis kunne et CPR-nummer som ’2310450637’ gives følgende URI:

`http://data.gov.dk/id/person/5985e9a05ca2d667b8a3f1b53609f16feccea23c1262172ddc192c8f/`

hvor CPR-nummeret er konverteret ved brug af hash-funktionen SHA-3 (Secure Hash Algorithm 3), hvormed entydigheden er bevares samtidigt med at anonymiteten er sikret.

Brug af SHA-3 (og tilsvarende) gør det muligt for et it-system at gentage konverteringen fra, som her et givet CPR-nummer, og altid få samme krypterede kode, der så kan anvendes til forespørgsel i andre systemer. Det er ikke muligt at gå den modsatte vej, det vil sige, der kan ikke konverteres tilbage fra SHA-3-koden til det oprindelige CPR-nummer. Den dannede HTTP-URI kan altså bruges uden frygt for at afsløre selve CPR-nummeret.

### 2.3 Link mellem repræsentationer af en ressource med flere repræsentationer.

§

Link mellem repræsentationer af en ressource med flere repræsentationer.

_Opfylder ISA-regel:_ Link to multiple representations

Stabile URIer anvendes til at identificere både digitale ressourcer og fysiske objekter. En digital ressource er i denne forbindelse noget der kan transmitteres som en strøm af bytes. Et fysisk objekt er et objekt, der i sig selv ikke kan transmittes som en byte-strøm.

Uanset hvilken type af ressource en URI repræsenterer, så vil forskellige brugsscenarier have behov for forskellige formater af den modtagne information. Afhængigt af om brugeren er et menneske, der skal have en visuel fremstilling, eller om brugeren er et maskinafviklet program, skal den returnerede information være i et format der, kan anvendes af brugeren. Hvis vi, som eksempel, har en URI som denne:

`https://data.gov.dk/model/core/foo-bar-model/`

så kan der være behov for, afhængigt af brugeren, at få returneret enten HTML eller et af RDFs serialiseringsformater (eksempelvis JSON-LD) Er brugeren en person der ønsker at få informationen i en browser vil HTML formentligt være at foretrække, mens det for en computer kan være bedre med et format som JSON-LD.

Det er muligt med en og samme URI at tilgå flere repræsentationformer af et indhold ved hjælp af http-protokollens ’content navigation’[\[6\]](#Fodnote 6) (indholdsnavigation).

For begge de (i dette tilfælde) to mulige repræsentationer gælder det, at de skal have deres egen adresse i form af en URL. Den enkleste måde at opnå det på vil være at benytte den originale URI og tilføje henholdsvis `.html` og `.jsonld`

De to URLer bliver altså henholdsvis

`https://data.gov.dk/model/core/foo-bar-model.html`

og

`https://data.gov.dk/model/core/foo-bar-model.jsonld`

En repræsentation af en ressource bør have reference til alle de øvrige repræsentationer af samme ressource.

Afhængigt at de enkelte repræsentationer vælges den korrekte metode til at angive et link til den eller de øvrige repræsentationer af ressourcen.

I vores eksempel vil der i HTML-dokumentet kunne indsættes et tag som dette:

<link rel="self" type="text/html" title="Foo Bar Model as HTML" href="https://data.gov.dk/model/core/foo-bar-model.jsonld">

<link rel="alternate" type="application/ ld+json " title="Foo Bar Model as JSON-LD " href=" https://data.gov.dk/model/core/foo-bar-model.jsonld">

mens det I en JSON-LD-repræsentation kunne se ud som følger

    {
    
      "links" : \[ {
    
        "href" : "https://data.gov.dk/model/core/foo-bar-model.jsonld",
    
        "rel" : "self",
    
        "type" : "application/ld+json",
    
        "title" : "Foo Bar Model as JSON-LD"
    
      }, {
    
        "href" : "https://data.gov.dk/model/core/foo-bar-model.html",
    
        "rel" : "alternate",
    
        "type" : "text/html",
    
        "title" : "Foo Bar Model as HTML"
    
      } \],
    
      …
    
    }

### 2.4 Anvend 303-omdirigering for fysiske objekter

§

Anvend 303-omdirigering for fysiske objekter

_Opfylder ISA-regel:_ Implement 303 redirects for real-world objects

Når en URI, der repræsenterer et konkret objekt, et fysisk objekt, skal åbnes, så skal der omdirigeres til et dokument, der beskriver objektet. Omdirigeringen sker med en 303 HTTP- svarkode.

Dette bør gøres på en måde, der er konsistent og overholdende retningslinjerne. Det anbefales, at gøre dette ved at ændre {type}-delen af URIen fra ’id’ til ’document’. Eksempelvis således:

Fra URIen for det konkrete objekt:

`https://data.gov.dk/id/organization/bb16/`

til URIen for dokumentet om objektet:

`https://data.gov.dk/document/organization/bb16/`

### 2.5 Brug dedikerede services

§

Brug dedikerede services

_Opfylder ISA-regel:_ Use dedicated service

Retningslinjerne anbefaler at benytte et mønster, hvor domænet er fastlagt til `https://data.gov.dk/`. Hvis alle de URIer, der bliver dannet efter retningslinjerne, derefter skulle håndteres af en enkelt service, ville der være skabt et ’single point of failure’; fejler den ene service ville alle opslag på URIerne fejle.

Flere distribuerede services bør derfor oprettes til håndtering af URI-opslag.

### 2.6 URIer bør ikke udrykke ejerskab

§

URIer bør ikke udtrykke ejerskab

_Opfylder ISA-regel:_ Avoid stating ownership

Mange eksisterende HTTP-URIer er dannet med et domæne, hvori et foranderligt navn indgår. Ofte er det navnet på eller akronymet for den organisation, der ejer websitet. Ændring af organisationsnavn medfører normalt også, at domænets navn bliver udskiftet. De URIer der er dannet med det gamle domænenavn skal derfor også ændres og er dermed ikke længere stabile.

Derfor bør URIer ikke indeholde dele, der angiver et specifikt ejerforhold.

Ved at bruge retningslinjerne undgås dette.

### 2.7 Undgå at brugere versionsnummererer URIer

§

Undgå at brugere versionsnummererer URIer

_Opfylder ISA-regel:_ Avoid version numbers

Mange ressourcer gennemløber et livsforløb. Dette sker eksempelvis for dokumenter og for modeller som vokabularer og anvendelsesprofiler. For at holde alle URIer persistente bør information om versionsnummer eller livscyklusstatus holdes ude af URIerne.

For ressourcer, der har en livscyklus, eksempelvis en model, kan løsningen være at have en fast URI, der altid omdirigeres til den seneste version af modellen ved brug af dennes URI. Eksempelvis således:

Som fast URI:

`https://data.gov.dk/model/profile/**familystructure/**`

URIer for modeller, der repræsenterer modellen på forskellige tidspunkter, henholdsvis 2/3 2017 og 25/4 2017:

`https://data.gov.dk/model/profile/familystructure-02032017/`

`https://data.gov.dk/model/profile/familystructure-25042017/`

Når den persistente URI `https://data.gov.dk/model/profile/familystructure/`  anvendes, bliver opslaget omdirigeret til den seneste model, altså til `https://data.gov.dk/model/profile/familystructure-25042017/`.

### 2.8 URIers referencedel bør ikke have fortløbende automatisk opdatering i distribuerede miljøer

§

URIers referencedel bør ikke have fortløbende automatisk opdatering i distribuerede miljøer

_Opfylder ISA-regel:_ Avoid using auto-increment

Dannelse af nye URIer for store datasæt kræver automatiserede processer, der skal garantere, at de producerede URIer er unikke.

Brug af fortløbende numre og automatiseret opdatering af disse er en mulighed hvis, og kun hvis, der er absolut sikkerhed for, at samme URI ikke bliver dannet eller vil blive dannet et andet sted eller på et andet tidspunkt.

### 2.9 URIer må ikke indeholde søgestrenge

§

URIer må ikke indeholde søgestrenge

_Opfylder ISA-regel:_  Avoid query strings

Brug af søgestrenge, eksempelvis ’`?para alue`’, giver ikke persistente URIer; URIens ressource kan principielt variere fra søgning til søgning.

### 2.10 En URI må ikke afsluttes med filtypeekstension

§

En URI må ikke afsluttes med filtypeekstenstion

_Opfylder ISA-regel:_ Avoid file extensions

De stabile URIer holdes fri af filtypeangivelser. Data eller dokumenter hvor filtypeekstension ønskes anvendt skal gives URIer, der henvises til som beskrevet under afsnittet ”En ressource kan have mange repræsentationer”.

## 3\. Eksempler på etablerede URIer

Nedenfor vises enkelte eksempler på ressourcers URIer, der er udformet efter retningslinjerne. Alle eksempler er taget i brug på tidspunktet for offentliggørelse af retningslinjerne.

### 3.1Ressourcer hvor type er ’`model`’

#### Ressourcer hvor URIen anvender mønsteret `’/model/core/’`:

|             |                                                                                                                                                                                                                                                                     |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | DCAT-DK                                                                                                                                                                                                                                                             |
| Beskrivelse | DCAT-DK er et vokabular, der udvider mulighederne for beskrivelse af datasæt i dansk fællesoffentlig kontekst og definerer egenskaber såsom datasætansvarlig, betalingspålagt, personoplysningskategori og fortrolighedsgrad, som ikke indgår i DCAT-AP eller DCAT. |
| URI         | `https://data.gov.dk/model/core/dcat-dk/`                                                                                                                                                                                                                           |

#### Ressourcer hvor URIen anvender mønsteret ’`/model/profile/`’:

|             |                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Navn        | DCAT-AP-DK                                                                                                                                                                                                                                                                                                                                                                                 |
| Beskrivelse | DCAT-AP-DK er en specifikation til beskrivelse af datasæt og datakataloger til anvendelse i dansk fællesoffentlig regi. Specifikationen omfatter basisoplysninger om datasæt, som fx titel, beskrivelse, udgiver, udgivelsesdato mv., samt en ensartet struktur for disse oplysninger i et fælles udvekslingsformat, som gør det muligt at dele oplysninger om datasæt på en effektiv måde |
| URI         | `https://data.gov.dk/model/profile/dcat-ap-dk/`                                                                                                                                                                                                                                                                                                                                            |

|             |                                                                                                                                          |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | Arkivprofil                                                                                                                              |
| Beskrivelse | Anvendelsesprofil for det sæt af oplysningstyper, der er påkrævet eller anbefalet ifm. afgivelse af it-systemoplysninger til Rigsarkivet |
| URI         | `https://data.gov.dk/model/profile/itsystemap-archv/`                                                                                    |

### 3.2 Ressourcer hvor type er ’`concept`’

#### Ressourcer hvor URIen anvender mønsteret ’`/concept/core/`’:

|             |                                                                                                          |
| ----------- | -------------------------------------------------------------------------------------------------------- |
| Navn        | Arkivinstitutionstyper                                                                                   |
| Beskrivelse | Klassifikation, der består af typer af offentlige institutioner, der har til opgave at bevare arkivalier |
| URI         | `https://data.gov.dk/concept/core/ach-org-type/`                                                         |

|             |                                                                                                                                                                                                                                         |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | Sagsområder                                                                                                                                                                                                                             |
| Beskrivelse | Klassifikation, der består af typer af sagsområder i henhold til 'Bekendtgørelse om bevaring og kassation af digitalt skabte data og dokumenter fra kommunerne' og 'Bekendtgørelse om bevaring og kassation af arkivalier i regionerne' |
| URI         | `https://data.gov.dk/concept/core/archival-case-area#`                                                                                                                                                                                  |

|             |                                                                                                                                                                                                                                 |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | Arkiveringsversionsperiodetyper                                                                                                                                                                                                 |
| Beskrivelse | Klassifikation, der består af typer af arkiveringsperioder set i forhold til deres afgrænsning. Kommentar: hvorvidt data i et it-system afleveres som et øjebliksbillede, en afgrænset periode eller ved afsluttet arkivperiode |
| URI         | `https://data.gov.dk/concept/core/archivetype/`                                                                                                                                                                                 |

|             |                                                                                                                                                      |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | Arkiveringspligttyper                                                                                                                                |
| Beskrivelse | Klassifikation, der består af typer af arkiveringspligt set i forhold til, om data skal bevares eller kasseres iht. gældende arkiveringsbestemmelser |
| URI         | `https://data.gov.dk/concept/core/arch-obl-type/`                                                                                                    |

|             |                                                                                                                                                    |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | Konverteringsstatusser                                                                                                                             |
| Beskrivelse | Klassifikation, der består af statusser ift. konvertering set ud fra omfanget af et (manuelt eller automatisk) datakonverterings- og import forløb |
| URI         | `https://data.gov.dk/concept/core/conversionstatus`                                                                                                |

|             |                                                                                                      |
| ----------- | ---------------------------------------------------------------------------------------------------- |
| Navn        | Begrebsmodel for beskrivelse af datasæt                                                              |
| Beskrivelse | Begrebsmodel der indeholder centrale begreber i forhold til beskrivelse af dataset og datakataloger. |
| URI         | `https://data.gov.dk/concept/core/dataset-1.0.0`                                                     |

#### Ressourcer hvor URIen anvender mønsteret ’`/concept/profile/`’:

|             |                                                                                                                                                                                                                                                                     |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | It-systemanskaffelsesstyper                                                                                                                                                                                                                                         |
| Beskrivelse | Klassifikation der består af typer af anskaffelse af it-systemer _Eksempler: fx om det er udviklet i egen organisation, bestillingsudviklet (fx ved udbud) eller er anskaffet som et kommercielt (Commercial-of-the-shelf, COTS) eller open source-standardsystem._ |
| URI         | `https://data.gov.dk/concept/profile/aquisition-types`                                                                                                                                                                                                              |

|             |                                                                                                                                                    |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | Fortrolighedsgrader iht. sikkerhedscirkulæret (EU/NATO)                                                                                            |
| Beskrivelse | Klassifikation der består af grader af fortrolighed, forstået som i hvilket omfang information kan videregives iht. sikkerhedscirkulæret (EU/NATO) |
| URI         | `https://data.gov.dk/concept/profile/conf-eu-nato-types`                                                                                           |

|             |                                                                                                                                   |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | It-systemkritikalitetstyper                                                                                                       |
| Beskrivelse | Klassifikation, der består af typer af kritikalitet, ud fra hvorvidt et it-systems driftsforstyrrelser udgør en særlig høj risiko |
| URI         | `https://data.gov.dk/concept/profile/criticality-types`                                                                           |

|             |                                                                                                                                                                                                                                                                                                                                                                                                  |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Navn        | Begrebsliste til Arkivprofilen (archvSYS-AP)                                                                                                                                                                                                                                                                                                                                                     |
| Beskrivelse | Samlet begrebsliste med begreber, der er relevante ifm. afgivelse af oplysninger om it-systemer til Rigsarkivet. Bemærk, at denne anvendelsesorienterede begrebsliste udvælger og sammensætter begreber fra forskellige emneområder, se fx begrebsmodellen for it-system og begrebsmodellen for digital arkivering, som er [udstillet online](https://data.gov.dk/document/itsystem-ap/v1/uml/). |
| URI         | `https://data.gov.dk/concept/profile/itsystemap-archv/`                                                                                                                                                                                                                                                                                                                                          |

|             |                                                                                                                                                                       |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | Personoplysningskategorier                                                                                                                                            |
| Beskrivelse | Klassifikation, der består af kategorier af personoplysninger ud fra følsomhed, idet der gælder forskellige betingelser og procedurer for behandling af oplysningerne |
| URI         | `https://data.gov.dk/concept/profile/personal-data-categories`                                                                                                        |

|             |                                                                                                                                                             |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navn        | Offentlige organisationstyper                                                                                                                               |
| Beskrivelse | Klassifikation, der består af typer af offentlige organisationer set i forhold til styring og forvaltning i dansk administrativ og fællesoffentlig kontekst |
| URI         | `https://data.gov.dk/concept/profile/public-org-types`                                                                                                      |

|             |                                                                                          |
| ----------- | ---------------------------------------------------------------------------------------- |
| Navn        | It-systemmålgrupper                                                                      |
| Beskrivelse | Klassifikation, der består af typer af brugere, som et givet it-system henvender sig til |
| URI         | `https://data.gov.dk/concept/profile/target-types`                                       |

|             |                                                                                      |
| ----------- | ------------------------------------------------------------------------------------ |
| Navn        | It-miljøtyper                                                                        |
| Beskrivelse | Klassifikation, der består af typer af it-miljø, som et it-system kan instantieres i |
| URI         | `https://data.gov.dk/concept/profile/tech-env-types`                                 |

## 4\. EUs dataportals temaer for datasæt

| Akronym for temaet (= emne) | Dansk betegnelse                                | Temaets URI                                                                                                                          |
| --------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| ‘agri’                      | Landbrug, fiskeri, skovbrug og fødevarer        | [http://publications.europa.eu/resource/authority/data-theme/AGRI](http://publications.europa.eu/resource/authority/data-theme/AGRI) |
| ‘econ’                      | Økonomi og finanser                             | [http://publications.europa.eu/resource/authority/data-theme/ECON](http://publications.europa.eu/resource/authority/data-theme/ECON) |
| ‘educ’                      | Uddannelse, kultur og sport                     | [http://publications.europa.eu/resource/authority/data-theme/EDUC](http://publications.europa.eu/resource/authority/data-theme/EDUC) |
| ‘ener’                      | Energi                                          | [http://publications.europa.eu/resource/authority/data-theme/ENER](http://publications.europa.eu/resource/authority/data-theme/ENER) |
| ‘envi’                      | Miljø                                           | [http://publications.europa.eu/resource/authority/data-theme/ENVI](http://publications.europa.eu/resource/authority/data-theme/ENVI) |
| ‘gove’                      | Regeringen og den offentlige sektor             | [http://publications.europa.eu/resource/authority/data-theme/GOVE](http://publications.europa.eu/resource/authority/data-theme/GOVE) |
| ‘heal’                      | Sundhed                                         | [http://publications.europa.eu/resource/authority/data-theme/HEAL](http://publications.europa.eu/resource/authority/data-theme/HEAL) |
| ‘intr’                      | Internationale spørgsmål                        | [http://publications.europa.eu/resource/authority/data-theme/INTR](http://publications.europa.eu/resource/authority/data-theme/INTR) |
| ‘just’                      | Retfærdighed, retssystem og offentlig sikkerhed | [http://publications.europa.eu/resource/authority/data-theme/JUST](http://publications.europa.eu/resource/authority/data-theme/JUST) |
| ‘soci’                      | Befolkning og samfund                           | [http://publications.europa.eu/resource/authority/data-theme/SOCI](http://publications.europa.eu/resource/authority/data-theme/SOCI) |
| ‘regi’                      | Regioner og byer                                | [http://publications.europa.eu/resource/authority/data-theme/REGI](http://publications.europa.eu/resource/authority/data-theme/REGI) |
| ‘tech’                      | Videnskab og teknologi                          | [http://publications.europa.eu/resource/authority/data-theme/TECH](http://publications.europa.eu/resource/authority/data-theme/TECH) |
| ‘tran’                      | Transport                                       | [http://publications.europa.eu/resource/authority/data-theme/TRAN](http://publications.europa.eu/resource/authority/data-theme/TRAN) |

## Fodnoter

\[1\] [https://www.rfc-editor.org/rfc/rfc3986.html](https://www.rfc-editor.org/rfc/rfc3986.html)

\[2\] [https://www.w3.org/RDF/](https://www.w3.org/RDF/)

\[3\] [https://joinup.ec.europa.eu/catalogue/distribution/study-persistent-uris...](https://joinup.ec.europa.eu/catalogue/distribution/study-persistent-uris-identification-best-practices-and-recommendations-topic)

\[4\] [https://www.w3.org/TR/dwbp/](https://www.w3.org/TR/dwbp/)

\[5\] [https://tools.ietf.org/html/rfc7231#section-6.4.4](https://tools.ietf.org/html/rfc7231#section-6.4.4)

\[6\] [https://www.w3.org/blog/2006/02/content-negotiation/](https://www.w3.org/blog/2006/02/content-negotiation/)
