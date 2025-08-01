## File cleaner
Read a file, remove all the extra spaces and write it back to the same file.

For example, if the file input was
```
hello     world    my    name   is       raman
```

After the program runs, the output should be

```
hello world my name is raman

const fs = require('fs');

try {
    const data = fs.readFileSync('example.txt', 'utf8');
    const result = data.replace(/\s+/g, ' ').trim();
    try {
        fs.writeFileSync('example.txt', result);
        console.log('File has been saved!');
    } catch (err) {
        console.error(err);
    }
} catch (err) {
    console.error(err);
}