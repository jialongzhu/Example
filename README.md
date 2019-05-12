# n-
#include<stdio.h>
long long s[100];
int main() {
	int n,t;
	
	while (scanf_s("%d", &n) != EOF) {
		for (int i = 1; i <= n; i++){
			scanf_s("%lld",&s[i]);
		}
		int i = 1, g = 1;
		long long multiply = 1;
		long long b = 1;
		if (n == 1) {
			b = s[1];
		}
		for (int i = 1; i <n; i++) {
			if (s[i] > s[i + 1]) {
				t = s[i];
				s[i] = s[i + 1];
				s[i + 1] = t;
			}
			for (int x = s[i]; x>0; x--) {
				if (s[i] % x == 0 && s[i + 1] % x == 0) {
					g = g * x;
					multiply = s[i] * s[i + 1];
					b = multiply / x;
					s[i + 1] = b;
					break;
				}
			}
			g = 1;
		}
		printf("%lld\n", b);
		
	}
	return 0;
}
