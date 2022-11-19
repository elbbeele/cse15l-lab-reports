# Lab Report 5 Week 8 #

## grade.sh Code

```
# Create your grading script here

#set -e
CP=".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"

rm -rf student-submission
git clone $1 student-submission
echo "cloned"


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
javac -cp $CP *.java
if [ -f ListExamples.class ]
then 
    echo "compiled"
else 
    echo "tests didn't compile"
    echo "FAIL"
    exit
fi



java -cp $CP org.junit.runner.JUnitCore TestListExamples > junit.txt

cat junit.txt


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

### Example 3:
![Image](https://elbbeele.github.io/cse15l-lab-reports/third.png)
