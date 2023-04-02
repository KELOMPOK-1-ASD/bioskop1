# bioskop1
# log in and menus
username = ''
password = ''
def login():
    global username
    global password
    username = input("Masukkan Nama: ")
    password = input("Masukkan password: ")
    for each in pelanggan:
        if username == each["nama"] and password == each["password"]:
            clear()
            print("tunggu sebentar.")
            clear()
            print("tunggu sebentar..")
            clear()
            print("tunggu sebentar...")
            clear()
            print("login berhasil")
            clear()
            menu_member()
            break
    else:
        print(colored("username dan password anda salah", 'red'))
        welcome()

def register():
    nama = input('Masukan Nama Baru: ')
    for each in pelanggan:
        if  nama in each["nama"]:
            print("Nama sudah ada")
            welcome()
            break
    else:
        password = input('Masukan Password Baru: ')
        pelanggan.append(
            {
            'nama':(nama),
            'password':(password)}
        )
        kusus_nama_user.append(nama)
        clear()
        print("tunggu sebentar.")
        clear()
        print("tunggu sebentar..")
        clear()
        print("tunggu sebentar...")
        clear()
        print("akun baru berhasil dibuat")
        clear()
        welcome()
    
        

 
def admin():
    nama = input("Masukkan Nama: ")
    password = input("Masukkan password: ")
    if nama == data_admin['nama'] and password == data_admin['password']:
        clear()
        print("tunggu sebentar.")
        clear()
        print("tunggu sebentar..")
        clear()
        print("tunggu sebentar...")
        clear()
        print("login berhasil")
        clear()
        menu_admin()
    else:
        print(colored("username dan password anda salah", 'red'))
        welcome()

        
def ubah_pw():
    pw = input("Masukkan password Lama: ")
    for each in pelanggan:
        if pw == each["password"] and password == each["password"]:
            each["password"] = input("Masukkan password Baru: ")
            clear()
            print("password Anda Berhasil Diganti")
            print("Login Kembali")
            login()
            break
    else:
        print(colored("password anda salah", 'red'))
        edit_akun()
        
def ubah_nama():
    lama = input("Masukkan Nama Lama: ")
    for each in pelanggan:
        if lama == each["nama"] and username == each["nama"]:
            each["nama"] = input("Masukkan Nama Baru: ")
            kusus_nama_user.append(each["nama"])
            kusus_nama_user.pop(kusus_nama_user.index(lama))
            clear()
            print("Nama Anda Berhasil Diganti")
            print("Login Kembali")
            login()
            break
    else:
        print(colored("nama anda salah", 'red'))
        edit_akun()

def edit_akun():
    print('Pilihan')
    print('1. Edit Nama')
    print('2. Edit password')
    print('3. Menu')
    while True:
        try:
            pilih = int(input('Masukkan Pilihan: '))
            break
        except:
            print("Masukan Dengan Angka")
    if pilih == 1:
        clear()
        ubah_nama()
    elif pilih == 2:
        clear()
        ubah_pw()
    elif pilih == 3:
        welcome()
    else:
        print('Pilihan Tidak Ada')
        edit_akun()

def welcome():
    print(colored('+===============================================+', 'cyan'))
    print(colored('|', 'cyan'), colored('Selamat datang di bioskop xxi                ', 'yellow'), colored('|', 'cyan'))
    print(colored('|', 'cyan'), colored('silakan login sesuai role anda               ', 'yellow'), colored('|', 'cyan'))
    print(colored('|===============================================|', 'cyan'))
    print(colored('|', 'cyan'), colored('1. Admin                                     ', 'yellow'), colored('|', 'cyan'))
    print(colored('|', 'cyan'), colored('2. pelanggan                                 ', 'yellow'), colored('|', 'cyan'))
    print(colored('|', 'cyan'), colored('3. register                                  ', 'yellow'), colored('|', 'cyan'))
    print(colored('|', 'cyan'), colored('4. Keluar aplikasi                           ', 'yellow'), colored('|', 'cyan'))
    print(colored('+===============================================+', 'cyan'))
    while True:
        try:
            options = int(input("masukan pilihan: "))
            
            break
        except:
            print("Masukan Dengan Angka")
    if options == 1:
        clear()
        admin()
        clear()
    elif options == 2:
        clear()
        login()
        clear()
    elif options == 3:
        clear()
        register()
        clear()
    elif options == 4:
        print("Terima Kasih Telah Mengunjungi Bioskop kami")
        raise SystemExit
    else:
        print("Pilihan Tidak Ada")
        
        welcome()

def menu_admin():
    ulang = 'ya'
    while ulang == 'ya':
        print(colored('==========================', 'cyan'))
        print(colored("Selamat Datang Admin",'green'))
        print(colored('==========================', 'cyan'))
        print(colored("1. Tambah film",'yellow'))
        print(colored("2. Lihat film",'yellow'))
        print(colored("3. cari film",'yellow'))
        print(colored("4. Hapus film",'yellow'))
        print(colored("5. Ubah film",'yellow'))
        print(colored("6. Data film yg masuk",'yellow'))
        print(colored("7. Data pelanggan",'yellow'))
        print(colored("8. Logout",'yellow'))
        print(colored("9. Keluar aplikasi",'yellow'))
        print(colored('==========================', 'cyan'))
        while True:
            try:
                pilih = int(input("Masukkan Pilihan Anda: "))
                break
            except:
                print("Masukan Dengan Angka")
        if __name__ == '__main__':
            if pilih == 1:
                clear()
                tempat.addfilm()
                clear()
                time.sleep(1.5)
            elif pilih == 2:
                if len(tempat.films) < 1:
                    clear()
                    print('tidak ada film yg tersedia')
                    clear()
                    time.sleep(1.5)
                    continue
                clear()
                tempat.lihatdata()
                input("Tekan Enter Untuk Kembali")
                clear()
                time.sleep(1.5)
            elif pilih == 3:
                if len(tempat.films) < 1:
                    clear()
                    print('tidak ada film yg tersedia')
                    clear()
                    time.sleep(1.5)
                    continue
                clear()
                tempat.lihatdata()
                search()
                time.sleep(1.5)
                clear()
                    
            elif pilih == 4:
                if len(tempat.films) < 1:
                    clear()
                    print('tidak ada film yg tersedia')
                    clear()
                    time.sleep(1.5)
                    continue
                clear()
                tempat.lihatdata()
                while True:
                    try:
                        
                        item = int(input('Pilih Nomor film Yang Ingin Dihapus: '))
                        time.sleep(1.5)
                        break
                    except:
                        print("Masukan Dengan Angka")
                if item  > len(tempat.films):
                    clear()
                    print('Pilihan Nomor Tidak Ada')
                    clear()
                    time.sleep(1.5)
                else:
                    tempat.films.remove(tempat.films[item - 1])
                    jb.pop(item)
                    clear()
                    print("film Yang Anda Pilih Telah Dihapus")
                    clear()
                    time.sleep(1.5)
            elif pilih == 5:
                time.sleep(1.5)
                if len(tempat.films) < 1:
                    clear()
                    print('tidak ada film yg tersedia')
                    clear()
                    time.sleep(1.5)
                    continue
                clear()
                tempat.lihatdata()
                while True:
                    try:
                        item = int(input('Pilih Nomor film Yang Ingin Diupdate: '))
                        break
                    except:
                        print("Masukan Dengan Angka")
                if item  > len(tempat.films):
                    clear()
                    print('Pilihan Nomor Tidak Ada')
                    clear()
                    time.sleep(1.5)
                else:
                    clear()
                    ubah_barang = tambah()
                    if ubah_barang.addfilm() == True :
                        tempat.films.remove(tempat.films[item - 1])
                        tempat.films.insert(item, ubah_barang)
                        print('film Yang Anda Pilih Telah Diupdate')
                        clear()
                        time.sleep(1.5)
                if len(tempat.films) < 1:
                    clear()
                    print('tidak ada film yg tersedia')
                    clear()
                    time.sleep(1.5)
                    continue
            elif pilih == 6:
                clear()
                time.sleep(1.5)
                if len(tempat.films) < 1:
                    clear()
                    print('Tidak Ada film Yang Pernah Di Data atau Kosong')
                    clear()
                    time.sleep(1.5)
                    continue
                clear()
                print(link.printList())
                print("Banyaknya film Yang Pernah Masuk: ", queue.size())
                input("\nTekan Enter Untuk Kembali")
                clear()
                time.sleep(1.5)
            elif pilih == 7:
                clear()
                users.field_names = ['Nama', 'Password']
                users.clear_rows()
                for i in range(len(pelanggan)):
                    users.add_row([pelanggan[i]['nama'], pelanggan[i]['password']])
                print(users)
                print(colored("============================================", 'cyan'))
                print(colored("1. urutkan nama pelanggan secara ascending",'yellow' ))
                print(colored("2. urutkan nama pelanggan secara descending",'yellow'))
                print(colored("3. kembali",'yellow'))
                print(colored("============================================", 'cyan'))
                while True:
                    try:
                        pilih = int(input("Masukkan Pilihan Anda: "))
                        break
                    except:
                        print("Masukan Dengan Angka")
                        clear()
                if pilih == 1:
                    clear()
                    time.sleep(1.5)
                    print("nama pelanggan")
                    n = len(kusus_nama_user)
                    quickSort(kusus_nama_user, 0, n-1)
                    for x in kusus_nama_user:
                        print("~>",x)
                    input("Tekan enter untuk kembali ke menu")
                    time.sleep(0.5)
                    clear()
                   
                    

                elif pilih == 2:
                    clear()
                    time.sleep(0.5)
                    print("nama pelanggan")
                    n = len(kusus_nama_user)
                    quickSort(kusus_nama_user, 0, n-1 )
                    for i in range(0, len(kusus_nama_user)) :
                        kusus_nama_user[i] = (kusus_nama_user[i])
                        kusus_nama_user.sort(reverse = True)
                    for x in kusus_nama_user:
                        print("~>",x)
                    input("Tekan enter untuk kembali ke menu")
                    time.sleep(0.5)
                    clear()
                    
                elif pilih == 3:
                    clear()
                    time.sleep(0.5)
                    
                    menu_admin()
                else:
                    clear()
                    print("Pilihan Tidak Ada")
                    clear()
                    time.sleep(0.5)
                    
                    menu_admin()
            elif pilih == 8:
                clear()
                time.sleep(0.1)
                print(colored("anda berhasil logout", 'green'))
                clear()
                print("waktu anda logout")
                print()
                print("~ tanggal  :",day)
                print("~ jam      :",current_time)

                welcome()
            elif pilih == 9:
                print("Terima Kasih Telah Mengunjungi Bioskop kami")
                raise SystemExit
            else:
                print("Pilihan Hanya 1-10!")
                print("Jika Ingin Kembali Ketik ya atau Jika Tidak Tekan Enter")
                ulang = input('Ingin Kembali? ')
    else:
        print("Terima Kasih Telah Mengunjungi Bioskop kami")
        raise SystemExit

def menu_member():
    ulang = 'ya'
    while ulang == 'ya':
        global username
        print(colored('==========================', 'cyan'))
        print(f'\033[1;32;40mselamat datang {username}\033[0m')
        print(f"\033[1;32;40msaldo anda: {pelanggan[0]['saldo']}\033[0m")
        print(colored("========================", 'cyan'))
        print(colored("1. struk pembelian",'yellow'))
        print(colored("2. beli film",'yellow'))
        print(colored("3. Edit Akun",'yellow'))
        print(colored("4. logout",'yellow'))
        print(colored("5. Keluar aplikasi",'yellow'))
        print(colored("========================", 'cyan'))
        while True:
            try:
                pilih = int(input("Masukkan Pilihan Anda: "))
                break
            except:
                print("Masukan Dengan Angka")
        if __name__ == '__main__':
            if pilih == 1:
                clear()
                print(colored("==========================================", 'cyan'))
                print("struk pembelian")
                print()
                for i in range(len(beli_film)):
                    if beli_film[i]['jumlah'] > 1:
                        print("nama film   : ",beli_film[i]['jenis'])
                        print("jam_tayang film   : ",beli_film[i]['jam_tayang'])
                        print("Harga film  : ",beli_film[i]['harga'])
                        print("uang          : ",beli_film[i]['jumlah'])
                        print("kembalian     : ",beli_film[i]['kembalian'])
                        print("\n")

                print(colored("==========================================", 'cyan'))
                input("Tekan enter untuk kembali ke menu")
                clear()
                time.sleep(1.5)
            elif pilih == 2:
                time.sleep(1.5)
                if len(tempat.films) < 1:
                    clear()
                    print('film tidak tersedia')
                    clear()
                    time.sleep(1.5)
                    continue
                clear()
                tempat.membeli_film()
                time.sleep(1.5)
                clear()
            elif pilih == 3:
                clear()
                time.sleep(1.5)
                edit_akun()
                clear()
            elif pilih == 4:
                clear()
                time.sleep(0.1)
                print(colored("anda berhasil logout", 'green'))
                clear()
                print("waktu anda logout")
                print()
                print("~ tanggal  :",day)
                print("~ jam      :",current_time)

                welcome()
            elif pilih == 5:
                print("Terima Kasih Telah Mengunjungi Bioskop kami")
                raise SystemExit
            else:
                print("Pilihan Hanya 1-6!")
                print("Jika Ingin Kembali Ketik ya atau Jika Tidak Tekan Enter")
                ulang = input('Ingin Kembali? ')
                
    else:
        print("Terima Kasih Telah Mengunjungi Bioskop kami")
        raise SystemExit

welcome()
