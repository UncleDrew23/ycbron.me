+++
date = "2020-03-10"
title = "时间复杂度分析"
tags = [
    "Algorithm",
    "Data Structure"  
]
categories = [
    "Algorithm",
    "Data Structure",
]
series = ["Data Structures and Algorithms"]
featured_image = "https://images.unsplash.com/photo-1558566121-1fd2259638ef?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
+++


### 只关注循环执行次数最多的一段代码

   ```c++
    int cal(int n) {
      int sum = 0;
      int i = 1;
      for (; i <= n; ++i) {
        sum = sum + i;
      }
      return sum;
    }
   ```



### 加法法则：总复杂度等于量级最大的那段代码的复杂度

   ```c++
   int cal(int n) {
      int sum_1 = 0;
      int p = 1;
      for (; p < 100; ++p) {
        sum_1 = sum_1 + p;
      }
   
      int sum_2 = 0;
      int q = 1;
      for (; q < n; ++q) {
        sum_2 = sum_2 + q;
      }
    
      int sum_3 = 0;
      int i = 1;
      int j = 1;
      for (; i <= n; ++i) {
        j = 1; 
        for (; j <= n; ++j) {
          sum_3 = sum_3 +  i * j;
        }
      }
    
      return sum_1 + sum_2 + sum_3;
    }
   ```

### 乘法法则：嵌套代码的复杂度等于嵌套内外代码复杂度的乘积

   ```c++
   int cal(int n) {
      int ret = 0; 
      int i = 1;
      for (; i < n; ++i) {
        ret = ret + f(i);
      } 
    } 
    
    int f(int n) {
     int sum = 0;
     int i = 1;
     for (; i < n; ++i) {
       sum = sum + i;
     } 
     return sum;
    }
   ```

### 常见的多项式复杂度

   - O(1)
   
     ```c++
      int i = 8;
      int j = 6;
      int sum = i + j;
     ```


   - O(logn)、O(logn)
   
     ```c++
      i=1;
      while (i <= n)  {
        i = i * 2;
      }
     ```
   
   - O(m+n)、O(m*n)
   
     ```c++
     int cal(int m, int n) {
       int sum_1 = 0;
       int i = 1;
       for (; i < m; ++i) {
         sum_1 = sum_1 + i;
       }
     
       int sum_2 = 0;
       int j = 1;
       for (; j < n; ++j) {
         sum_2 = sum_2 + j;
       }
     
       return sum_1 + sum_2;
     }
     ```


