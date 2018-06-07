# Hackerrank Solutions

### Given an array of numbers, find the number of occurances of the largest number
```
function birthdayCakeCandles(ar) {
    let maxHeight = 0;
    let counter = 0;
    for (let i=0;i<ar.length;i++){
        if (ar[i]>maxHeight){
            maxHeight = ar[i]
        }
    }
    ar.map(x=>{
        if (x===maxHeight){
            counter++;
        }
    })
    return counter;
}
```

### Given an array of five numbers, find the smallest and largest sum of any of the four numbers
```
function miniMaxSum(arr) {
    let wholeSum = 0;
    let sumArr = [];
    wholeSum = arr.reduce(function(acc,val){
        return acc + val;
    });
    for (let i=0;i<arr.length;i++){
        sumArr.push(wholeSum-arr[i])
    };
    console.log(`${Math.min(...sumArr)} ${Math.max(...sumArr)}`);
}
```

### Create a staircase of asterisks with n asterisks in the base, and one fewer asterisk each level of the staircase gone up
```
function staircase(n) {
    for (let i=1; i<=n;i++){
        console.log(" ".repeat(n-i)+"#".repeat(i))
    }
}
```
