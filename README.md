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


