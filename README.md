#### Vũ Thị Thuỷ Tiên  
#### **Báo cáo học Con trỏ:**  

#####1. Khái niệm:  

- Con trỏ là một biến dùng để chứa địa chỉ. Mỗi loại địa chỉ thì có loại con trỏ tương ứng. Trước khi sử dụng biến con trỏ ta phải khai báo trước khi sử dụng  
- Khai báo:  `<kiểu_DL> * <tên_biến_con_trỏ>;`  
- VD: `int x, y, *p, *c;`  

#####2. Con trỏ và mảng 1 chiều  

- Các phần tử của mảng có thể được xác định thông qua con trỏ. Ta có khai báo : `float a[10];`  
- VD:  Nhập từ bàn phím các phần tử của mảng và tính tổng các phần tử đó  
```sh
#include<stdio.h>  
void main()  
{  
    float a[5], s ; int i;  
    for(i=0;i<5;i++)  
    {  
        printf(“\na[%d]= ”,i);  
        scanf(“%f”,&a[i]);  
    }  
    s=0;  
    for (i=0;i<5;i++) s+=a[i];  
    printf(“\n Tong =%8.2f”,s);  
    getch();  
}
```    
#####3. Con trỏ với mảng nhiều chiều  

- Ðể tính toán địa chỉ của thành phần a[i][j] chúng ta sử dụng công thức sau : `(float *)a+i*n+j.`  
a là một hằng con trỏ trỏ đến các dòng của một ma trân hai chiều, vì vậy  
a trỏ đến dòng thứ nhất  
a+1 trỏ đến dòng thứ hai  
a+2 trỏ đến dòng thứ ba  
- VD nhập giá trị của ma trận hai chiều:  
```sh
#include <stdio.h>  
void main()  
{  
    float a[10][20];  
    int i,j,n;  
    printf("Nhap vao kich thuoc ma tran n=");  
    scanf("%n",&n);  
    for(i=0;i<n;i++)  
        for(j=0;j<n;j++)  
        {  
            printf("a[%d][%d] = ",i,j);  
            scanf("%f",(float *)a+i*20+j);  
        }  
    getch();  
}
```  
#####4. Phép toán trên con trỏ  
######4.1. Phép gán: 

- Chỉ nên thực hiện trên các con trỏ có cùng kiểu, khi thực hiện trên con trỏ phải thực hiện phép ép kiểu:  
- Vd:   
```sh
int x;
char *p;
p=(char*)(&x);
```
######4.2. Phép tăng giảm địa chỉ  

- VD: `float x[30], *px;`   

######4.3. Phép so sánh: 

- Dùng so sánh các con trỏ cùng kiểu, giả sử p1 và p2 là hai con trỏ kiểu float thì tồn tại phép so sánh  
p1 < p2 // địa chỉ p1 trỏ tới thấp hơn địa chỉ p2 trỏ tới  
p1==p2   

#####5. Con trỏ kiểu void  

- Là con trỏ đặc biệt không có kiểu, nó có thể nhận bất kỳ địa chỉ nào. Con trỏ kiểu void thường dùng làm đối để nhận bất kỳ địa chỉ nào thông qua phép ép kiểu trong thân hàm
- Các phép toán tăng giảm địa chỉ, so sánh không dùng được con trỏ kiểu void   

######6. Mảng con trỏ  

- Mảng con trỏ là một mảng mà mỗi phẩn tử của nó có thể chứa một địa chỉ nào đó. Mảng con trỏ có nhiều kiểu, mỗi phẩn tử của mảng kiểu nào thì sẽ chứa địa chỉ kiểu tương ứng với nó. Mảng con trỏ được khai báo theo mẫu sau: `<kiểu Dl> *<tênmảng>[N]`  
- Khi gặp khai báo mảng con trỏ thì máy sẽ cấp phát N khoảng nhớ liên tiếp cho N phần tử tương ứng trong mảng
