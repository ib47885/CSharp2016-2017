# JMBAG
0036478852

#Pitanje1
U Bin/Debug folderu konzolne aplikacije pojavili su se još i ClassLibrary1.dll i ClassLibrary1.pdb.

Kada se pobriše ClassLibrary.dll i pokuša pokrenuti KonzolnaAplikacija.exe
kompajler baca Unhandled Exception: System.IO.FileNotFoundException: Could not load file or assembly 'ClassLibrary1'.

Baca je jer aplikacija KonzolnaAplikacija.exe za izvršavanje koristi metodu iz klase ClassLibrary1 pa za njeno ispravno
izvršavanje potrebno je imati i .dll file. Jer kada se pokreæe exe koji referencira dll, moraju biti oba dostupna pri pokretanju exe programa u istom folderu.
Zato bi pri slanju exe programa morala poslati i sve dll-ove koje exe referencira, a koji nisu u GAC-u.


#Pitanje2
Nakon mijenjanja sadržaja metode u ClassLibrary1 i ponovnog pokretanja KonzolneAplikacije klikom na KonzolnaAplikacija.exe u Bin/Debug direktoriju,
ispisao se stari string jer se pri tom koristi stari dll od ClassLibrary1. Pokretanjem KonzolneAplikacije u Visual Studiu pomoæu F5 ispisao se novi string jer 
se prevoðenjem KonzolneAplikacije prevodi i sve što ona referencira.


#Pitanje3
Pokretanjem KonzolneAplikacije iz Visual Studia ispisalo se Pero: Hello World.


#Pitanje4
Nakon dodavanja PeroClassLibrary.dll kao referencu KonzolnojAplikaciji, PeroClassLibrary.dll se doda(kopira) u Bin/Debug direktorij.


#Pitanje5
Ako se obriše originalni dll sa diska (iz originalnog foldera, a ne iz Bin/Debug), u Bin/Debug i dalje ostaje kopija koja se koristi u listi referenci.


#Pitanje6
Nakon brisanja NodaTime direktorija unutar packages direktorija u solutionu i buildanja KonzolneAplikacije nakon toga, aplikacija je radila normalno, a u 
packages direktoriju ponovno se generirao NodaTime direktorij sa istim sadržajem kao prije brisanja.
