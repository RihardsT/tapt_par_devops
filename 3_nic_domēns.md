# Nic.lv domēna vārds
Piereģistrējies https://www.nic.lv/ un uztaisi domēna vārdu.  
Viens `.id.lv` domēna vārds katram Latvijas iedzīvotājam ir par brīvu,
ta ka uztaisi kādu labu domēnu.  
Manuprāt, labāk ja izdomā vārdu, kas varētu būt derīgs teju jebkam.  
Pārbaudu tur domēnu `DOMAIN.id`.lv izskatās ir pieejams.
Ieliec `DOMAIN` vietā sevis izvēlētu vārdu.  
Ja ir luste, vari pat tur uztaisīt `DOMAIN.id.lv`, ar mīkstinājuma zīmi. :grinning:  
Kā tīk.  

- Piereģistrē domēnu, kādu izvēlējies
(skaties lai ir .id domēns, jo tas par brīvu vienkārši).  
- Uztaisi serverīti (ja esi Terraform lietu jau izdarījusi, tad izmantojot to)
- Kad serveris ir uztaisīts, tad atpakaļ iekš NIC, tev ir tur jāielogojas,
jāiet uz `Mani domēna vārdi` un jāpievieno jauns A ieraksts.
  - Hostname: Tavs izvēlētais domēna vārds, piem. `DOMAIN.id.lv`
  - IP: Servera IP adrese
  - NIC'ā šim brīvajam domēnam vari uztaisīt līdz 5 domēna ierakstiem.
  Tas var noderēt subdomēniem, kā `SUB.DOMAIN.id.lv` vai tamlīdzīgi.
- Kad domēns saglabāts un serveris ir ejošs,
tad tik jāgaida kādas divas stundas vismaz,
līdz tas domēna vārds tiks izlaists pa pasauli,
līdz to varēsi mierīgi lietot to pārlūkā.
- Vari uz to pamēģināt aiziet pārlūkā. Kamēr lec ārā kaut kāda NIC lapa,
ir vēl jāpagaida. Ja ir timeout, tad domēna vārds varētu jau strādāt.
- Kad ir timeout tai lapai, tad uz serverīša palaid atkal to python simple server.
  - Tad browserī pārbaudi, vai redzi to: `DOMAIN.id.lv:8000` visticamāk.
  Ja tas tad parāda kaut ko, tad tad jau domēns iet, un arī idejiski serveris.

Tālākais uzdevums ir turpināt veidot pašu mājaslapu
un tad pēcāk to varēs palaist uz tā serverīša tā, ka pieejams caur domēnu.
