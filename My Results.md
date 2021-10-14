# Här är mina resultat hittils:

I den här filen ska ni beskriva:
- Era experiment
- Era slutsatser

## Svar till frågor på del 7:
# a.
- Det går snabbare om man ökar hastigheten (lr) till en viss gräns. I vårat fall så ger värdet lr=0.1 den snabbaste tiden. Men när vi testar med högre värden såsom 0.5 och 10.0 så    ger inte det någon snabbare tid. 

- Det verkar som att det finns en gräns för hur högt optimalt värde på lr man kan ha. När man sätter ett högt värde så påverkas inte träningstiden så mycket men värdena på epoch_loss  och epoch_accuracy blir mycket sämre.

-  I figurerna: "a_epoch_accuracy" och "a_epoch_loss" så kan man tydligt se en tydlig skillnad på värdena. De två linjer som avviker sig väldigt mycket ifrån de andra linjerna är resultaten då lr är satta till 10.0 och 1000.0


# b. 
- Ju mer man sänker värdet på batch_size desto bättre/önskvärda blir värdena, dock så tar träningen längre tid.

- I figurerna: "b_epoch_accuracy" och "b_epoch_loss" så ser vi resultaten på experimentent med olika batch_size värden. De olika värden som testats är: 256, 200, 150 och 100.


# c.
- Träningstiden mellan de olika modellerna skiljer sig väldigt mycket. Träningen för "convolutional model" tog ungefär 9 gånger längre tid att träna än den "vanliga" modellen.

- Anledningen till varför träningstiden är längre för convolutional model är för att den analyserar en bild mycket djupare än ett normalt nätverk och innehar ett såkallat convolutional layer som är bra för att fånga "lokal"information (t.ex. grannpixlar i en bild eller omgivande ord i en text) samt för att minska modellens komplexitet. Kort sagt kan man säg att modellen analyserar bilden bit för bit i med avsikt att på att få ett bättre resultat på vad det egentligen är på bilden. Detta leder i sin tur att analysering samt träningen tar längre tid att genomföra än det gör för den vanliga modellen.



## Glöm inte!
Glöm inte att ha med figurer:
![TensorBoard download](fig/TensorBoardDownload.png "Glöm inte att kryssa i 'Show data download links' så att ni kan ladda ner era filer.")
