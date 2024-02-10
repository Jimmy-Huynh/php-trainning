# php-trainning

## 1. Xác định thời gian cách đây 29 ngày.

```php
function tinhThoiGianCachDay29Ngay() {
    // Lấy thời gian hiện tại
    $ngayHienTai = time();
    
    // Sử dụng strtotime để tính thời gian cách đây 29 ngày
    $ngayCachDay29Ngay = strtotime("-29 days", $ngayHienTai);
    
    // Định dạng lại thời gian thành ngày/tháng/năm
    $ngayCachDay29NgayFormat = date("d/m/Y", $ngayCachDay29Ngay);
    
    return $ngayCachDay29NgayFormat;
}

// Gọi hàm và in ra thời gian cách đây 29 ngày
echo tinhThoiGianCachDay29Ngay();

```

Hàm này sử dụng `strtotime` để tính thời gian cách đây 29 ngày từ thời điểm hiện tại và sau đó sử dụng `date` để định dạng lại thời gian thành ngày/tháng/năm. Cuối cùng, nó trả về thời gian cách đây 29 ngày dưới dạng một chuỗi.

## 2. Đảo ngược các từ trong chuỗi.

```php
function daoNguocTuTrongChuoi($chuoi) {
    // Tách các từ trong chuỗi thành mảng các từ
    $mangTu = explode(" ", $chuoi);
    
    // Đảo ngược thứ tự các phần tử trong mảng
    $mangTuDaoNguoc = array_reverse($mangTu);
    
    // Kết hợp các từ đã đảo ngược thành một chuỗi mới
    $chuoiDaoNguoc = implode(" ", $mangTuDaoNguoc);
    
    return $chuoiDaoNguoc;
}

// Chuỗi ban đầu
$chuoiBanDau = "Đây là một ví dụ";

// Gọi hàm và in ra chuỗi đã đảo ngược các từ
echo daoNguocTuTrongChuoi($chuoiBanDau);

```
Hàm này sử dụng `explode` để tách các từ trong chuỗi thành một mảng các từ. Sau đó, nó sử dụng `array_reverse` để đảo ngược thứ tự các phần tử trong mảng. Cuối cùng, nó sử dụng `implode` để kết hợp các từ đã đảo ngược thành một chuỗi mới và trả về chuỗi đó.

## 3. Viết chương trình in các phần tử trùng nhau trong mảng.

```php
function inPhanTuTrungNhau($mang) {
    $soLanXuatHien = array_count_values($mang); // Tính số lần xuất hiện của mỗi phần tử trong mảng
    
    // Duyệt qua mảng số lần xuất hiện để in ra các phần tử trùng nhau
    foreach ($soLanXuatHien as $phanTu => $soLan) {
        if ($soLan > 1) {
            echo "Phần tử '$phanTu' xuất hiện $soLan lần<br>";
        }
    }
}

// Mảng ví dụ
$mang = array("a", "b", "c", "a", "d", "b", "e", "f", "c", "g");

// Gọi hàm để in ra các phần tử trùng nhau trong mảng
inPhanTuTrungNhau($mang);

```

Trong đoạn mã này, chúng ta sử dụng hàm `array_count_values()` để tính số lần xuất hiện của mỗi phần tử trong mảng và lưu kết quả vào một mảng khác. Sau đó, chúng ta duyệt qua mảng số lần xuất hiện và in ra các phần tử có số lần xuất hiện lớn hơn 1.

## 4. Sắp xếp các phần tử trong mảng tăng dần.

```php
function sapXepTangDan($mang) {
    // Sử dụng hàm sort để sắp xếp mảng tăng dần
    sort($mang);
    
    return $mang;
}

// Mảng ví dụ
$mang = array(5, 3, 7, 1, 9, 2, 4, 6, 8);

// Gọi hàm để sắp xếp mảng tăng dần
$mangSapXep = sapXepTangDan($mang);

// In ra mảng sau khi đã sắp xếp
echo "Mảng sau khi đã sắp xếp tăng dần: ";
foreach ($mangSapXep as $phanTu) {
    echo $phanTu . " ";
}

```

Trong đoạn mã này, chúng ta sử dụng hàm `sort()` để sắp xếp mảng tăng dần. Hàm này sẽ sắp xếp các phần tử trong mảng mà không thay đổi các khóa của chúng. Sau đó, chúng ta chỉ cần lặp qua mảng đã sắp xếp để in ra các phần tử.

## 5. Đảo ngược các phần tử trong mảng.

```php
function daoNguocMang($mang) {
    // Sử dụng hàm array_reverse để đảo ngược các phần tử trong mảng
    $mangDaoNguoc = array_reverse($mang);
    
    return $mangDaoNguoc;
}

// Mảng ví dụ
$mang = array(1, 2, 3, 4, 5);

// Gọi hàm để đảo ngược các phần tử trong mảng
$mangDaoNguoc = daoNguocMang($mang);

// In ra mảng sau khi đã đảo ngược
echo "Mảng sau khi đã đảo ngược: ";
foreach ($mangDaoNguoc as $phanTu) {
    echo $phanTu . " ";
}

```

Trong đoạn mã này, chúng ta sử dụng hàm `array_reverse()` để đảo ngược các phần tử trong mảng và lưu kết quả vào một mảng mới. Sau đó, chúng ta chỉ cần lặp qua mảng mới để in ra các phần tử đã được đảo ngược.

## 6. Viết chương trình tính tổng các chữ số của một số nguyên bất kỳ.

```php
function tinhTongChuSo($soNguyen) {
    $tong = 0;
    
    // Chuyển số nguyên thành một chuỗi để dễ dàng truy cập từng chữ số
    $chuoiSo = (string) $soNguyen;
    
    // Duyệt qua từng chữ số và cộng vào biến tổng
    for ($i = 0; $i < strlen($chuoiSo); $i++) {
        $tong += intval($chuoiSo[$i]);
    }
    
    return $tong;
}

// Số nguyên ví dụ
$soNguyen = 12345;

// Gọi hàm để tính tổng các chữ số
$tong = tinhTongChuSo($soNguyen);

// In ra tổng các chữ số
echo "Tổng các chữ số của số $soNguyen là: $tong";

```

Trong đoạn mã này, chúng ta chuyển số nguyên đầu vào thành một chuỗi để dễ dàng truy cập từng chữ số. Sau đó, chúng ta duyệt qua từng chữ số trong chuỗi và cộng chúng lại với nhau để tính tổng. Cuối cùng, chúng ta trả về tổng các chữ số.
