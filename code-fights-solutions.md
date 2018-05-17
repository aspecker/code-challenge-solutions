# Solutions to Codefights.com challenges
## Adam Specker

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
