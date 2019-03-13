# modul_7
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
<?php

include '../connect.php';

$query = "SELECT * FROM dosen";
$result = mysqli_query($connect, $query);
$num = mysqli_num_rows($result);

?>

<!DOCTYPE html>
<html>
<head>
    <title>Page Title</title>
</head>
<body>
    <table border='1'>
    <h2>Data Dosen</h2>
    <tr>
        <th>No.</th>
        <th>Nama Dosen</th>
        <th>Telepon</th>
        <th>Aksi</th>
        <th>Delete</th>
    </tr>

    <?php
        if($num > 0)
        {
            $no = 1;
            while($data = mysqli_fetch_assoc($result))
            {
                echo "<tr>";
                echo "<td>" . $no . "</td>";
                echo "<td>" . $data['nama_dosen'] . "</td>";
                echo "<td>" . $data['telp'] . "</td>";
                echo "<td><a href='Form-Update.php?id_dosen=" . $data['id_dosen'] . "'>Edit</a> | ";
                echo "<td><a href='Delete.php?id_dosen=" . $data['id_dosen'] . "'onclick='return confirm(\"Apakah Anda Yakin Ingin Menghapus Data ?\")' >Hapus</a></td>";              
                echo "</tr>";
                $no++;
            }
        }
        else
        {
            echo "<td colspan='3'> Tidak Ada Data</td>";
        }
    ?>

    </table>
</body>
</html>
4. Berikan code query untuk mengupdate sebuah data yang ada pada ke database?
<?php

include '../connect.php';

$id_dosen = $_POST['id_dosen'];
$nama_dosen = $_POST['nama_dosen'];
$telp = $_POST['telp'];

$query = "UPDATE dosen SET nama_dosen = '$nama_dosen', telp = '$telp' WHERE id_dosen = $id_dosen";

$result = mysqli_query($connect, $query);

$num = mysqli_affected_rows($connect);


if($num > 0)
{
    echo "Berhasil Update Data <br>";
}
else
{
    echo "Gagal Update Data <br>";
}
echo "<a href='Read.php'> Lihat Data</a>";

?>

5. Berikan code query untuk menghapus sebuah data yang ada pada ke database?
<?php
include '../connect.php';

$id_dosen = $_GET['id_dosen'];

$query = "DELETE FROM dosen WHERE id_dosen = $id_dosen";

$result = mysqli_query($connect, $query);

$num = mysqli_affected_rows($connect);

if($num > 0)
{
    echo "Berhasil Hapus Data <br>";
}
else
{
    echo "Gagal Hapus Data <br>";
}
echo "<a href='read.php'> Lihat Data</a>";
?>
