# -Balance-cubes-hackerearth
/*There are  cubes of sugar. All cubes of sugar are pure except one cube which is impure. The property states that the cube which is impure weighs less than that of pure. You have only one balance weighing machine which has two sides so that you can compare the weight of things you put on both sides. In one operation you can use a balanced weighing machine once. You have to find which cube is impure using a balanced weighing machine in minimum operation possible so that after all the operations you performed, you become sure that this piece of the cube is surely impure.   Note: After that minimum operations, you have to be absolutely certain about that impure cube in the worst-case scenario. 
Input format  The first line contains  denoting the number of cubes of sugar. 
Output format  Print the number of minimum operations to find that impure cube in a single line.*/

#include <iostream>
#include <math.h>
using namespace std;
int main() {
	int n;
	cin>>n;
	int x=ceil(log(n)/log(3));
	cout<<x;
}
  /*if you take example of n=9 while taking log(9,2) what you are doing, you are dividing 9 into 2 parts so that whose weight is less you can operate further on that 

9 you divide it into 4 and 4 leaving 1 sugar piece(4+4+1=9) aside now in the worst case you will find duplicate sugar piece out of any one of those 4 

after operation 1-4(containing duplicate sugar)

after operation 2-2(containing duplicate sugar)

after operation 3-1(containing duplicate sugar)

but what if we do it like dividing 9 into 3 sections at a time we can compare 2 sections so we compare any 2 of them if we find any section with lower weight means it contains the duplicate sugar and if we get equal weight of both the sections we compared then the third section left is going to be having the duplicate sugar 

so at the end of operation 1 we are going to find a section of 3 pieces out of 1 is duplicate now in operation 2 we are going to divide 3 pieces into 3 sections we get 1 piece for each section we are going to compare 2 pieces and if out of that 1 is having lower weight then we are done but if not then its the 3rd piece that we haven't compared was the duplicate one. So now we have done this problem in 2 Operations that's what we need minimizing no. of operations. Take the ceil value of log(n,3) because what log(n,3) gives it gives the number of times you have to divide pieces to reach the one required suppose if n=8 you cant divide it into 3 equal sections (it cant be divided in decimals) so you have to divide 8 into 3,3,2 now you are going to compare sections containing 3 and 3 and after operation 1 you are going to find a section containing duplicate sugar be it any of the 3 one or the one containing 2 pieces  log(8,3) is 1.8927 integral part is 1 so int x=log(8,3) is going to return 1 but are we done? NO we just need 1 more operation that's what the decimal value represent that by taking powers of 3 you cant reach 8 by just 1 (3^1) but if you raise it to 2 (3^2=9) you go beyond 8 so the number of 3 we need are in between that is 1.8927 but still it's greater than 1 means if we have divided it completely in 3,3,3 as we did in the case of n=9 than we get whole 2 steps here if we divide it completely in equals 3 sections we are going to require these much 3's to reach 1,1,1 but here we can't perform 1.8927 operations we even can't divide 8 in equal 3 sections so we have to perform the whole 2 operations-------if you can't able to understand what I said above ignore that just take the ceil value because you need more operations.

now if you are wondering that what if we divide it into more sections like 5 or anything that we can think of ?

CRUX of the problem

the answer is no because here the problem says that you can only use 2 thing at a time to compare that gives 3rd one a special power that if you divide into three sections compare 2 if you don't get one with lower weight then it's the 3rd section that we haven't checked. if the problem says that we can check 3 sections at a time then we should divide it into 4 sections.*/
