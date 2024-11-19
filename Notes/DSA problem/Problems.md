# Bit manipulation 

## Basics 
- Converting a number to binary 
- ![](../statics/Pasted%20image%2020241115154045.png)
- Converting from binary to decimal
- ![](../statics/Pasted%20image%2020241115154122.png)
- 1s and 2s compliment
- ![](../statics/Pasted%20image%2020241115154248.png)


## Swap with variable 
```
a = a ^ b 
b = a ^ b // value of a here is (a ^ b) ^ b so b cancel out remains a
a = a ^ b // value of a is (a ^ b) ^ b , here b is = a so remain b
```
we know that xor of same is zero 

## Check if ith bit is set or not 
```
1 << 2 (i) 
```
