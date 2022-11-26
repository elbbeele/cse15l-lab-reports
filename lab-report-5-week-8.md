# Lab Report 5 Week 8 #

## grade.sh Code

```
# Create your grading script here

#set -e
CP=".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"

rm -rf student-submission > out.txt 2> err.txt
git clone $1 student-submission > git.txt 2> giterr.txt

cat git.txt
cat giterr.txt

echo $?


# check that the student code has the correct file submitted
if [ -e student-submission/ListExamples.java ]
then
    echo "correct file submitted"
else
    echo "incorrect file submitted"
    echo "FAIL"
    exit
fi


#get sutdent code and your test .java file into the same directory
cp TestListExamples.java student-submission
cp -r lib student-submission
cd student-submission

echo "copy into new directory"

#compile tests
javac -cp $CP *.java > compile.txt 2> compileErr.txt

cat compile.txt
cat compileErr.txt

if [ -f ListExamples.class ]
then 
    echo "compiled"
else 
    echo "tests didn't compile"
    echo "FAIL"
    exit
fi



java -cp $CP org.junit.runner.JUnitCore TestListExamples > junit.txt 2> juniterr.txt

cat junit.txt
cat juniterr.txt

if [[ $? -eq 0 ]]
then
    echo "PASS"
else
    echo "FAIL"
    exit
fi

```

## Examples of Student Submissions

### Example 1:
![Image](https://elbbeele.github.io/cse15l-lab-reports/first.png)

### Example 2:
![Image](https://elbbeele.github.io/cse15l-lab-reports/second.png)

Tracing for Example 2:
- Standard output:
```
JUnit version 4.13.2
..
Time: 0.01

OK (2 tests)
```

- Standard error: empty, no errors

- The first if statement for checking if the correct file was submitted returned true because the student submission folder had the file with the correct name, therefore allowing this code to run. The second if statement also returned true because there were no failed tests that was contained in the text file from running the JUnit Tests. 
- Because the two if statements both returned true, the else condition lines were not run because it didn't fit the criteria to be run. For example, the else statement for checking if the correct file was submitted wasn't checked because the first condition of having the correct file was passed. The second else statement was also not reached because all the test cases were passed. 

### Example 3:
![Image](https://elbbeele.github.io/cse15l-lab-reports/third.png)
