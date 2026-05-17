# Latihan Golang — Struct & Interface

Buat sebuah program sederhana menggunakan bahasa Go dalam satu file bernama `main.go` untuk mempelajari penggunaan `struct`, `method`, dan `interface`.

## Instruksi

### 1. Buat Interface

Buat interface bernama `Animal`.

Interface tersebut wajib memiliki 2 method:

```go
MakeSound()
GetInfo() string
```

Keterangan:
- `MakeSound()` digunakan untuk menampilkan suara hewan
- `GetInfo()` digunakan untuk mengembalikan informasi hewan dalam bentuk string

---

### 2. Buat Struct

Buat 2 struct berikut:

#### Struct `Cat`

Field yang harus dimiliki:
- `Name`
- `Age`

#### Struct `Dog`

Field yang harus dimiliki:
- `Name`
- `Age`

---

### 3. Implementasikan Method

Setiap struct wajib mengimplementasikan seluruh method dari interface `Animal`.

#### Untuk `Cat`

- `MakeSound()` menampilkan:
  ```text
  Meow~
  ```

- `GetInfo()` mengembalikan string seperti:
  ```text
  Cat: Milo, 2 years old
  ```

---

#### Untuk `Dog`

- `MakeSound()` menampilkan:
  ```text
  Woof~
  ```

- `GetInfo()` mengembalikan string seperti:
  ```text
  Dog: Bruno, 4 years old
  ```

---

### 4. Buat Function

Buat function bernama:

```go
ShowAnimal(animal Animal)
```

Di dalam function tersebut:
1. tampilkan hasil dari `GetInfo()`
2. jalankan method `MakeSound()`
3. tampilkan garis pemisah:
   ```text
   -------------------
   ```

---

### 5. Implementasi di `main()`

Di dalam function `main()` lakukan langkah berikut:

1. Buat object `Cat`
   - Name: `Milo`
   - Age: `2`

2. Buat object `Dog`
   - Name: `Bruno`
   - Age: `4`

3. Panggil function:
   ```go
   ShowAnimal()
   ```
   untuk masing-masing object.

---

# Contoh Input

```text
Cat:
Name = Milo
Age  = 2

Dog:
Name = Bruno
Age  = 4
```

---

# Contoh Output

```text
Cat: Milo, 2 years old
Meow~
-------------------
Dog: Bruno, 4 years old
Woof~
-------------------
```

---

# Rules

- Semua kode hanya dalam file `main.go`
- Gunakan package `fmt`
- Tidak boleh menggunakan package lain
- Gunakan method untuk menampilkan data
- Jangan hardcode seluruh output langsung di `main()`
