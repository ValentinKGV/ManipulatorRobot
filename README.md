![image](https://github.com/user-attachments/assets/59328fd8-eac2-4cb6-bd43-5749885c7fba)

# Proiect: Sortare cu Braț Robotic pe Bază de Culoare

Acest proiect simulează un sistem de sortare automatizată utilizând un braț robotic industrial. Sistemul detectează culoarea activă a unei cutii și sortează obiectele corespunzător în acea cutie.

## 🧠 Descriere generală

Brațul robotic preia obiecte de pe un transportor și le plasează în cutii colorate. Fiecare culoare reprezintă o destinație specifică. Procesul este declanșat de un semnal binar asociat fiecărei cutii (ex: `Cutia_Alba`, `cutia_Negro` etc.).

## ⚙️ Funcționalitate

1. **Mișcare inițială** la poziția `Home`.
2. **Așteptare** până când o variabilă de tip `Cutia_...` este setată la `1`.
3. **Selecție cutie activă** și executarea secvenței de pick and place în buclă de 8 ori.
4. **Mișcare finală** înapoi la `Home` și activarea semnalului `aa_delete`.

## 🗃️ Cutii suportate

| Culoare        | Variabilă semnal        | Poziții Pick & Place asociate        |
|----------------|--------------------------|--------------------------------------|
| Albă           | `Cutia_Alba`             | `B_pick`, `B_place`, `B_place_2`     |
| Neagră         | `cutia_Negro`            | `B2_pick`, `B2_place`, `B2_place_2`  |
| Roșie          | `Cutia_Rosie`            | `galben_pick`, `B_rosu_place`, `B_rosu_place_2` |
| Albastră       | `Cutia_albastru`         | `rosu_pick`, `B_albastru_place`, `B_albastru_place_2` |
| Verde          | `Cutia_Verde`            | `albastru_pick`, `B_verde_place`, `B_verde_place_2` |
| Galbenă        | `Cutia_Galben`           | `cyan_pick`, `B_galben_place`, `B_galben_place_2` |
| Cyan           | `Cutia_Cyan`             | `gri_pick`, `B_cyan_place`, `B_cyan_place_2` |
| Portocalie     | `Cutia_Portocaliu`       | `maro_pick`, `B_portocaliu_place`, `B_portocaliu_place_2` |
| Gri            | `Cutia_Gri`              | `portocaliu_pick`, `B_gri_place`, `B_gri_place_2` |
| Maro           | `Cutia_Maro`             | `verde_pick`, `B_maro_place`, `B_maro_place_2` |

## 🔄 Procedura `New_Pick_and_place`

Această procedură realizează:

- Preluare obiect (`Pick`) folosind coordonatele definite.
- Ridicare la o poziție sigură.
- Deplasare și plasare în cutia corespunzătoare (`Place`).
- Eliberare obiect și revenire la poziția deasupra cutiei.

## 🔧 Semnale utilizate (DO)

| Semnal        | Descriere                         |
|---------------|------------------------------------|
| `aa_gripper`  | Controlul închiderii deschiderii gripperului |
| `aa_copy_X`   | Semnal pentru activarea secvenței pe cutia X |
| `aa_delete`   | Semnal de finalizare               |

## 🖼️ Simulare

Imaginea atașată arată o simulare 3D în care brațul interacționează cu 10 cutii colorate și o linie de obiecte care urmează a fi sortate.
