# core-code-upskilling-readme

# Week 1

## Ensure Question

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ensure Question</title>
    
</head>
<body>

<p id="demo"></p>

<script>

    let s = "Guatemala";
              
    function ensureQuestion (s) {
      return s.endsWith("?") ? s : s + "?";       
    } 
    
    document.getElementById("demo").innerHTML = ensureQuestion(s);

</script>

</body>
</html>

```

## Reversed Words

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reversed Words</title>
</head>
<body>

<p id="demo"></p>    
    
<script>

    let str = "Guatemala feliz que tus aras";

    function reversedWords(str) {
            return str
                .split(" ")
                .reverse()
                .join(" ");
        }

    document.getElementById("demo").innerHTML = reversedWords(str);

</script>    
    
</body>
</html>

```
## Smallest Integer in Array 

```
const arr = [14, 58, 20, 77, 66, 82, 42, 67, 42, 4]
            const min = Math.min(...arr)
            console.log(min)

```
## Odd or Even

```
const arr = [5, 1, 8, 4, 6, 9];
            const assignSum = (arr = []) => {
                const sum = arr.reduce((acc, val) => {
                    return acc + val;
                }, 0);
                const isSumEven = sum % 2 === 0;
                return isSumEven ? 'even' : 'odd';
            };
            console.log(assignSum(arr));

```
# Week 2

## Is Palindrome?

Challenge: A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This includes capital letters, punctuation, and word dividers.

Implement a function that checks if something is a palindrome. If the input is a number, convert it to string first.

Examples(Input ==> Output)
"anna"   ==> true

For this solution I used a Regular expression to match character combinations in the strings and several built-in methods.

```
function palindrome(str) {
   var re = /[^A-Za-z0-9]/g;
   var lowRegStr = str.toLowerCase().replace(re, '');
   var reverseStr = lowRegStr.split('').reverse().join('');
   return reverseStr === lowRegStr;
}
        
palindrome("Never odd or even");
```
