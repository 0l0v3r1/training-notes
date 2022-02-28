# Bash Conditional Statements and Loops

## 4.5.2 Bash Conditional Statements

* Basic Conditional statement:
```bash
if <condition>; then
<commands>
fi
```

* More:

```bash
if <x>; then
	command
elif <y>; then
	command2
else
	command3
fi
```

* Nymbers can be compared using the following operators:
	* `-eq`= equal
	* `-ne` = not equal
	* `-lt` = less than
	* `-le` = less than or equal
	* `-gt` = greater than
	* `-ge` = greater than or equal

* **Example:**
```bash
#!/bin/bash

x = 231
y = 321

if [ "$x" -eq "$y" ]; then
	echo "They're Equal"
fi
```
*pay atention to the spaces within the square brackets*

## 4.5.3.1 Bash for loop

* To print every item in the current directory:
```bash
#!/bin/bash
for i in $(ls); do
	echo item: $i
done
```

* To iterate over numbers use `seq`:

```bash
#!/bin/bash
for i in `seq 1 10`; do
	echo $i
done

```

## 4.5.3.2 Bash While Loop

* The while loop can be very useful when iterating over items in a file:

```bash
while [condition]; do <command>;<command2>;<command3>;done
```

* To read adn print items from a file :

```bash
while read line; do echo $line; done; < file.txt
```

***
***

# Bash Scripting Part 1

* A one-liner to extract open ports from nmap outputs to a comma seperated list:

```bash
cat *.nmap | grep "open" | grep -v "filtered" | cut -d "/" -f 1 | sort -u | xargs | tr ' ' ',' > ports.txt
```

***
***

# Bash Scripting Part 2

* To check if a list of hosts are alive or not:
```bash
#!/bin/bash

for protocol in 'http://' 'https://'; do
	while read line;
	do
		code = $(curl -L --write-out "%{http_code}\n" --output /dev/null --silent --insecure $protocol$line)
	if [ $code = "000" ]; then
		echo "$protocol$line: not responding."
	else
		echo "$protocol$line: HTTP $code"
		echo "$protocol$line: $code" >> alive.txt
	fi
	done < domains.txt
done
```

