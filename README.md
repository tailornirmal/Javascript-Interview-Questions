# Javascript-Interview-Questions

Repository for Interview Questions Related to JS, HTML, CSS, React JS, Redux, Tailwind, API Integration etc.

<h1>Javascript Programms</h1>

# Write a javascript function to get the total of given arguments like total(2,3,4,5)(4,5,6)

```
    function getTotal(...args) {
        let sum = 0;
        for (let i = 0; i < args.length; i++) {
            sum += args[i];
        }

        return function (...ar) {
            for (let i = 0; i < ar.length; i++) {
            sum += ar[i];
            }
            return sum;
        };
    }

    console.log(total(2, 3, 4, 5)(4, 5, 6)); // Output 29

```
