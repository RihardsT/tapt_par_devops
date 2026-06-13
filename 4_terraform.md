Jauns toolis!  
https://www.terraform.io/  

Terraform ir viens no DevOps rīkiem, kas ļauj aprakstīt Infrastruktūru ar kodu - Infrastructure as Code.  
Jebšu aprakstīt serverus iekš koda, lai nebūtu ik reizi, kad nepieciešams uztaisīt serveri mākonī, jāiet un jāklikšķinās.  
Aprakstīt to visu kodā ir forši, jo mūsdienās praktiski visi uzņēmumi pāriet uz mākoni un arī serverus ceļ augšā un dzēš regulāri, attiecīgi tāds rīks, kas ļauj to darīt caur kodu ir lietderīgs, jo tas ir atkārtojams process. Tiks uztaisīts tieši tāds serveris, kāds aprakstīts palaižot vienu komandu.

Getting started:
Terraform netiek izlaists iekš
- Lejupielādē Terraform iekš sava Linux
  - Pārlūkā atver https://www.terraform.io/downloads.html un nokopē download linku priekš Linux 64-bit
  - Iekš termināļa to lejupielādē ar `wget` komandu:
    - `wget LINK_HERE`
    - Pieraksti šo. wget ir vienkāršākā komanda, ko var izmantot, lai lejupielādētu failus iekš termināļa.
  - Lejupielādēto .zip failu ir jāatspiež. Tā kā esi iekš Linux, to var izdarīt ar `unzip` komandu
    - Iespējams, ka `unzip` komanda nav uzreiz pieejama, tad tā ir jāieinstalē iekš Ubuntu
    - `sudo apt install unzip` vajadzētu strādāt
    - Tad var to zip failu atspiest
    - `unzip ter_TAB_FOR_AUTOCOMPLETE`
    - Pieraksti ko ar šo komandu var izdarīt arī
  - Atspiedās tīrs fails `terraform`, kas ir executable
    - To vari paskatīties ar `ls -lah` komandu. `ls --help` ja gribi zināt ko tā komanda un arī tie parametri nozīmē.
    - Redzēsi ka izvadās apmēram šādi:  
`-rwxr-xr-x 1 USERNAME USERNAME 75M Jul 21 21:22 terraform`
     - Secīgi, tas parāda permissions
     - `rwxr-xr-x` - permissions ir 3 (read/write/execute) start 3 "useriem": owner/group/guest, jebšu `rwx/r-x/r-x`
     - Attiecīgi šeit tu redzi, ka ownerim ir atļauts failu read/write/execute, bet grupai un guest userim ir atļauts to tikai read/execute.
     - Tas execute permission parāda, ka šo failu var palaist, līdzīgi kā ar `cd` un citām komandām. Fails arī citādi iekrāsots, parādot, ka tas ir executable.
     - Tālāk ko tas `ls` izvadīja: `USERNAME USERNAME` daļa parāda faila owner/group.
     - Tad faila izmērs, modificēšanas datums un faila nosaukums. Ko tas 1 pēc permissions nozīmē es pats nezinu.
  - Šo failu tu pašlaik vari palaist norādot tā atrašanās vietu.
    - Piem palaid `pwd`, redzi pašreizējo lokāciju kur atrodies. Pieņemot ka fails ir turpat kur esi, tad to ko pwd izvadīja pieliec priekšā, jebšu piem `/home/USERNAME/terraform --version`. Tas ir izmantojot pilno faila path.
    - To pašu var panākt izmantojot saīsinājumu pašreizējai mapei `./`: `./terraform --version`
    - Tāpat, tā kā pieņemu ka tas pagaidām ir tavā māju mapē, tad to var arī palaist šādi: `~/terraform --version`
  - Bet tu, protams, vēlētos, lai nebūtu jānorāda faila atrašanās vieta, lai to palaistu.  
Tu gribētu to palaist tāpat, kā pārējās komandas, kā pie `cd`, pa tiešo.
    - To var izdarīt pārvietojot šo terraform failu uz `/usr/local/bin/` mapi.  
Tā ir viena no mapēm, kurā lietotāji var likt programmas, lai tās būtu uzreiz pieejamas terminālī.
    - Attiecīgi, pārvieto terraform failu uz to mapi ar `mv` komandu:  
`mv terraform /usr/local/bin/`  
Lasi: move FILE to DESTINATION
    - Pārbaudi, vai tas tagad iet bez path (`./`) priekšā, vienkārši `terraform --version`
    - Ja tas strādā, tad super.
    - Komanda, ar kuru vari pārbaudīt, kur atrodas programmas ir `which`  
Palaid `which terraform` un tam vajadzētu izvadīt `/usr/local/bin/terraform` tagad.

Galvenais uzdevums:
Aprakstīt vienu serverīti kā kodu. https://registry.terraform.io/providers/hetznercloud/hcloud/latest/docs
- Uztaisi jaunu git repozitoriju, savā code mapē kur tev tā ir.
  - Repozitorijā tev būs jāuztaisa `.gitignore` fails, kurā norādīsi ko nevajadzētu saglabāt iekš git.
  - To ko tur vajadzētu izlaist, iekomentēšu vēlāk. Iedošu vēlāk arī piemēru ar savu repo.
- Tad seko līdzi dokumentācijai un skaties, vai vari to saprast, saprast kas ir tur jāraksta.
  - Ja ir luste, tad vari pat pameklēt kādu Terraform tutoriāli pati.
- Kad esi sarakstījusi tur visu, tad vari mēģināt palaist Terraform, lai tas taisītu serveri.
  - `terraform plan` - ja šis neizmet skaidri error, tad varētu būt, ka ies. Tad:
  - `terraform apply` - šī komanda mēģinās uztaisīt visus tos resursus, ko aprakstīji ar terraform
  - `terraform destroy` - šī komanda izdzēsīs iepriekš izveidotos resursus/serveri. Šo laid tad kad esi pabeigusi strādāt ar to serveri, kad to vairāk uz doto brīdi nevajag.

Ja pildi pa nakti un ir jautājumi, tad vari iekomentēt. Tad jau paziņosi, ka man jāpārbauda un tad iekomentēšu cerams kaut ko palīdzošu.
Lai veicas. :smile:
