# JMBAG
0036478852

#Pitanje1
U Bin/Debug folderu konzolne aplikacije pojavili su se jo� i ClassLibrary1.dll i ClassLibrary1.pdb.

Kada se pobri�e ClassLibrary.dll i poku�a pokrenuti KonzolnaAplikacija.exe
kompajler baca Unhandled Exception: System.IO.FileNotFoundException: Could not load file or assembly 'ClassLibrary1'.

Baca je jer aplikacija KonzolnaAplikacija.exe za izvr�avanje koristi metodu iz klase ClassLibrary1 pa za njeno ispravno
izvr�avanje potrebno je imati i .dll file. Jer kada se pokre�e exe koji referencira dll, moraju biti oba dostupna pri pokretanju exe programa u istom folderu.
Zato bi pri slanju exe programa morala poslati i sve dll-ove koje exe referencira, a koji nisu u GAC-u.


#Pitanje2
Nakon mijenjanja sadr�aja metode u ClassLibrary1 i ponovnog pokretanja KonzolneAplikacije klikom na KonzolnaAplikacija.exe u Bin/Debug direktoriju,
ispisao se stari string jer se pri tom koristi stari dll od ClassLibrary1. Pokretanjem KonzolneAplikacije u Visual Studiu pomo�u F5 ispisao se novi string jer 
se prevo�enjem KonzolneAplikacije prevodi i sve �to ona referencira.


#Pitanje3
Pokretanjem KonzolneAplikacije iz Visual Studia ispisalo se Pero: Hello World.


#Pitanje4
Nakon dodavanja PeroClassLibrary.dll kao referencu KonzolnojAplikaciji, PeroClassLibrary.dll se doda(kopira) u Bin/Debug direktorij.


#Pitanje5
Ako se obri�e originalni dll sa diska (iz originalnog foldera, a ne iz Bin/Debug), u Bin/Debug i dalje ostaje kopija koja se koristi u listi referenci.


#Pitanje6
Nakon brisanja NodaTime direktorija unutar packages direktorija u solutionu i buildanja KonzolneAplikacije nakon toga, aplikacija je radila normalno, a u 
packages direktoriju ponovno se generirao NodaTime direktorij sa istim sadr�ajem kao prije brisanja.
