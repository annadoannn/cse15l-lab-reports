# Lab Report 3 -- Bugs and Commands
## PART ONE - BUGS
Provide:

- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
- An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
- The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.

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


