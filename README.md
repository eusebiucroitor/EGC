# EGC
#Teme- Croitor Eusebiu
Exercițiul 1

Dacă schimbăm valoarea constantei MatrixMode.Projection în altă opțiune, de exemplu, MatrixMode.Modelview, vom observa că proiecția scenei nu mai este configurată corect. Acest lucru va influența modul în care obiectele sunt desenate și afișate pe ecran.

Exercițiul 3

Ce reprezintă un viewport în OpenGL?
Viewport-ul în OpenGL este zona de pe ecran unde sunt redat obiectele 3D. Aceasta este definită de coordonatele colțului stânga-jos și de dimensiunile lățimii și înălțimii. Viewport-ul mapează coordonatele scenei 3D la coordonatele 2D ale ecranului. Acesta se configurează folosind funcția glViewport(x, y, width, height).

Ce înseamnă FPS (Frames per Second) în contextul OpenGL?
FPS (Frames per Second) reprezintă numărul de cadre pe care aplicația le poate procesa și reda pe secundă. În OpenGL, FPS-ul este un indicator al performanței și al fluidității animațiilor sau interacțiunilor grafice. Un FPS mai mare duce la o experiență vizuală mai lină, iar un FPS scăzut poate cauza lag sau sacadări. Deși OpenGL nu gestionează direct FPS-ul, acesta poate fi monitorizat și optimizat pe baza performanței hardware-ului.

Când este apelată metoda OnUpdateFrame()?
Metoda OnUpdateFrame() este apelată la începutul fiecărui cadru de randare, pentru a actualiza logica jocului sau aplicației. Aceasta include calcule care nu sunt direct legate de randarea grafică, cum ar fi mișcarea obiectelor, gestionarea coliziunilor, procesarea input-urilor utilizatorului sau orice altă actualizare necesară între cadrele de randare.

Ce este modul imediat de randare în OpenGL?
Modul imediat de randare (immediate mode) este un mod mai vechi în care obiectele grafice sunt definite în mod direct în cod folosind funcțiile glBegin() și glEnd(). Deși acest mod este ușor de înțeles și utilizat, el este ineficient pentru randările complexe deoarece trimite date către GPU la fiecare apel de funcție, ceea ce duce la un consum mai mare de resurse.

Care este ultima versiune OpenGL care acceptă modul imediat?
Ultima versiune de OpenGL care susține pe deplin modul imediat de randare este OpenGL 3.0. În versiunile ulterioare, modul imediat a fost marcat ca fiind depășit (deprecated) și a fost înlocuit cu tehnici mai performante, cum ar fi utilizarea Vertex Buffer Objects (VBO) și Vertex Array Objects (VAO) pentru o gestionare mai eficientă a datelor grafice.

Când se execută metoda OnRenderFrame()?
Metoda OnRenderFrame() este apelată la fiecare ciclu de randare pentru a desena un nou cadru. Aceasta se ocupă de procesul de randare al obiectelor vizibile pe ecran. De obicei, această metodă este executată de mai multe ori pe secundă, iar frecvența de apelare depinde de ratele de refresh ale monitorului sau de setările FPS ale aplicației.

De ce trebuie să fie apelată cel puțin o dată metoda OnResize()?
Metoda OnResize() trebuie apelată cel puțin o dată pentru a ajusta corect dimensiunile viewport-ului și pentru a recalcula matricea de proiecție 3D în funcție de dimensiunile ferestrei sau ale ecranului. Fără această actualizare, obiectele ar putea fi redimensionate sau deformate incorect, iar scena ar putea să nu fie redată corect.

Ce parametri are metoda CreatePerspectiveFieldOfView() și care sunt domeniile lor de valori?
Metoda CreatePerspectiveFieldOfView() este utilizată pentru a crea o matrice de proiecție în perspectivă, care determină cum sunt proiectate obiectele 3D pe ecranul 2D. Parametrii săi sunt:

    Field of View (FOV) – reprezintă unghiul câmpului vizual pe verticală, exprimat în grade. Valoarea sa variază de obicei între 30° și 90°, deși poate depinde de scena specifică.
    Aspect Ratio – raportul dintre lățimea și înălțimea ferestrei de vizualizare. Este necesar pentru a preveni distorsiunile imaginii.
    Near Clip – distanța până la planul de tăiere apropiat, care definește limita mai apropiată a scenei care va fi redată. Valori tipice sunt de ordinul 0.1.
    Far Clip – distanța până la planul de tăiere îndepărtat, care definește limita mai îndepărtată a scenei care va fi vizibilă. De obicei, valoarea acestuia poate fi mare, de exemplu 1000.
