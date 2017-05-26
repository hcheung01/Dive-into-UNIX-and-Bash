#Dive-into-UNIX-and-Bash

1. Create multiple new tabs and extra credit is learning the keyboard shortcut for creating new tab:  

Shell, New Tab OR just COMMAND + T 

2. Write a command that prints out the string “hello, world”. Do it two different ways:

  Echo “hello, world” 
Echo hello, world 

3. Type the command echo ‘hello (with a mismatched single quote), an then get out of trouble using the technique from Box 4. :

echo “hello (use Ctrl + C to exit) 

4. The echo utility writes any specified operands, separated by single blank (` ') characters and followed by a newline (`\n') character, to the standard output:

     The following option is available:

     -n    Do not print the trailing newline character.  This may also be achieved by appending `\c' to
           the end of the string, as is done by iBCS2 compatible systems.  Note that this option as well
           as the effect of `\c' are implementation-defined in IEEE Std 1003.1-2001 (``POSIX.1'') as
           amended by Cor. 1-2002.  Applications aiming for maximum portability are strongly encouraged
           to use printf(1) to suppress the newline character.

     Some shells may provide a builtin echo command which is similar or identical to this utility.  Most
     notably, the builtin echo in sh(1) does not accept the -n option.  Consult the builtin(1) manual
     page.

5. Print the string Use “man echo” including the quotes  echo:

‘Use “man echo”’ 

6. Print “hello” without the trailing newline:

  echo -n hello

7. How to make the terminal to sleep for 5 seconds:   

sleep 5 

8. Using echo and >, make files called line_1.txt and line_2.txt containing the first and second lines of Sonnet 1, respectively:

echo “From fairest creatures we desire increase,” > line_1.txt 
echo “That thereby beauty’s Rose might never die.” >> line_2.txt 

9. Replicate the original sonnet_1.txt (containing the first two lines of the sonnet) by first redirecting the contents of line_1.txt and then appending the contents of line_2.txt. Call the new file sonnet_1_copy.txt, and confirm using diff that it’s identical to sonnet_1.txt. Hint: When there is no diff between two files, diff simply outputs nothing:

 diff line_1.txt sonnet_1.txt 

10. Use cat to combine the contents of line_1.txt and line_2.txt in reverse order using a single command, yielding the file sonnet_1_reversed.txt. Hint: The catcommand can take multiple arguments:

cat line_2.txt line_1.txt > sonnet_1_reversed.txt 

11. Use the echo command and the redirect operator > to make a file called foo.txtcontaining the text “hello, world”. Then, using the cp command, make a copy of foo.txt called bar.txt. Using the diff command, confirm that the contents of both files are the same:
echo “hello, world” > foo.txt 
cp foo.txt bar.txt
 diff foo.txt bar.txt 

12. By combining the cat command and the redirect operator >, create a copy of foo.txtcalled baz.txt without using the cp command:

cat foo.txt > baz.txt 

13. Create a file called quux.txt containing the contents of foo.txt followed by the contents of bar.txt. Hint: As noted in Section 2.1.1, catcan take multiple arguments:

cat foo.txt bar.txt > quux.txt 

14. How do rm nonexistent and rm -f nonexistent differ for a nonexistent file?  :

Here -f (for “force”) overrides the implicit -i option and removes all files immediately. 

15. Type the sequence of commands needed to create an empty file called foo, rename it to bar, and copy it to baz:

touch foo 
mv foo bar
 cp bar baz 

16. What is the command to list only the files starting with the letter “b”? Hint: Use a wildcard:

ls b* 

17. Remove both bar and baz using a single call to rm. Hint: If those are the only two files in the current directory that start with the letter “b”, you can use the wildcard pattern from the previous exercise:

  rm -f b* 

18. Using ls, confirm that sonnets.txt exists on your system. How big is it in bytes? Hint: Recall from Section 2.2 that the “long form” of lsdisplays a byte count:

95635 bytes 

19. Suppose you wanted to list the files and directories using human-readable byte counts, all, by reverse time-sorted long-form. What command would you use? Why might this command be the personal favorite of the author of this tutorial?

ls -h -rtl sonnets.txt 

20. By piping the results of tail sonnets.txt through wc, confirm that (like head) the tailcommand outputs 10 lines by default  :

tail sonnets.txt | wc  
result: 10 lines 77 bytes 425 words 

21. By running man head, learn how to look at the first n lines of the file. By experimenting with different values of n, find a head command to print out just enough lines to display the first sonnet in its entirety:

  first 20 lines: head -n 20 sonnets.txt 

22. Pipe the results of the previous exercise through tail (with the appropriate options) to print out only the 14 lines composing Sonnet 1. Hint: The command will look something like head -n <i> sonnets.txt | tail -n <j>, where <i> and <j> represent the numerical arguments to the -noption:

tail -n 14 sonnets.txt 
