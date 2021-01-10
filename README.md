# Area-Calculation-methods-Integral-

#include <stdio.h>
#include <math.h>

void main(){
    float a,b,c,sz,ing1;
    int n;
    printf("Enter a range (a,b) to calculate area of function e^-x\na = ");
    scanf("%f",&a);
    printf("b = ");
    scanf("%f",&b);
    printf("Enter a stepsize(width) for calculation(0.05 recomended)\nWidth = ");
    scanf("%f",&sz);
    for(ing1=0,n=0,c=a;c<b;c+=sz,n++){
    ing1=ing1+sz*exp(-c);   //Rectangular calculation
    }
    printf("(Rectangular) Area = %f\nNumber of rectangles = %d\n",ing1,n);
    
    for(ing1=0,n=0,c=a;c<b;c+=sz,n++){
    ing1=ing1+ 0.5*sz*(exp(-c+ sz)+exp(-c));  //Trapizium calculation 
    }
    printf("(Trapizium) Area = %f\nNumber of Trapiziums = %d\n",ing1,n);
    
    ing1=exp(-a);
    for(n=1,c=a+sz;c<b;c+=sz,n++){
        if (n%2!=0)
        ing1=ing1+ 4*exp(-c);
        else
        ing1=ing1+2*exp(-c);
    }
    ing1= (sz/3)*(ing1+exp(-b));
    printf("(Simpson's rule) Area = %f\nNumber of terms = %d",ing1,n+1);
}
