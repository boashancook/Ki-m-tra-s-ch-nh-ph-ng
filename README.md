# Ki-m-tra-s-ch-nh-ph-ng
Viết 1 hàm kiểm tra 1 số có là chính phương hay không (số chính phương là số bằng bình phương của một số nguyên nào đó); một hàm kiểm tra 1 số có phải là số Pitago hay không (số Pitago là số chính phương và bằng tổng 2 số chính phương khác). Trong hàm main nhập số nguyên dương và sử dụng các hàm trên kiểm tra có là số chính phương? số Pitago?
#include <stdio.h>
#include <conio.h>
#include <math.h>

int socp(int);
int soptg(int);

void main()

{
	clrscr();
	int n;
	printf("Nhap so nguyen duong n=");
	scanf("%d", &n);
	if (socp(n)) printf("\n%d la so chinh phuong", n);
	else printf("\n%d khong phai so chinh phuong", n);
	if (soptg(n)) printf("\n%d la so Pitago", n);
	else printf("\n%d khong phai so Pitago", n);
	getch();
}

int socp(int n)
{
	int t = sqrt(n);
	if (n == t *t) return 1;
	else return 0;
}

int soptg(int n)
{
	int i;
	if (!socp(n)) return 0;
	else
	{
		for (i = 1; i < n; i++)
			if (socp(i) && socp(n - i)) break;
		if (i < n) return 1;
		else return 0;
	}
}
