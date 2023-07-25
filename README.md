# Sonic in Spatiu: 
Sonic in Spatiu este un joc de acuratete ce are scopul utilitar de a creste timpul de reactie. Pentru un copil, timpul de reactie este in stransa legatura cu dezvoltarea mintala a acestuia.
Site-ul jocului: https://www.sonicinspace.eu/
Trailer: https://www.youtube.com/watch?v=_kI8zGOssqQ
# Instructiuni:
Jocul se prezinta foarte simplu, dar in spate exista o complexitate foarte mare.
Extrageti din #release ultima versiune a jocului si deschideti PsychEngine.exe.
Veti observa un meniu cu 4 butoane. Apasati pe ***Story Mode*** si de acolo selectati primul joc, apasand Enter. Recomand pentru incepatori sa joace pe dificultatea **Easy** 
Veti observa un cutscene cu un tutorial. Controalele sunt WASD/Arrow Keys, dar pot fi schimbate din butonul ***Optiuni***
Jocul a inceput, have fun!

# Pentru celelalte butoane

La al doilea buton, ***Freeplay*** Puteti selecta ce melodie doriti, fara cutscene/dialog.
Al treilea buton ***Donati***, va redirectioneaza catre o pagina de donatii.
Al patrulea buton ***Optiuni*** va puteti schimba controalele, sa modificati grafica, fps-urile, culorile de pe sageti, etc.

# Documentatia propriu zisa:

Sonic in spatiu a fost facut in framework-ul Haxe, impreuna cu engine-ul PsychEngine.
Haxe este un limbaj de programare și un compilator multiplatforme de nivel înalt care poate produce aplicații și source code, pentru multe platforme de calcul diferite dintr-un code-base.

# FL Studio 20

Este un program de editare muzicala, foarte complex. In acest program toate melodiile sunt compuse de mine. Fiecare melodie vine cu un instrumental si vocals. Acestea vor fi randate in doua fisiere audio de tip .ogg care se pun separat in joc. La instrumental, am folosit plugin-urile: Genny, Genesis. Se pot face atat melodii moderne, cat si melodii pixelate. Pe parte de Voice o sa auziti vocea caracterelor. De exemplu caracterul Sonic.exe pixelat din melodia Fun-In-Space a fost facut cu vocea mea, inregistrand aceste 5 sunete: Aiii, Eeeee, Eeiii, Eoooouu, Ouuu. Din aceste 5 sunete am facut 45, diferenta dintre ele fiind frecventa, le-am adaugat in piano roll, apoi am scazut pitch-ul la 12 si am adaugat efectele: Chorus, Soundgoodizer, FX, Reeverb, Delay. Restul caracterelor functioneaza si ele pe acelasi principiu.

# Adobe Animate

Este un program de editare vizuala. M-a ajutat sa creez animatiile personajelor. De exemplu caracterul Sonic.exe a fost desenat de mine in ***Photoshop*** pentru fiecare miscare in parte: Idle, Right pose, Left pose, Down pose, Up pose. Pentru fiecare pose, am separat desenul intreg pe bucati, maini, cap, corp. Le-am separat deoarece in ***Adobe Animate*** fiecare parte are cate o frecventa diferita. Pe acest caracter, s-au facut 11 cadre pentru fiecare pose in parte. Pentru a nu desena de 11 ori caracterul de la 0, desenul original a fost deformat pentru fiecare cadru in parte cu o intensitate de loop, astfel incat sa se individualizeze un sprite sheet smooth. Restul caracterelor functioneaza si ele pe acelasi principiu.

# HaxeFlixel

 In acest framework am facut UI-ul jocului, unde am folosit diferite efecte. De exemplu pe meniul principal, unde se regasesc cele patru butoane, am facut o animatie si am adaugat coordonate x,y in fisierul MainMenuState.hx din source

				{
					case 0: 
						menuItem.y = 34.95;
						menuItem.x = 659.4;

					case 1: 
						menuItem.y = 193.75;
						menuItem.x = 629.8;

					case 2:
						menuItem.y = 393;
						menuItem.x = 576.5;
					case 3:
						menuItem.y = 712.9;
						menuItem.x = 494.75;
			}
			if(FlxG.save.data.antialiasing)
				{
				 menuItem.antialiasing = true;
				}
			   if (firstStart)
				FlxTween.tween(menuItem,{y: 60 + (i * 160)},1 + (i * 0.25) ,{ease: FlxEase.expoInOut, onComplete: function(flxTween:FlxTween) 
				 { 
				  
				  changeItem();
				 }});
			   else
				menuItem.y = 60 + (i * 160);

Totodata in acest framework se afla baza jocului in sine. Acest joc de acuratete, fiind compus din 4 sageti, are ca si scop sa interactioneze cu un anumit caracter, ce urmeaza directia unei sageti. Daca sageata este cu directia spre Nord, caracterul va activita animatia Up pose.
Am folosit pentru fiecare melodie niste evenimente, ce se adauga in PsychEngine si se randeaza cu un fisier de timp: events.json, ce functioneaza pe baza unui scrip. De exemplu sa zicem ca vrem sa adaugam un efect de flash. Am facut fisierul ***Flash camera.lua*** ce contine informatii principale despre activarea unei functii flash:
    { 
        if n == 'Flash Camera' then
	   makeLuaSprite('flash', '', 0, 0);
        makeGraphic('flash',1280,720,'ffffff')
	      addLuaSprite('flash', true);
          setLuaSpriteScrollFactor('flash',0,0)
	      setProperty('flash.scale.x',2)
	      setProperty('flash.scale.y',2)
    }    
La fel si pentru creerea unui stage, se aplica setari asemanatoare

# PsychEngine
Este un engine special pentru jocurile de acuratete, care este Open-Source si urmareste modelul FNF. Acest engine practic m-a ajutat sa pun mult mai usor sagetile din joc, ce vine cu o gama variata de optiuni complexe. Am facut in acest engine chart-ul din jocul meu, adica am asezat sagetile individual, astfel incat sa pice pe ritm cum trebuie. Pe fiecare melodie am facut 3 chart-uri pentru fiecare dificultate. Pe parte de cod, informatiile se salveaza aici pentru fiecare melodie: bin\mods\data. Totodata optiunea de events este inserata tot in acest engine. Pentru a face un chart, in joc exista o comanda secreta. Din meniul principal trebuie apasat butonul 7, dupa vom da jos spre Chart Editor si de acolo ne selecom melodia pe care am pus-o in fisierele jocului. 
# Credits
Sega Sonic Team: Yuji Naka, Naoto Ohshima, Hirokazu Yasuhara
Psych Engine Team: shadowmario, river, shubs
FNF crew: ninjamuffin99, phantomarcade, evilsk8r, kawaisprite
Vs Sonic.exe Team: SasterCommandoDev, MarStarBro (Formerly), averyavary (Formerly), Revie (Formerly), RightBurst_Ultra (Formerly)  
# Analiza pieței
Sonic In spatiu, este un joc de ritmica, asemanator cu Osu-mania, pe modelul FNF.
Imbunatatiri, reprezinta faptul ca in Osu, ca si parte de UI, poate fi plictisitor pentru unii jucatori. Sonic in Spatiu, contine in plus anumite personaje si o poveste. Jocul Osu-Mania este bazat doar pe sageti, in timp ce Sonic In Spatiu contine Sprite Sheet-uri. Pe langa acest lucru se individualizeaza si categoria Events, de unde am adaugat efectele de Flash si de Cinematics atunci cand se intampla ceva important in joc, in Osu mania, Fnf, nu exista acesta optiune.
#  Planificarea dezvoltarii
Am planificat sa folosesc limbajul de programare Haxe, deoarece este foarte prietenos cu developerul. Atunci cand fac o greseala in cod si dau compile din CMD se individualizeaza automat greseala si iti spune ce sa modifici. Din punctul meu de vedere este limbajul perfect de programare pentru a face jocuri de ritmica. Aici m-am ocupat de UI, de punerea sagetilor. Apoi am folosit Adobe Animate pentru a face animatiile de pe caractere, adica sprite sheed-urile, iar in FL Studio 20, am compus melodiile. Jocul este optimizat si nu consuma foarte mult RAM si CPU.
# Maturitatea aplicație
Aplicatia este pregatita 100% si deja este lansata pentru public.
Dar contine si versiunile vechi, unde au fost anumite bug-uri care in versiunea finala nu mai exista.

