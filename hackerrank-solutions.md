# Hackerrank Solutions

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
