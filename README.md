Latihan1.py
1. Tampilkan n bilangan acak yang lebih kecil dari 0,5
2. nilai n diisi pada saat runtime
3. anda bisa menggunakan kombinasi while dan for untuk
4. gunakan fungsi random() yang dapat diimport terlebih dahulu
import random

# Meminta input nilai n dari pengguna
n = int(input("Masukkan jumlah bilangan acak yang ingin dihasilkan: "))

# Counter untuk menghitung jumlah bilangan acak yang telah dihasilkan
count = 0

# Menghasilkan dan menampilkan n bilangan acak yang lebih kecil dari 0.5
while count < n:
    angka_acak = random.random()  # Menghasilkan bilangan acak antara 0 dan 1
    if angka_acak < 0.5:
        print(angka_acak)
        count += 1
Penjelasan:
Program meminta pengguna untuk memasukkan nilai n, yaitu jumlah bilangan acak yang ingin dihasilkan.
Variabel count digunakan untuk melacak jumlah bilangan acak yang telah dihasilkan dan ditampilkan.
while loop berjalan hingga jumlah bilangan yang dihasilkan (count) mencapai nilai n.
Fungsi random.random() menghasilkan bilangan acak antara 0 dan 1.
Jika bilangan acak yang dihasilkan lebih kecil dari 0.5, bilangan tersebut dicetak, dan count bertambah 1.

Masukkan jumlah bilangan acak yang ingin dihasilkan: 2
0.3941907227644629
0.4661362905543749

Latihan2.py
Seorang pengusaha menginvestasikan uangnya untuk memulai usahanya dengan modal
awal 100 juta, pada bulan pertama dan kedua belum mendapatkan laba. pada bulan ketiga
baru mulai mendapatkan laba sebesar 1% dan pada bulan ke 5, pendapatan meningkat 5%,
selanjutnya pada bulan ke 8 mengalami penurunan keuntungan sebesar 2%, sehingga laba
menjadi 3%. Hitung total keuntungan selama 8 bulan berjalan usahanya.
JAWAB:
# Modal awal
modal_awal = 100_000_000  # 100 juta

# Persentase laba per bulan (sesuai kondisi)
laba_per_bulan = [0, 0, 0.01, 0.01, 0.05, 0.05, 0.05, 0.03]

# Menghitung total keuntungan selama 8 bulan
total_keuntungan = 0
for bulan, laba in enumerate(laba_per_bulan):
    keuntungan_bulan_ini = modal_awal * laba
    total_keuntungan += keuntungan_bulan_ini
    print(f"Bulan {bulan+1}: Keuntungan = {keuntungan_bulan_ini:.2f}")

# Output total keuntungan selama 8 bulan
print(f"Total Keuntungan selama 8 bulan: {total_keuntungan:.2f}")

Penjelasan:
modal_awal adalah modal awal yang diinvestasikan pengusaha.
laba_per_bulan adalah daftar persentase laba per bulan sesuai dengan kondisi yang diberikan.
Loop for digunakan untuk menghitung keuntungan per bulan berdasarkan persentase laba yang telah ditentukan.
Hasil total_keuntungan selama 8 bulan akan dicetak di akhir.
Jalankan kode ini untuk mendapatkan hasil total keuntungan dalam 8 bulan.

Bulan 1: Keuntungan = 0.00
Bulan 2: Keuntungan = 0.00
Bulan 3: Keuntungan = 1000000.00
Bulan 4: Keuntungan = 1000000.00
Bulan 5: Keuntungan = 5000000.00
Bulan 6: Keuntungan = 5000000.00
Bulan 7: Keuntungan = 5000000.00
Bulan 8: Keuntungan = 3000000.00
Total Keuntungan selama 8 bulan: 20000000.00

Latihanpy.3
# Saldo awal
saldo = 1_000_000

# Fungsi untuk menampilkan menu dan menjalankan simulasi ATM
def atm():
    global saldo
    while True:
        print("\n=== Selamat Datang di Mesin ATM ===")
        print("1. Cek Saldo")
        print("2. Tarik Tunai")
        print("3. Keluar")
        
        # Meminta pilihan dari pengguna
        pilihan = input("Pilih menu (1/2/3): ")
        
        if pilihan == '1':
            # Tampilkan saldo saat ini
            print(f"Saldo Anda saat ini: Rp{saldo:,}")
        
        elif pilihan == '2':
            # Meminta jumlah penarikan
            try:
                jumlah_tarik = int(input("Masukkan jumlah yang ingin ditarik: Rp"))
                
                # Mengecek apakah saldo mencukupi
                if jumlah_tarik > saldo:
                    print("Saldo tidak mencukupi. Silakan masukkan jumlah yang lebih kecil.")
                elif jumlah_tarik <= 0:
                    print("Jumlah penarikan tidak valid.")
                else:
                    saldo -= jumlah_tarik
                    print(f"Penarikan berhasil. Sisa saldo Anda: Rp{saldo:,}")
            
            except ValueError:
                print("Masukkan jumlah dalam angka.")
        
        elif pilihan == '3':
            # Keluar dari program
            print("Terima kasih telah menggunakan ATM. Selamat tinggal!")
            break
        
        else:
            print("Pilihan tidak valid. Silakan pilih menu yang tersedia.")

# Menjalankan program ATM
atm()

Penjelasan:
saldo diinisialisasi dengan nilai Rp1.000.000 sebagai saldo awal.
Fungsi atm() digunakan untuk menampilkan menu ATM dan menerima input dari pengguna.
Program menggunakan while loop untuk menampilkan menu secara terus-menerus hingga pengguna memilih opsi "Keluar".
Jika pengguna memilih "Cek Saldo", saldo saat ini ditampilkan.
Jika pengguna memilih "Tarik Tunai", program meminta input jumlah yang akan ditarik, memeriksa apakah saldo mencukupi, dan mengurangi saldo jika memungkinkan.
Jika pengguna memilih "Keluar", program akan berhenti.
Jalankan kode ini untuk melihat simulasi mesin ATM.

=== Selamat Datang di Mesin ATM ===
1. Cek Saldo
2. Tarik Tunai
3. Keluar
Pilih menu (1/2/3): 1
Saldo Anda saat ini: Rp1,000,000

=== Selamat Datang di Mesin ATM ===
1. Cek Saldo
2. Tarik Tunai
3. Keluar
Pilih menu (1/2/3): 2     
Masukkan jumlah yang ingin ditarik: Rp900000
Penarikan berhasil. Sisa saldo Anda: Rp100,000

=== Selamat Datang di Mesin ATM ===
1. Cek Saldo
2. Tarik Tunai
3. Keluar
Pilih menu (1/2/3): 3
Terima kasih telah menggunakan ATM. Selamat tinggal!
