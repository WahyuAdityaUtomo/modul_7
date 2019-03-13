# modul_7

Soal

1. Berikan contoh kode keneksi untuk ke database pd php?
<?php

$host = "localhost";
$db = "db_universitas";
$uname = "root";
$pass = "";

$connect = mysqli_connect($host, $uname, $pass, $db);

if(!$connect)
{
    echo "Koneksi ke DataBase Gagal : " . mysqli_connect_error();
}

?>
2. Bagaimana cara anda membuat database pada phpMySQl!
Buka PhpMyadmin, lalu klik new kemudian beri nama database kemudian klik create.

3. Berikan code query untuk menampilkan sebuah data yang ada pada ke database?

$query = "SELECT * FROM dosen";
$result = mysqli_query($connect, $query);
$num = mysqli_num_rows($result);

4. Berikan code query untuk mengupdate sebuah data yang ada pada ke database?

$query = "UPDATE dosen SET nama_dosen = '$nama_dosen', telp = '$telp' WHERE id_dosen = $id_dosen";

$result = mysqli_query($connect, $query);

$num = mysqli_affected_rows($connect);

5. Berikan code query untuk menghapus sebuah data yang ada pada ke database?

$id_dosen = $_GET['id_dosen'];

$query = "DELETE FROM dosen WHERE id_dosen = $id_dosen";

$result = mysqli_query($connect, $query);

$num = mysqli_affected_rows($connect);

ScreenShot


1.
![php1](https://user-images.githubusercontent.com/41880161/54256521-de5fbe80-458e-11e9-88ce-d5a58a6d6d2c.JPG)
2.
![php2](https://user-images.githubusercontent.com/41880161/54256522-de5fbe80-458e-11e9-8940-1e49fc85d05e.JPG)
3.
![php3](https://user-images.githubusercontent.com/41880161/54256524-def85500-458e-11e9-93c9-bc430a4e8f1e.JPG)
4.
![php4](https://user-images.githubusercontent.com/41880161/54256525-def85500-458e-11e9-966b-51d38d8f906f.JPG)
5.
![php5](https://user-images.githubusercontent.com/41880161/54256527-df90eb80-458e-11e9-9a3d-fc848c6a39af.JPG)



