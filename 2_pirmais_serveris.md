### Piereģistrējies Hetzner mākonītim un uztaisi mazu serverīti
Izmanto refferal linku: https://hetzner.cloud/?ref=DDdI3GwQrA9F  
Tur viss būs sarežģīti, bet skaties kā tur to izdarīt ar Paypal.  
Tur laikam 20 eur caur tavu PayPal novilks, ta ka tam gatavojies.  
Ja vari, tad pieraksti un/vai uztaisi screenshot'us ar to kā, tas gāja,
lai es varētu nākotnē vēl kādam to linku dot un soli pa solim tad to izskaidrot.  

Kad esi piereģistrējies, ielogojies, tad tur jāuztaisa pirmkārt ir "projektiņš",
kurā iekšā tad serverus varēs taisīt.

Tad nākamais uzdevums būs uztaisīt serverīti.  
Add server:
- Location: Izvēlies kur tev patīk labāk. Man patik Helsinki
- OS Image: Tava mīļākā Linux distribūcija: Ubuntu 20.04
- Type: Standard, Local storage, CX11 šobrīd pietiks
- Volume: Nevajag. To var arī pēcāk pielikt
- Network: šobrīd nevajag. To varēs arī pēcāk pielikt
- Firewall: Pašlaik nevajag
- Additional features: Pašlaik nevajag
- SSH Keys: Šo vajag. Ņem to pašu SSH publisko atslēgu, ko liki iekš Gitlab.
  - Atver termināli (to Ubuntu), tad iekš Ubuntu tava lietotāja māju
  (~, /home/USERNAME) mapītes būs `.ssh` mape,
  kurā būs tā nepieciešamā `.pub` atslēga.
  - Pēc defaulta ielogojas mājas mapītē, bet ja gribi ātri uz to aiziet,
  tad vari palaist `cd` komandu bez jebkādiem parametriem.
  - Tad nolasi to publisko atslēgu: `less .ssh/TAB_TAB_TAB` -
  ieraksti `less .ssh/` tad spied TAB vairākas reizes,
  līdz tas parāda tās mapes saturu,
  proti, tam jāparada vismaz 2 failus: `id...` un `id...pub`.  
  Tev ir vajadzīgs tas `.pub` fails.
  - Atver to, nokopē to visu un iekopē iekš mākonīša (browserī),
  tur kur `Add an SSH key`. Visu faila saturu tur kur ir SSH key.  
  Nosaukumu tad var likt kādu vēlies.
- Name: Servera nosaukums. Var būt jebkas kā tu vēlies.  
Man personīgi patīk kas īss, bet var palikt tas, kas tur ir pēc noklusējuma.

`Create & Buy now` lai uztaisītu to serveri.

Tad kad parādās, ka serveris ir uztaisījies
(ir sarakstā un rādās zaļš aplītis, ka ieslēgts),
tad nokopē tā IPv4 adresi un pamēģini tajā serverī ielogoties.  
Ielogošanās serverī notiek ar SSH komandu (no sava Ubuntu termināļa):
```
ssh root@IP_ADDRESS_HERE
```
Accept to ko tas tur ziņo, ka pieņem to atslēgu vai tamlīdzīgi.  
Bums. Tad tev vajadzētu būt iekšā serverī.  
To vari redzēt redzēt, ka hostname un username terminālī ir cits.  
Ja atminies, iepriekš bija `USERNAME@....`, tagad vajadzētu būt `root@...`  
Esi tajā serverī.  

Tas serveri ir pieejams no interneta.  
Vari to ātri pārbaudīt ar vienkāršu python komandu:
```
python3 -m http.server 8000
# vai šo, atkarībā no tā, kāda python versija ir ieinstalēta
python2 -m SimpleHTTPServer 8000
```
Tad iekš browsera vari pārbaudīt, vai tas ir pieejams:  
`IP_ADDRESS_HERE:8000`

Ja tas viss iet, tad viss iet. Šim uzdevumam tas ir gana.  
Vari apturēt to python programmu un arī iziet no servera,
spied `ctrl + c` un `ctrl + d` līdz tiec līdz savam Ubuntu,
kad parādās `USERNAME@...`  

Tad izdzēs to serveri no mākoņa.  
Ļoti svarīgi, lai nemaksātu par to, ko nelieto.
