# Hackerrank Solutions

### If grade is less than 3 away from the next multiple of 5 and greater than 38, round up. Otherwise, return original score
```
function gradingStudents(grades) {
    return grades.map(x=>{
        let rounder = (Math.ceil(x/5))*5;
        console.log(rounder);
        if (x<38){
            return x;
        } else if (rounder-x<3){
            return rounder;
        } else {
            return x;
        }
    })
}
```

### Given a square matrix, calculated the difference between the sums of both diagonals
```
function diagonalDifference(a) {
    let sum1 = 0;
    let sum2 = 0;
    for (let i =0; i<a.length;i++){
        sum1 += a[i][i]
        sum2 +=a[i][a.length-1-i]
    }
    return Math.abs(sum1-sum2)
}
```

### Given a time in HH:MM:SS:AM or HH:MM:SS:PM, convert to 24 hour time in HH:MM:SS format
```
function timeConversion(s) {
    let hours = s.substring(0,2);
    let milStr = ''
    if (s.includes('PM')){
        let milHours = parseInt(hours)+12;
        milStr = milHours.toString()
        if (hours==='12'){
            milStr='12'
        }
        return milStr + s.substring(2,8);
    }  
    if (s.includes('AM')){
        if (hours==='12'){
            milStr = '00';
        } else {
            milStr = hours;
        }
        return milStr + s.substring(2,8);
    }
}
```

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
