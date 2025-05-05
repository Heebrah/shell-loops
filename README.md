# shell-loops
Here's a concise note on **loops in shells (e.g., Bash shell scripting)**:

---

### 🔁 **Loops in Shells (Bash)**

Loops are used to repeatedly execute a block of code.

### 🔁 **`for` Loop in Shell (Bash)**

The `for` loop is used to iterate over a list of items or a range of numbers.

#### 1. **Basic Syntax**

```bash
for variable in list
do
  commands
done
```

#### 2. **Example: List Iteration**

```bash
for color in red green blue
do
  echo "Color: $color"
done
```

**Output:**

```
Color: red
Color: green
Color: blue
```

#### 3. **Using a Range (Brace Expansion)**

```bash
for i in {1..5}
do
  echo "Number: $i"
done
```

#### 4. **C-style `for` Loop**

```bash
for ((i=1; i<=5; i++))
do
  echo "Index: $i"
done
```

#### 5. **Looping Over Command Output**

```bash
for file in $(ls *.txt)
do
  echo "Found file: $file"
done
```

> ⚠️ Be cautious with word splitting and spaces in filenames.

#### 6. **Control Statements**

* `break`: Exit the loop early.
* `continue`: Skip the current iteration.

```bash
for i in {1..5}
do
  if [ $i -eq 3 ]; then
    continue
  fi
  echo "Value: $i"
done
```

Here's a clear and concise note on the **`while` loop** in shell scripting:

---

### 🔁 **`while` Loop in Shell (Bash)**

The `while` loop executes a block of code **as long as a condition is true**.

#### 1. **Basic Syntax**

```bash
while [ condition ]
do
  commands
done
```

#### 2. **Example: Counting from 1 to 5**

```bash
count=1
while [ $count -le 5 ]
do
  echo "Count: $count"
  ((count++))
done
```

**Output:**

```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

#### 3. **Infinite Loop**

```bash
while true
do
  echo "Press Ctrl+C to stop"
  sleep 1
done
```

#### 4. **Looping Through File Lines**

```bash
while read line
do
  echo "Line: $line"
done < myfile.txt
```

#### 5. **Control Statements**

* `break`: Exit the loop immediately.
* `continue`: Skip the current iteration and continue with the next.

```bash
count=0
while [ $count -lt 5 ]
do
  ((count++))
  if [ $count -eq 3 ]; then
    continue
  fi
  echo "Number: $count"
done
```

---
#### 3. **`until` Loop**

Opposite of `while`; runs until the condition becomes true.

```bash
count=1
until [ $count -gt 5 ]
do
  echo "Until Count: $count"
  ((count++))
done
```

#### 4. **Loop Control**

* `break`: exits the loop
* `continue`: skips to next iteration

```bash
for i in {1..5}
do
  if [ $i -eq 3 ]; then
    continue
  fi
  echo "Number: $i"
done
```
Here's a clear and concise note on the **`until` loop** in shell scripting:

---

### 🔁 **`until` Loop in Shell (Bash)**

The `until` loop is similar to a `while` loop, but it runs the block **until the condition becomes true** (i.e., it loops **while** the condition is false).

#### 1. **Basic Syntax**

```bash
until [ condition ]
do
  commands
done
```

#### 2. **Example: Count from 1 to 5**

```bash
count=1
until [ $count -gt 5 ]
do
  echo "Count: $count"
  ((count++))
done
```

**Output:**

```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

#### 3. **Infinite Loop Example**

```bash
until false
do
  echo "This will run forever unless stopped"
done
```

#### 4. **Using `break` and `continue`**

```bash
count=0
until [ $count -ge 5 ]
do
  ((count++))
  if [ $count -eq 3 ]; then
    continue
  fi
  echo "Number: $count"
done
```

---

> ✅ **Key Difference**:
>
> * `while` runs **while condition is true**.
> * `until` runs **while condition is false**.


## Project on shell loops
1. For loops:  using C-style syntax my code is

```#!/bin/bash
#this is a f r loop code
for (( i=0; i<5; i++ )); do
#this line print out the number from 0 - 4
    echo "Number $i"
    done
```
https://imgur.com/WPDo1Rm

giving it an execution permission (chmod +x for_loop.sh) and running it the output gives
```
Number 0
Number 1
Number 2
Number 3
Number 4
```
https://imgur.com/1uACDJJ

2. While loop: Counting from 1 to 5
````
#!/bin/bash
# initializing variable
count=1
# looping the variable if it's less than 5
while [ $count -le 5 ]
do
  echo "Count: $count"
    ((count++))
    done

````
https://imgur.com/lXwIUX8

giving it an execution permission (chmod +x while_loop.sh) and running it the output gives
````
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
````
https://imgur.com/XRIIjba

3. until loop: Count from 1 to 5

````
#!/bin/bash
# initializing loop variable
count=1
# using the until loop to loop count when its less than 5
until [ $count -gt 5 ]
do
  echo "Until Count: $count"
    ((count++))
    done
            
````

https://imgur.com/kSY0WSo

giving it an execution permission (chmod +x until_loop.sh) and running it the output gives
````
Until Count: 1
Until Count: 2
Until Count: 3
Until Count: 4
Until Count: 5

````
https://imgur.com/DKwXCsi