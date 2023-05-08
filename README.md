Download Link: https://assignmentchef.com/product/solved-program-3-unix-tools-cs580u
<br>
<h3><u>Driver Code and Test Input Files</u></h3>

<h3>●       Provided Files</h3>

<ul>

 <li><a href="https://drive.google.com/open?id=0B5NpY9dM1zfBMkt4cTFBMXVlMVE">c</a> //Driver Code for Part 2</li>

 <li><a href="https://drive.google.com/open?id=0B5NpY9dM1zfBYXZoRmdUemUyd3c">o</a> //object file for part 1</li>

</ul>




Part 1:  GDB

In Part 1 of the program we will be using gdb to defuse a “bomb”.




<ul>

 <li>The nefarious Dr. Evil has planted a “binary bomb” on our machines. A binary bomb is a program that consists of a sequence of phases. Each phase expects you to type a particular string on the standard input (stdin). If you type the correct string, then the phase is defused and the bomb proceeds to the next phase. Otherwise, the bomb explodes by printing “BOOM!!!” and then terminating. The bomb is defused when every phase has been defused. Your mission, which you have no choice but to accept, is to defuse your bomb before the due date. Good luck.</li>

 <li>Below, I have given you two source code files and an object file. You must write a makefile that will link them into a binary executable.

  <ul>

   <li>Download source files from the git classroom Asgn-3 repo

    <ul>

     <li><u><a href="https://drive.google.com/open?id=0B5NpY9dM1zfBclpsNDZqY2Vzckk">c</a></u></li>

     <li><a href="https://drive.google.com/open?id=0B5NpY9dM1zfBcGprSmhFN3FhTkE">c</a></li>

     <li><a href="https://drive.google.com/open?id=0B5NpY9dM1zfBYXZoRmdUemUyd3c">o</a></li>

    </ul></li>

   <li>In your makefile, create a target called defuseTheBomb that produces a binary executable called defuseTheBomb.</li>

   <li><strong>DO NOT </strong>point the ‘all’ target to the defuseTheBomb target.</li>

  </ul></li>

 <li>Once you start execution of the program, you have <strong><em>200 seconds</em></strong> to defuse the bomb. Using GDB, step through the code, inspecting each passcode as you go.

  <ul>

   <li>The passcodes are random and will change each time you execute, so you have to learn how to use GDB.</li>

   <li>Each phase’s passcode is the same length as the phase, so phase 1 only has a single letter passcode</li>

  </ul></li>

 <li>Once you complete all 6 phases, a file called bomb_defused.txt will be generated. <strong>Make sure you include this file, <em>unaltered</em>, with your submission.</strong></li>

</ul>

<strong> </strong>

<strong>NOTE: </strong>Part A includes an object file, <em>hidden.o</em>, which was compiled on the machine in the lab. You <strong>must</strong> include this file to complete part A. The remaining portions of the lab can be completed on any machine with the <em>valgrind</em> and <em>make</em> utilities.




Part 2: Valgrind

<ul>

 <li>I have provided you with code for Part B above called c that contains 3 functions riddled with memory errors, including a segmentation fault.</li>

 <li>Run the provided code with Valgrind to inspect the memory errors.</li>

 <li>Fix all memory errors so that Valgrind reports no memory leaks and errors.

  <ul>

   <li>You should see the following once you have fixed all of the errors:

    <ul>

     <li>All heap blocks were freed — no leaks are possible…ERROR SUMMARY: 0 errors from 0 contexts</li>

    </ul></li>

   <li><em>CONSTRAINT: You may alter the code in any line in the 3 functions, but you can not simply delete lines of code.</em></li>

  </ul></li>

</ul>

<em> </em>

Part 3: Bash Script

<ul>

 <li>Write a bash script called ‘trash’ that takes a single argument, which should be the name of an existing file in the current directory.</li>

 <li>The script should move the given file, if it exists, to a directory named TRASH that is located within the same directory as the script (./TRASH).</li>

 <li>If the TRASH directory does not exist, the script should create it. If the given file does not exist, an appropriate error message should be printed.</li>

 <li>The script should also check all files currently in the TRASH folder to see if they have been there for more than 1 hour. If they have, they should be deleted.

  <ul>

   <li>Hint: There are several “environment” variables that automatically exist within a bash script. These include the following. You may want to explore what values these hold by echoing them to stdout.

    <ul>

     <li>$HOME</li>

     <li>$USER</li>

     <li>$PWD</li>

     <li>$PATH</li>

    </ul></li>

   <li>You should be able to run your script as follows:./trash.sh &lt;filename&gt;

    <ul>

     <li><em>This means you will need to use the </em><a href="https://ss64.com/bash/chmod.html"><em>‘chmod’</em></a><em> command to mark it as executable</em></li>

    </ul></li>

   <li>Once your <em>trash</em> script is working well, modify it so that it accepts a list of files and moves all of them to the trash. The script should print an error message for each file that does not exist.

    <ul>

     <li>When testing your script, try invoking it with a command like the following:

      <ul>

       <li>./trash.sh *.oThe *.o filename tells the shell to provide the list of files to be moved by <em>trash</em>.</li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>

Part 4: Another Makefile

<ul>

 <li>Create a makefile with the following targets

  <ul>

   <li>all

    <ul>

     <li><em>all</em> should have the 3 targets below as dependencies to allow us to run your code</li>

    </ul></li>

   <li>defuseTheBomb

    <ul>

     <li>Should compile the defuseMe.c and bomb.c to separate object files, then link them with the provided hidden.o to create an executable. This means you will need at <em>minimum 3 targets </em>for this part of the program.</li>

    </ul></li>

   <li>checkmem

    <ul>

     <li>Should compile your corrected <a href="https://drive.google.com/open?id=0B5NpY9dM1zfBMkt4cTFBMXVlMVE">c</a> for part 2 and run it with Valgrind</li>

    </ul></li>

   <li>clean

    <ul>

     <li>The <em>clean</em> target uses your bash script from part 3, trash.sh, to remove any executable and object files you created when testing.</li>

     <li>Be careful you do not accidentally delete the provided object file hidden.o</li>

    </ul></li>

  </ul></li>

</ul>




Part 5: Submission




<ul>

 <li>Commit your changes in git and push your repository</li>

 <li><span style="text-decoration: line-through;">While inside your program 3 folder, create a zip archive with the following command </span>

  <ul>

   <li><span style="text-decoration: line-through;">zip -r &lt;yourid&gt;_program3 &lt;files to include&gt;</span>

    <ul>

     <li><span style="text-decoration: line-through;">This creates an archive of all file and folders in the current directory called &lt;yourid&gt;_program3.zip</span></li>

     <li><strong><span style="text-decoration: line-through;">Do not zip the folder itself, only the files required for the lab</span></strong></li>

     <li><strong><span style="text-decoration: line-through;">Do not include your object files or executables</span></strong></li>

    </ul></li>

   <li><span style="text-decoration: line-through;">Upload the archive to Blackboard under Program 3.</span></li>

  </ul></li>

</ul>




<h3><u>Grading Rubric</u></h3>

<strong><em>TOTAL: 25 points</em></strong>

<h2>●       Part 1: (4 points)</h2>

<ul>

 <li>contains bomb_defused.txt with unique identifying key showing the bomb was defused (2 points)</li>

 <li>Uses separate compilation, compiling defuseMe.o and bomb.o to object files, then links all 3 into an executable (2 points)</li>

</ul>

<h2>●       Part 2: (10 points)</h2>

<ul>

 <li>Passes Valgrind Tests without memory leak or error (10 points)</li>

</ul>

<h2>●       Part 3: (5 points)</h2>

<ul>

 <li>bash script takes a single command line argument</li>

 <li>checks if argument is a file</li>

 <li>create TRASH directory if necessary</li>

</ul>

<h2>●       Part 4: (6 points)</h2>

<ul>

 <li>Makefile has all target that runs the defuseTheBomb, checkmem, and clean targets (1 point)</li>

 <li>Makefile has target that compiles the defuseTheBomb executable (1 point)</li>

 <li>Makefile has target for checkmem that compiles course to an executable and launches valgrind (2 points)</li>

 <li>Makefile has target clean that uses the trash.sh script to clean all non-essential files (object files other than hidden.o and executables) (2 points)</li>

</ul>

<h2>●       Submission Guidelines</h2>

<ul>

 <li>Does not follow requested program structure and submission format (-5 points)</li>

</ul>

<h3><u>Guidelines</u></h3>

This is an individual assignment. You must do the vast majority of the work on your own. It is permissible to consult with classmates to ask general questions about the assignment, to help discover and fix specific bugs, and to talk about high level approaches in general terms. It is not permissible to give or receive answers or solution details from fellow students.




You may research online for additional resources; however, you may not use code that was written specifically <em>to</em> solve the problem you have been given, and you may not have anyone else help you write the code or solve the problem. You may use code snippets found online, providing that they are appropriately and clearly cited, within your submitted code.

<em> </em>





