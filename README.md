[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/OlW38W4k)
# Recurrence Analysis -- Mystery Function

Analyze the running time of the following recursive procedure as a function of
$n$ and find a tight big $O$ bound on the runtime for the function. You may
assume that each operation takes unit time. You do not need to provide a formal
proof, but you should show your work: at a minimum, show the recurrence relation
you derive for the runtime of the code, and then how you solved the recurrence
relation.

```javascript
function mystery(n) {
    if(n <= 1)
        return;
    else {
        mystery(n / 3);
        var count = 0;
        mystery(n / 3);
        for(var i = 0; i < n*n; i++) {
            for(var j = 0; j < n; j++) {
                for(var k = 0; k < n*n; k++) {
                    count = count + 1;
                }
            }
        }
        mystery(n / 3);
    }
}
```

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

// Credit goes to geeksforgeeks.org for explaining how to solve this recurrence relation

$T(n)$ = runtime of mystery

$T(n) = 3T(n) + O(n^5)$  
    ->  $3T(n)$ is the three recursive calls with $n/3$
    ->  $O(n^5)$ is the 3 nested loops: two have max index $n^2$

$T(n) = aT(n/b) + f(n)$  
    ->  a and b are both three
    ->  $f(n) = O(n^5)$

log^3(3) = 1
$n^5$ vs. $n^1$
c > log^b(a)

$f(n) = theta(n^c) = O(n^5)$