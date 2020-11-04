# Таблиці таксонів орнітофауни світу (за IOC World Bird List v10.2), підготовлені для імпорту у середовище СКБД

## Загальна інформація

Репозиторій містить 5 окремих таблиць (для кожного таксономічного рівня від ряду до підвиду), які укладені у формі, що дозволяє швидко імпортувати їх у середовище будь-якої системи керування базами даних. Це забезпечується форматом представлення даних (csv), а також тим, що в таблицях вже визначені поля первинних (Primary key) та зовнішніх (Foreign key) ключів.

Таблиці укладені на основі IOC World Bird List v10.2<sup>1</sup>. Безпосереднім джерелом даних для таблиць був використаний файл [IOC_Names_File_Plus-10.2_full_ssp.xlsx](http://www.worldbirdnames.org/IOC_Names_File_Plus-10.2_full_ssp.xlsx "IOC_Names_File_Plus-10.2_full_ssp.xlsx"). Крім того, до таблиці зі списком видів були додані українські назви птахів за Г. В. Фесенком<sup>2</sup>. Власне джерелом українських назв був файл [Multiling IOC 10.2_b.xlsx](http://worldbirdnames.org/Multiling%20IOC%2010.2_b.xlsx "Multiling IOC 10.2_b.xlsx").

## Специфікації

### Загальні специфікації

 Таблиці представлені у форматі csv. У якості роздільника полів використаний символ ";". Вміст текстових полів позначений подвійними лапками.

### Специфікації окремих таблиць

#### Файл Order_IOC_V10_2.csv

Файл містить перелік 40 рядів орнітофауни світу

##### Опис полів

1. OrderID (INT) — унікальний ідентифікатор ряду (Primary key); значення ідентифікаторів рядів ідентичні таким у файлі IOC_Names_File_Plus-10.2_full_ssp.xlsx;
2. OrderSc (VARCHAR) — наукова назва ряду;
3. Code (VARCHAR) — коди статусу;
4. Comment (TEXT) — інформація щодо таксономічних змін у даній версії списку, а також посилання на літературні джерела, на основі яких ці зміни були внесені.

#### Файл Familia_IOC_V10_2.csv

Файл містить перелік 252 родин орнітофауни світу

##### Опис полів

1. OrderID_idx — (INT) — ідентифікатор ряду (Foreign key);
2. FamilyID (INT) — унікальний ідентифікатор родини (Primary key); значення ідентифікаторів родин ідентичні таким у файлі IOC_Names_File_Plus-10.2_full_ssp.xlsx;
3. NumberOfSpecies (INT) — кількість видів у родині;
4. EnglishName (VARCHAR) — англійська назва родини;
5. FamilySc (VARCHAR) — наукова назва родини
6. Code (VARCHAR) — коди статусу;
7. Comment (TEXT) — інформація щодо таксономічних змін у даній версії списку, а також посилання на літературні джерела, на основі яких ці зміни були внесені.


#### Файл Genus_IOC_V10_2.csv

Файл містить перелік 2359 родів орнітофауни світу

##### Опис полів

1. FamilyID_idx (INT) — ідентифікатор родини (Foreign key);
2. GenusID (INT) — унікальний ідентифікатор роду (Primary key); значення ідентифікаторів родів ідентичні таким у файлі IOC_Names_File_Plus-10.2_full_ssp.xlsx;
3. Extinct (INT) — вимерлі роди (позначаються числами 1 та 2);
4. GenusSc (VARCHAR) — наукова назва роду;
5. Authority (VARCHAR) — автор та рік опису таксону;
6. Code (VARCHAR) — коди статусу;
7. Comment (TEXT) — інформація щодо таксономічних змін у даній версії списку, а також посилання на літературні джерела, на основі яких ці зміни були внесені.

#### Файл Species_IOC_V10_2.csv

Файл містить перелік 10787 нині існуючих видів птахів, а також 158 видів птахів, що вимерли.

##### Опис полів

1. GenusID_idx (INT) — ідентифікатор роду (Foreign key);
2. SpeciesID (INT) — унікальний ідентифікатор виду (Primary key); значення ідентифікаторів видів ідентичні таким у файлі IOC_Names_File_Plus-10.2_full_ssp.xlsx;
3. Extinct (INT) — вимерлі види (позначаються числами 1 та 2);
4. SpeciesEn (VARCHAR) — англійська назва виду;
5. SpeciesSc (VARCHAR) — наукова назва виду;
6. Authority  (VARCHAR) — автор та рік опису таксону;
7. BrRange (VARCHAR) — гніздовий ареал виду;
8. NonbrRange (VARCHAR) — негніздовий ареал виду;
9. Code (VARCHAR) — коди статусу;
10. Comment (TEXT) — інформація щодо таксономічних змін у даній версії списку, а також посилання на літературні джерела, на основі яких ці зміни були внесені.


#### Файл Subspecies_IOC_V10_2.csv

Файл містить перелік 20003 підвидів птахів.

##### Опис полів

1. SpeciesID_idx (INT) — ідентифікатор виду (Foreign key);
2. SspID (INT) — унікальний ідентифікатор підвиду (Primary key); значення ідентифікаторів підвидів ідентичні таким у файлі IOC_Names_File_Plus-10.2_full_ssp.xlsx;
3. Extinct (INT) — вимерлі підвиди (позначені числом 1);
4. SspSc (VARCHAR) — наукова назва підвиду;
5. Authority (VARCHAR) — автор та рік опису таксону;
6. BrRange (VARCHAR) — гніздовий ареал підвиду;
7. NonbrRange (VARCHAR) — негніздовий ареал підвиду;
9. Code (VARCHAR) — коди статусу;
10. Comment (TEXT) — інформація щодо таксономічних змін у даній версії списку, а також посилання на літературні джерела, на основі яких ці зміни були внесені.

The repository contains five tables with lists of birds taxa of the world fauna. These tables are designed for using bird taxonomy in a databases. Each of the tables contains a list of one of the five levels of bird taxa (order, family, genus, species, subspecies). The IOC World Bird List V. 10.2 was used for create the tables.

<sup>1</sup> Gill, F., Donsker, D., & Rasmussen, P. (Eds). 2020. IOC World Bird List (v10.2) [Data set]. World Bird Names. https://doi.org/10.14344/IOC.ML.10.2.
<sup>2</sup> Фесенко, Г. В. 2018. Вітчизняна номенклатура птахів світу. Видавець ФО-П Чернявський Д. О. („Діонат”), Кривий Ріг, 1–580.

<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/3.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/3.0/">Creative Commons Attribution 3.0 Unported License</a>.
