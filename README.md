# C_program_basic_question
## PROBLEM STATEMENT 
Find the Majority Element in an Array 
Write a program to find the majority element in an array (an element that appears more than n/2 
times). 
For example, in the array [3, 3, 4, 2, 4, 4, 2, 4, 4], the output should be 4. Do not use any 
built-in functions for array manipulation or counting. 
 
## PROGRAM: 
```
#include <stdio.h> 
#include<stdbool.h> 
int main() 
{ 
    int a; 
    scanf("%d",&a); 
    int arr[a]; 
    for(int i=0;i<a;i++){ 
        scanf("%d",&arr[i]); 
    } 
    int count[a]; 
    bool flag[a]; 
    for(int i=0;i<a;i++){ 
        count[i]=1; 
        for(int j=i+1;j<a;j++){ 
            if(arr[i]==arr[j]){ 
                if (flag[i]==false){ 
                    count[i]+=1; 
                    flag[j]=true; 
                } 
            } 
        } 
    } 
    int max=1; 
    int index=0; 
    for(int i=0;i<a;i++){ 
        if ((count[i]>1) && (count[i]>a/2)){ 
            if (count[i]>max){ 
                max=count[i]; 
                index=i; 
            } 
        } 
    } 
    printf("Majority element in the given array is: %d",arr[index]); 
} 
``` 
 
 
### SAMPLE INPUTS AND OUTPUTS: 
![image](https://github.com/user-attachments/assets/6b5ebab7-73a3-4030-ba79-0b7ffb0c6f63)

### Explanation: 
• I take the inputs a(the number of elements) and the array arr from the user. 
• Then I declare two array(count,flag) for storing the count of the elements and flag to mark 
the elements that are repetitive. 
• Then I iterate over the elements by using two for loops to find and increase the count of the 
elements. Here based on the repetitiveness of the element I update the count of the 
element only once. (if the same element appears again later I didn’t update it since its 
already counted) 
• Then I find the maximum of the count and return the index as the output.
