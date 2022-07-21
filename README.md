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
