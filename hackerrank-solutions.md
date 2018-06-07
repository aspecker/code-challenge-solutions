# Hackerrank Solutions

### Create a staircase of asterisks with n asterisks in the base, and one fewer asterisk each level of the staircase gone up
```
function staircase(n) {
    let counter = n;
    for (let i=1; i<=n;i++){
        console.log(" ".repeat(n-i)+"#".repeat(i))
    }

}
```
