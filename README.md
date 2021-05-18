# Wang.Cash

Anggota kelompok 3 :
* Aulia Rahmanita     (140810200004)
* Nawang Ilmi Adzani  (140810200014)
* Indah Sutriyati     (140810200040)

# Wang.Cash

Anggota kelompok 3 :
* Aulia Rahmanita     (140810200004)
* Nawang Ilmi Adzani  (140810200014)
* Indah Sutriyati     (140810200040)

mysql> create database cobaproject;
Query OK, 1 row affected (0.13 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| bentuk_tiga        |
| cobaproject        |
| db_mahasiswa       |
| dbcustomer         |
| information_schema |
| jurusan            |
| kuis2              |
| kuliah             |
| mahasiswa          |
| mysql              |
| performance_schema |
| pertemuan4         |
| pustaka            |
| sys                |
| tk_normalisasi     |
| uts                |
+--------------------+
16 rows in set (0.06 sec)

mysql> use cobaproject
Database changed

mysql> create table mahasiswa (
ID_Mhs int (6) NOT NULL,
Nama_Mhs varchar(40),
Jenis_Kelamin varchar (1),
Alamat varchar (40),
Status varchar (10),
primary key (ID_Mhs)
);
Query OK, 0 rows affected, 1 warning (0.19 sec)

mysql> desc mahasiswa;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| ID_Mhs        | int         | NO   | PRI | NULL    |       |
| Nama_Mhs      | varchar(40) | YES  |     | NULL    |       |
| Jenis_Kelamin | varchar(1)  | YES  |     | NULL    |       |
| Alamat        | varchar(40) | YES  |     | NULL    |       |
| Status        | varchar(10) | YES  |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
5 rows in set (0.02 sec)


create table hutang (
Kode_Hutang varchar (8) NOT NULL,
ID_Mhs int (6),
Nama_Mhs varchar(40),
Besar_Hutang varchar (25),
Tanggal_Pengeluaran date,
primary key (Kode_Hutang),
foreign key (ID_Mhs) references mahasiswa (ID_Mhs)
);
Query OK, 0 rows affected, 1 warning (0.12 sec)

create table admin (
ID_Admin int (6) NOT NULL,
Nama_Admin varchar(40),
Jenis_Kelamin varchar (1),
Alamat varchar (40),
primary key (ID_Admin)
);
Query OK, 0 rows affected, 1 warning (0.07 sec)


create table pengeluaran (
Kode_Pengeluaran varchar (8) NOT NULL,
ID_Admin int (6),
Nama_Mhs varchar(40),
Besar_Pengeluaran varchar (25),
Tanggal_Pengeluaran date,
primary key (Kode_Pengeluaran),
foreign key (ID_Admin) references admin (ID_Admin)
);
Query OK, 0 rows affected, 1 warning (0.08 sec)

create table pemasukan (
Kode_Pemasukan varchar (8) NOT NULL,
ID_Admin int (6),
Nama_Mhs varchar(40),
Besar_Pemasukan varchar (25),
Tanggal_Pemasukan date,
primary key (Kode_Pemasukan),
foreign key (ID_Admin) references admin (ID_Admin)
);
Query OK, 0 rows affected, 1 warning (0.10 sec)

show tables;
+-----------------------+
| Tables_in_cobaproject |
+-----------------------+
| admin                 |
| hutang                |
| mahasiswa             |
| pemasukan             |
| pengeluaran           |
+-----------------------+
5 rows in set (0.02 sec)


insert into mahasiswa values
('200004' , 'Aulia Rahmanita' , 'P' , 'Kuningan' , 'BE'),
('200014' , 'Nawang Ilmi Adzani' , 'P' , 'Bandung' , 'BE'),
('200040' , 'Indah Sutriyati' , 'P' , 'Cimahi' , 'BE'),
('200001' , 'Ariq Hakim Ruswadi' , 'L' , 'Bandung' , 'non-BE'),
('200002' , 'Rommel Malik Kusnadi' , 'L' , 'Kuningan' , 'non-BE'),
('200003' , 'Affan Rifqy Kurniadi' , 'L' , 'Bandung' , 'non-BE'),
('200006' , 'Hali Putri Aisyah' , 'P' , 'Bandung' , 'non-BE'),
('200009' , 'Wafi Fahruzzaman' , 'L' , 'Bandung' , 'BE'),
('200010' , 'Rizky Mahardika Hariyanto' , 'L' , 'Cimahi' , 'BE'),
('200033' , 'Rafa Azka Ulinnuha' , 'P' , 'Bekasi' , 'non-BE'),
('200047' , 'Kharisma Fitri Nurunnisa Siahaan' , 'P' , 'Bandung' , 'non-BE'),
('200055' , 'Wafa Tsabita' , 'P' , 'Sumedang' , 'BE'),
('200062' , 'Zahran Hanif Fathanmubin' , 'L' , 'Jakarta' , 'BE'),
('200064' , 'Muhammad Ariiq Rakha Shafa' , 'L' , 'Garut' , 'BE'),
('200036' , 'Laura Azra Aprilyanti' , 'P' , 'Banjar' , 'BE')
;
Query OK, 16 rows affected (0.03 sec)
Records: 16  Duplicates: 0  Warnings: 0

select *from mahasiswa;
+--------+----------------------------------+---------------+----------+--------+
| ID_Mhs | Nama_Mhs                         | Jenis_Kelamin | Alamat   | Status |
+--------+----------------------------------+---------------+----------+--------+
| 200001 | Ariq Hakim Ruswadi               | L             | Bandung  | non-BE |
| 200002 | Rommel Malik Kusnadi             | L             | Kuningan | non-BE |
| 200003 | Affan Rifqy Kurniadi             | L             | Bandung  | non-BE |
| 200004 | Aulia Rahmanita                  | P             | Kuningan | BE     |
| 200006 | Hali Putri Aisyah                | P             | Bandung  | non-BE |
| 200009 | Wafi Fahruzzaman                 | L             | Bandung  | BE     |
| 200010 | Rizky Mahardika Hariyanto        | L             | Cimahi   | BE     |
| 200013 | Rihlan Lumenda Suherman          | L             | Sukabumi | BE     |
| 200014 | Nawang Ilmi Adzani               | P             | Bandung  | BE     |
| 200033 | Rafa Azka Ulinnuha               | P             | Bekasi   | non-BE |
| 200036 | Laura Azra Aprilyanti            | P             | Banjar   | BE     |
| 200040 | Indah Sutriyati                  | P             | Cimahi   | BE     |
| 200047 | Kharisma Fitri Nurunnisa Siahaan | P             | Bandung  | non-BE |
| 200055 | Wafa Tsabita                     | P             | Sumedang | BE     |
| 200062 | Zahran Hanif Fathanmubin         | L             | Jakarta  | BE     |
| 200064 | Muhammad Ariiq Rakha Shafa       | L             | Garut    | BE     |
+--------+----------------------------------+---------------+----------+--------+
16 rows in set (0.00 sec)

mysql> insert into admin values
('111001' , 'Anggie Forestry' , 'P' , 'Kuningan'),
('111002' , 'Wildan Hanif Musyaffa' , 'L' , 'Kebumen')
;
Query OK, 2 rows affected (0.01 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> select *from admin;
+----------+-----------------------+---------------+----------+
| ID_Admin | Nama_Admin            | Jenis_Kelamin | Alamat   |
+----------+-----------------------+---------------+----------+
|        1 | Anggie Forestry       | P             | Kuningan |
|        2 | Wildan Hanif Musyaffa | L             | Kebumen  |
+----------+-----------------------+---------------+----------+
2 rows in set (0.00 sec)


mysql> desc pengeluaran;
+---------------------+-------------+------+-----+---------+-------+
| Field               | Type        | Null | Key | Default | Extra |
+---------------------+-------------+------+-----+---------+-------+
| Kode_Pengeluaran    | varchar(8)  | NO   | PRI | NULL    |       |
| ID_Admin            | int         | YES  | MUL | NULL    |       |
| Nama_Mhs            | varchar(40) | YES  |     | NULL    |       |
| Besar_Pengeluaran   | varchar(25) | YES  |     | NULL    |       |
| Tanggal_Pengeluaran | date        | YES  |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
5 rows in set (0.02 sec)

mysql> desc pemasukan;
+-------------------+-------------+------+-----+---------+-------+
| Field             | Type        | Null | Key | Default | Extra |
+-------------------+-------------+------+-----+---------+-------+
| Kode_Pemasukan    | varchar(8)  | NO   | PRI | NULL    |       |
| ID_Admin          | int         | YES  | MUL | NULL    |       |
| Nama_Mhs          | varchar(40) | YES  |     | NULL    |       |
| Besar_Pemasukan   | varchar(25) | YES  |     | NULL    |       |
| Tanggal_Pemasukan | date        | YES  |     | NULL    |       |
+-------------------+-------------+------+-----+---------+-------+
5 rows in set (0.00 sec)

mysql> desc hutang;
+---------------------+-------------+------+-----+---------+-------+
| Field               | Type        | Null | Key | Default | Extra |
+---------------------+-------------+------+-----+---------+-------+
| Kode_Hutang         | varchar(8)  | NO   | PRI | NULL    |       |
| ID_Mhs              | int         | YES  | MUL | NULL    |       |
| Nama_Mhs            | varchar(40) | YES  |     | NULL    |       |
| Besar_Hutang        | varchar(25) | YES  |     | NULL    |       |
| Tanggal_Pengeluaran | date        | YES  |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
5 rows in set (0.00 sec)


