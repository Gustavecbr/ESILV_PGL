# TD1

## Exercice 1 : Move around

#### Question 1: Go to the root directory
``` 
cd/ 
``` 

#### Question 2: Display the content of the current (root) directory
```
ls
```

#### Question 3: Check your current location
```
pwd
```

#### Question 4: Try to create a directory named test
```
mkdir test
```

#### Question 5: Go to the general home directory (should contain folders named after each user)
```
cd 
cd ..
cd ..
```

#### Question 6: Go to your home directory
```
cd home
```

#### Question 7: Go back to the general home directory (located "just above")
```
cd ..
```

#### Question 8: Go again "just above", you should be back to the root directory
```
cd ..
```

#### Question 9: Go directly to your home directory (named after you). It should be a very simple command, which take no name as parameter of the path
```
cd 
```

#### Question 10: Try to create a directory named test
``` 
mkdir test
```

#### Question 11: Go into this new directory
```
cd test 
```

#### Question 12: Check your current location
```
pwd
```

## Exercise 2: Create, Rename, copy, delete

#### Question 1: Go to your home directory (should be named after you, you might be
there by default)
```
cd
```

#### Question 2: Check your current location
```
pwd
```

#### Question 3: Create a folder linux_ex_1
```
mkdir linux_ex_1
```

#### Question 4: Go into this folder
```
cd linux_ex_1
```

#### Question 5: Create an empty text file named [first_name]_[last_name].txt (e.g. alexis_bogroff.txt)
```
touch gustave_cabirou.txt
```

#### Question 6: Create a folder notes
```
mkdir notes
```

#### Question 7: Move your text file into this folder
```
mv gustave_cabirou.txt notes
```

#### Question 8: Rename the text file by appending the current year [first_name]_[last_name]_[current_year].txt
```
mv gustave_cabirou.txt gustave_cabirou_2023.txt
```

#### Question 9: Make a copy of this folder, name it notes_2022
```
cp -r notes notes_2023
```
#### Question 10: Delete the first folder (notes) using the verbose option
```
rm -r notes
```

## Exercice 3: Create and run a script

#### Question 1: Create a script script_1.sh in the folder linux_ex_1
```
cd linux_ex_1
vi script_1.sh
```

#### Question 2: In the script, write the commands that would output the following : Script running please wait ... Done.
```
esc + i 
Write : echo "Script running please wait ..."
enter
Write : echo "Done."
```

#### Question 3: Quit editing and save the script
```
esc + : + wq!
```

#### Question 4: Display the content of the script (using a command, not from an editor)
```
cat script_1.sh
```

#### Question 5: Run the script
```
chmod +x script_1.sh
./script_1.sh
```


# TD3

## Exercise 1: Grep and awk on tabular data

#### Question 1: Display the list of files and folders at the root using ls -l
```
ls -l /
```

#### Question 2: In a pipeline (using |), append a grep instruction to only display informations of bin
```
ls -l / | grep "bin"
```

#### Question 3: Append an awk instruction to only display the size of bin
```
ls -l / | grep "bin" | awk '{print $5}'
```

#### Question 4: Now rather extract the month, day and year of creation of the folder bin
```
ls -ld /bin | awk '{print $6, $7, $8}'
```

#### Question 5: Now rearrange the instruction to get the following output format : 2020-Oct-26 (from original data : Oct 26 2020)
```
ls -ld --time-style=long-iso /bin | awk '{print $6}' | sed 's/-/ /2; s/-/ /2'
```

## Exercise 2: Grep with Regex, and sed on unstructured data
#### Question 1: Run the following command : curl https ://en.wikipedia.org/wiki/List_of_cyberattacks > cyberattacks.txt
```
curl https://en.wikipedia.org/wiki/List_of_cyberattacks > cyberattacks.txt
```

#### Question 2: Use grep to extract all the lines that contain the keyword "meta"
```
grep "meta" cyberattacks.txt
```

#### Question 3: Now only extract "meta" and the first following word. You might use grep options to enable the use of regex (Regular Expressions) 
```
grep -o "meta [a-zA-Z]*" cyberattacks.txt
```

#### Question 4: Only extract the following word (but not the keyword "meta")
```
grep -o "meta [a-zA-Z]*" cyberattacks.txt | awk '{print $2}'
```

#### Question 5: Let’s now try more interesting (yet complex) patterns
```
cat cyberattacks.txt | grep -A1 'mw-content-text' | grep -v 'mw-content-text'
```

#### Question 6: Your turn: - Extract the tab title - Make a list of cyber attacks based on section titles
```
cat cyberattacks.txt | grep -o "<title>.*</title>" | sed 's/<title>//; s/<\/title>//'
cat cyberattacks.txt | grep "^<h2>" | sed 's/<h2>//; s/<\/h2>//'
```


