# Практична 9 
Виконав: Печкур Максим
# Опис
Розглянемо процес переходу від цілого x до цілого y вздовж цілих точок прямої. Довжина кожного кроку має бути невід’ємною та бути або на одиницю більшою, або дорівнювати, або на одиницю меншою за довжину попереднього кроку. Довжина першого і останнього кроків повинна бути 1.

Створіть функцію, яка обчислює мінімальну кількість кроків, необхідних для переходу від x до y. Він повинен обробляти 0 <= x <= y < 2 31 .

# Код
```
#include <stdio.h>

int krok (int x, int y){
  
    int res=0, dist= y-x;
    int step_size = 1;
    
    while (dist > 0) {
        
        if (dist - step_size >= 0) {
            dist -= step_size;
        } else {
            step_size = dist;
            dist = 0;
        }
        res++;
        
        if (dist == 0) break;
        
        if (dist - step_size >= 0) {
            dist -= step_size;
        } else {
            step_size = dist;
            dist = 0;
        }
        res++;
        
        step_size++;
    }
    return res; 
}


int main()
{   int x, y;
    
    printf("Введіть X ");
    scanf("%d",&x);
    
    printf("Введіть Y ");
    scanf("%d",&y);
    
    if(y<x || x<0 || y<0){
        printf("Помилка вводу");
        return 47;
    }
   
    int res=krok(x,y);
    printf("X:%d Y:%d res:%d", x, y, res);

    return 0;
}
```
