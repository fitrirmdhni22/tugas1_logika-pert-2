|                |                    |
| -------------- | ------------------ |
|      Nama    | Fitri Ramadhani |
|      NIM     |      312410085     |
|     Kelas    |      TI.24.A.1      |
|  Mata Kuliah | Logika Informatika (tugas pert-2) |

#### Soal Pertanyaan
``` Sebuah jasa pengiriman memiliki aturan biaya yang bergantung pada beberapa faktor. Biaya dasar pengiriman ditetapkan sebesar Rp 10.000.
Jika berat paket melebihi 5 kg, maka akan dikenakan tambahan biaya sebesar Rp 5.000. Selain itu, jika jarak pengiriman lebih dari 10 km, maka ada tambahan biaya sebesar Rp 8.000.
Jika pelanggan memilih layanan pengiriman express, maka akan dikenakan tambahan biaya sebesar Rp 20.000. Namun, jika pelanggan merupakan member, mereka akan mendapatkan diskon 10% dari total biaya pengiriman yang dihitung sebelum diskon.

Buatlah sebuah fungsi dalam Python yang dapat menghitung total biaya pengiriman berdasarkan aturan tersebut, dengan parameter berat paket, jarak pengiriman, jenis pengiriman (biasa atau express), serta status keanggotaan pelanggan (member atau non-member).
```

# Input Program
```python
def hitung_biaya_pengiriman(berat, jarak, jenis_pengiriman, status_member):
    biaya_dasar = 10000
    biaya_total = biaya_dasar
    rincian_biaya = [("Biaya Dasar", biaya_dasar)]
    
    if berat > 5:
        tambahan_berat = 5000
        biaya_total += tambahan_berat
        rincian_biaya.append(("Biaya Berat > 5 kg", tambahan_berat))
    
    if jarak > 10:
        tambahan_jarak = 8000
        biaya_total += tambahan_jarak
        rincian_biaya.append(("Biaya Jarak > 10 km", tambahan_jarak))
    
    if jenis_pengiriman.lower() == "express":
        biaya_express = 20000
        biaya_total += biaya_express
        rincian_biaya.append(("Biaya Pengiriman Express", biaya_express))
    
    diskon = 0
    if status_member.lower() == "member":
        diskon = biaya_total * 0.1
        biaya_total -= diskon
        rincian_biaya.append(("Diskon Member (10%)", -diskon))
    
    print(f"{'Keterangan':<25} {'Biaya (Rp)'}")
    print("="*40)
    for item in rincian_biaya:
        print(f"{item[0]:<25} {item[1]:>10,.2f}")
    print("="*40)
    print(f"{'Total Biaya Pengiriman':<25} {biaya_total:>10,.2f}")
    
    return biaya_total

if __name__ == "__main__":
    nama = input("Masukkan Nama: ")
    nim = input("Masukkan NIM: ")
    print(f"Halo, {nama} (NIM: {nim})!\n")
    
    try:
        berat_paket = float(input("Masukkan berat paket (kg): "))
        jarak_pengiriman = float(input("Masukkan jarak pengiriman (km): "))
        jenis_pengiriman = input("Masukkan jenis pengiriman (biasa/express): ").strip().lower()
        status_member = input("Apakah Anda member? (member/non-member): ").strip().lower()
        
        total_biaya = hitung_biaya_pengiriman(berat_paket, jarak_pengiriman, jenis_pengiriman, status_member)
    except ValueError:
        print("Input tidak valid. Pastikan berat dan jarak menggunakan angka.")
```

### Output Program
```
PS C:\Users\AXIOO\Documents\KULIAH\KULIAH\tugas logika pert2> python -u "c:\Users\AXIOO\Documents\KULIAH\KULIAH\tugas logika pert2\tugas.py"
Masukkan Nama: FITRI RAMADHANI
Masukkan NIM: 312410085
Halo, FITRI RAMADHANI (NIM: 312410085)!

Masukkan berat paket (kg): 8
Masukkan jarak pengiriman (km): 14
Masukkan jenis pengiriman (biasa/express): biasa
Apakah Anda member? (member/non-member): member
Keterangan                Biaya (Rp)
========================================
Biaya Dasar                10,000.00
Biaya Berat > 5 kg          5,000.00
Biaya Jarak > 10 km         8,000.00
Diskon Member (10%)        -2,300.00
========================================
Total Biaya Pengiriman     20,700.00

PS C:\Users\AXIOO\Documents\KULIAH\KULIAH\tugas logika pert2> python -u "c:\Users\AXIOO\Documents\KULIAH\KULIAH\tugas logika pert2\tugas.py"
Masukkan Nama: Arya Mohan
Masukkan NIM: 312410098
Halo, Arya Mohan (NIM: 312410098)!

Masukkan berat paket (kg): 6
Masukkan jarak pengiriman (km): 12
Masukkan jenis pengiriman (biasa/express): express
Apakah Anda member? (member/non-member): non-member
Keterangan                Biaya (Rp)
========================================
Biaya Dasar                10,000.00
Biaya Berat > 5 kg          5,000.00
Biaya Jarak > 10 km         8,000.00
Biaya Pengiriman Express   20,000.00
========================================
Total Biaya Pengiriman     43,000.00
PS C:\Users\AXIOO\Documents\KULIAH\KULIAH\tugas logika pert2>
```
### SEKIAN TERIMA KASIH
