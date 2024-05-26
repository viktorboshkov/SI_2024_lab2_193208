 VIKTOR BOSHKOV 193208 

2. Изработувам CFG дијаграм во онлајн алатка lucidchart

3. икломатската комплексност се пресметува користејќи го методот на McCabe, кој вели дека комплексноста е дадена од формулата:

Цикломатската комплексност може да се пресмета на повеќе начини. Еден начин е да се користи формулата 
M = N - N + 2P

Идентификувани се  7 услови и 2 фор циклуси значи P = 7 + 2 = 9
M = P + 1
M = 9 + 1 = 10
цикломатската комплексност на овој код е 10.


4.


if (allItems == null)

Во случај allItems = null и payment е поголем од 0, ќе се фрли RuntimeException со порака "allItems list can't be null!"
if (item.getName() == null || item.getName().length() == 0)

Кога вредноста на името е null или пак должината на името е 0, а сите други вредности се пополнети и payment е поголем од 0, тогаш задачата ќе продолжи да се извршува бидејќи името ќе се сетира на "unknown".
if (item.getBarcode() != null)

Доколку вредноста на баркодот е null и сите други вредности се пополнети правилно, на пример getName = "Item", getBarcode = "2r13f", getPrice = 100, getDiscount = 0.20, тогаш ќе се фрли RuntimeException со порака "No barcode!"
if (allowed.indexOf(c) == -1)

Ако баркодот содржи невалидни знаци, тогаш ќе се фрли RuntimeException со порака "Invalid character in item barcode!"
if (item.getDiscount() > 0)

Кога вредноста на попустот е поголема од 0, на пример 0.2, и ако цената на предметот е 100, тогаш сумата ќе се зголеми за 20 (100 * 0.2).
if (item.getDiscount() > 0)

Ако вредноста на попустот не е поголема од 0, тогаш цената на производот ако изнесува 100, сумата ќе остане 100.
if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0')

Со влезни параметри getName = "Item1", getBarcode = "03m23", getPrice = 400, getDiscount = 0.10, сумата ќе биде 40 по одземените 30.
if (sum <= payment)

Ако влезниот параметар за payment е поголем од сумата, резултатот ќе биде true. На пример, ако getPrice = 100 и getDiscount = 10, а payment = 50, тогаш sum = 10 и овој услов ќе враќа true. Ако payment = 9, тогаш овој услов ќе враќа false.
if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0')

За вредности getName = "Item1", getBarcode = "01234", getPrice = 310, getDiscount = 0.10, условот е точен, па сумата се намалува за 30.
if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) != '0')

За вредности getName = "Item1", getBarcode = "12345", getPrice = 310, getDiscount = 0.10, условот е точен, па сумата не се намалува за 30.
if (item.getPrice() > 300 && item.getDiscount() <= 0 && item.getBarcode().charAt(0) != '0')

За вредности getName = "Item1", getBarcode = "0234", getPrice = 310, getDiscount = -1.10, условот е невистинит и сумата не се намалува.
if (item.getPrice() <= 300 && item.getDiscount() <= 0 && item.getBarcode().charAt(0) != '0')

За вредности getName = "Item1", getBarcode = "234", getPrice = 300, getDiscount = -1.10, условот е точен и сумата ќе се намали за 30.
if (item.getPrice() <= 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) != '0')

За вредности getName = "Item1", getBarcode = "234", getPrice = 300, getDiscount = -1.10, условот не е точен и сумата нема да се намали.
if (item.getPrice() <= 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0')

За вредности getName = "Item1", getBarcode = "0234", getPrice = 300, getDiscount = 0.10, условот е точен и сумата ќе се намали.
if (item.getPrice() <= 300 && item.getDiscount() <= 0 && item.getBarcode().charAt(0) == '0')

За вредности getName = "Item1", getBarcode = "234", getPrice = 300, getDiscount = -0.10, условот не е точен и сумата нема да се намали.
if (item.getPrice() > 300 && item.getDiscount() <= 0 && item.getBarcode().charAt(0) == '0')

За вредности getName = "Item1", getBarcode = "0234", getPrice = 350, getDiscount = -0.10, условот е точен и сумата ќе се намали.





5.


if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0') за вредности getName="Item1", getBarcode="01234", getPrice=310, getDiscount=0.10 условот е точен при што истиот се извршува и сумата се намалува за 30
if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) != '0') за вредности getName="Item1", getBarcode="01234", getPrice=310, getDiscount=0.10 уловот е точен и вредноста треба да се намали за 30

if (item.getPrice() > 300 && item.getDiscount() <= 0 && item.getBarcode().charAt(0) != '0') за вредности getName="Item1", getBarcode="0234", getPrice=310, getDiscount=-1.10 условот е невистинит и сумата не се намалува

if (item.getPrice() <= 300 && item.getDiscount() <= 0 && item.getBarcode().charAt(0) != '0') за вредности getName="Item1", getBarcode="234", getPrice=300, getDiscount=-1.10 условот е точен и сумата ќе за намали за 30

if (item.getPrice() <= 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) != '0') за вредности getName="Item1", getBarcode="234", getPrice=300, getDiscount=-1.10 условот не е точен и сумата нема да се намали

if (item.getPrice() <= 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0') за вредности getName="Item1", getBarcode="0234", getPrice=300, getDiscount=0.10 условот е точен и сумата ќе се намали

if (item.getPrice() <= 300 && item.getDiscount() <= 0 && item.getBarcode().charAt(0) == '0') за вредности getName="Item1", getBarcode="234", getPrice=300, getDiscount=-0.10 условот не е точен и сумата нема да се намали

if (item.getPrice() > 300 && item.getDiscount() <= 0 && item.getBarcode().charAt(0) == '0') за вредности getName="Item1", getBarcode="0234", getPrice=350, getDiscount=-0.10 условот е точен и сумата ќе се намали



