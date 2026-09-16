# Kaylila-dan-Lauren-TTS-4
"""
input_data.py
Bagian Anggota A - Fungsi untuk mencatat (input) data hasil panen.
"""

data_panen = []  # menyimpan semua data panen dalam bentuk list of dict


def input_data_panen():
    """Meminta input data panen dari pengguna dan menyimpannya ke list data_panen."""
    print("\n=== Input Data Panen ===")
    nama_petani = input("Nama petani   : ")
    jenis_tanaman = input("Jenis tanaman : ")
    tanggal_panen = input("Tanggal panen (DD-MM-YYYY): ")

    while True:
        try:
            berat_panen = float(input("Berat panen (kg): "))
            break
        except ValueError:
            print("Input tidak valid, masukkan angka. Contoh: 120.5")

    while True:
        try:
            harga_per_kg = float(input("Harga per kg (Rp): "))
            break
        except ValueError:
            print("Input tidak valid, masukkan angka. Contoh: 5000")

    data = {
        "nama_petani": nama_petani,
        "jenis_tanaman": jenis_tanaman,
        "tanggal_panen": tanggal_panen,
        "berat_panen": berat_panen,
        "harga_per_kg": harga_per_kg,
    }

    data_panen.append(data)
    print("Data panen berhasil disimpan.\n")


def lihat_semua_data():
    """Menampilkan seluruh data panen yang sudah diinput (untuk pengecekan)."""
    if not data_panen:
        print("Belum ada data panen.")
        return

    print("\n=== Daftar Data Panen ===")
    for i, d in enumerate(data_panen, start=1):
        print(f"{i}. {d['nama_petani']} - {d['jenis_tanaman']} - "
              f"{d['berat_panen']} kg - {d['tanggal_panen']}")


# Menu sederhana untuk menjalankan fungsi input berulang kali
def main():
    while True:
        print("\n1. Input data panen")
        print("2. Lihat semua data")
        print("3. Keluar")
        pilihan = input("Pilih menu: ")

        if pilihan == "1":
            input_data_panen()
        elif pilihan == "2":
            lihat_semua_data()
        elif pilihan == "3":
            print("Program selesai.")
            break
        else:
            print("Pilihan tidak valid.")


if __name__ == "__main__":
    main()
