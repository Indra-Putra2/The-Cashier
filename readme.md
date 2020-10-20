# The Cashier
aplikasi ini berfungsi untuk mendata barang/jasa yang 
dibeli pelanggan menggunakan software the cashier sehingga 
mempermudah dan mempercepat transaksi.

### Fungctionality
- User dapat menginputkan nama barang atau jasa
- User dapat menginputkan jumlah barang
- User dapat menginputkan harga barang

### Penjelasan Code

```c#
public Calculator()
        {
            this.listItem = new List<Item>();
        }
```
digunakan untuk membuat list

```c#
public double getSubtotal()
        {
            subtotal = quantity * price;
            return subtotal;
        }
```
digunakan untuk menghitung subtotal dengan mengalikan quantity
dengan price

```c#
public double getTotal()
        {
            return total;
        }
```
digunakan untuk mendapatkan nilai total

```c#
public List<Item> getListItems()
        {
            return listItem;
        }
```
digunakan untuk mendapatkan semua nilai yg sudah di masukkan/diinputkan

```c#
public string getTitle()
        {
            return title;
        }
```
diguakan untuk mendapatkan nilai title

```c#
public int getQuantity()
        {
            return quantity;
        }
```
digunakan untuk mendapatkan nilai quantity

```c#
public string getType()
        {
            return type;
        }
```
digunakan untuk nilai type

```c#
public double getPrice()
        {
            return price;
        }
```
digunakan untuk mendapatkan nilai price

```c#
public void addItem(Item item)
        {
            this.listItem.Add(item);
            this.total += item.getSubtotal();
        }
```
Digunakan untuk menambahkan item yg di inputkan kemudian
dijumlahkan dengan total dan di nilainya dimasukkan di subtotal

```c#
 private void AddButton_Click(object sender, RoutedEventArgs e)
        {
            string title = itemNameBox.Text;
            int quantity = int.Parse(quantityBox.Text);
            string type = TypeBox.Text;
            double price = double.Parse(priceBox.Text);

            Item item = new Item(new Random().Next(), title, quantity, price, price, type);
            calculator.addItem(item);
            double total = calculator.getTotal();

            totalLabel.Content = string.Format("Rp. {0}", total);

            ListBox.Items.Refresh();
        }
```
digunakan untuk memproses data ketika tombol Tambahkan di klik
dan menampilkan data yang di masukkan

