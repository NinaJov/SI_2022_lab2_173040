# SI_2022_lab2_173040
Nina Jovanovik 173040

## 2 baranje
Vo kodot oznacena e sekoja linija kod so reden broj kako komentar dodadeni.
Tie redni broevi se koristat vo Control Flow Graph-ot.

![Control Flow Graph](./cfg.png)

## 3 baranje
N=24 (broj na jazli, oznaceni vo samiot kod)
E=32
V(G)=E-N+2=32-24+2=10

## 4 baranje
LIST0 = list=[]
LIST1 = list[size=9] = ["0", "#", "0", "0", "0", "#", "0", "#", "#"]
LIST2 = list[size=9] = ["0", "#", "0", "#", "0", "#", "0", "#", "#"]
| Node		|Source Line														| LIST0   				  | list[size=2] 			    | LIST1 							       | LIST2								|
|---------------|-----------------------------------------------------------------------------------------------------------------------|-----------------------------------------|-----------------------------------------|------------------------------------------------------------------|----------------------------------------------------------------|
| A		|if (list.size() <= 0)													|  * (sekako se slucuva proverka)	  | * (sekako se slucuva proverka)	    | * (sekako se slucuva proverka)	 			       | * (sekako se slucuva proverka)					|
| B		|throw new IllegalArgumentException("List length should be greater than 0")						|  * ( listata e prazna )	          | (nema da se izvrsi - ne prazna lista)   | (nema da se izvrsi - ne prazna lista)	 		       | (nema da se izvrsi - ne prazna lista) 				|
| C		|int n = list.size()													| ( nema da se izvrsi - frleno exception )| * (sekako se slucuva)		    | *	(sekako se slucuva) 					       | * (sekako se slucuva)						|
| D		|int rootOfN = (int) Math.sqrt(n)											| ( nema da se izvrsi - frleno exception )| * (sekako se slucuva)		    | * (sekako se slucuva)    					       | * (sekako se slucuva)						|
| E		|if (rootOfN * rootOfN  != n)												| ( nema da se izvrsi - frleno exception )| * (sekako se slucuva)		    | * (sekako se slucuva)   					       | * (sekako se slucuva)						|
| F		|throw new IllegalArgumentException("List length should be a perfect square")						| ( nema da se izvrsi - frleno exception )| * (2-ne e perfect square)		    | (nema da se izvrsi - 9=perfect square)			       | (nema da se izvrsi - 9=perfect square)				|
| G		|List<String> numMines = new ArrayList<>()										| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| * (sekako se slucuva)	 				       | * (sekako se slucuva)						|
| H		|for (int i = 0; i < n; i++)												| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| *	(sekako se slucuva) 					       | * (sekako se slucuva)						|
| I		|if (!list.get(i).equals("#"))												| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| *	(sekako se slucuva) 					       | * (sekako se slucuva)						|
| J		|int num = 0														| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| * (sekako se slucuva - ima elementi razlicni od #)	       | * (sekako se slucuva - ima elementi razlicni od #)		|
| K		|if ( (i % rootOfN != 0 && list.get(i - 1).equals("#")) || (i % rootOfN != rootOfN - 1 && list.get(i + 1).equals("#")) )| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| *	(sekako se slucuva - ima elementi razlicni od #) 	       | * (sekako se slucuva - ima elementi razlicni od #)		|
| L		|if ( (i % rootOfN != 0 && list.get(i - 1).equals("#")) && (i % rootOfN != rootOfN - 1 && list.get(i + 1).equals("#")) )| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| *	(sekako se slucuva - ima elementi so imaat ili levo ili desno) | * (sekako se slucuva - ima elementi so imaat ili levo ili desno|
| M		|num += 2														| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| (nema elementi so levo i desno)       			       | * (sekako se slucuva - ima elementi so od dvete strani #)	|
| N		|num  += 1														| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| * (sekako se slucuva - ima elementi so imaat ili levo ili desno) | * (sekako se slucuva - ima elementi so imaat ili levo ili desno|
| O		|if (i - rootOfN >= 0 && list.get(i - rootOfN).equals("#"))								| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| * (sekako se slucuva proverka - ima elemnti razlicni od #)       | * (sekako se slucuva proverka - ima elementi razlicni od #)	|
| P		|num++															| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| *	(sekako se slucuva - ima elementi so bomba nad/pod niv)        | * (sekako se slucuva - ima elementi so bomba nad/pod niv)	|
| Q		|if (i + rootOfN < n && list.get(i + rootOfN).equals("#"))								| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| *	(sekako se slucuva proverka - ima elemnti razlicni od #)       | * (sekako se slucuva proverka - ima elementi razlicni od #)	|
| R		|numMines.add(String.valueOf(num))											| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| * (sekako se slucuva - ima elemnti razlicni od #)	 	       | * (sekako se slucuva - ima elementi razlicni od #)		|
| S		|numMines.add(list.get(i))												| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| *	(sekako se slucuva - ima elemnti #) 			       | * (sekako se slucuva - ima elemnti #)				|
| T		|return numMines													| ( nema da se izvrsi - frleno exception )| ( nema da se izvrsi - frleno exception )| *	(sekako se slucuva - ne se frli exception ni ednas) 	       | * (sekako se slucuva - ne se frli exception ni ednas)		|










