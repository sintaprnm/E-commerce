# e-COMMERCE

### Sinta Purnama Dewi
2205551100

## About
Program ini bertujuan untuk membuat backend API untuk aplikasi e-commerce sederhana yang nantinya memberikan response dengan format JSON. Adapun request method pada API memuat: <br/>
**GET** untuk mendapatkan list atau detail data dari entitas. <br/>
**POST** untuk membuat data entitas baru. <br/>
**PUT** untuk mengubah data dari entitas. <br/>
**DELETE** untuk menghapus data dari entitas. <br/>

Data-data yang digunakan dalam aplikasi e-Commerce ini akan disimpan pada **database SQLite** yang kemudian akan dilakukan suatu pengujian API yang telah diprogram melalui aplikasi **Postman**

## Spesifikasi API dalam Aplikasi e-Commerce 
### **GET**

- GET /users untuk mendapatkan daftar semua user yang termuat di dalam database. <br/>
`localhost:8100/users`

'''
{
    
    "User Information": [
        {
            "First_Name": "Raya",
            "Type": "seller",
            "Email": "raya1207@gmail.com",
            "Last_Name": "Indriani",
            "id_user": 1,
            "Phone Number": "081654321780"
        },
        {
            "First_Name": "Akbar",
            "Type": "seller",
            "Email": "akbar12@gmail.com",
            "Last_Name": "Sanjiwani",
            "id_user": 2,
            "Phone Number": "085643218765"
        },
        {
            "First_Name": "Asti",
            "Type": "buyer",
            "Email": "astii@gmail.com",
            "Last_Name": "Putri",
            "id_user": 3,
            "Phone Number": "081236374142"
        },
        {
            "First_Name": "Ipin",
            "Type": "buyer",
            "Email": "ipin05@gmail.com",
            "Last_Name": "Sholeh",
            "id_user": 4,
            "Phone Number": "087654678089"
        },
        {
            "First_Name": "Rio",
            "Type": "buyer",
            "Email": "rio07@gmail.com",
            "Last_Name": "Akbar",
            "id_user": 5,
            "Phone Number": "012456987012"
        },
        {
            "First_Name": "Ayu",
            "Type": "buyer",
            "Email": "ayukirkir05@gmail.com",
            "Last_Name": "Kirana",
            "id_user": 6,
            "Phone Number": "081789564392"
        },
        {
            "First_Name": "Melia",
            "Type": "buyer",
            "Email": "meliarahma14@gmail.com",
            "Last_Name": "Rahmawati",
            "id_user": 7,
            "Phone Number": "088145674322"
        }
    ]
}
'''

<br/>

- GET /users/{id} untuk mendapatkan informasi user dan alamatnya. <br/>
`localhost:8100/users/1`

'''
{

    "User Information": [
        {
            "First_Name": "Raya",
            "Type": "seller",
            "Email": "raya1207@gmail.com",
            "Last_Name": "Indriani",
            "Id": 1,
            "City": "Denpasar",
            "Phone Number": "081654321780",
            "Postcode": "80119",
            "Province": "Bali"
        }
    ]
}
'''

Url di atas membatasi tampilan data user dengan id_user = 1 sehingga menampilkan informasi user dengan id_user = 1 beserta alamat dari user tersebut. 

<br/>

- GET /users/{id}/products untuk mendapatkan daftar produk milik user. <br/>
`localhost:8100/users/1/products` 

'''
{

    "Products Information": [
        {
            "User ID": 1,
            "Nama": "Raya",
            "Harga": 20000,
            "Deskripsi": "choki-choki bikin happy",
            "ID Barang": 11,
            "Nama Produk": "Choki choki",
            "Stock": 50
        },
        {
            "User ID": 1,
            "Nama": "Raya",
            "Harga": 40000,
            "Deskripsi": "coklatnya crunchy",
            "ID Barang": 12,
            "Nama Produk": "Dilan",
            "Stock": 35
        },
        {
            "User ID": 1,
            "Nama": "Raya",
            "Harga": 60000,
            "Deskripsi": "coklatnya lumer",
            "ID Barang": 15,
            "Nama Produk": "Delvi",
            "Stock": 40
        }
    ]
}
'''

Url di atas membatasi tampilan data user dengan id_user = 1 sehingga menampilkan informasi user dengan id_user = 1 beserta produk yang dimiliki user tersebut di mana user tersebut bertipe "seller". 

<br/>

- GET /users/{id}/orders untuk mendapatkan daftar order milik user. <br/>
`localhost:8100/users/3/orders` 

'''
{

    "Order Information": [
        {
            "Order": 21,
            "Nama": "Asti",
            "Total": 40000,
            "Diskon": 0,
            "id user": 3
        },
        {
            "Order": 24,
            "Nama": "Asti",
            "Total": 50000,
            "Diskon": 0,
            "id user": 3
        },
        {
            "Order": 28,
            "Nama": "Asti",
            "Total": 60000,
            "Diskon": 0,
            "id user": 3
        }
    ]
}
'''

Url di atas membatasi tampilan data user dengan id_user = 3 sehingga menampilkan informasi user dengan id_user = 3 beserta produk yang diorder dari user tersebut di mana user tersebut bertipe "buyer". 

<br/>

- GET /users/{id}/reviews untuk mendapatkan daftar review yang dibuat oleh user. <br/>
`localhost:8100/users/5/reviews`

'''
{

    "Reviews Information": [
        {
            "User": 5,
            "star": 5,
            "First Name": "Rio",
            "Deskripsi": "pelayanannya cepat dan ramah",
            "Last Name": "Akbar",
            "order": 23
        },
        {
            "User": 5,
            "star": 3,
            "First Name": "Rio",
            "Deskripsi": "produknya enak",
            "Last Name": "Akbar",
            "order": 30
        }
    ]
}
'''

Url di atas membatasi tampilan data user dengan id_user = 5 sehingga menampilkan informasi review yang diberikan oleh user dengan id_user = 5 saja". 

<br/>

- GET /orders/{id} untuk mendapatkan informasi order, buyer, detail order, review, product title, beserta pricenya. <br/>
`localhost:8100/orders/26` 

'''
{

    "Orders Information": [
        {
            "idUser": 6,
            "idOrder": 26,
            "Description": "pelayanannya sigap",
            "Price": "55000",
            "Star": 5,
            "Note": 66666,
            "idProduct": 14,
            "Quantity": 1,
            "Title": "Aiche",
            "Name": "Ayu"
        }
    ]
}
'''

Url di atas membatasi tampilan data orders dengan id_order = 26 sehingga menampilkan informasi order, buyer, detail order, review, product title, beserta price dari id_order = 26". 

<br/>

- GET /products untuk mendapatkan daftar semua produk. <br/>
`localhost:8100/products`

'''
{
    
    "Product Information": [
        {
            "Description": "choki-choki bikin happy",
            "User": 1,
            "Price": "20000",
            "Title": "Choki choki",
            "Id": 11,
            "Stock": 50
        },
        {
            "Description": "coklatnya crunchy",
            "User": 1,
            "Price": "40000",
            "Title": "Dilan",
            "Id": 12,
            "Stock": 35
        },
        {
            "Description": "dinginnya sampe ke dna",
            "User": 2,
            "Price": "50000",
            "Title": "Walls",
            "Id": 13,
            "Stock": 75
        },
        {
            "Description": "dinginnya nyegerin",
            "User": 2,
            "Price": "55000",
            "Title": "Aiche",
            "Id": 14,
            "Stock": 50
        },
        {
            "Description": "coklatnya lumer",
            "User": 1,
            "Price": "60000",
            "Title": "Delvi",
            "Id": 15,
            "Stock": 40
        }
    ]
}
'''
<br/>

- GET /products/{id} untuk mendapatkan informasi produk dan seller. <br/>
`localhost:8100/products/1` 

'''
{

    "Product Information": [
        {
            "First_Name": "Raya",
            "Type": "seller",
            "Description": "choki-choki bikin happy",
            "Email": "raya1207@gmail.com",
            "Price": "20000",
            "Last_Name": "Indriani",
            "Title": "Choki choki",
            "Seller": 1,
            "Id": 11,
            "id_user": 1,
            "Phone Number": "081654321780",
            "Stock": 50
        },
        {
            "First_Name": "Raya",
            "Type": "seller",
            "Description": "coklatnya crunchy",
            "Email": "raya1207@gmail.com",
            "Price": "40000",
            "Last_Name": "Indriani",
            "Title": "Dilan",
            "Seller": 1,
            "Id": 12,
            "id_user": 1,
            "Phone Number": "081654321780",
            "Stock": 35
        },
        {
            "First_Name": "Raya",
            "Type": "seller",
            "Description": "coklatnya lumer",
            "Email": "raya1207@gmail.com",
            "Price": "60000",
            "Last_Name": "Indriani",
            "Title": "Delvi",
            "Seller": 1,
            "Id": 15,
            "id_user": 1,
            "Phone Number": "081654321780",
            "Stock": 40
        }
    ]
}
'''

Url di atas membatasi tampilan data produk dengan seller yang memiliki id_user = 1 sehingga menampilkan informasi produk-produk apa saja yang dimiliki oleh seller tersebut.

<br/>

### **POST**
- Membuat data baru ke dalam aplikasi <br/>
`http://localhost:8100/users`

'''
{

    "First_Name": "Mirah",
    "Type": "buyer",
    "Email": "Mirahcan45@gmail.com",
    "Last_Name": "Chantika",
    "id_user": 8,
    "Phone Number": "081456873526"
}
'''

Berdasarkan url yang diterapkan pada metode POST melalui Postman yang mana pada tabel users ditambahkan data baru dengan id_user = 8.

![image](https://github.com/sintaprnm/E-commerce/assets/114934098/5b101b16-371d-4a19-971b-69f191e361cd)
<br/>


### **PUT**
- Mengubah data yang ada di mana saya mencoba untuk mengubah data pada salah satu seller <br/>
`http://localhost:8100/users/1`

Data sebelumnya
![image](https://github.com/sintaprnm/E-commerce/assets/114934098/0dec33ac-6f29-4867-9757-48c53985d122)

'''
{
    
    "First_Name": "Raya",
    "Type": "seller",
    "Email": "emailrayabaru@gmail.com",
    "Last_Name": "Indriani",
    "id_user": 1,
    "Phone Number": "081654321780"
}
'''

Berdasarkan url yang diterapkan pada metode PUT melalui Postman yang mana user dengan id_user = 1 akan diupdate datanya sesuai dengan data yang baru diinputkan.


<br/>

### **DELETE**
- Menghapus data dari entitas tertentu dimana saya mencoba untuk menghapus data yang terdapat pada tabel ... <br/>
`http://localhost:8100/users/7`

Berdasarkan url yang diterapkan pada metode DELETE melalui Postman yang mana user dengan id_user = 7 akan dihapus dari aplikasi e-Commerce. 

<br/>
