# Database Assessment — Basic Constraints
## PostgreSQL

Difficulty: Junior  
Estimated Time: 10–15 menit

---

# Scenario

Tim backend sedang membuat database sederhana untuk sistem online course.

Agar data tetap aman dan konsisten, beberapa constraint perlu ditambahkan ke database.

Tugas Anda:
lengkapi constraint pada tabel berikut.

---

# Starter Schema

```sql
CREATE TABLE users (
    id SERIAL,
    name VARCHAR(100),
    email VARCHAR(100)
);

CREATE TABLE courses (
    id SERIAL,
    title VARCHAR(100),
    instructor_id INT
);

CREATE TABLE enrollments (
    id SERIAL,
    user_id INT,
    course_id INT
);
```

---

# Tasks

## users
Tambahkan constraint agar:
- id unique
- name wajib diisi
- email wajib diisi
- email tidak boleh duplicate

---

## courses
Tambahkan constraint agar:
- title wajib diisi
- instructor_id wajib diisi

---

## enrollments
Tambahkan constraint agar:
- user_id wajib diisi
- course_id wajib diisi
- user tidak bisa enroll course yang sama dua kali

---

# Expected Behavior

---

## Valid User

```sql
INSERT INTO users(name, email)
VALUES ('Alice', 'alice@mail.com');
```

Expected:
```txt
success
```

---

## Duplicate Email

```sql
INSERT INTO users(name, email)
VALUES ('Bob', 'alice@mail.com');
```

Expected:
```txt
error duplicate email
```

---

## Duplicate Enrollment

```sql
INSERT INTO enrollments(user_id, course_id)
VALUES (1, 1);

INSERT INTO enrollments(user_id, course_id)
VALUES (1, 1);
```

Expected:
```txt
error duplicate enrollment
```

---

# Rules

- Gunakan PostgreSQL syntax
- Fokus pada constraint database
- Tidak perlu query SELECT/JOIN

---

# Yang Dinilai

- PRIMARY KEY
- NOT NULL
- UNIQUE
- constraint understanding
