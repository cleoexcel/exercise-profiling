# Modul 5: Java Profiling
## JMeter Report and Test Results
### **Endpoint** `/all-student`
JMeter
Before Optimization Test Result JMeter
<img src="src/images/testresults1.jpg" alt="all-student">
After Optimization Test Result JMeter
<img src="src/images/testresults1optimize.jpg" alt="all-student">
Before Optimization JMeter:
<img src="src/images/jmeter_allstudent.jpg" alt="all-student"/>
After Optimization JMeter:
<img src="src/images/jmeter_allstudent_after.jpg" alt="all-student"/>

Execution Time `getAllStudentWithCourses()` from Intellij Profiler:

| Before | After  | Diff Percentage |
| -- |--------|-----------------|
| 4526 ms | 680 ms | 85%             |

### **Endpoint** `/all-student-name`
JMeter
Before Optimization Test Result JMeter
<img src="src/images/testresults2.jpg" alt="all-student-name">
After Optimization Test Result JMeter
<img src="src/images/testresults2optimize.jpg" alt="all-student-name">
Before Optimization JMeter:
<img src="src/images/jmeter_allstudentname.jpg" alt="all-student-name"/>
After Optimization JMeter:
<img src="src/images/jmeter_allstudentsname_after.jpg" alt="all-student-name"/>

Execution Time `joinStudentNames()` from Intellij Profiler:

| Before | After  | Diff Percentage |
|--------|--------|-----------------|
| 493 ms | 140 ms | 71,6%           |

### **Endpoint** `/highest-gpa`
JMeter
Before Optimization Test Result JMeter
<img src="src/images/testresults3.jpg" alt="highest-gpa">
After Optimization Test Result JMeter
<img src="src/images/testresults3optimize.jpg" alt="highest-gpa">
Before Optimization JMeter:
<img src="src/images/jmeter_highestgpa.jpg" alt="highest-gpa"/>
After Optimization JMeter:
<img src="src/images/jmeter_highestgpa_after.jpg" alt="highest-gpa/>

Execution Time `findStudentWithHighestGpa()` from Intellij Profiler:

| Before | After | Diff Percentage |
|--------|-------|-----------------|
| 130 ms | 30 ms | 76,9%           |