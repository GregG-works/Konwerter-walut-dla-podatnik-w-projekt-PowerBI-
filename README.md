# Konwerter-walut-dla-podatnik-w-projekt-PowerBI-
Projekt ma na celu usprawnienie rozliczeń podatkowych dla polskich podatników, którzy rozliczają przychody w walutach obcych (np. mających obowiązek wypełnienia PIT-38 i rozliczających się z sprzedaży instrumentów finansowych u zagranicznego brokera) i muszą przeliczać je na złote (PLN) według kursu średniego ogłaszanego przez Narodowy Bank Polski z ostatniego dnia roboczego poprzedzającego dzień uzyskania przychodu/poniesienia kosztu. Szczegółowy opis dot. przeliczania walut obcych na złote w wymienionych przypadkach można znaleźć w Art. 11a Ustawy z dnia 26 lipca 1991 r. o podatku dochodowym od osób fizycznych (dokument dostępny na stronie sejmu RP).

## INSTRUKCJA UŻYTKOWANIA
### Wymagania
Do poprawnego działania projektu wymagane są zainstalowane na komputerze programy MS Excel oraz Power BI Desktop.
### Pobieranie projektu
Pobierz pliki projektu klikając ikonę 'Code' na stronie GitHub projektu, a następnie wybierz 'Download ZIP', co spowoduje pobranie skopmpresowanego folderu na Twoje urządzenie. Wypakuj pliki projektu w dowolnym miejscu na dysku, np. na pulpicie.
### Konfiguracja projektu
Przejdź do folderu z plikami projektu - znajdują się w nim 2 pliki programu Power BI Desktop z rozszerzeniem .pbix oraz folder 'Your table' z przykładowymi danymi w pliku MS Excel 'data.xlsx', dotyczącymi transakcji u (nieistniejącego) brokera o nazwie BROKERX.

Otwórz jeden z dwóch plików projektu z rozszerzeniem .pbix. Jeśli preferujesz projekt w języku polskim, otwórz plik 'Konwerter_walut_v1.0_PL.pbix'. Jeśli z jakichś względów preferujesz projekt w języku angielskim, otówrz plik 'Currencies_converter_v1.0_EN.pbix'. Po otwarciu powinna pokazać się strona z prezentacją danych w tabeli, filtrami danych po prawej stronie oraz sumą wartości z ostatniej kolumny tabeli w prawym dolnym rogu strony. Te dane pochodzą z przykładowej tabeli.

Aby móc wstawić swoje dane do projektu, przygotuj plik excel z co najmniej 5 kolumnami, z których:
- pierwsza zawiera datę (np. transakcji);
- druga zawiera cenę jednostkową w obcej walucie (np. zakupionego/sprzedanego instrumentu);
- trzecia zawiera 3-literową nazwę obcej waluty zgodną ze standardem ISO 4217 (np. EUR dla euro, USD dla dolara, CHF dla franka szwajcarskiego);
- czwarta zawiera ilość (np. zakupionego/sprzedanego instrumentu; nie musi to być liczba całkowita);
- piąta zawiera typ (np. K dla kupna instrumentu, S dla sprzedaży instrumentu; kolumna jest ważna, ponieważ dzięki niej można ustalić, które rodzaje transakcji będą do siebie dodawane; nie powinno się dodawać wartości transakcji kupna do wartości transakcji sprzedaży, jeśli obie wielkości są dodatnie (lub obie są ujemne)).
Tabela może zawierać także dodatkowe kolumny, ale ważne jest, aby pierwsze pięć zawierało opisane wyżej dane w odpowiedniej kolejności. Dzieki temu program Power BI Desktop wie, jak porządkować dane wyświetlane na głównej stronie. Wszystkie kolumny w tabeli powinny zawierać nagłówki. Nazwy kolumn nie są ważne, program Power BI Desktop zmieni pierwsze 5 nagłówków w trakcie przetwarzenia danych. Tworząc tabelę z danymi, użytkownik może wzorować się na tabeli dostępnej w folderze 'Your table'. Swoją tabelę zapisz pod nazwą 'data.xlsx' i wstaw do folderu 'Your table' - przykładowa tabela zostanie zastąpiona Twoją.

Ostatnim krokiem jest zmiana nazwy folderu z projektem. Przypomnijmy, że floder z projektem to ten, który zawiera 2 pliki projektu z rozszerzeniem .pbix oraz folderem 'Your table'. Skopiuj ścieżkę do folderu z projektem (jeśli zapisałeś/-aś ten folder na pulpicie będzie to np. C:\Users\Nazwa_komputera\Desktop\Konwerter). Następnie w otwartym pliku projektu (będąc w domyślnym widoku 'Report view') przejdź do zakładki 'Home' i kliknij 'Transform data' w sekcji 'Queries'. Pojawi się nowe okno. Na lewym panelu o nazwie 'Queries' wybierz 'RootPath'. Na środku strony pojawi się edytowalna linijka z tekstem 'C:\Converter'. Zmień tekst w linijce na ścieżkę z folderem projektu (wklej skopiowaną wcześniej ścieżkę). Po wklejeniu ścieżki kliknij 'Close & Apply' w lewym górnym rogu. Bieżące okno zostanie automatycznie zamkniętę i powrócisz do poprzedniego okna (poczekaj, aż program skończy aktualizować dane). Możesz teraz zapisać projekt, klikając iknonę dyskietki w lewym górnym rogu.

### Użytkowanie
Możesz teraz przeglądać dane z tabeli oraz wybierać filtry ('Data', 'Waluta' i 'Typ' w wersji polskiej lub 'Date', 'Currency' i 'Type' w wersji angielskiej), dostępne po prawej stronie. W prawym dolnym rogu pojawi się całkowita wartość w PLN z ostatniej kolumny tabeli po zastosowaniu filtrów. Możesz sprawdzić, jak zmienia się ta wartość ustalając różne przedziały dat, waluty lub typ (transakcji).

Możesz aktualizować swoją tabelę w pliku 'Your table', dodając nowe wiersze, lub wstawić nową tabelę pod tą samą nazwą. Za każdym razem, gdy wprowadzasz nowe dane (np. dopisując nowe rekordy z nowszymi datami), pamiętaj, aby w pliku projektu (będąc w widoku 'Report view') kliknąć 'Refresh' w zakładce 'Home' w sekcji 'Queries'. Spowoduje to aktualizację danych projektu i pobranie nowych danych ze strony NBP, dotyczących kursów walut (wymagane połączenie z internetem).

### Ostrzeżenie
Projekt jest jedynie narzędziem POMOCNICZYM i jego autor nie ponosi odpowiedzialności za jakiekolwiek nieprawidłowości powstałe w skutek jego użytkowania.
