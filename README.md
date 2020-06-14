# Aplicatii Distribuite Avansate
# Lab1
A fost implementata procesarea cu ajutorul TPL (OpenMP) si AKKA.NET (OpenMPI). Pe parcursul lucrarii s-a facut o paralela intre aceste 2 metodologii. Totodata a fost testata aplicatia cu Sleepy Fibonacci si Busy Fibonacci.

# TPL sleepy
![image](https://user-images.githubusercontent.com/26895687/84590177-f2066e80-ae3c-11ea-8e37-6074b6ef6d3a.png)

# TPL busy
![image](https://user-images.githubusercontent.com/26895687/84590191-15311e00-ae3d-11ea-9018-b04e8ed19d26.png)

Se observa ca atunci cind rulam Bussy Fibonacci cu mai multe fire de executie - timpul de executie creste mai rapid ca cel cind utilizam sleepy Fibonacci. Asta se datoreaza faptului ca busy fibonacci va consuma resursele procesorului mai drastic ca sleepy fibonacci. Sleepy fibonacci presupune adormirea firului de executie, astfel se reduce consumul.

# AKKA.Net sleepy
![image](https://user-images.githubusercontent.com/26895687/84590225-693c0280-ae3d-11ea-9d6e-4ed427700866.png)

# AKKA.Net busy
![image](https://user-images.githubusercontent.com/26895687/84590237-7c4ed280-ae3d-11ea-8a2c-9b604395733e.png)

# TPL vs AKKA
![image](https://user-images.githubusercontent.com/26895687/84590250-97214700-ae3d-11ea-85e1-018c4015af18.png)

# Concluzie
Daca sa facem o paralela intre aceste doua abordari: Timpul de executie in cazul cu TPL este un pic mai mic. Asta se datoreaza faptului ca nu este nevoie sa sincronizam actorii si sa transmitem mesaje la actori, insa totodata AKKA.NET permite o decuplare mai eficienta. Pe linga aceasta AKKA.NET permite incapsularea acestui proces de concurenta. Noi nu avem de afacere cu fire de executie, fiecare actor ruleaza pe firul sau de executie si este adormit atit timp cind nu primeste mesaje. Cu ajutorul AKKA.NET se poate foarte eficient de asigurat comunicare intre aplicatii aflate la distanta si prelucrarea mesajelor.

In momentul cind numarul de fire de executie depaseste numarul de fire de executie a procesorului, timpul de executie creste.
