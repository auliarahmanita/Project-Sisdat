# Wang.Cash

Anggota kelompok 3 :
* Aulia Rahmanita     (140810200004)
* Nawang Ilmi Adzani  (140810200014)
* Indah Sutriyati     (140810200040)

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

insert into admin values
('111001' , 'Anggie Forestry' , 'P' , 'Kuningan'),
('111002' , 'Wildan Hanif Musyaffa' , 'L' , 'Kebumen')
;
Query OK, 2 rows affected (0.01 sec)
Records: 2  Duplicates: 0  Warnings: 0




