# Uneltele folosite

## Embedded Wizard
Pentru dezvoltarea interfețelor grafice se va folosi suita Embedded Wizard. Versiunea educațională (limitată în complexitate) se găsește pe site-ul producătorului
[Embedded Wizard](https://embedded-wizard.de). De acolo puteți descărca mediul dezvoltare prin click pe butonul _Download free edition_

Pentru a putea descărca trebuie să completați un formular
![image](https://user-images.githubusercontent.com/10776166/194034757-e40ebb83-c1e2-402f-81f8-f016d6530443.png)
Embedded wizard este disponibil pentru foarte multe diferite platforme încorporate. La laborator vom folosi plăcuțele de dezvoltare
STM32F746G-Discovery, și evident trebuie descărcat kitul corespunzător acestei plăcuțe.

După completarea formularului apare următoarea pagină:
![image](https://user-images.githubusercontent.com/10776166/194036787-bfc4291d-8a9e-440c-b18d-7282d6e6752f.png)

Trebuie descărcat de aici:
- **Embedded Wizard Studio Free 11** - pachetul de instalare pentru IDE
- **Embedded Wizard Platform Package for STM32** - pachetul de instalare pentru platforma țintă (se va instala după instalarea IDE-ului)
- **Embedded Wizard Build Environment for STM32F746 Discovery Board** - arhivă cu codurile sursă și scripturile de compilare necesare dezvoltării aplicațiilor, aceasta se dezarhivează într-un director convenabil (de exemplu C:\STM32) și va fi punctul de plecare pentru dezvoltarea aplicațiilor de laborator

Tot pe această pagină găsiți si informații adiționale despre instalare și folosirea mediului de dezvoltare.

## STM32Cube

Pentru programarea plăcilor aveți nevoie de [STM32CubeProgrammer](https://www.st.com/en/development-tools/stm32cubeprog.html) disponibil be site-ul producătorului de microcontroller.
După instalarea acestui program trebuie să editați fișierul _Application/FlashDownload/FlashDownload.cfg_ în directorul unde ați instalat mediul de dezvoltare de la Tara (implicit în C:\STM32\STM32F746-Discovery) și să modificați _Stm32CubeProgrammerPath_ să coincidă cu directorul unde ați instalat STM32CubeProgrammer. Dacă ați lăsat instalarea pe calea implicit propusă probabil și valoarea existentă din fișierul de configurare va fi cea bună.

Unealta de sus permite doar încărcarea programului compilat (folosind uneltele din mediul de dezvoltare despachetat) care după aceea se va rula pe plăcuță și poate fi
observat modul de funcționare. Dacă însă întâmpinați erori în funcționare și vreți să depanați programul pas cu pas veți avea nevoie de IDE-ul complet de la ST.

IDE-ul se numește [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) și de asemenea poate fi descărcat de pe site-ul producătorului. Aceasta
este o suită completă bazat pe Eclipse, care conține editor de cod, compilator și debugger. Proiectele exemple din Embedded Wizard pot fi configurate pentru a genera
cod și pentru acest IDE în loc de generare pentru linia de comandă. După generarea codului din Embedded Wizard, se poate încărca proiectul în STM32CubeIDE și
editat/compilat mai departe aici, respectiv în final se poate depana codul respectiv direct pe plăcuța de dezvoltare.

