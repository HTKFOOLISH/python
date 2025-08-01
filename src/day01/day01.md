# Basic Python

## Mục Lục

- [Basic Python](#basic-python)
  - [Mục Lục](#mục-lục)
  - [Python Syntax](#python-syntax)
  - [Python Indentation](#python-indentation)
  - [Comments](#comments)
  - [Data types](#data-types)
    - [Number](#number)
    - [String](#string)
    - [Booleans](#booleans)
    - [List](#list)
    - [Dictionary](#dictionary)
    - [Tuple](#tuple)
    - [Set](#set)
  - [Checking Data types](#checking-data-types)
  - [Exercises - Day 1](#exercises-day-1)
    - [Exercise: Level 1](#exercise-level-1)
    - [Exercise: Level 2](#exercise-level-2)
    - [Exercise: Level 3](#exercise-level-3)

## Python Syntax

Python Script được viết trong Python interactive shell hoặc là code editor, có đuôi `.py`

## Python Indentation

Trong **python**, `indentation` (thụt lề) là cách mà bạn tổ chức các dòng lệnh bằng cách thêm khoảng trắng đầu dòng. Điều này rất quan trọng đối với **Python**.  
Không giống với các ngôn ngữ như là C hay C++, **Python** sử dụng indentation để xác định khối lệnh (**code block**) thay vì dấu `{}`.

Ví dụ đơn giản, bạn có thể thấy thông qua đoạn code dưới đây:  
Sử dụng vòng lặp in ra lần lượt `hello` và `hi`, số vòng lặp là 2

```python
# === Đoạn Code đúng ===
for i in range (2): # vòng lặp sẽ lặp 2 lần
    print('hello')
    print('hi')

# output:
# hello
# hi
# hello
# hi
```

```python
# === Đoạn Code sai ===
for i in range (2): # vòng lặp sẽ lặp 2 lần
    print('hello')

print('hi')

# output:
# hello
# hello
# hi
```

Ta có thể thấy đoạn code đúng hai dòng lệnh nằm ở trong khối lệnh `for` nên mỗi lần lặp sẽ in ra hai dòng ấy, tương tự ở đoạn code sai có thể thấy được rằng dòng `print('hi')` nằm ngoài khối lệnh `for` do đó chỉ in ra một lần.

Nhưng nếu không `indent` hoăc `indent` sai thì sẽ bị lỗi. Xem ví dụ dưới đây:

```python
if True:
print('ok')
```

```shell
Output:

IndentationError: expected an indented block after 'if' statement on line 1
```

Như vậy:

- Python sử dụng `indentation` (thụt lề) để xác định khối lệnh
- Mặc định 1 dấu tab (hoặc 4 dấu cách)
- Không `indentation` hoặc sai thì gặp lỗi **`IndentationError`**

Indentation trong các câu lệnh:

- `if`, `for`, `while`, `def`, `class`, `try`, `with`, ...
- Hoặc đơn giản là sau dấu `:`.

## Comments

**Comments** (chú thích) là những dòng không thực thi, được sử dụng để giải thích code, giúp dễ đọc và bảo trì code.  
Sử dụng **comments** một cách thông minh sẽ giúp code của chúng ta dễ đọc dễ hiểu, và sau này khi cần đọc lại thì không gây khó chịu cho cả chúng ta.

Có hai loại **comments**:

- **Single-line comment**:
  - Chú thích trên một dòng, sử dụng dấu `#`.
  - Hoặc nếu muốn **comment** dòng nào, đối với vscode thì sử dụng tổ hợp phím `ctrl` + `/`.
- **Multi-line comment**:
  - Chú thích trên nhiều dòng
    - Cách 1: Sử dụng nhiều dòng **Single-line comment**.
    - Cách 2:
      - Sử dụng chuỗi nhiều dòng `''' ... '''` hoặc `""" ... """`.
      - Lưu ý:
        - Đây là một kỹ thuật **string** (chuỗi) của **python** chứ không phải là comment.
        - Nhưng do là nó không được gán vào biến nào nên được bỏ qua trong **python**.
        - Chỉ sử dụng khi ghi chú quá dài.

Ví dụ:

```python
# đây là single-line comment
x = 5
```

```python
# === Multi-line comment ====

# -- Sử dụng nhiều single-line comment --

# Dòng 1
# Dòng 2
# ...
# Dòng N.

# -- Hoặc là sử dụng chuỗi trên nhiều dòng --

"""
Như này:
dòng 1
...
dòng N.
"""

'''
Hoặc là như này:
dòng 1
dòng 2
...
dòng N.
'''
```

## Data types

Trước hết, hãy bắt đầu với một số thứ cơ bản nhất của từng kiểu dữ liệu cơ bản nhất của **python**, không cần phải đi sâu vào trong phần này.

### Number

- Integer: Số nguyên (số âm, số 0 và số dương). Ví dụ: ..., -2, -1, 0, 1, 2, ...
- Float: Các số thập phân như: ..., -3.5, -1.0, 0.0, 1.0, 3.5, ...
- Complex:
  - Các số phức như: 1 + j, 2 + 4j
  - Lưu ý trong toán học là số có chữ `i` nhưng trong **python** thì sẽ có công thức như sau:
    - `M + Nj`
    - Với `M` là phần thực và `Nj` là phần ảo:
      - `N`, `M`: là một số bất kỳ.
      - chữ cái `j`: thành phần định nghĩa số phức trong **python**.

### String

Là một tập hợp các ký tự (**characters**) nằm bên trong dấu nháy đơn hoặc dấu nháy kép.  
Nếu một **string** (chuỗi) cần có nhiều dòng (2 dòng trở lên) thì ta sử dụng 3 dấu nháy đơn/kép liên tiếp (**triple quote**).

Dưới đây là các ví dụ về chuỗi hợp lệ trong Python.

```python
s1 = 'HTKFOOLISH'
s2 = "HTKFOOLISH là một người siêu đẹp zai 😁"
s3 = '''
HTKFOOLISH là một người siêu đẹp zai 😁.
Siêng làm
Học giỏi
Khà Khà
'''
s4 = """
Tôi là HTKFOOLISH!
Thiên thượng thiên hạ, duy ngã độc tôn.
T LÀ NHẤT
KHÀ KHÀ ! ! !
"""

print(s1)
print(s2)
print(s3)
print(s4)

```

### Booleans

Kiểu dữ liệu đúng hoặc sai. Trả về hai giá trị hoặc là `True` hoặc là `False`

Ví dụ:

```python
print(2 == 3) # False
print(3 == 3) # True
```

### List

**List** - một kiểu dữ liệu dạng danh sách, được sử dụng nhiểu trong **Python**. Có thể chứa nhiều phần tử, mỗi phần tử có thể là các kiểu dữ liệu khác nhau.

ví dụ:

```python
# === Khai báo list ===

lst_int = [1, 3, 4]

lst_mixed_datatypes = [1, 'Hello', 3.14, True, -1j];

empty_lst = []

nested_list = [[1, 2, 3], [4.5, 5.0]]

print(lst_int)
print(lst_mixed_datatypes)
print(empty_lst)
print(nested_list)

```

```shell
Output:

[1, 3, 4]
[1, 'Hello', 3.14, True, (-0-1j)]
[]
[[1, 2, 3], [4.5, 5.0]]
```

### Dictionary

**Dictionary** (từ điển):

- Là kiểu dữ liệu lưu trữ theo cặp `key: value` (khoá và giá trị)
- Truy cập thông qua `key` thay vì `index` (chỉ số) như trong **list**

Ví dụ:

- Tạo 1 dictionary như dưới đây

```python
student = {
  'name'      : 'HTKFOOLISH',
  'age'       : 21,
  'isStudent' : True,
  'skills'     : ['Python', 'HTML&CSS', 'C/C++']
}

# Với:
# 'name', 'age', 'isStudent' : key
# 'HTKFOOLISH', 21, True     : value
```

- Truy cập giá trị có hai cách:
  - Cách dưới đây có thể gây lỗi nếu như `key` không tồn tại

```python
# Truy cập đúng
print(student['name'])        # HTKFOOLISH
print(student['age'])         # 21
print(student['isStudent'])   # True

# Truy cập sai (Không tìm thấy key)
print(student['skill'])         # xuất hiện lỗi KeyError

```

- Tránh trường hợp lỗi như trên thì ta sử dụng phương thức `<dict-name>.get(key)` với `<dict-name>` được thay thế bằng tên của **dictionary**. Xem ví dụ dưới đây

```python
# Truy cập đúng

print(student.get('name'))        # HTKFOOLISH
print(student.get('age'))         # 21
print(student.get('isStudent'))   # True

# Truy cập sai (Không tìm thấy key) => Trả kết quả về None
# Mình cố tình nhập thiếu/sai để hiển thị kết quả, đúng sẽ là skills
print(student.get('skill'))         # None

```

### Tuple

- Là một tập hợp các kiểu dữ liệu khác nhau, giống **list**.
- Không thể thay đổi các giá trị sau khi tạo.

Ví dụ:

```python
# khởi tạo tuple
days = ('Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun')

print(days)

# Đổi giá trị đầu tiên thành giá trị mới
days[0] = 'MON'     # ('Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun')

# TypeError: 'tuple' object does not support item assignment
# Lỗi xuất hiện khi chạy chương trình
# Do không thể gán giá trị cho tuple sau khi khởi tạo
```

### Set

- Tương tự **list** và **tuple**.
- Điểm khác:
  - Các phần tử không trùng lặp.
  - Tự sắp xếp theo 1 trật tự nhất định.
  - Không thể truy cập bằng chỉ số.

Ví dụ:

```python
# khởi tạo set
int_set = {1, 2, 4, 3, 5, 3, 3, 2, 1, 'a', 'A', 'HTKFOOLISH'}

# in ra set vừa khởi tạo
print(int_set)  # {1, 2, 3, 4, 5, 'HTKFOOLISH', 'a', 'A'}
```

## Checking Data types

Để kiểm tra dữ liệu của biến hoặc là dữ liệu, ta sử dụng hàm `type()`

```python
print(type(3))                          # <class 'int'>

print(type(3.0))                        # <class 'float'>

print(type(0.5j))                       # <class 'complex'>

print(type('HTKFOOLISH'))               # <class 'str'>

print(type(True))                       # <class 'bool'>

lst = [1, 'Hello', 3.14, True, -1j]
print(type(lst))                        # <class 'list'>

student = {
  'name'      : 'HTKFOOLISH',
  'age'       : 21,
  'isStudent' : True,
  'skills'    : ['Python', 'HTML&CSS']
}
print(type(student))                    # <class 'dict'>

days = (
  'Mon',
  'Tue',
  'Wed',
  'Thu',
  'Fri',
  'Sat',
  'Sun'
)
print(type(days))                       # <class 'tuple'>

my_set = {1, 2, 4, 3, 5, 3, 3, 2, 1,
          'a', 'A', 'HTKFOOLISH'}
print(type(my_set))                     # <class 'set'>
```

## Exercises Day 1

### Exercise: Level 1

1. Kiểm tra phiên bản Python mà bạn đang sử dụng là version bao nhiêu.

```shell
python --version
```

Hoặc

```shell
python -V
```

2. Mở một file python có tên là `operations.py` và thực hiện phép toán giữa hai số **3** và **4**:

   - phép cộng (+)
   - phép trừ (-)
   - phép nhân (\*)
   - phép chia lấy dư (%)
   - phép chia lấy nguyên (//)
   - phép chia (/)
   - phép luỹ thừa (\*\*)

3. Viết các chuỗi (**string**) sau:

   - Tên
   - Nơi sống
   - sở thích

4. Kiểm tra kiểu dữ liệu của các dữ liệu dưới đây:

   - 10
   - 9.8
   - 3.14

   - 4 - 4j
   - ['HTKFOOLISH', 'Python', 'VIE']
   - Tên
   - Thành Phố
   - Sở Thích

### Exercise: Level 2

1. Tạo một folder `day_1` nằm bên trong dự án của bạn. Tạo file `helloworld.py` và làm lại bài tập **Exercise: Level 1**.

### Exercise: Level 3

1. Viết một ví dụ cho các **data types** (kiểu dữ liệu) khác nhau trong Python: Number(Integer, Float, Complex), String, Boolean, List, Tupple, Set, Dictionary.

2. (\*\*) Tìm khoản cách giữa hai điểm cho trước lần lượt là A(2, 3) và B(10, 8)

   - Đây là bài tập vận dụng.
   - Gợi ý:

     - [Euclidean distance](https://en.wikipedia.org/wiki/Euclidean_distance#:~:text=In%20mathematics%2C%20the%20Euclidean%20distance,being%20called%20the%20Pythagorean%20distance.)

     - căn bậc hai là luỹ thừa `1/2`.
