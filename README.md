# coreCImodel

# CreateBy : ihsandulu

# 27 Nov 2021

# Codeigniter 4

Core CI Model

File digunakan didalam Model, untuk kebutuhan berikut:

1. Menangkap request berupa Get dan Post di dalam Model
2. Membuat query builder di dalam Model

==========================================================================

Cara Penggunaan:

1. Tempatkan file Core_m.php pada \app\Models
2. Rubah 'extends Model' menjadi 'extends Core_m' pada file model anda.

Contoh:

Rubah dari :

---

namespace App\Models;

use CodeIgniter\Model;

class Login_m extends Model
{

---

menjadi :

---

namespace App\Models;

class Login_m extends Core_m
{

---

Jika file anda berada di dalam folder maka tambahkan 'use App\Models\Core_m;'

Contoh : saya mempunyai file Mcost_m di dalam folder '\app\Models\Master'
Maka saya tambahkan 'use App\Models\Core_m;' sebagai berikut :

---

namespace App\Models\Master;

use App\Models\Core_m;

class Mcost_m extends Core_m
{

---

==========================================================================

Koneksi Database

Line yg berisi : $this->db = Database::connect("default"); , berguna untuk mengaktifkan database default.
Jika anda memiliki database ke dua maka aktifkan line berikut : $this->akunting = Database::connect("databasekedua");

Contoh :
Saya mempunyai 2 database pada file .env sebagai berikut:
database.default.hostname = domainkamu
database.default.database = master
database.default.username = postgres
database.default.password = passwordkamu
database.default.DBDriver = Postgre
database.default.port = 5432

database.akunting.hostname = domainkamu
database.akunting.database = accounting
database.akunting.username = postgres  
database.akunting.password = passwordkamu  
database.akunting.DBDriver = Postgre  
database.akunting.port = 5432

# dengan demikian saya akan mengaktifkan pada file Core_m.php sebagai berikut:

$this->db = Database::connect("default");
$this->akunting = Database::connect("databasekedua");

==========================================================================

**_Semoga Bermanfaat. Aamiiin_**
