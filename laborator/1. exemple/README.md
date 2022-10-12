# Exemple Embedded Wizard

Mediul de dezvoltare construit de Tara Systems pentru placa STM32F746G Discovery vine cu o serie de exemple.
Acest tutorial va parcurge pașii necesari rulării exemplelor.

## Deschiderea exemplului în Embedded Wizard

Se deschide Embedded Wizard și din fereastra de pornire se selectează Open existing project.
Alternativ se poate deschide un proiect existent și din meniul File.

![splash](https://user-images.githubusercontent.com/10776166/195396651-6a1d93da-6fe8-468c-8445-e3d68ce8b6e9.png)

În fereastra de selecție se navighează în directorul `C:\STM32\STM32F746-Discovery\Examples\SmartThermostat și se deschide fișierul cu extensia `.ewp`
![open project](https://user-images.githubusercontent.com/10776166/195396863-2c505c99-f6aa-4736-afd8-6f65f694f127.png)

Fișierele de proiect în Embedded Wizard au extensia `.ewp`, la fel puteți să deschideți și proiectele de la toate celelalte exemple

## Embedded Wizard Studio

După deschiderea proiectului ajungem la fereastra principală a Embedded Wizard.
![EmWi](https://user-images.githubusercontent.com/10776166/195398925-2b7ed635-7896-493a-a1f5-ad9e82a8ecc5.png)

Aceasta conține un toolbar obișnuit în partea superioară, o galerie de componente în partea central-stânga, un inscpector în partea central-dreapta,
o fereastră de mesaje stânga jos și un editor de cod în partea dreapta jos. În rest, partea centrală a ferestrei este umplut cu composer.

Galeria de componente poate fi folosit pentru a selecta elementele de limbaj Chora, componente vizuale și diferite șabloane de obiecte pe care vrem să
adăugăm la program. Acestea pot fi adăugate prin drag-and-drop trăgând la poziția dorită în Composer. Inspectorul poate fi folosit pentru a selecta și
a configura proprietățile componentelor vizuale din proiect. Editorul de cod evident permite scrierea codului Chora aferent componentelor selectate.
Iar fereastra de mesaje va afișa mesajele de întâmpinare și mesajele de eroare întâmpinate (în construirea codului și la depanare).

## Simularea programului

Embedded Wizard conține un Prototyper — un simulator care permite rularea programul GUI direct pe calculator pentru a vizualiza cum va arăta
interfața grafică încărcată și pe microcontroler. Aceasta va rula doar interfața grafică (fără interacțiune cu perifericele din microcontroler)
dar totuși este un ajutor pentru dezvoltarea elementelor vizuale și a animațiilor folosite.

Pentru a porni prototyperul se va folosi iconița ![play](https://user-images.githubusercontent.com/10776166/195400882-f036beb6-484e-4990-8539-6f5c68ac9ee8.png)
(_Start prototyper with application class_) sau se apasă pe combinația de taste Ctrl-F5.

Prototyper-ul se va deschide într-o fereastră nouă de dimensiunea identică cu rezoluția ecranului configurat pentru placa de dezvoltare (480x272 în cazul nostru)
![prototyper](https://user-images.githubusercontent.com/10776166/195401433-eb98b9a3-e083-4477-946f-e5d1af005c89.png)

Aceasta va rula toate animațiile definite și se poate interacționa cu mouse-ul pe post de touchscreen.

## Generarea programului pentru microcontroler

După ce GUI-ul dezvoltat a fost validat în prototyper, va trebui generat codul C care să se compileze pe microcontroler. Pentru generarea codului C se va folosi
iconița ![image](https://user-images.githubusercontent.com/10776166/195402137-490e0373-49f2-4c19-99e7-fc31f01e0779.png) (_Build this profile_) sau se va apăsa pe tasta F8.

Exemplul de laborator este deja configurat pentru generare în mediul de dezvoltare în folderul dedicat `Application\Generated Code`. Pentru simplitatea sistemului de
compilare C, toate exemplele vor folosi acest director ca destinație.

## Compilarea programului pentru microcontroler

Codul generat anterior este depus într-un director comun, pe lângă care în directoarele mediului de dezvoltare se regăsesc și toate celelalte coduri sursă C și
bibliotecile pentru STM32 necesare compilării programului. Mediul de dezvoltare este prevăzut și de un sistem _make_ responsabil pentru compilare, configurat
astfel încât să compileze implicit orice exemplu cu care vine mediul de dezvoltare.

Pentru a porni sistemului se folosește fișierul _StartGCCBuildEnvironment.bat_ din directorul de rădăcină a mediului de dezvoltare care va porni o linie de
compandă pregătită pentru compilare.

Compilarea în sine se realizează cu comanda `make` dată în această fereastră, iar încărcarea programului compilat pe microcontroler se face cu comanda
`make install`.
