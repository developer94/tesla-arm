ARM-A3 Konfigurisanje peer to peer mreze
========================================

Dobijamo : 3 Windows 7 virtuelne masine (2 su ucenicke , 1 profesorska)
Primer A3-1
***Prvo kod sve tri masine proveriti dal su sve Internal Network - intnet (Settings-Network..)***
1)PROFESORSKA
  1.1) Dajes IP
- Start-Search-ncpa.cpl - Desni klik na konekciju - Properties - Obelezi Internet Protocol(TCP/IPv4) pa potom Properties - 192.168.100.67 255.255.255.224 
1.2) Menjas ime racunara	
- Start - My Computer(Desni klik-Properties)-Tu na Change Settings (pri dnu desno je)-Change - U zadatku je dato kako da nazoves (u nasem slucaju A3-1) je to PROF-00 -Ok . Morate ga restartovati
1.3) Dodajes jedan admin nalog
- Start-Control Panel - User Accounts – Add or remove user.. - PROFESOR(ime prema zadatku) - Administrator.. OK . Klik na taj nalog I Create password -  npr : !passw0rd (ovo je jak password) 
!!!!POTOM START - LOG OFF-SWITCH I PREDJI NA TAJ AKAUNT U NASTAVI DALJI RAD 1.4!!!
      1.4)Kreiraj Homegroup - Start -  Control Panel,napisi homegroup u search box, I klkini na HomeGroup.
Potom Create HomeGroup – U principu kod kreiranja homegroupe treba  stiklirati samo stampace . – Finish.
Password koji vam da je jako bitan njega cete koristiti da uclanti ucenika u vasu grupu , taj password uvek mozete videti u Homegroup – View or print the homegroup password
Zatim u okviru Homegroup prozora skrolujte do dole I nadjite Change advanced sharing settings
-Otvorite Home or Work I nadjite Password protected sharing I iskljucite ga. 
1.5)Kreiranje direktorijuma i sharing 		
-Kreiraj ga na DESKTOPU -desni klik -New Folder-NASTAVNI MATERIJAL(ime prema zadatku).
-Desni klik na taj folder potom – Share with - I odaberite Homegroup(Read) (ucenici nemaju
pravo prema zadataku da menjaju faljove profesora) (ako te pita stavi private network)


1.6) Kreiranje stampaca i njegov sharing     
- Start-Devices and printers-Desni klik na prazan proctor - Add a printer-Add a local printer- Next- Nista ne diraj kod portova samo Next-Izaberite stampac vec koji je Next- Ime npr Printer Next-Sad odaberi Do not share - No Next-Next-Finish (ovo cete lako podesiti na osnovu parametra stampaca u skoli il vec kod kuce za sad samo ovako da prodjemo)
-Start- Devices and printers -desni klik na vas Printer–PRINTER PROPERTIES - Sharing - Share this printer.
1.7) Sharing CD/DVD i USB
***U svim primerima se trazi deljenje stampaca!! A u nekim il USB il CD/DVD il samo stampac ovde cu da pokazem za USB I CD/DVD a stampac vam je 1.6)
-Sharing CD/DVD My Computer-desni klik na CD – Share with –Advanced sharing- opet Advanced sharing-Share this folder i u Permission stiklirati samo Read -Apply- Ok-
- Sharing USB : Ubacis USB u profesorski (Devices-USB- i stkliraj vas usb pa onda) My Computer-desni klik na USB(Removable Disk) – Share with –Advanced sharing- opet Advanced sharing-Share this folder i u Permission stiklirati samo Read -Apply- Ok-
2)UCENICKE
	2.1) Dajes IP		
- Start-Search-kucaj ncpa.cpl - Desni klik na konekciju - Properties - Obelezi Internet Protocol(TCP/IPv4) pa potom Properties. Das ip adresu 192.168.100.68 255.255.255.224  
2.2)Menjas ime racunara	
- Start-My Computer(Desni klik-Properties)-Tu idi na Change Settings (pri dnu desno je)-Change 
 	U nasem slucaju(A3-1) je to RACUNAR-01 .Morate ga restartovati.
	2.3)Dodajes jedan limitirani ucenicki nalog 	
- Start-Control Panel - User Accounts - Create a new account
Nalog ce se prema nasem zadataku zvati UCENIK - Next - odaberi Standard User - Create Account (bez lozinke prema upustvu zadataka). (on ceti tek trebati na kraju)

2.4)Pridruzivanje postojecoj Homegroup-i
		Start -  Control Panel,napisi homegroup u search box, I klkini na HomeGroup. Tu ce vam reci da postoji vec
		Jedan kreiran homegroup koji je kreirao PC-00 (profesorski) ukucajte password I pridruzite ovaj racunar.

2.5)Kreiranje direktorijuma i sharing     
- Kreirajte ga na DESKTOPU- desni klik -New Folder ime TIM(prema zadatku).U njemu prema zadatku u notepad-u il wordu kreirajte dokument_01 i dokument_02 (po dve recenice unutra).     – Potom desni klik na folder TIM-Share with-Homegroup(Read/Write) (zato sto je profesoru dozvoljeno da menja )
2.5) Zatvaranje portova USB , CD/DVD      
 		- Zatvaranje CD/DVD 
- Zatvaranje USB porta 
1.	Open an MMC (start > Run or Start > type MMC)
2.	Add/Remove Snap-in
3.	Select Group Policy Object Editor – Idi Browse –Users  I tu odaberi nalog ucenicki koji si kreirao !
4.	Rastvori ovo levo sto ti je pa - Navigate to User Configuration > Administrative Templates > System > Removable Storage Access
5.	Tu dakle idite ENABLE za sledece :
CD and DVD Deny read access
CD and DVD Deny write access     (ovo 2 su cd/dvd)
Removable Disks:Deny read access
Removable Disks:Deny write access (ovo 2 su za usb)
File-Save
Kad ste ovo odradili Start-Serach- I kucaj sledecu komadu : gpupdate /force
	

3)Isto uradi i za ucenicku jos jednu… Kraj prema zahtevu neophodno je da se ulogujes na ucenicki racunar sa onim nalogom UCENIK i da odstampas sadrzaj fajla dokument_01
