# Code Challenges Encountered in Life, Work and Development

## Sort an array of students into randomly assigned teams of two
```
const removeOne = (array)=>{
    let rando = Math.floor(Math.random()*(array.length));
    let removee = array[rando];
    array = [...array.slice(0,rando),...array.slice(rando+1)]
    return [removee,array];
}  

const teamBuilder = students =>{
    let oddball;
    let teams = [];

    // if count is uneven, remove one student from array and make them the oddball
    if (students.length%2===1){
        let arr = removeOne(students);
        oddball = arr[0];
        students = arr[1];
    }

    // while any students remain, remove them from students array and sort into arrays of two
    while(students.length>0){
        let arr = removeOne(students);
        let removee = arr[0];
        students = arr[1];
        if (teams[0]===undefined){
            teams=[[removee]];
        } else if (teams[teams.length-1][0]===undefined) {
            teams = [...teams,[removee]];
        } else if (teams[teams.length-1][1]===undefined){
            teams=teams.concat([teams[teams.length-1].concat([removee])]);
            // teams = teams.slice(0,teams.length-2).concat([teams[teams.length-1].push(removee)]);
        } else {
            teams=[...teams,[removee]]
        }
    }

    // solve why single arrays were present
    // until then, filter arrays with only one student, leaving teams of two
    teams = teams.filter(arr=>arr.length>1);

    // if an oddball was generated, push it into a random team of two
    if (oddball){
        teams[Math.floor(Math.random()*(teams.length))].push(oddball);
    }

    return teams;
}
console.log(teamBuilder(students));
```
