# Dokumentacja-IAM

## Aktualizacja Drupala:  
po wykonaniu polecenna 'drush up drupal'  
zostanie nadpisany plik '.gitignore'  
należy go przywrócić np. za pomocą polecenia 'git checkout .gitignore' jeszcze przed zaindeksowaniem plików  

## Szablon (Theme):  
Szablon stworzony na bazie skórki Zen https://www.drupal.org/project/zen  

### Compass + Sass
(SAAS + Compass)  

Praca z compassem wymaga określonych wersji gemów. Z najnowszymi style nie są generowane poprawnie.

sudo gem install bundler  
cd sites/all/themes/iam  
bundle install  
bundler exec compass watch  

Dokumentacja Zen Grids  
http://v1.zengrids.com/ (wersja 1.5)  

#### W razie problemów

    sudo gem uninstall sass
    sudo gem install sass -v 3.2.19
    sudo gem uninstall compass
    sudo gem install compass -v 0.12.6


Preferowane podejście RWD: mobile first  

Zmienne zdefiniowane są tutaj: sites/all/themes/iam/sass/_init.scss  

Fonty włączone są tutaj: sites/all/themes/iam/sass/_normalize.scss  

Layout: sites/all/themes/iam/sass/layouts/_responsive.scss  

W katalogu components są style dla poszczególnych regionów, bloków, widoków itp.

#### UWAGA: wersja Compass-a 1.x powoduje rozsypanie grid-a. Ostatnia zalecana, działająca wersja to Compass 0.12.7 (Alnilam).


--------------------------------------------------------------------------------------  
## System Menu

Menu: moduł Superfish (menu RWD - Superfish plugin - sf-Smallscreen)  

## Moduł Features

Zmiany konfiguracji eksportujemy za pomoca modułu Features (https://www.drupal.org/project/features), moduły wygenerowane nazywamy z prefixem "iam_" oreślając w języku angielskim zawartosć (częśc funkcjonalnosci) z którą jest powiązany i zapisujemy w katalogu "sites/all/modules/features/".

Język źródłowy kodu, nazwy modułów, jezyk features i stringi w kodzie mają mieć jezyk źródłowy angielski.

Bloki: wyświetlanie skonfigurowane za pomocą modułu Context. Własne bloki dodajemy jako "boxes" (https://www.drupal.org/project/boxes) - nie korzystamy z drupalowego 'block'  

##Funkcje scss

em(size) - przelicza wielkość fontu w px na em'y na podstawie $base-font-size    
Przykładowe użycie: font-size: em(24), gdzie 24 to wielkość fonta w px  
