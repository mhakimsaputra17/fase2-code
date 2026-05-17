# Latihan Golang — Struct & Interface

Buat program sederhana dalam file `main.go` untuk mempelajari `struct` dan `interface`.

## Instruksi

1. Buat interface bernama `Animal` yang memiliki method:
   - `MakeSound()`
   - `GetInfo() string`

2. Buat dua struct:
   - `Cat`
   - `Dog`

   Kedua struct memiliki field:
   - `Name`
   - `Age`

3. Implementasikan semua method dari interface `Animal` pada masing-masing struct.

4. Untuk `Cat`:
   - `MakeSound()` menampilkan `Meow~`
   - `GetInfo()` mengembalikan informasi seperti:
     ```text
     Cat: Milo, 2 years old
     ```

5. Untuk `Dog`:
   - `MakeSound()` menampilkan `Woof~`
   - `GetInfo()` mengembalikan informasi seperti:
     ```text
     Dog: Bruno, 4 years old
     ```

6. Buat function `ShowAnimal(animal Animal)` yang:
   - menampilkan hasil `GetInfo()`
   - menjalankan `MakeSound()`
   - menampilkan garis pemisah

7. Di dalam `main()`:
   - buat object `Cat`
   - buat object `Dog`
   - panggil `ShowAnimal()` untuk masing-masing object

---

# Contoh Input

```text
Cat:
Name = Milo
Age  = 2

Dog:
Name = Bruno
Age  = 4
