Bash Scripting 20 activities

1. Create a simple script which will accept some command line arguments and echo out some details about them (eg, how many are there, what is the second one etc):  #1/bin/bash cp $1 cp $2 echo “how many are there” for $2  Check: ls -lh $2 
2. Create a script which will print a random word. There is a file containing a list of words on your system (usually /usr/share/dict/words or /usr/dict/words):  shuf -n1  /usr/share/dict/words 
3. Expand the previous activity so that if a number is supplied as the first command line argument then it will select from only words with that many characters:  CH=$1;
	WordFile=/usr/share/dict/words;
	TOTW=$(grep -Ec "^.{$CH}$" $WordFile);
	RWORD=$(($RANDOM%$TOTW+1));
	grep -E "^.{$CH}$" $WordFile|sed -n "$RWORD p

4. Now let's create a script which will take a filename as its first argument and create a dated copy of the file. eg. if our file was named file1.txt it would create a copy such as 2017-05-30_file1.txt. (To achieve this you will probably want to play with command substitution and the command date)  
5. Challenge: To make it a bit harder, see if you can get it so that the date if after the name of the file (eg. file1_2017-05-30.txt (The command basename can be useful here.)
6. Challenge: Now see if you can expand the previous question to accept a list of files on the command line and it will create a named copy of all of them. (The command xargs may be useful here.)
7.
