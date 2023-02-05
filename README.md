# TD1_1

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



