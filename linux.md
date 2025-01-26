# Do 60 podstawowych poleceń Linuksa
- Przyjrzyjmy się 60 najczęściej używanym poleceniom systemu Linux i ich przykładom, służącym do administrowania systemem.

- Wskazówka dla profesjonalistów:
    Jeśli chcesz sprawdzić użycie, składnię i opcje polecenia, użyj flagi `--help`. Na przykład wpisz `ls --help`, aby wyświetlić przewodnik po narzędziu `ls`.

## 1. polecenie `ls`
- Polecenie `ls` wyświetla zawartość folderu, w tym pliki i katalogi. Oto składnia:
    ```bash
    ls [opcje] [katalog_lub_ścieżka]
    ```
    Jeśli pominiesz ścieżkę, polecenie `ls` sprawdzi zawartość bieżącego katalogu. Aby wyświetlić elementy wewnątrz podfolderów, dodaj opcję `-R`. Tymczasem użyj `-a`, aby wyświetlić ukrytą zawartość.

## 2. polecenie `pwd`
- Aby sprawdzić pełną ścieżkę bieżącego katalogu roboczego, użyj polecenia `pwd`. Jego składnia jest następująca:
    ```bash
    pwd [opcje]
    ```
    Polecenie `pwd` ma tylko dwie opcje. Opcja `-L` drukuje zawartość zmiennej środowiskowej, np. skróty, zamiast rzeczywistej ścieżki bieżącej lokalizacji. Tymczasem `-P` wyświetla dokładną lokalizację.

    Na przykład `/shortcut/folder` jest skrótem do `/actual/path`, a obecnie jesteś w `/actual/path/dir`. Jeśli użyjesz opcji `-L`, wynik będzie następujący:
    ```
    /skrót/folder/katalog
    ```
    Tymczasem opcja `-P` wydrukuje dokładną ścieżkę kanoniczną:
    ```
    /aktualna/ścieżka/katalog
    ```

## 3. polecenie `cd`
- Użyj `cd`, aby poruszać się między katalogami w swoim Linux VPS. Nie ma żadnej opcji, a składnia jest prosta:
    ```bash
    cd [ścieżka_lub_katalog]
    ```
    W zależności od lokalizacji, może być konieczne określenie tylko katalogu nadrzędnego. Na przykład, pomiń `path` z `path/to/directory`, jeśli już jesteś w jednym z nich. Polecenie `cd` ma kilka skrótów:
    - `cd` – powraca do katalogu domowego bieżącego użytkownika.
    - `cd ..` – przesuwa katalog w górę.
    - `cd -` – wraca do poprzedniego katalogu.

## 4. polecenie `mkdir`
- Polecenie `mkdir` pozwala na utworzenie jednego lub wielu katalogów. Składnia wygląda następująco:
    ```bash
    mkdir [opcje] nazwa_katalogu1 nazwa_katalogu2
    ```
    Aby utworzyć folder w innej lokalizacji, podaj pełną ścieżkę. W przeciwnym razie to polecenie utworzy nowy element w bieżącym katalogu roboczym.

    Na przykład wprowadź poniższe polecenie, aby utworzyć nowy folder w katalogu `/path/to/target_folder`:
    ```bash
    mkdir /path/to/target_folder/nowy_folder
    ```
    Domyślnie `mkdir` pozwala bieżącemu użytkownikowi czytać, zapisywać i wykonywać pliki w nowym folderze. Możesz ustawić niestandardowe uprawnienia podczas tworzenia, dodając opcję `-m`. Aby dowiedzieć się więcej o zarządzaniu uprawnieniami, przeczytaj sekcję `chmod` poniżej.

## 5. polecenie `rmdir`
- Uruchom `rmdir`, aby usunąć puste katalogi w systemie Linux. Składnia polecenia wygląda następująco:
    ```bash
    rmdir [opcje] nazwa_katalogu
    ```
    Polecenie `rmdir` nie zadziała, jeśli katalog zawiera podfoldery. Aby wymusić usunięcie, dodaj opcję `-p`. Pamiętaj, że musisz być właścicielem elementu, który chcesz usunąć, lub zamiast tego użyj `sudo`.

## 6. polecenie `rm`
- Polecenie `rm` usuwa pliki z katalogu. Musisz mieć uprawnienia do zapisu do folderu lub użyć `sudo`. Oto składnia:
    ```bash
    rm [opcje] plik1 plik2
    ```
    Możesz dodać opcję `-r`, aby usunąć folder i jego zawartość, w tym podkatalogi. Użyj flagi `-i`, aby wyświetlić komunikat potwierdzający przed usunięciem lub `-f`, aby całkowicie je dezaktywować.

    Ostrzeżenie! Unikaj używania `-r` i `-f`, chyba że jest to konieczne. Zamiast tego dodaj opcję `-i`, aby zapobiec przypadkowemu usunięciu.

## 7. polecenie `cp`
- Użyj polecenia `cp`, aby skopiować pliki z bieżącego katalogu do innego folderu. Składnia wygląda następująco:
    ```bash
    cp [opcje] plik1 plik2 [ścieżka_docelowa]
    ```
    Możesz również użyć `cp`, aby zduplikować zawartość jednego pliku do innego, używając tej składni. Jeśli cel znajduje się w innej lokalizacji, określ pełną ścieżkę w następujący sposób:
    ```bash
    cp plik_źródłowy /ścieżka/do/pliku_docelowego
    ```
    Dodatkowo polecenie `cp` pozwala na duplikowanie katalogu i jego zawartości do innego folderu za pomocą opcji `-R`:
    ```bash
    cp -R /ścieżka/do/folderu /ścieżka/do/folderu_docelowego
    ```

## 8. polecenie `mv`
- Głównym zastosowaniem polecenia `mv` jest przeniesienie pliku lub folderu do innej lokalizacji. Oto składnia:
    ```bash
    mv plik_lub_katalog [katalog_docelowy]
    ```
    Na przykład przeniesiemy plik `file1.txt` z innej lokalizacji do katalogu `/new/file/directory` za pomocą tego polecenia:
    ```bash
    mv /oryginalna/ścieżka/plik1.txt ścieżka/docelowa
    ```
    Możesz również użyć polecenia `mv`, aby zmienić nazwy plików w systemie Linux. Oto przykład:
    ```bash
    mv stara_nazwa.txt nowa_nazwa.txt
    ```
    Jeśli podasz pełną ścieżkę, możesz jednocześnie zmieniać nazwy plików i przenosić je do nowej lokalizacji, jak w tym przykładzie:
    ```bash
    mv stara/lokalizacja/starej_nazwy.txt nowa/ścieżka/dla/nowej_nazwy.txt
    ```

## 9. polecenie `touch`
- Uruchom polecenie `touch`, aby utworzyć nowy pusty plik w określonym katalogu. Składnia jest następująca:
    ```bash
    touch [opcje] [ścieżka_i_nazwa_pliku]
    ```
    Jeśli pominiesz ścieżkę, polecenie `touch` utworzy nowy plik w bieżącym katalogu roboczym. Oto przykład:
    ```bash
    touch plik.txt
    ```

## 10. polecenie `file`
- Polecenie `file` sprawdza typ pliku, taki jak TXT, PDF lub inny. Składnia jest następująca:
    ```bash
    file [nazwa_pliku]
    ```
    Jeśli użyjesz tego polecenia na dowiązaniu symbolicznym, wyświetli ono rzeczywisty plik połączony ze skrótem. Możesz dodać opcję `-k`, aby wydrukować bardziej szczegółowe informacje o elemencie.

## 11. polecenia `zip` i `unzip`
- Polecenie `zip` kompresuje jeden lub wiele plików do archiwum ZIP, zmniejszając ich rozmiar. Oto składnia:
    ```bash
    zip [opcje] zip_file_name plik1 plik2
    ```
    Aby wyodrębnić skompresowany plik do bieżącego katalogu roboczego, użyj polecenia `unzip` w następujący sposób:
    ```bash
    unzip [opcje] zip_file_name
    ```

## 12. polecenie `tar`
- Polecenie `tar` pakuje wiele plików lub katalogów do archiwum bez kompresji. Składnia wygląda następująco:
    ```bash
    tar [opcje] tar_file_name plik1 plik2
    ```
    Aby utworzyć nowy plik TAR, musisz dodać opcję `-c`. Następnie użyj flagi `-f`, aby określić nazwę archiwum.

    Jeśli chcesz włączyć kompresję, dodaj konkretną opcję opartą na preferowanej metodzie. Na przykład, poniższy kod połączy `file1.txt` i `file2.txt` z kompresją gzip:
    ```bash
    tar -cfz archiwum.tar.gz file1.txt file2.txt
    ```
    Pamiętaj, że format pliku archiwum będzie się różnić w zależności od metody kompresji. Niezależnie od rozszerzenia, możesz rozpakować plik TAR, używając następującej składni:
    ```bash
    tar [opcje] tar_file_name
    ```

## 13. Polecenia `nano`, `vi` i `jed`
- Polecenia `nano`, `vi` i `jed` pozwalają edytować pliki. Mają taką samą składnię, z wyjątkiem początku, gdzie określasz nazwę narzędzia:
    ```bash
    nano/vi/jed nazwa_pliku
    ```
    Jeśli plik docelowy nie istnieje, te polecenia utworzą nowy. Ponieważ Twój system może nie mieć tych narzędzi do przetwarzania tekstu wstępnie zainstalowanych, skonfiguruj je za pomocą menedżera pakietów.

## 14. polecenie `cat`
- Polecenie concatenate lub `cat` ma różne zastosowania. Najbardziej podstawowym jest drukowanie zawartości pliku. Oto składnia:
    ```bash
    cat nazwa_pliku
    ```
    Aby wydrukować zawartość w odwrotnej kolejności, użyj `tac`. Jeśli dodasz symbol operatora standardowego wyjścia (`>`), polecenie `cat` utworzy nowy plik. Na przykład poniższe polecenie spowoduje utworzenie `plik.txt`:
    ```bash
    cat > plik.txt
    ```
    Możesz również użyć `cat` z operatorem, aby połączyć zawartość wielu plików w nowy element. W tym poleceniu `file1.txt` i `file2.txt` połączą się w `target.txt`:
    ```bash
    cat file1.txt file2.txt > target.txt
    ```

## 15. polecenie `grep`
- Globalne wyrażenie regularne print lub `grep` pozwala wyszukiwać konkretne wiersze w pliku za pomocą słów kluczowych. Jest to przydatne do filtrowania dużych danych, takich jak logi. Składnia wygląda następująco:
    ```bash
    grep [opcje] słowo_kluczowe [plik]
    ```
    Możesz również filtrować dane z innego narzędzia, przesyłając je do polecenia `grep`. Na przykład poniższe przeszukuje plik `file.txt` w wynikach polecenia `ls`:
    ```bash
    ls | grep "file.txt"
    ```

## 16. polecenie `sed`
- Użyj polecenia `sed`, aby szybko wyszukiwać i zamieniać wzorce w plikach. Podstawowa składnia wygląda następująco:
    ```bash
    sed [opcje] 's/wzorzec_docelowy/nowy_wzorzec/' plik_wejściowy
    ```
    Możesz zastąpić ciąg w wielu plikach jednocześnie, wymieniając je. Oto przykład polecenia `sed`, które zmienia kolor czerwony w `colors.txt` i `hue.txt` na niebieski:
    ```bash
    sed 's/red/blue/' colors.txt hue.txt
    ```

## 17. polecenie `head`
- Użyj polecenia `head`, aby wydrukować pierwsze kilka wpisów pliku. Podstawowa składnia jest następująca:
    ```bash
    head [opcje] nazwa_pliku
    ```
    Można również wydrukować pierwsze kilka wierszy wyniku innego polecenia, przekazując je w następujący sposób:
    ```bash
    polecenie | head [opcje]
    ```
    Domyślnie `head` pokaże pierwsze dziesięć wierszy. Możesz jednak zmienić to ustawienie, używając opcji `-n`, a następnie żądanej liczby.

    W międzyczasie użyj opcji `-c`, aby wydrukować pierwsze kilka wpisów na podstawie rozmiaru bajtów, a nie całego wiersza.

## 18. polecenie `tail`
```bash
tail [opcje] nazwa_pliku
polecenie | tail [opcje]
```
Narzędzie `tail` ma również tę samą opcję co `head`. Na przykład wyodrębnimy ostatnie pięć wierszy z wyjścia polecenia `ping`:
```bash
ping -c 10 8.8.8.8 | tail -n 5
```

## 19. polecenie awk
Polecenie `awk` wyszukuje i manipuluje wzorcami wyrażeń regularnych w pliku. Oto podstawowa składnia:
```bash
awk '/wzorzec wyrażenia regularnego/{akcja}' plik_wejściowy.txt
```
Chociaż podobny do `sed`, `awk` oferuje więcej operacji poza podstawianiem, w tym drukowanie, obliczenia matematyczne i usuwanie. Pozwala również na uruchomienie złożonego zadania za pomocą instrukcji `if`.

Możesz uruchomić wiele akcji, wymieniając je według kolejności wykonania, rozdzielone średnikiem (`;`). Na przykład, to polecenie `awk` oblicza średni wynik studenta i wyświetla nazwiska, które są powyżej tego progu:
```bash
awk -F':' '{ total += $2; students[$1] = $2 } END { average = total / length(students); print "Średnia:", average; print "Powyżej średniej:"; for (student in students) if (students[student] > average) print student }' score.txt
```

## 20. polecenie sortowania
Użyj polecenia `sort`, aby uporządkować zawartość pliku w określonej kolejności. Jego składnia wygląda następująco:
```bash
sort [opcje] [nazwa_pliku]
```
Należy pamiętać, że to narzędzie nie modyfikuje samego pliku, a jedynie drukuje zmienioną zawartość jako dane wyjściowe.

Domyślnie polecenie `sort` używa kolejności alfabetycznej od A do Z, ale możesz dodać opcję `-r`, aby odwrócić kolejność. Możesz również sortować pliki numerycznie, używając flagi `-n`.

## 21. polecenie cięcia
Polecenie `cut` wybiera określone sekcje z pliku i drukuje je jako dane wyjściowe Terminala. Składnia wygląda następująco:
```bash
cut [opcje] [nazwa_pliku]
```
W przeciwieństwie do innych narzędzi Linux, opcje polecenia `cut` są obowiązkowe dla sekcji plików. Oto niektóre flagi:
- `-f` – wybiera określone pole wiersza.
- `-b` – obcina linię o określony rozmiar w bajtach.
- `-c` – dzieli wiersz na sekcje przy użyciu określonego znaku.
- `-d` – oddziela wiersze na podstawie ograniczników.

Możesz łączyć wiele opcji, aby uzyskać bardziej szczegółowy wynik. Na przykład to polecenie wyodrębnia pole od trzeciego do piątego z listy rozdzielonej przecinkami:
```bash
cut -d',' -f3-5 lista.txt
```

## 22. polecenie diff
Polecenie `diff` porównuje dwa pliki i drukuje ich różnice. Oto składnia:
```bash
diff [nazwa_pliku1] [nazwa_pliku2]
```
Domyślnie polecenie `diff` pokazuje tylko różnice między dwoma plikami. Aby wydrukować całą zawartość i wyróżnić rozbieżności, włącz format kontekstu za pomocą opcji `-c`. Możesz również zignorować rozróżnianie wielkości liter, dodając `-i`.

Na przykład uruchom poniższe polecenie, aby wyświetlić tylko różnice między plikami `1.txt` i `2.txt`:
```bash
diff -c 1.txt 2.txt
```

## 23. polecenie tee
Polecenie `tee` wyprowadza wyniki innego polecenia zarówno do Terminala, jak i do pliku. Jest to pomocne, jeśli chcesz użyć danych do dalszego przetwarzania lub tworzenia kopii zapasowych. Oto składnia:
```bash
[polecenie] | tee [opcje] [nazwa_pliku]
```
Jeśli określony plik nie istnieje, `tee` go utworzy. Zachowaj ostrożność podczas używania tego polecenia, ponieważ nadpisze ono istniejącą zawartość. Aby zachować i dołączyć istniejące dane, dodaj opcję `-a`.

Na przykład zapiszemy dane wyjściowe polecenia `ping` jako nowe wpisy w pliku `test_network.txt`:
```bash
ping 8.8.8.8 | tee -a test_network.txt
```

## 24. polecenie locate
Polecenie `locate` wyszukuje plik i drukuje jego ścieżkę lokalizacji. Oto składnia:
```bash
locate [opcje] [słowo_kluczowe]
```
Jeśli używasz opcji `-r` do wyszukiwania plików za pomocą wyrażeń regularnych, pomiń argument `[słowo_kluczowe]`. Polecenie `locate` domyślnie rozróżnia wielkość liter, ale możesz wyłączyć to zachowanie za pomocą flagi `-i`.

Należy pamiętać, że `locate` będzie szukać plików w swojej bazie danych. Chociaż takie zachowanie przyspiesza proces wyszukiwania, należy poczekać na odświeżenie listy przed znalezieniem nowo utworzonych elementów.

Można również wprowadzić poniższe dane ręcznie, aby ponownie załadować dane:
```bash
updatedb
```

## 25. polecenie find
Polecenie `find` wyszukuje plik w określonym katalogu. Oto składnia:
```bash
find [ścieżka] [opcje] [wyrażenie]
```
Jeśli nie określisz ścieżki, polecenie `find` przeszuka Twój bieżący katalog roboczy. Aby znaleźć pliki według ich nazwy, dodaj opcję `-name`, a następnie słowo kluczowe.

Możesz określić typ poszukiwanego elementu za pomocą flagi `-type`. Opcja `-type f` przeszuka tylko pliki, podczas gdy `-type d` znajdzie katalogi. Na przykład sprawdzimy plik `file.txt` w `path/to/folder`:
```bash
find path/to/folder -type f -name "file.txt"
```
W przeciwieństwie do `locate`, polecenie `find` przeszukuje foldery w czasie rzeczywistym. Chociaż spowalnia proces, możesz od razu szukać nowych elementów, nie czekając na odświeżenie bazy danych systemu.

## 26. polecenie sudo
Superuser do lub `sudo` umożliwia użytkownikom innym niż root, którzy są częścią grupy sudo, wykonywanie poleceń administracyjnych. Po prostu dodaj to na początku innego narzędzia w następujący sposób:
```bash
sudo [opcje] [twoje_polecenie]
```
Na przykład, aby otworzyć plik, używając `nano` jako administrator, wprowadź poniższe polecenie:
```bash
sudo nano plik.txt
```
Terminal poprosi Cię o podanie hasła użytkownika przed wykonaniem polecenia. Domyślnie musisz je ponownie wprowadzić po pięciu minutach bezczynności.

Zazwyczaj nie dodaje się żadnych opcji do `sudo`, ale można je sprawdzić, wpisując:
```bash
sudo --help
```
Ostrzeżenie! Ponieważ użytkownicy z uprawnieniami sudo mogą zmieniać różne ustawienia systemu, używaj tego polecenia ostrożnie.

## 27. Polecenia su i whoami
Polecenie `su` pozwala na przełączenie się na innego użytkownika w sesji Terminala. Składnia wygląda następująco:
```bash
su [opcje] [nazwa_użytkownika]
```
Jeśli nie określisz żadnej opcji ani nazwy użytkownika, to polecenie przełączy Cię na użytkownika root. W takim przypadku musisz wprowadzić hasło przed zmianą konta.

Możesz sprawdzić aktualnie zalogowanego użytkownika z poziomu wiersza poleceń Linux. Alternatywnie, użyj polecenia `whoami`:
```bash
whoami
```

## 28. polecenie chmod
`Chmod` pozwala zmienić uprawnienia plików lub katalogów. Podstawowa składnia wygląda następująco:
```bash
chmod [opcje] [uprawnienia] [plik_lub_katalog]
```
W systemie Linux istnieją trzy uprawnienia do folderów i plików – odczyt (`r`), zapis (`w`) i wykonywanie (`x`). Można je przypisać trzem stronom – właścicielowi, grupie lub innym kontom nienależącym do żadnej z tych kategorii. Rozważmy ten przykład:
```bash
chmod -rwx---r-- plik1.txt
```
Miejsce po pierwszym myślniku (`-`) określa uprawnienia właściciela pliku `file1.txt`. W poprzednim przykładzie przyznajemy mu uprawnienie `rwx`.

Następne miejsce jest dla grup. Ponieważ nie przyznamy im żadnych uprawnień, wstawiliśmy trzy łączniki, aby wskazać pustkę. Ostatnie miejsce jest dla innych użytkowników, którzy mają tylko uprawnienia do odczytu lub `r`.

## 29. polecenie chown
Polecenie `chown` pozwala zmienić właściciela plików, katalogów lub dowiązań symbolicznych. Oto składnia:
```bash
chown [opcje] [nowy_właściciel:nowa_grupa] [plik1] [plik2]
```
Jeśli chcesz przypisać użytkownika jako nowego właściciela elementu, pozostaw nazwę grupy pustą. Na przykład, uczynimy `admin-vps` właścicielem pliku `file1.txt`:
```bash
chown admin-vps file1.txt
```
Odwrotnie, pomiń nazwę użytkownika, aby wszyscy członkowie grupy stali się właścicielami. Pamiętaj, aby napisać dwukropki (`:`) w następujący sposób:
```bash
chown :newgroup file1.txt
```

## 30. Polecenia useradd, passwd i userdel
Użyj polecenia `useradd`, aby utworzyć nowe konto w systemie Linux. Składnia jest następująca:
```bash
useradd [opcje] [nowa_nazwa_użytkownika]
```
Domyślnie polecenie `useradd` nie prosi o podanie hasła nowemu użytkownikowi. Możesz je dodać lub zmienić ręcznie później za pomocą polecenia `passwd`:
```bash
passwd nowa_nazwa_użytkownika
```
Aby usunąć użytkownika, należy użyć polecenia `userdel`, po którym następuje nazwa konta, zgodnie ze składnią podaną w przykładzie:
```bash
userdel nowa_nazwa_użytkownika
```
Ponieważ zarządzanie innymi użytkownikami wymaga uprawnień superużytkownika, uruchom te polecenia jako root lub z prefiksem `sudo`.

Wskazówka dla profesjonalistów: Aby ustawić hasło i inne szczegóły podczas tworzenia konta, należy zamiast tego użyć polecenia `adduser`.

## 31. polecenie df
Polecenie `df` sprawdza wykorzystanie dysku w systemie Linux, wyświetlając użyte miejsce w procentach i kilobajtach (KB). Składnia wygląda następująco:
```bash
df [opcje] [system_plików]
```
Należy pamiętać, że polecenie `df` działa na poziomie systemu plików. Jeśli nie określisz żadnego, narzędzie wyświetli wszystkie aktywne systemy plików.
## 32. polecenie du
Aby sprawdzić rozmiar katalogu i jego zawartość, użyj polecenia `du`. Oto składnia:
```bash
du [katalog]
```
Polecenie sprawdzi Twój katalog roboczy, jeśli nie określisz ścieżki lub folderu. Domyślnie rozbija użycie dysku każdego podfolderu, ale możesz dodać opcję `-s`, aby podsumować całkowite użycie w jednym wyjściu.

Można również użyć opcji `-M`, aby zmienić jednostkę KB na MB.

## 33. polecenie top
Polecenie `top` wyświetla wszystkie uruchomione procesy w systemie i ich zużycie sprzętu. Składnia wygląda następująco:
```bash
top [opcje]
```
Polecenie `top` ma różne opcje. Na przykład `-p` pozwala sprawdzić konkretny proces, określając jego ID. Tymczasem dodaj flagę `-d`, aby zmienić opóźnienie między aktualizacjami ekranu.

## 34. polecenie htop
Podobnie jak `top`, polecenie `htop` pozwala wyświetlać i zarządzać procesami na serwerze Linux. Ma również taką samą składnię:
```bash
htop [opcje]
```
`htop` ma opcje podobne do `top`, ale możesz dodać dodatkowe. Na przykład `-C` włącza tryb monochromatyczny, podczas gdy `--tree` pokazuje procesy w widoku hierarchicznym.

## 35. polecenie ps
Polecenie `ps` podsumowuje stan wszystkich uruchomionych procesów w systemie Linux w określonym czasie. W przeciwieństwie do `top` i `htop`, nie aktualizuje informacji automatycznie. Oto składnia:
```bash
ps [opcje]
```
Możesz wydrukować bardziej szczegółowy raport, dodając inne opcje. Na przykład użyj `-A`, aby wyświetlić wszystkie procesy w systemie, `-r`, aby sprawdzić tylko te uruchomione, lub `-u username`, aby zapytać te powiązane z konkretnym kontem.

## 36. polecenie uname
Polecenie `uname` wyświetla szczegółowe informacje o Twoim komputerze z systemem Linux, w tym sprzęt, nazwę i jądro systemu operacyjnego. Jego podstawowa składnia wygląda następująco:
```bash
uname [opcje]
```
Bez żadnej opcji polecenie wyświetli nazwę jądra twojego systemu. Aby sprawdzić wszystkie informacje o twoim komputerze, dodaj opcję `-a`.

## 37. polecenie hostname
Użyj polecenia `hostname`, aby sprawdzić nazwę hosta VPS i inne powiązane informacje. Oto składnia:
```bash
hostname [opcje]
```
Jeśli pozostawisz opcję pustą, polecenie wydrukuje nazwę hosta. Dodaj `-i`, aby sprawdzić adres IP serwera, `-a`, aby wydrukować alias nazwy hosta i `-A`, aby wyświetlić w pełni kwalifikowaną nazwę domeny systemu (FQDN).

## 38. polecenie time
Polecenie `time` mierzy czas wykonywania poleceń lub skryptów, aby uzyskać wgląd w wydajność systemu. Podstawowa składnia wygląda następująco:
```bash
time polecenie_lub_skrypt
```
Możesz zmierzyć serię poleceń, oddzielając je podwójnymi znakami ampersand (`&&`) lub średnikami (`;`) w następujący sposób:
```bash
time polecenie; polecenie; polecenie
```

## 39. polecenie systemctl
Polecenie `systemctl` służy do zarządzania usługami w systemie Linux. Oto podstawowa składnia:
```bash
systemctl [podpolecenie] [nazwa_usługi] [opcje]
```
Podpolecenia reprezentują Twoje zadanie, takie jak wylistowanie, ponowne uruchomienie, zakończenie lub włączenie usług. Na przykład, wylistujemy usługi Linux używając tego:
```bash
sudo systemctl list-unit-files --type service --all
```
Należy pamiętać, że to polecenie może nie działać w przypadku starszych dystrybucji, ponieważ używają one innego menedżera usług.

## 40. polecenie watch
Polecenie `watch` pozwala na ciągłe uruchamianie narzędzia w określonych odstępach czasu w celu monitorowania zmian w wynikach. Oto podstawowa składnia:
```bash
watch [opcje] command_name
```
Domyślnie `watch` będzie uruchamiał polecenie co dwie sekundy, ale możesz zmienić interwał, używając opcji `-n`, a następnie delay. Jeśli chcesz wyróżnić zmiany w wynikach, dodaj flagę `-d`.

## 41. polecenie jobs
Zadania to zadania lub polecenia, które są uruchamiane w bieżącej powłoce. Aby je sprawdzić, użyj polecenia `jobs` z następującą składnią:
```bash
jobs [opcje] [Job_ID]
```
Uruchomienie tego polecenia bez argumentu spowoduje wyświetlenie wszystkich zadań uruchomionych na pierwszym planie i w tle Terminala. Jeśli nie masz żadnych bieżących zadań, zwróci ono puste wyjście.

Możesz wyświetlić bardziej szczegółowe informacje o każdym zadaniu, dodając opcję `-l`. Tymczasem użyj `-n`, aby wyświetlić tylko zadania, których status zmienił się od ostatniego powiadomienia.

## 42. polecenie kill
Użyj polecenia `kill`, aby zakończyć proces używając jego ID. Oto podstawowa składnia:
```bash
kill [signal_option] Process_ID
```
Aby uzyskać identyfikator procesu, uruchom następujące polecenie:
```bash
ps ux
```
Polecenie `kill` ma 64 sygnały zakończenia. Domyślnie używa metody `SIGTERM`, która pozwala programowi zapisać postęp przed zamknięciem.

## 43. polecenie shutdown
Polecenie `shutdown` pozwala wyłączyć lub ponownie uruchomić system Linux o określonej porze. Oto składnia:
```bash
shutdown [opcja] [czas] [wiadomość]
```
Jeśli uruchomisz polecenie bez żadnych argumentów, system wyłączy się natychmiast. Harmonogram można określić w formacie 24-godzinnym lub względnym. Na przykład wpisz `+5`, aby wyłączyć system po pięciu minutach. Aby ponownie uruchomić komputer, dodaj opcję `-r`.

Argument `message` określa powiadomienie, które otrzymają inni użytkownicy w systemie przed wyłączeniem serwera.

## 44. polecenie ping
Polecenie `ping` wysyła pakiety do serwera docelowego i pobiera odpowiedzi. Jest pomocne w diagnostyce sieci. Podstawowa składnia wygląda następująco:
```bash
ping [opcja] [nazwa_hosta_lub_adres_IP]
```
Domyślnie polecenie `ping` wysyła nieskończoną liczbę pakietów, dopóki użytkownik nie zatrzyma go ręcznie, naciskając kombinację klawiszy `Ctrl + C`.

Można jednak określić niestandardową liczbę za pomocą opcji `-c`. Można również zmienić interwał między transferami, dodając `-i`.

Na przykład, wyślijmy 15 pakietów co dwie sekundy do serwera Google:
```bash
ping -c 15 -i 2 google.com
```

## 45. polecenie wget
Polecenie `wget` pozwala pobierać pliki z Internetu za pomocą protokołów HTTP, HTTPS lub FTP. Oto składnia:
```bash
wget [opcje] [URL]
```
Domyślnie polecenie `wget` pobierze element do bieżącego katalogu roboczego. Na przykład uruchom to polecenie, aby pobrać najnowszy instalator WordPressa:
```bash
wget https://wordpress.org/latest.zip
```

## 46. polecenie cURL
Użyj polecenia `cURL`, aby przesłać dane z serwera lub do serwera, określając jego adres URL. Podstawowa składnia wygląda następująco:
```bash
curl [opcje] URL
```
Uruchomienie `cURL` bez opcji spowoduje wydrukowanie zawartości HTML witryny w Twoim Terminalu. Jeśli dodasz opcję `-O` lub `-o`, polecenie pobierze pliki z określonego łącza.

Polecenie `cURL` jest również pomocne w testowaniu punktów końcowych API lub serwera. Możesz to zrobić, dodając opcję `-X`, a następnie metodę HTTP, w zależności od tego, czy chcesz pobrać, czy przesłać dane.

Na przykład poniższe polecenie pobierze dane z określonego punktu końcowego interfejsu API:
```bash
curl -X GET https://api.example.com/endpoint
```

## 47. polecenie scp
Polecenie `scp` pozwala na bezpieczne kopiowanie plików i katalogów między systemami przez sieć. Składnia wygląda następująco:
```bash
scp [opcja] [źródłowa nazwa użytkownika@IP]:/[nazwa katalogu i pliku] [docelowa nazwa użytkownika@IP]:/[katalog docelowy]
```
Jeśli kopiujesz elementy do lub z komputera lokalnego, pomiń adres IP i ścieżkę. Podczas przesyłania pliku lub folderu z komputera lokalnego określ jego nazwę po opcjach.

Na przykład uruchomimy następujące polecenie, aby skopiować plik `file1.txt` do katalogu `path/to/folder` naszego serwera VPS jako użytkownik root:
```bash
scp file1.txt root@185.185.185.185:path/to/folder
```
Możesz zmienić domyślny port SCP, podając jego numer po opcji `-P`. W międzyczasie użyj flagi `-l`, aby ograniczyć przepustowość transferu i dodaj `-C`, aby włączyć kompresję.

## 48. polecenie rsync
Polecenie `rsync` synchronizuje pliki lub foldery między dwoma miejscami docelowymi, aby upewnić się, że mają tę samą zawartość. Składnia wygląda następująco:
```bash
rsync [opcje] źródło miejsce_docelowe
```
Źródło i miejsce docelowe mogą być folderem w tym samym systemie, maszyną lokalną lub serwerem zdalnym. Jeśli synchronizujesz zawartość z VPS, określ nazwę użytkownika i adres IP w następujący sposób:
```bash
rsync /ścieżka/do/lokalnego/folderu/ vps-user@185.185.185.185:/ścieżka/do/zdalnego/folderu/
```
Możesz dodać opcję `-a`, aby zsynchronizować atrybuty pliku lub folderu, w tym ich linki symboliczne. W międzyczasie użyj flagi `-z`, aby włączyć kompresję podczas transferu.

## 49. polecenie ip
Narzędzie `ip` pozwala na wylistowanie i zarządzanie parametrami sieciowymi systemu, podobnie jak polecenie `ifconfig` w starszych dystrybucjach Linuksa. Oto składnia:
```bash
ip [obiekt] [polecenie] [opcje]
```
Uruchomienie tego polecenia bez argumentów spowoduje wydrukowanie podręcznika, łącznie z wyjaśnieniem dopuszczalnych opcji i obiektów.

Aby zarządzać parametrem sieciowym, określ akcję w argumencie polecenia. Na przykład uruchom to, aby wyświetlić adres IP swojego systemu:
```bash
ip addr show
```

## 50. polecenie netstat
Polecenie `netstat` wyświetla informacje o konfiguracji sieciowej systemu. Składnia jest prosta:
```bash
netstat [opcje]
```
Dodaj opcję zapytania o określone informacje sieciowe. Oto kilka flag do użycia:
- `-a` – wyświetla gniazda nasłuchujące i zamknięte.
- `-t` – pokazuje połączenia TCP.
- `-u` – wyświetla połączenia UDP.
- `-r` – wyświetla tabele routingu.
- `-i` – wyświetla informacje o interfejsach sieciowych.
- `-c` – nieprzerwanie wyprowadza informacje o sieci w celu monitorowania w czasie rzeczywistym.

## 51. polecenie traceroute
Polecenie `traceroute` śledzi ścieżkę pakietu podczas podróży między hostami, dostarczając informacji, takich jak czas transferu i zaangażowane routery. Oto składnia:
```bash
traceroute [opcje] cel
```
Możesz użyć nazwy hosta, nazwy domeny lub adresu IP jako miejsca docelowego. Jeśli nie określisz opcji, `traceroute` uruchomi test przy użyciu ustawień domyślnych.

Zmień maksymalną liczbę przeskoków pakietów za pomocą opcji `-m`. Aby zapobiec rozwiązywaniu adresów IP przez `traceroute`, dodaj `-n`.

Można również włączyć limit czasu w sekundach, używając flagi `-w`, po której następuje czas trwania.

## 52. polecenie nslookup
Polecenie `nslookup` żąda od serwera DNS (Domain Name System) sprawdzenia domeny powiązanej z adresem IP lub odwrotnie. Oto składnia:
```bash
nslookup [opcje] domena_lub_ip [serwer_dns]
```
Jeśli nie określisz serwera DNS, `nslookup` użyje domyślnego resolvera Twojego dostawcy usług internetowych. Możesz dodać inne opcje, aby zmienić sposób, w jaki to polecenie wysyła zapytanie o adres IP lub domenę.

Na przykład użyj opcji `-type=`, aby określić informacje, które chcesz sprawdzić, takie jak rekordy DNS.

Można również skonfigurować automatyczne ponawianie prób za pomocą flagi `-retry=` i dodać `-port=`, aby użyć określonego portu.

Ponieważ niektóre dystrybucje Linuksa nie mają tego narzędzia preinstalowanego, możesz napotkać błąd „command not found”. Możesz go skonfigurować, pobierając `bind-utils` lub `dnsutils` za pośrednictwem menedżera pakietów.

## 53. polecenie dig
Polecenie `domain information groper` lub `dig` wyświetla informacje o domenie. Jest podobne do `nslookup`, ale bardziej kompleksowe. Składnia wygląda następująco:
```bash
dig [opcje] [serwer] [typ] nazwa-lub-ip
```
Uruchomienie `dig` bez argumentu spowoduje sprawdzenie rekordów A określonej domeny przy użyciu domyślnego resolvera systemu operacyjnego. Możesz zapytać o konkretny rekord, określając go w argumencie `[type]`, jak w poniższym przykładzie:
```bash
dig MX domena.com
```
Aby uruchomić odwrotne wyszukiwanie DNS, dodaj opcję `-x` i użyj adresu IP jako celu.

## 54. polecenie history
Uruchom polecenie `history`, aby sprawdzić poprzednio uruchomione narzędzia. Oto jego składnia:
```bash
history [opcje]
```
Dodaj opcję `-r`, jeśli chcesz wyczyścić historię terminala. Aby ponownie uruchomić określone narzędzie z listy, wprowadź wykrzyknik, a następnie jego ID.

Na przykład użyj poniższego, aby uruchomić 145. polecenie:
```bash
!145
```

## 55. polecenie man
Polecenie `man` lub manual wyświetla kompleksowy przewodnik innego narzędzia. Składnia wygląda następująco:
```bash
man [opcje] [numer_sekcji] nazwa_polecenia
```
Jeśli podasz tylko nazwę polecenia, `man` wyświetli cały podręcznik. Alternatywnie możesz wybrać jedną z dziewięciu sekcji, używając ich identyfikatorów, aby wydrukować bardziej szczegółowe informacje.

Na przykład uruchom poniższe polecenie, aby sprawdzić sekcję podręcznika polecenia `ls` dotyczącą wywołań bibliotecznych:
```bash
man 3 ls
```
## 56. polecenie echo
Użyj `echo`, aby wydrukować tekst w poleceniu jako wyjście terminala. Oto składnia:
```bash
echo [opcje] [tekst]
```
Możesz również dodać symbol przekierowania (`>`), aby wydrukować tekst w pliku zamiast Terminala. Jeśli użyjesz dwóch symboli (`>>`), dołączy on istniejącą zawartość. Składnia polecenia wygląda następująco:
```bash
echo [opcje] [tekst] > [nazwa_pliku]
```
Jeśli twój tekst zawiera zmienną środowiskową lub powłoki, taką jak `$var`, `echo` wyświetli rzeczywistą wartość. To polecenie jest powszechnie używane do testowania i skryptowania powłoki bash.

## 57. polecenie ln
Polecenie `ln` łączy pliki lub katalogi ze skrótem. Składnia wygląda następująco:
```bash
ln [opcje] źródło cel
```
To polecenie automatycznie utworzy skrót, co oznacza, że nie musisz tworzyć go ręcznie. Na przykład poniższe polecenie umożliwi Ci otwarcie pliku `file.txt` za pomocą skrótu `shortcut.txt`:
```bash
ln file.txt shortcut.txt
```
Domyślnie `ln` tworzy twardy link, co oznacza, że zmiany w źródle zostaną odzwierciedlone w połączonym elemencie i odwrotnie. Aby skonfigurować miękki lub symboliczny link, dodaj opcję `-s`.

## 58. polecenie alias i unalias
Polecenie `alias` pozwala ustawić inną nazwę dla ciągu, który należy do pliku, tekstu, programu lub nazwy polecenia. Oto składnia:
```bash
alias nazwa='string'
```
Na przykład poniższy kod przypisze `k` jako alias poleceniu `kill`, umożliwiając użycie litery zamiast pełnej nazwy:
```bash
alias k='kill'
```
Aby sprawdzić alias polecenia, uruchom `alias`, a następnie alternatywną nazwę. Na przykład sprawdzimy poprzedni fragment kodu:
```bash
alias k
```
Polecenie `alias` pokaże literę powiązaną z poleceniem.

Możesz usunąć alias, uruchamiając następującą składnię:
```bash
unalias [nazwa]
```
## 59. polecenie kal
Polecenie cal wyświetla kalendarz w interfejsie wiersza poleceń Linuxa. Oto składnia:
```bash
cal [opcje] [miesiąc] [rok]
```
Jeśli nie dodasz żadnego argumentu, polecenie pokaże bieżącą datę. Alternatywnie możesz wprowadzić konkretny miesiąc i rok w formacie liczbowym.

Możesz również dodać opcję -3 , aby wyświetlić bieżący, poprzedni i następny miesiąc.

## 60. polecenie apt i dnf
Polecenie apt pozwala zarządzać bibliotekami zaawansowanych narzędzi pakietów (APT) w systemach operacyjnych opartych na Debianie, takich jak Ubuntu i Kali Linux . Składnia wygląda następująco:

podpolecenie 
```bash
apt [opcje]
```
Podpolecenia definiują działanie, takie jak aktualizacja biblioteki, uaktualnienie oprogramowania, instalacja aplikacji lub usunięcie pakietu. Na przykład zainstalujemy edytor tekstu Vim :

apt zainstaluj vim
W Linuksie polecenia zarządzania pakietami różnią się w zależności od dystrybucji. Na przykład dystrybucje oparte na Red Hat Enterprise Linux, takie jak CentOS i AlmaLinux, używają dnf . Ma taką samą składnię i opcje jak apt .