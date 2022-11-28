# Week 8 Lab Report 5
```
rm -rf student-submission
git clone $1 student-submission

if [[ $? -eq 0 ]]
then
    echo "The file was cloned successfully!"
else
    echo "The file has failed to be cloned!"
    echo "0/9"
    exit 1
fi
cp -r lib student-submission
cp TestListExamples.java student-submission
cd student-submission

if [[ -f "ListExamples.java" ]]
then
    echo "The correct file was found!"
else
    echo "The correct file was not found!"
    echo "1/9"
    exit 1
fi
#javac -cp ".;./lib/hamcrest-core-1.3.jar;./lib/junit-4.13.2.jar" *.java 2> error.txt
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java 2> error.txt
if [[ $? -eq 0 ]]
then
    echo "The tests were compiled successfully"
else
    echo "The tests failed to compile."
    echo "2/9"
    exit 1
fi

#java -cp ".;./lib/hamcrest-core-1.3.jar;./lib/junit-4.13.2.jar" org.junit.runner.JUnitCore TestListExamples > results.txt
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > results.txt
grep -q "OK" results.txt

if [[ $? -eq 0 ]]
then
    echo "9/9"
    exit 0 
else
    score=$(grep -o 'Failures: [1-5]' results.txt | grep -Eo '[1-5]+')
    failed=`cat results.txt | grep "Tests run:"`
    echo $failed
    let "score = 9 - score"
    echo "$score/9."
    exit 1
fi
```
![image](screenshots/lab5pic1.png)
![image](screenshots/lab5pic2.png)
- rm -rf student-submission is supposed to remove the insides of any previous file that already has this directory name!
- git clone is used to create or fill a directory named student-submission with the directory we are cloning
- if[[ $? -eq 0]] was true because the git clone was successful! The return code was zero, and thus the if statement would be true
- echo is just for me to print out useful information for the user telling them that it was indeed cloned successfully
- the next three lines are skipped because the first part of the if statement was executed
- cp -r lib student-submission clones the lib directory into the student-submission directory to have everything in one place
- cp TestListExamples.java student-submission also coppies the TestListExamples.java into the student-submission directory to have everything located in one place
- cd student-submission brings us into the directory that we git cloned
- if [[ -f "ListExamples.java" ]] makes sure that the correct file is found since it will give a 0 return code if it can find the file, and a nonzero code if it can not
- In this case, it did work. Thus, it echos "The correct file was found!"
- The next three lines are skipped due to the first part of the if statement being true
- the javac line compiles all .java files, and if there was any error, then there would be standard error out to error.txt. It also has a return code zero or non zero based on its success
- if [[ $? -eq 0 ]] is to decide if the file compiled or not
- Since the files did not compile the first part of the if statement is skipped
- I echo "The tests failed to compile.", and "2/9" to provide them with their current score, then exit
- Although the rest of the lines do not run since it did not compile, but the next would have been running TestListExamples on the java line and the standard output would go to results.txt
- grep -q "OK" results.txt returns a zero if it can find "OK" and a non zero if it can't
- This leads me to my if statement if [[ $? -eq 0 ]], which echos 9/9 if it passed all the tests. 
- If it didn't pass all the tests it would go to the bottom where I used two greps using "|" to use the output of my first grep statement as the output modified for my second grep statement
- The next is using cat results.txt "|" grep "Tests run:" to print out the rest of the line after and including "Tests run:", which will allow the student to know how many of the tests they failed!
- I echo this result
- I calculate the score based on the failed test from 1-5
- I give them their score out of 9
- I exit
![image](screenshots/lab5pic3.png)


