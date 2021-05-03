## Základ
1. Nejpoužívanější je .cmd
2. Na začátek by se vždy mělo napsat
* `@echo off` 
## Podmínky
* Kontroluji zda soubor existuje
 ``` IF EXIST "soubor.txt" ECHO fakticky existuje ```
* Kontroluji zda soubor neexistuje
``` IF NOT EXIST "soubor.txt" ECHO mrzí mě to :( bylo pozdě ```
* Kontroluji zda soubor existuje pokud ne vykonám else
``` 
    IF EXIST "soubor.txt"( 
      ECHO fakticky existuje
    )
    ELSE(
      ECHO mrzí mě to
    )
```
* ZDA proměnná je stejná jako proměnná
```
  SET promenna=Nazdar
  IF "%promenna%"=="Nazdar"(
    ECHO %promenna%
  )
```
** S použitím přepínače /I nebude rozlišovat malá a velká písmena
  ```
  IF /I "%promenna%"=="Nazdar"()
```
* Operátory
```
SET /A var=1

IF /I "%var%" EQU "1" ECHO stejné

IF /I "%var%" NEQ "0" ECHO není stejné

IF /I "%var%" GEQ "1" ECHO větší nebo stejné

IF /I "%var%" LEQ "1" ECHO menší nebo stejné
```
## Proměnné
* Pomocí slovíčka set nastavujeme proměnné
    ```
      SET foo=3
      SET fo=foo+3
    ```
* Vstup odchytáváme do proměnných takhle:
    ```
      SET /p foo=
    ```
* S proměnnýma pracujeme pak už vždy v procentech
    ```
      %proměnná%
    ```
## Výstup
* Používáme příkaz echo
    ```
      echo Doopravdy neznám %proměnná%
    ```
## Cykly
* GOTO
    ```
     :zacatek
    ECHO Jsem zacyklen
    GOTO :zacatek
    ```
* For
** Přejíždím soubory ve složce
  ```
  FOR %SOUBOR IN (%USERPROFILE%\*) DO @ECHO %SOUBOR
  ```
** Přejíždím složky
  ```
  FOR /D %SLOZKA IN (%USERPROFILE%\*) DO @ECHO %SLOZKA
  ```
 ## Pauza
 ```
 pause
 ```
 * bez zeptání
  ```
 pause>nul
 ```
