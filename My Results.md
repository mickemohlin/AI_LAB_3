# Svar till frågor på del 7:
## a.
- Det går snabbare om man ökar hastigheten (lr) till en viss gräns. I vårat fall så ger värdet lr=0.1 den snabbaste tiden. Men när vi testar med högre värden såsom 0.5 och 10.0 så    ger inte det någon snabbare tid. 

- Det verkar som att det finns en gräns för hur högt optimalt värde på lr man kan ha. När man sätter ett högt värde så påverkas inte träningstiden så mycket men värdena på epoch_loss  och epoch_accuracy blir mycket sämre.

-  I figurerna: "a_epoch_accuracy" och "a_epoch_loss" så kan man tydligt se en tydlig skillnad på värdena. De två linjer som avviker sig väldigt mycket ifrån de andra linjerna är resultaten då lr är satta till 10.0 och 1000.0


## b. 
- Ju mer man sänker värdet på batch_size desto bättre/önskvärda blir värdena, dock så tar träningen längre tid.

- I figurerna: "b_epoch_accuracy" och "b_epoch_loss" så ser vi resultaten på experimentent med olika batch_size värden. De olika värden som testats är: 256, 200, 150 och 100.


## c.
- Träningstiden mellan de olika modellerna skiljer sig väldigt mycket. Träningen för "convolutional model" tog ungefär 9 gånger längre tid att träna än den "vanliga" modellen.

- Anledningen till varför träningstiden är längre för convolutional model är för att den analyserar en bild mycket djupare än ett normalt nätverk och innehar ett såkallat convolutional layer som är bra för att fånga "lokal"information (t.ex. grannpixlar i en bild eller omgivande ord i en text) samt för att minska modellens komplexitet. Kort sagt kan man säg att modellen analyserar bilden bit för bit i med avsikt att på att få ett bättre resultat på vad det egentligen är på bilden. Detta leder i sin tur att analysering samt träningen tar längre tid att genomföra än det gör för den vanliga modellen.


## d.
- På bilderna "d_moved_data", "d_rotated_data" och "d_test_data" kan man se skillnaderna på resulteten mellan den normala och konvolutionella modellen.
    - Vänstra delen på bilderna: Normala modellens resultat.
    - Högra delen på bilderna: Konvolutionella modellens resultat.

- Resultaten mellan de olika testseten skiljer sig ganska så markant. Anlendningen till varför man kan se en skillnad på resultaten är för att datan som modellerna får in som input har olika format. Datan som är "normal" är enklare för modellerna att tolka och förutsäga till skillnad mot siffrorna som exempelvis är roterade.

- Skillnaderna på resultaten (Average accuracy) mellan de olika datasetsen är inte riktigt samma för modellerna.
    - Skillnad på resultat mellan moved och rotated:
        - Normal Model: 62.15
        - Convolutional Model: 68.57
    - Skillnad på resultat mellan rotated och test:
        - Normal Model: 18.84
        - Convolutional model: 10.94

## e.
- Ju mer neuroner man lägger till i ett lager desto bättre blir average accuracy, dock så tar träningen längre tid.

- Resultat (Average Accuracy) av olika neuroner:
    - 4 neuroner: 82.71 (25s)
    - 8 neuroner: 91.07 (21s)
    - 16 neuroner: 92.44 (23s)
    - 32 neuroner: 93.10 (24s)
    - 64 neuroner: 93.69 (27s)
    - 128 neuroner: 93.84 (39s)
    - 256 neuroner: 93.98 (56s)
    - 512 neuroner: 94.18 (1m 28s)
    - 1024 neuroner: 94.39 (2m 54s)
    - 2048 neuroner: 94.52 (5m 14s)

- Den undre gränsen är nog på 8 neuroner eftersom att träningstiden är som minst då samt att average accuracy håller sig över 90. Efter det så verkar värdet försämras rätt så drastiskt samt så ökar träningstiden.

- Det verkar inte finns någon övre gräns på hur många neuroner man ska ha, ju fler man har desto bättre resultat får man. Men om man inte vill vänta allt för länge på träningen så skulle jag säga att 64 neuroner är en bra gräns, med avseende på resultat och tid.


## f.
- De olika testade värdena är:
    1. kernel_size: (8,8), strides: (1,1) --> Average Accuracy: 97.40 (9m 48s)
    2. kernel_size: (8,8), strides: (2,2) --> Average Accuracy: 96.85 (2m 25s)
    3. kernel_size: (12,12), strides: (1,1) --> Average Accuracy: 97.40 (8m 20s)
    4. kernel_size: (12, 12), strides: (2,2) --> Average Accuracy: 97.01 (2m 33s)
    5. kernel_size: (13, 13), strides: (1,1) --> Average Accuracy: 97.56 (9m 38s)
    6. kernel_size: (14, 14), strides: (1,1) --> Average Accuracy: 97.27 (8m 14s)
    7. kernel_size: (16,16), strides: (1,1) --> Average Accuracy: 96.58 (8m 15s)
    8. kernel_size: (14,14), strides: (3,3) --> Average Accuracy: 94.82 (1m 18s)
    9. kernel_size: (16,16), strides: (1,1) --> Average Accuracy: 96.58 (8m 15s)

- Slutsats:
    - När värdet på "strides" ökar, så minskar därmed prestandan, det optimala värdet enligt resultatet på dessa tester är: (1,1)
    - När värdet på "kernel_size" överstiger (13,13) så minskar prestandan, med det sagt så är det optimala värdet (13,13)
    - De bästa värdena för att få så bra prestanda som möjligt och inte bryr sig om hur lång tid det tar är då kernel_size: (13,13) och strides: (1,1).


## g.
- Testade antal lager och dess resultat på den "vanliga modellen"
    1. 1 lager --> Time: 23s | Rotated Data: 76.17 | Moved Data: 12.65 | Test Data: 93.28
    2. 2 lager --> Time: 24s | Rotated Data: 75.84 | Moved Data: 13.40 | Test Data: 93.86
    3. 3 lager --> Time: 25s | Rotated Data: 79.85 | Moved Data: 13.11 | Test Data: 94.81
    4. 4 lager --> Time: 26s | Rotated Data: 79.88 | Moved Data: 13.91 | Test Data: 94.29
    5. 5 lager --> Time: 26s | Rotated Data: 79.37 | Moved Data: 14.70 | Test Data: 94.65
    6. 6 lager --> Time: 27s | Rotated Data: 77.13 | Moved Data: 15.05 | Test Data: 95.36
    7. 7 lager --> Time: 29s | Rotated Data: 78.53 | Moved Data: 14.49 | Test Data: 94.89
    8. 8 lager --> Time: 29s | Rotated Data: 77.84 | Moved Data: 13.59 | Test Data: 94.50

- Slutsats: 
    - Tiden ökar med ungefär en sekund med varje lager man lägger till.
    - För rotated data så ökar precisionen fram till 4 lager och därefter så sjunker det om man lägger till fler lager.
    - För moved och test data så ökar precisionen fram till 6 lager och sjunker därefter efter ytterligare lager.

