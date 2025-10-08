# Kom i gang med FastAPI

Dette repo forsøger at beskrive, hvordan man basalt kommer i gang med [FastAPI](https://fastapi.tiangolo.com/) til Python.

## Hvad er FastAPI?

FastAPI er et moderne, hurtigt (high-performance) web framework til Python, som bruges til at bygge API’er – altså programmeringsgrænseflader, som gør det muligt for forskellige systemer at kommunikere med hinanden over internettet.

Det er især designet til at være:

- Let at bruge og læse.
- Meget hurtigt – både i udviklingstid og i kørsel.
- Automatisk dokumenterende – det genererer interaktiv dokumentation via Swagger og ReDoc.

### 'API' .. hvad er dog det!?

**API** står for _**A**pplication **P**rogramming **I**nterface_ og er et programmeringsinterface, som gør det muligt for forskellige programmer at kommunikere med hinanden.

#### Eksempel på forklaring af brugen af et API

Forestil dig, at du har en app på din telefon, som viser dig dagens vejr. Den app har ikke selv alle vejrinformationerne – den henter dem fra en anden tjeneste, f.eks. DMI eller en global vejrserver.

Men hvordan gør den det?

Den bruger et API – som er en slags standardiseret adgang til data og funktioner i den anden tjeneste.

Det er altså grundlæggende et **API** (noget kode som kører på en server - og _**ikke**_ på din telefon) som sender din telefon vejrdataene, hvilket din telefons app så bruger til at vise dig vejrdata.

## Lav selv et basic API med FastAPI

For at vise, hvordan du kommer i gang med selv at lave API'er med FastAPI, så vil vi følge nedenstående steps til det:

1. Installer nødvendigt software
2. Kod dit eget simple API

### Installer nødvendigt software

For om lidt at kunne kode dit eget simple API, så er du nødt til at installere følgende software:

- [VS Code](https://code.visualstudio.com/)
- [Python](https://www.python.org/downloads/)
- [FastAPI](https://fastapi.tiangolo.com/)

Installationen af både VS Code og Python burde være rimelig lige til - ellers så få lige hjælp af en voksen.

At installere FastAPI er også ret nemt. Men hvis ikke du ved, hvordan man installere Python pakker som FastAPI eller andet, så kommer her en forklaring på, hvordan du gør via VS Code.

#### Installation af FastAPI

Måden du installere FastAPI vhja. VS Code er følgende:

1. Åbn VS Code
2. Åbn en terminal i VS Code
3. Installer FastAPI i terminalen med kommandoen: **pip install "fastapi[standard]"**

## Kod dit eget simple API

Overordnet set er måden man koder sit eget API med FastAPI (i en fil kaldet <code>main.py</code> i VS Code) følgende:

1. importer FastAPI
2. Lav en FastAPI 'app'
3. Definer dine routes
4. Start en FastAPI udviklingsserver
5. Besøg dit API i din browser

Denne proces gennemgås opbyggeligt i nedenstående.

### Step 1: Importer FastAPI

I en Python fil (altså en fil med filtypenavnet '.py' - her i vores et eksempel en fil kaldet 'main.py') skal du først importere FastAPI sådan her:

```python
from fastapi import FastAPI
```

### Step 2: Lav en FastAPI 'app'

Med din import kan du lave en FastAPI 'app' ved at initialisere en variabel med et kald til FastAPI:

```python
from fastapi import FastAPI

app = FastAPI()
```

### Step 3: Definer dine routes

Her er vil blot definere en meget, meget simple route, hvis url du vil kunne besøge i din browser, når vi i næste step starte vores FastAPI udviklingsserver.

Routen vi her vil lave er blot et simpelt JSON respons - JSON er det dataformat som apps og servere oftest bruger til at udveksle data mellem hinanden - som blot giver dig en form for "Hello World" tekst. Koden er:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def root():
    return {"message": "Hello World"}
```

### Step 4: Start en FastAPI udviklingsserver
Mere skal der faktisk ikke til for at lave - et godt nok virkelig, virkelig simpelt - API med FastAPI.

Eneste du nu mangler er først at starte en FastAPI udviklingsserver, og dernæst at besøge den url som FastAPI giver dig i den browser (sidstnævnte gør vi i næste step).

Indtast derfor følgende kommando i din terminal (og tryk 'enter' ..):

```bash
fastapi dev main.py
```

### Step 5: Besøg dit API i din browser
Med det skulle du gerne få et link i din terminal til dit API, som du bl.a. vil kunne se i browser.

Helt konkret skulle du gerne få et link a la <code>http://127.0.0.1:8000</code> som du kan klikke på for at se dit API 'live' i din browser.

## Bidrag til dette materiale
Dette materiale er lavet med bidrag af:

- [Jonas Bak Phillipson](https://github.com/jbakchr) (_Formand og Kaptajn for Coding Pirates Hillerød_)

## Tak
Til at skrive dette materiale har følgende ressourcer været brugt til at gøre det hele (forhåbentligt) mere forståeligt for både børn og voksne.

En tak skal derfor lyde til:

- [Real Python](https://realpython.com/) - til hjælp med at kode et API med FastAPI
- [Microsoft Copilot](https://copilot.microsoft.com/) - til hjælp med at gøre forklaringen af et API simpelt for især børn

