## Notasi Algoritmik CheatSheet

**Kamus**
```
type Point:<X:real,Y:real> {Contoh Tipe Bentukan}

Nmax : integer
found: boolean
P : Point {objek dari tipe bentukan}
C : character

constant nmax : integer = 1000
constant pi : real = 3.14


```

**Fungsi // Prosedur**
```
// Deklarasi
function PointToKuadran(point : Point) -> integer {Menerima tipe bentukan Point dan menghasilkan integer}

// Contoh
function addXY(x:integer,y:integer) -> integer
Algoritma
  -> x + y {-> itu artinya return ya}

procedure Tulis(input pesan:string) 
{
I.S. Sembarang
F.S. Pesan tertulis ke layar
Proses : Menulis isi pesan ke layar
Gatau ini harus atau engga wkwk
}

procedure sortArray(input/output T:anArray)
Algoritma
  {Lakukan sesuatu supaya array T tersort. Pengubahan elemen bisa dilakukan langung di T}
```

**Analisis Kasus**
```
if {Suatu Kasus} then
  {Your code ...}
 else if {kasus yang lain} then
  {your code...}
 else 
  {your code ...}
```

**Skema Pengulangan**
```
repeat n times 
  {your code...}


repeat
  {your code...}
until {condition}


while {condition} do:
  {your code}

{nama pencacah} traversal [{starting range}..{ending range}]
  {your code...}

// Contoh
i traversal [1..10]
  output(i)
// Range yang dimaksud adalah inklusif dalam kasus diatas, 1 dan 10 termasuk ke dalam iterasi
```
**Dengan Mark atau Tanpa Mark ??**
```
Dengan Mark : Elemen yang terakhir bukanlah elemen sebenarnya
```

```
Tanpa Mark : Elemen terakhir adalah elemen sebenarnya.
             
```
Kasih contoh dalam python aja ya :)

```python
# Dengan Mark
i = 0
N = 10
while i < N:
  # Do something
  i += 1
# Setelah loop selesai, i akan bernilai 11.Ini disebut elemen fikitf. cmiiw :v
```

```python
# Tanpa Mark
i = 0
N = 10
while True:
  # Do something
  if i == N:
    break
  i += 1
# Setelah loop selesai, i akan bernilai 10.Elemen ini bukan elemen fiktif. cmiiw :v
```

**Array**
```
// Deklarasi
Tab : array[1..100] of integer 

arrayOfPoint : array[1..100] of Point
// Contoh akses array waktu ujian !!!
Tab[1]
Tab[100]

// Contoh input elemen array
Tab : array[1..100] of integer

i traversal [1..100]
  input(Tab[i])
```

**Sorting Array**
```
// Counting Sort
procedure CountSORT (input/output T : TabInt, input N : integer)
{ mengurut tabel integer [1..N] dengan pencacahan }


Kamus Lokal

{ ValMin & ValMax: batas Minimum & Maximum nilai di T, hrs diketahui }
TabCount : array [ValMin..ValMax] of integer;
i, j : integer; { indeks untuk traversal tabel }
K : integer; { jml elemen T yg sudah diisi pada pembentukan kembali }


ALGORITMA

if (N > 1) then
  { Inisialisasi TabCount }
  i traversal [ValMin..ValMax]
    TabCounti <- 0
    
  { Counting }
  i traversal [1..N]
    TabCountT[i] <- TabCountT[i] + 1
  { Pengisian kembali : T1 ≤ T2 ≤ ... ≤ TN }
  
  K <- 0
  
  i traversal [ValMin..ValMax]
  if (TabCounti ≠ 0) then
    j traversal [1..TabCounti]
      K <- K + 1
      TK <- i
```

```
// Selection Sort
procedure MAXSORT (input/output T : TabInt, input N : integer)
{ mengurut tabel integer [1..N] terurut mengecil dgn maksimum suksesif }


Kamus Lokal

i : integer { indeks untuk traversal tabel }
Pass : integer { tahapan pengurutan }
Temp : integer { memorisasi harga untuk penukaran }
IMax : integer { indeks, di mana T[Pass..N] bernilai maksimum }


Algoritma

if (N > 1) then
  Pass traversal [1..N-1]
    { Tentukan Maximum [Pass..N] }
    IMax <- Pass
    i traversal [Pass+1.. N]
      if (TIMax < Ti ) then
        IMax <- i
    { TIMax adalah maximum T[Pass..N] }
    {Tukar TIMax dengan TPass }
    Temp <- TIMax
    TIMax <- TPass
    TPass <- Temp
    { T1..Pass terurut: T1 ≥ T2 ≥ ... ≥ TPass }
{ Seluruh tabel terurut, T1 ≥ T2 ≥ ... ≥ TN }
```

**Data**

```
nama file : data.txt
Misalkan datanya seperti ini
<Nama1,Nilai1,NIM1>
<Nama2,Nilai2,NIM2>
.
.
.
<MarkNama,MarkNilai,MarkNIM>

Beberapa style untuk mengakses:
Kamus
  type rekamanDataType : <Nama:string, nilai:integer,NIM:integer>
  VariabelRekaman : SEQFILE of
                      (*) dataRekaman : rekamanDataType     {Isi data}
                      (1) <MarkNama,MarkNilai,MarkNIM> {Mark}
Algoritma
  assign(VariabelRekaman,"data.txt")
  open(VariabelRekaman,dataRekaman) // Sekarang isi variabel dataRekaman adalah <Nama1,Nilai1,NIM1>
  read(VariabelRekaman,dataRekaman) // Sekarang isi variabel dataRekaman adalah <Nama2,Nilai2,NIM2>

  close(VariabelRekaman) // Ingat yang ini

// Style yang lain
Kamus
  type rekamanDataType : <Nama:string, nilai:integer,NIM:integer>
  
  constant mark : rekamanDataType = <MarkNama,MarkNilai,MarkNIM>
  VariabelRekaman : SEQFILE of
                      (*) dataRekaman : rekamanDataType     {Isi data}
                      (1) mark {Mark}
  assign(VariabelRekaman,"data.txt")
  rewrite(VariabelRekaman) // Jika mau menulis data ke data.txt
  write(VariabelRekaman,isiData) // Untuk menulis isiData ke file data.txt
  
  write(VariabelRekaman,mark) // Ingat ini
  
  close(VariabelRekaman) // Ingat Yang ini
```

# Udah ngantuk weh. Semoga ujiannya lancar ya :)
