# Lab Report 3 -- Bugs and Commands
## PART ONE - BUGS
- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
~~~
  @Test
  public void avgwolowest() {
    double[] input1 = {1,1,2,2,3};
    assertEquals(2.0, ArrayExamples.averageWithoutLowest(input1),0.01);
  }
~~~
- An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
~~~
  @Test
  public void avgwolowest2() {
    double[] input1 = {1,2,3,4,5};
    assertEquals(3.5, ArrayExamples.averageWithoutLowest(input1),0.01);
  }
~~~
- The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
![image](lab3.png)


- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.
__Before the fix:__
~~~
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
~~~

__After the fix:__
~~~
static double averageWithoutLowest(double[] arr) {
    if (arr.length <= 1) {
        return 0.0;
    }

    double lowest = arr[0];
    double sum = 0;
    int count = 0;

    for (double num : arr) {
        if (num < lowest) {
            lowest = num;
        }
    }

    boolean excludedOneLowest = false;
    for (double num : arr) {
        if (num == lowest && !excludedOneLowest) {
            excludedOneLowest = true;
        } else {
            sum += num;
            count++;
        }
    }

    if (count == 0) {
        return 0.0; // All elements in the array are the same (the lowest)
    }

    return sum / count;
  }

}
~~~
The fix addressed the issue that the code wouldn't take into account that there could be a possibility of having multiple lowest integers in an array, and will exclude them from the calculation. I modified the code to exclude only one occurrence of the lowest value instead of excluding all of the lowest values.


## PART TWO - RESEARCHING COMMANDS
I chose `grep`.
### Find four command-line options or alternate ways to use the `grep` command.
give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.


### 1. `-i` command-line option
[link to -i ](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/)


__example of using `grep -i` on a file:__
~~~~
grep -i "emergency" technical/911report/chapter-9.txt
~~~~

output:
~~~
Emergency response is a product of preparedness. On the morning of September 11,
                local public servants, especially the first responders: fire, police, emergency
                and exposed vulnerabilities in the World Trade Center's and the city's emergency
                to ensure safety, and elevators stopped. The public-address system and emergency
                Twin Towers. The 911 emergency call system was overwhelmed. The general evacuation
            To manage fire emergency preparedness and operations, the Port Authority created the
                with building occupants during an emergency.
                use the emergency intercom phone to obtain specific information on how to proceed.
                drill announcement advised participants that in the event of an actual emergency,
                provided at the time of an emergency. Civilians were not informed that rooftop
                Mayor's Office of Emergency Management (OEM).
                emergency, a leading role would be played by the Special Operations Division. This
                rescues, and the Emergency Service Unit (ESU), which carried out specialized rescue
                emergency call system. Its approximately 1,200 operators, radio dispatchers, and
                of emergency response. When a 911 call concerned a fire, it was transferred to FDNY
            Office of Emergency Management and Interagency Preparedness.
            In 1996, Mayor Rudolph Giuliani created the Mayor's Office of Emergency Management,
                Marco Crupi incident. After OEM's Emergency Operations Center was activated,
                response to the emergency," while the OEM was "designated the 'On Scene Interagency
                many civilians may have been unable to use the emergency intercom phones, as they
                emergency personnel to reach them. This advice was given to callers from the North
                to remain in place, it did not correspond to any prewritten emergency
            Emergency medical services (EMS) personnel were directed to one of four triage areas
            Around the city, the NYPD cleared major thoroughfares for emergency vehicles to
                of the North Tower-began to activate the Emergency Operations Center by calling such
                OEM. In addition, the Federal Emergency Management Agency (FEMA) was called and
            The emergency response effort escalated with the crash of United 175 into the South
                emergency personnel inside, as well a number of individuals-both first responders
                stairs and observed that the power was lost and emergency lights activated.
                largest loss of life of any emergency response agency in history. The PAPD suffered
                moved quickly north and established an emergency operations command post at the
            EMERGENCY RESPONSE ATTHE PENTAGON
            The emergency response at the Pentagon represented a mix of local, state, and federal
                management structure for emergency response, was in place in the National Capital
                terrorist attack affected the daily operations and emergency management requirements
            While no emergency response is flawless, the response to the 9/11 terrorist attack on
                relationships and trust established among emergency responders; second, the adoption
                State Police, the Virginia Department of Emergency Management, the FBI, FEMA, a
            Command was established at 9:41. At the same time, the Arlington County Emergency
                both sites will likely recur in any emergency of similar scale. The task looking
            Like the national defense effort described in chapter 1, the emergency response to
                911 operators and FDNY dispatch were not adequately integrated into the emergency
                disasters, it is important to integrate those taking 911 calls into the emergency
                would be "responsible for the management of the City's response to the emergency."
                by clearing emergency lanes to the WTC.
                emergency of this scale contributed to the early lack of units in the South Tower,
                not "responsible for the management of the City's response to the emergency," as the
            In May 2004, New York City adopted an emergency response plan that expressly
~~~

Using `grep -i`, we can command it to return lines containing the specified text pattern from the specified file, regardless of whether the pattern is in uppercase or lowercase. This is helpful for searching for specific keywords or text, and `grep -i` allows you to find all occurrences of those keywords, regardless of case sensitivity. 

__example of using `grep -i` on a directory:__
~~~
grep -i "word" technical
~~~
output:
~~~
grep: technical: Is a directory
~~~

`grep -i` doesn't work on directories since `grep` alone is designed to search for patterns within files. 

### 2. `-n` command line option:
[link to -n](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/)
__example of using `grep -n` on a file:__
~~~
grep -n "We" technical/911report/preface.txt
~~~
output:
~~~
5:            We present the narrative of this report and the recommendations that flow from it to
10:            We have come together with a unity of purpose because our nation demands it.
26:                our mandate. We have sought to be independent, impartial, thorough, and nonpartisan.
33:            We learned about an enemy who is sophisticated, patient, disciplined, and lethal. The
39:            We learned that the institutions charged with protecting our borders, civil aviation,
41:                adjust their policies, plans, and practices to deter or defeat it. We learned of
43:                between and within agencies. We learned of the pervasive problems of managing and
47:                We hope that the terrible losses chronicled in this report can create something
50:                meet the challenges now confronting us. We need to design a balanced strategy for
52:                the same time protecting our country against future attacks. We have been forced to
59:                Commissioners, whose dedication to this task has been profound. We have reasoned
61:                dialogue. We want to express our considerable respect for the intellect and judgment
63:            We want to thank the Commission staff. The dedicated professional staff, headed by
68:                have been superb. We thank the Congress and the President. Executive branch agencies
69:                have searched records and produced a multitude of documents for us. We thank
73:                assistance. We owe a huge debt to their investigative labors, painstaking attention
74:                to detail, and readiness to share what they have learned. We have built on the work
76:                fine work helped us get started. We thank the City of New York for assistance with
79:            We conclude this list of thanks by coming full circle: We thank the families of 9/11,
83:            We want to note what we have done, and not done. We have endeavored to provide the
87:                issues and organizations, we are conscious of our limits. We have not interviewed
89:                inevitably will come to light. We present this report as a foundation for a better
91:            We have listened to scores of overwhelming personal tragedies and astounding acts of
92:                heroism and bravery. We have examined the staggering impact of the events of 9/11 on
93:                the American people and their amazing resilience and courage as they fought back. We
95:                preparing to respond if it becomes necessary. We emerge from this investigation with
97:                for the American people. We recognize the formidable challenges that lie ahead.
98:            We also approach the task of recommendations with humility. We have made a limited
99:                number of them. We decided consciously to focus on recommendations we believe to be
100:                most important, whose implementation can make the greatest difference. We came into
103:                considered the views of others. We hope our report will encourage our fellow
~~~

`grep -n` returns the line numbers and the line that contains the specified text pattern. It's useful if we needed to find a specific line to go back to and edit its contents. 

__example of using `grep -n` on a directory:__
~~~
grep -n "We" technical/911report
~~~
output: 
~~~
grep: technical/911report: Is a directory
~~~

`grep -n` doesn't work on a directory since it's intended for searching patterns within the content of files. 
