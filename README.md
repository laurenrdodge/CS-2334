# Class Notes Week 3

driver class is where you run your code

driver or main will be where you use all of your class objects




<img width="510" alt="Screenshot 2023-01-31 at 3 16 09 PM" src="https://user-images.githubusercontent.com/123114320/215886831-e2b11535-1026-47a6-b9d9-62bf37aa18c3.png">
<img width="510" alt="Screenshot 2023-01-31 at 3 04 55 PM" src="https://user-images.githubusercontent.com/123114320/215886838-45f0c75d-d1c4-4d45-bdc9-a8e20c0c2f73.png">
<img width="510" alt="Screenshot 2023-01-31 at 3 04 10 PM" src="https://user-images.githubusercontent.com/123114320/215886840-67f3de63-e7ea-443a-b93e-e5f16d761ce9.png">

for objects if you change one the other is affected because they are pointing to the same object in the heap

Arrays - use a continuous block of memory
ArrayLists - the points in memory can be scattered

By changing one object in an arraylist you can change all of them

Overall ArrayLists are better and have more features but could run slower for more intensive applications



The string class is immutable

StringBuffer - like string but is easier to access since it is mutable

You can append (without worrying about method overloading), insert, return a substring, etc.

Ex: Initialize 

StringBuffer s = new StringBuffer("Oklahoma City");

If you do s.insert(8, "ABC"); and then print it, "OklahomaABC City" will be printed out

If you do s.insert(0, 5); "5OklahomaABC City" will be printed out

If you then do s.insert(1, true) "5trueOklahomaABC City" will be printed out

If you do s.insert(5, 41.35d); "5true41.35OKlahomaABC City" will be printed out

**d is not added because it is there to specify that it is a double**

If you specify  char arr[] = ('j', 'a', 'v', 'a'a); and do s.insert(2, arr); "5tjavarue41.35OklahomaABC City" will be printed out

Encapsulation can be broken
