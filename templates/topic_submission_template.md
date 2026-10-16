# Zgłoszenie tematu

Odpowiedź mieści się na jednej stronie. Projekt dotyczy nadzorowanej klasyfikacji jednolabelowej: każdy przykład ma dokładnie jedną klasę.

**1. Roboczy tytuł**: 
Klasyfikacja typu Pokémona na podstawie oficjalnej grafiki.

**2. Modalność**: 
Obraz

**3. Problem klasyfikacji**: 
Rozpoznawanie głównego typu (żywioł) Pokémona wyłącznie na podstawie jego wyglądu na obrazku. Klasą jest jeden, główny typ (Type1) stworka (np. Ogień, Woda). Łącznie występuje 18 klas. W przypadku Pokémonów posiadających dwa typy, podczas wczytywania danych drugi typ zostanie odrzucony, aby skupić się tylko na pierwszym. Dzięki temu każdemu obrazkowi przypisana zostanie dokładnie jedna klasa docelowa.

**4. Pytanie eksperymentalne**: 
Czy model wykorzystujący transfer learning (zbudowany do rozpoznawania zdjęć w świecie rzeczywistym) potrafi dobrze wyodrębniać cechy rysunków i czy radzi sobie z tym zadaniem lepiej niż prosta, niewielka sieć konwolucyjna trenowana od zera. Analizie poddane zostanie również to, z jakimi typami model ma największe trudności (np. czy typ Fairy i Normal są dla niego wizualnie zbyt podobne).

**5. Źródło danych z linkiem**: 
Kaggle: Pokemon Images and Types
[https://www.kaggle.com/datasets/vishalsubbiah/pokemon-images-and-types](https://www.kaggle.com/datasets/vishalsubbiah/pokemon-images-and-types)

**6. Przybliżona wielkość zbioru**: 
809 obrazków.

**7. Lista klas i to, jak zostały oznaczone**: 
18 klas odpowiadających typom w grze (Normal, Fire, Water, Grass, Electric, Ice, Fighting, Poison, Ground, Flying, Psychic, Bug, Rock, Ghost, Dark, Dragon, Steel, Fairy). Etykiety są przypisane z dołączonego pliku CSV z kolumny `Type1` kolumny `Type2` i `Evolution` beda ignorowane.

**8. Licencja danych**: 
Udostępniony zbiór danych i plik z etykietami na platformie Kaggle posiada licencję: Attribution 4.0 International (CC BY 4.0)

**9. Proponowana jednostka generalizacji**: 
Jednostką generalizacji jest unikalne ID gatunku Pokémona. Podział całego zbioru na części nastąpi na podstawie tego identyfikatora. Jeśli Pokémon o danym ID trafi do zbioru walidacyjnego, to żadna inna grafika przedstawiająca ten sam gatunek nie może pojawić się w zbiorze treningowym.

**10. Planowany baseline**: 
Najprostsza z możliwych sieć CNN (np. złożona z 2-3 warstw konwolucyjnych), zbudowana i trenowana od podstaw na pikselach obrazków.

**11. Wstępny pomysł na model pretrained**: 
Model ResNet-18 wstępnie trenowany na zbiorze ImageNet. Fine-tuning tylko ostatniej warstwy: wagi samego modelu zostaną zamrożone, a na końcu dodany zostanie prosty klasyfikator dostosowany do 18 klas docelowych.

**12. Potencjalne ograniczenia obliczeniowe**: 
Moc obliczeniowa nie powinna stanowić problemu, ponieważ obrazki mają małą rozdzielczość, a proces uczenia będzie szybki. Wyzwaniem jest mała liczba danych – około 800 przykładów łącznie. W przypadku szybkiego przeuczania się modelu na pamięć konieczne będzie wdrożenie technik augmentacji zdjec.

**13. Informacje osobowe, dostęp i przechowywanie**: 
Dane nie zawierają żadnych informacji osobowych ani poufnych.Zostanie zastosowane pobieranie danych prosto w notatniku, a w samym repozytorium w katalogu data/sample/ znajdzie się jedynie kilka przykładowych obrazków.
