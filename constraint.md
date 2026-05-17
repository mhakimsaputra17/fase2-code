# Database Assessment — Constraints & Relationships
## PostgreSQL · Online Course System

Difficulty: Junior  
Estimated Time: 15–25 menit

---

# Scenario

Tim backend sedang membuat database sederhana untuk platform online course.

Database harus memastikan:
- data user valid
- setiap course memiliki instructor
- enrollment tidak duplicate
- relasi antar tabel tetap konsisten

Engineer sebelumnya sudah membuat starter schema,
tetapi constraint belum ditambahkan.

Tugas Anda:
melengkapi constraint pada tabel berikut.

---

# Learning Goals

Assessment ini mengukur:
- understanding constraint types
- relational integrity
- foreign key usage
- unique constraint usage
- many-to-many awareness

---

# Project Structure

```txt
database/
└── schema.sql
```

---

# Existing Schema

## schema.sql

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

## 1. Users Table

Tambahkan constraint agar:
- setiap user memiliki identifier unik
- name wajib diisi
- email wajib diisi
- email tidak boleh duplicate

---

## 2. Courses Table

Tambahkan constraint agar:
- setiap course wajib punya instructor
- instructor harus valid user yang ada di tabel users

---

## 3. Enrollments Table

Tambahkan constraint agar:
- setiap enrollment wajib punya user
- setiap enrollment wajib punya course
- user tidak boleh enroll course yang sama lebih dari sekali

---

# Expected Behavior

---

# Case 1 — Valid User

Query:

```sql
INSERT INTO users(name, email)
VALUES ('Alice', 'alice@mail.com');
```

Expected:
```txt
INSERT berhasil
```

---

# Case 2 — Duplicate Email

Query:

```sql
INSERT INTO users(name, email)
VALUES ('Bob', 'alice@mail.com');
```

Expected:
```txt
ERROR duplicate data
```

---

# Case 3 — Invalid Instructor

Query:

```sql
INSERT INTO courses(title, instructor_id)
VALUES ('Docker Basics', 999);
```

Expected:
```txt
ERROR invalid reference
```

---

# Case 4 — Duplicate Enrollment

Query:

```sql
INSERT INTO enrollments(user_id, course_id)
VALUES (1, 1);

INSERT INTO enrollments(user_id, course_id)
VALUES (1, 1);
```

Expected:
```txt
ERROR duplicate enrollment
```

---

# Rules

- Gunakan PostgreSQL syntax
- Constraint harus dibuat langsung di schema
- Tidak boleh handle validation di application layer
- Fokus pada database integrity

---

# Assessor Discussion Questions

Assessor mungkin akan bertanya:

- Kenapa email perlu unique?
- Apa fungsi foreign key?
- Apa yang terjadi jika foreign key tidak digunakan?
- Kenapa enrollments disebut bridge table?
- Kenapa duplicate enrollment harus dicegah?

---

# What Assessor Looks For

- PRIMARY KEY understanding
- FOREIGN KEY understanding
- UNIQUE constraint usage
- NOT NULL usage
- relational thinking
- data integrity awareness

---

# Notes

Peserta diperbolehkan:
- menggunakan inline constraint
- menggunakan CONSTRAINT naming
- menggunakan composite UNIQUE

Selama behavior schema sesuai requirement.
