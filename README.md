# Heapsort
It is a recursive function, it includes buildmax heap and heapsort function 
```
#include <stdio.h>
int heapsize;

void max_H(int a[], int i,int n)
 {
    int l, r, larg, t;
    l = 2 * i+1;
    r = 2 * i + 2;
    larg = i;
    if (l < n && a[l] > a[i])
        larg = l;
    if (r < n && a[r] > a[larg])
        larg = r;
    if (larg != i) {
        t = a[i];
        a[i] = a[larg];
        a[larg] = t;  
        max_H(a, larg,n);    
    }
    
 //   printf("%d\n",a[i]);
}

int delete(int a[],int n)
{
int max;
int maxheapidx=n-1;
if(maxheapidx<0)
printf("error 0 nodes presnt");
max=a[0];
a[0]=a[maxheapidx];
maxheapidx =maxheapidx-1;
max_H(a,0,n);
    return max;
}



void Build_max_Heap(int a[],int n)
{
    int i;
    for(i=((n/2)-1);i>=0;i--)
    { 
        max_H(a,i,n); 
    }
}



void Heapsort(int a[], int n)
{ 
    int i,temp;
    Build_max_Heap(a,n);
    for(i=n-1;i>=0;i--)
    {
        temp=a[0];
        a[0]=a[i];
        a[i]=temp;
        n= n-1;
        max_H(a,0,n);
        
    }
    
    
}

void display(int a[],int n)
{ 
  int i;
  
    printf("Sorted values:\n");
    for (i = 0; i < n; i++)
    {
        printf("%d\n",a[i]);
    }
    printf("\n");
}


int main() {
    int a[] = {14, 1, 10, 8, 7, 9, 3, 2, 4, 6,68,38,25,48};
    int n= sizeof(a)/sizeof(a[0]);
    printf("n=%d\n",n);
  /*  for (i = 0; i <=9; i++) {
        max_H(a, i,n);
    }*/
    
   // display(a);
   // delete(a,n);
   Heapsort(a,n);   
    display(a,n);
    return 0;
}















//--------------------------------------

// Max-Heap data structure in C
/*
#include <stdio.h>
void heapify(int array[], int size, int i);
void printArray(int array[], int size);
int size = 0;
void swap(int *a, int *b)
{
  int temp = *b;
  *b = *a;
  *a = temp;
}



void heapify(int array[], int size, int i)
{
  if (size == 1)
  {
    printf("Single element in the heap");
  }
  else
  {
    int largest = i;
    int l = 2 * i + 1;
    int r = 2 * i + 2;
    if (l < size && array[l] > array[largest])
      largest = l;
    if (r < size && array[r] > array[largest])
      largest = r;
    if (largest != i)
    {
      swap(&array[i], &array[largest]);
      heapify(array, size, largest);
    }
  }
}




int main()
{
  int array[10]={14, 1, 10, 8, 7, 9, 3, 2, 4, 6};
  for (int i =0; i<=9; i++)
  {
    heapify(array, 10, i);
  }

  printf("Max-Heap array: ");
  printArray(array,10);

}



void printArray(int array[], int size)
{
  for (int i = 0; i < size; ++i)
    printf("%d ", array[i]);
  printf("\n");
}*/
```
