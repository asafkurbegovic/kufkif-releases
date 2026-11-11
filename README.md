# KUFKIF Modern – izdanja

Gotove verzije aplikacije **KUFKIF Modern**, programa za vođenje knjige ulaznih i izlaznih
faktura (KUF/KIF) i izvoz eKUF/eKIF CSV fajlova za portal e-Porezi (UIO).

U ovom repou su **samo gotovi programi** (ZIP). Nema izvornog koda ni podataka bilo koje firme.
Instalirana aplikacija odavde sama provjerava i preuzima nove verzije.

## Preuzimanje

Najnovija verzija: **[Releases → Latest](https://github.com/asafkurbegovic/kufkif-releases/releases/latest)**

| Računar | Fajl |
|---|---|
| Windows 10 / 11 (64-bit) | `KUFKIF-Modern-win-x64.zip` |
| Windows 7 SP1 | `KUFKIF-Modern-win7.zip` |

Fajlovi „Source code (zip / tar.gz)“ GitHub automatski dodaje uz svako izdanje. Oni nisu
potrebni i ne sadrže aplikaciju.

## Prva instalacija

1. Skini ZIP za svoj računar.
2. Raspakuj ga u **vlastiti folder**, npr. `C:\KUFKIF`.
   - ne direktno na Desktop, u Documents ili Downloads
   - ne u `Program Files` (tu aplikacija nema dozvolu da se sama ažurira)
3. Pokreni:
   - Windows 10/11: `KUFKIF.Modern.App.exe`
   - Windows 7: `KUFKIF.Modern.App.Win7.exe` (potreban je .NET Framework 4.8)

Ako se aplikacija već koristi, raspakuj ZIP **preko postojećeg foldera**. Podaci se ne čuvaju
u folderu aplikacije, pa ostaju netaknuti.

## Ažuriranje

- Pri pokretanju aplikacija provjeri ima li nova verzija i ponudi instalaciju.
  Ručno: dugme **„Provjeri update“** u zaglavlju.
- Prije svakog ažuriranja automatski se pravi backup baze.
- Ako nova verzija ima problem: dugme **„Vrati prethodnu“** vraća verziju koja je bila prije
  zadnjeg ažuriranja.
- Bez interneta aplikacija normalno radi, samo ne provjerava nove verzije.

## Gdje su podaci

Svi podaci su lokalno na računaru, u `%LOCALAPPDATA%\KUFKIF-Modern\`:

| Putanja | Sadržaj |
|---|---|
| `kufkif.sqlite` | baza (firma, KUF, KIF) |
| `backups\` | automatski backup baze prije svakog ažuriranja (zadnjih 20) |
| `previous\` | prethodna verzija programa (za „Vrati prethodnu“) |
| `app.log`, `update.log` | dnevnik rada i ažuriranja |

Za ručni backup dovoljno je kopirati `kufkif.sqlite` dok je aplikacija zatvorena.

## Problemi

- **Windows 7: provjera nove verzije javlja grešku pri spajanju.** Računaru vjerovatno
  nedostaju ažurni root certifikati ili podrška za TLS 1.2. Instaliraj Windows Update
  zakrpe ili ručno preuzmi i raspakuj novu verziju odavde.
- **Windows SmartScreen / antivirus upozorava.** Program nije digitalno potpisan.
  Odaberi „More info → Run anyway“.
- **Ažuriranje nije uspjelo.** Aplikacija i podaci ostaju na staroj verziji. Detalji su u
  `%LOCALAPPDATA%\KUFKIF-Modern\update.log`.
