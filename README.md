# Basics of bash scripting

## Variables <br>
We can assign value to a variable temprorily <br>
```
a=10
```
<br>
For string
<br>

```
a="some string"
```
<br>

## Increment/Decrement

Examples of increment operator <br>

```
i+=1
```
or
```
i++
```
or
```
i=$((i+1))
```
The decrement operator can use in similar way

<br>
<br>

## Extract data

Prints first 6 bytes <br> 
```
head -c 6 file
```
<br>

Prints first 5 lines <br>
```
head -n 5 file
```
<br>

Prints last 3 lines <br>
```
tail -n 3 file
```
<br>

Print content of column 8 <br>
```
awk '{print $8}'
```
<br>

Print the while line conataing the word "volume" <br>
```
grep volume file
```
<br>


## Piping
This is used when we want to pass data processed from one command to another <br>

The command below first extracts the line containing the word "volume", then it filters last 2 lines using the `tail` command and then extracts the first line using `head`. Then it print the 8th column of the string using `awk`
```
grep volume file | tail -2 | head -1 | awk '{print $8}'
```



<br>

## Loops in bash

### For loop

Loop with strings
```
for element in elem1 elem2 elem2
do
  echo "Element: $element"
done
```
<br>

Loop with numbers
```
for i in {0..3}
do
  echo "Number: $i"
done
```
<br>

Using array
```
bookArr=(first second third)
for book in "${bookArr[@]}"
do
  echo "Book: $book"
done
```
<br>

Loop conataning counter <br>
```
for ((i = 0 ; i <= 100 ; i++))
do
  echo "Count: $i"
done
```
<br>
<br>

### While loop

Basic while loop <br>
```
i=1
while [ $i -le 10 ]; do
   echo $i
   i=$((i+1))
done
```
<br>

It can also be used to read input file from file or stream <br>
```
while read line; do
   echo $line
done < file.txt
```
<br>
<br>

## Find and replace

Replace 2nd line with the stirng "hello" <br>
```
sed -i '2s/.*/hello/' file.txt
```
<br>

Replace the "hi" in the 2nd line with "hello" <br>
```
sed -i '2s/hi/Hello/' file
```
<br>
