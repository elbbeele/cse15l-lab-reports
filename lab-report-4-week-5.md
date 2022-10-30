# Week 5 Lab Report
## Investigating GREP command line

### *-i: Searching without case*

This command is searching for whatever was passed through the command line while ignoring the case of it. This can be helpful when text files, such as the examples below uses the match but with upper case or lower case letters.


#### *Example 1*
```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -i "omari" ./technical/911report/chapter-1.txt
    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.
    Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.
    Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.
    Between 6:45 and 7:40, Atta and Omari, along with Satam al Suqami, Wail al Shehri, and Waleed al Shehri, checked in and boarded American Airlines Flight 11, bound for Los Angeles. The flight was scheduled to depart at 7:45.
    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in Boston. Their selection affected only the handling of their checked bags, not their screening at the checkpoint. All five men cleared the checkpoint and made their way to the gate for American 11. Atta, Omari, and Suqami took their seats in business class (seats 8D, 8G, and 10B, respectively). The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 between 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.
    At the same time or shortly thereafter, Atta-the only terrorist on board trained to fly a jet-would have moved to the cockpit from his business-class seat, possibly accompanied by Omari. As this was happening, passenger Daniel Lewin, who was seated in the row just behind Atta and Omari, was stabbed by one of the hijackers-probably Satam al Suqami, who was seated directly behind Lewin. Lewin had served four years as an officer in the Israeli military. He may have made an attempt to stop the hijackers in front of him, not realizing that another was sitting behind him.
```

#### *Example 2*
```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -i "again" ./technical/911report/preface.txt
                avoid such tragedy again?
                the same time protecting our country against future attacks. We have been forced to
 ```

#### *Example 3*
```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -i "MArtin" ./technical/911report/chapter-13.3.txt
            7. See Martin Marty and R. Scott Appleby, eds., Fundamentalism Observed, vol. 1
            105. See Martin Sieff, "Terrorist Is Driven by Hatred for U.S., Israel," Washington
 ```


### *-c: Counting the number of matches*

This command displays the number of times what was passed through in the command line appears in the file. This can be helpful in adjusting errors that might pop up consistently because of misspellings.

#### *Example 1*

```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -c "omari" ./technical/911report/chapter-1.txt 
0
```
#### *Example 2*

```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -c "again" ./technical/911report/preface.txt    
2
```
#### *Example 3*

```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -c "Martin" ./technical/911report/chapter-13.3.txt
2
```


### *-n: Showing line number with match*

This command line prints out the lines that matches with the command line input with their line numbers. This can be helpful in shifting through large amounts of data in files. 

#### *Example 1*

```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -n "Omari" ./technical/911report/chapter-1.txt
8:    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.
14:    Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.
18:    Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.
22:    Between 6:45 and 7:40, Atta and Omari, along with Satam al Suqami, Wail al Shehri, and Waleed al Shehri, checked in and boarded American Airlines Flight 11, bound for Los Angeles. The flight was scheduled to depart at 7:45.
34:    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in Boston. Their selection affected only the handling of their checked bags, not their screening at the checkpoint. All five men cleared the checkpoint and made their way to the gate for American 11. Atta, Omari, and Suqami took their seats in business class (seats 8D, 8G, and 10B, respectively). The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 between 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.
70:    At the same time or shortly thereafter, Atta-the only terrorist on board trained to fly a jet-would have moved to the cockpit from his business-class seat, possibly accompanied by Omari. As this was happening, passenger Daniel Lewin, who was seated in the row just behind Atta and Omari, was stabbed by one of the hijackers-probably Satam al Suqami, who was seated directly behind Lewin. Lewin had served four years as an officer in the Israeli military. He may have made an attempt to stop the hijackers in front of him, not realizing that another was sitting behind him.
```
#### *Example 2*

```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -n "again" ./technical/911report/preface.txt     
13:                avoid such tragedy again?
52:                the same time protecting our country against future attacks. We have been forced to
```
#### *Example 3*

```
(base) elizabethlee@ElizabethsMBP2 docsearch % grep -n "Martin" ./technical/911report/chapter-13.3.txt
14:            7. See Martin Marty and R. Scott Appleby, eds., Fundamentalism Observed, vol. 1
1446:            105. See Martin Sieff, "Terrorist Is Driven by Hatred for U.S., Israel," Washington
```

 
