# Solutions to Codefights.com challenges
## Adam Specker

### Given l<=a<=b<=r, find the number of ways that a + b can equal n
```
function countSumOfTwoRepresentations2(n, l, r) {
    let ways = 0;
    for (let i = l; i <= r; i ++){
        let b = n - i;
        if (b>=1&&b<=r&&b>=)
    }
    return ways;
}
```

### Determine the smallest factorial that is greater than or equal to integer n
```
function leastFactorial(n) {
    let product = 1;
    for (let i=1; i<=n;i++){
        product = product*i
        if (product>=n){
            return product;
        } 
    }
}
```

### given an array of four non-negative ints less than 256, pack these numbers into one number based on an 8 bit binary representation
### For a = [24, 85, 0], the output should be arrayPacking(a) = 21784.
### An array [24, 85, 0] looks like [00011000, 01010101, 00000000] in binary. After packing these into one number we get 00000000 01010101 00011000 (spaces are placed for convenience), which equals to 21784.
```
function arrayPacking(a) {
    let numStr='';
    for (let i=0;i<a.length;i++){
        let bit = a[i].toString(2);
        if (bit.length<8){
            for (let j=bit.length;j<8;j++){
                bit = "0".concat(bit);
            }
        }
        numStr =bit.concat(numStr);
    }
    return parseInt(numStr,2)
}
```

### determine how much call time a user can have based on rates of first minute, minutes 2-10, and minutes 11+ with a fixed amount of money s
```
function phoneCall(min1, min2_10, min11, s) {
	let time =0;
    while (s>=0){
        if (time===0){
            if (s>=min1){
                time ++;
                s-=min1;
            } else {
                return time;
            }
        } else if (time>0&&time<10){
            if (s>=min2_10){
                time ++;
                s-=min2_10;
            } else {
                return time;
            }
        } else {
            if (s>=min11){
                time++;
                s-=min11;
            } else {
                return time;
            }
        }
    }
    return time;
}
```
### Calculate the maximum value of items that can be carried of certain weights, not exceeding maxweight
```
function knapsackLight(value1, weight1, value2, weight2, maxW) {
    if (weight1+weight2<=maxW){
        return value1+value2;
    } else if (weight1<=maxW&&weight2<=maxW){
        if (value1>value2){
            return value1;
        } else {
            return value2;
        }
    } else if (weight1<=maxW||weight2<=maxW){
        if (weight1<=maxW){
            return value1
        } else {
            return value2
        }
    } else {
        return 0;
    }
}
```
### given integers a and b, calculate if `while a is not equal to b, increase a by 1 ,decrease b by 1` is an infinite loop
```
function isInfiniteProcess(a, b) {
    if (a>b){
        return true;
    }
    else if ((a%2===0&&b%2===0)||(a%2===1&&b%2===1)){
        return false;
    } else {
        return true;
    }
}
```
