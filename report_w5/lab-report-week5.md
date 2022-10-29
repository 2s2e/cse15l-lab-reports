<!-- Consider the commands less, find, and grep. Choose one. Online, find 3 interesting command-line options or alternate ways to use the command you chose. For example, we saw the -name option for find in class. For each of those options, give 3 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

That makes 9 total examples, three each for three different command-line options. Many commands like these have pretty sophisticated behavior possible – it can take years to be exposed to and learn all of the possible tricks and inner workings.

To find information about the commands, a simple Web search like “find command-line options” will probably give decent results. There is also a built-in command on many systems called man (short for “manual”) that displays information about commands; you can use man grep, for example, to see a long listing of information about how grep works.-->

# **grep**

## -c
The -c option prints the amount of lines in the ext file that match the given pattern.

**Example 1:**
```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/911report# grep -c "FAA: " chapter-1.txt
16
```
Here, the grep command prints out the number of lines which contain tha pattern "FAA: ", which allows me to find how many times the FAA speaks in this recorded documented quickly.

**Example 2:**

```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/911report# grep -c "\n\n" chapter-10.txt
20
```
Searching for \n\n lets me find the number of double line breaks, which lets me easily find the number of sections in the text.

**Example 3:**

```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/911report# grep -c "CIA" *.txt 
chapter-10.txt:7
chapter-11.txt:32
chapter-12.txt:0
chapter-13.1.txt:39
chapter-13.2.txt:4
chapter-13.3.txt:143
chapter-13.4.txt:179
chapter-13.5.txt:95
chapter-1.txt:1
chapter-2.txt:0
chapter-3.txt:158
chapter-5.txt:3
chapter-6.txt:113
chapter-7.txt:0
chapter-8.txt:68
chapter-9.txt:0
preface.txt:2
```
The -c option can be used with multiple files to generate a visualization of in which files a certain file appears the most often. With this search, I can tell at a glance which documents contain the most mentions of the CIA.

## -C 

-C n prints out the lines that are n lines above and below any matching lines

**Example 1:**

```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/biomed# grep -C 3 http 1471-213X-1-2.txt
          Computer analysis
          Sequence homologies were identified with the Blast
          algorithm [ 37, 38] at the National Center for
          Biotechnology Information (http://www.ncbi.nlm.nih.gov/).
          To identify long-range palindromic structures, an RNA
          secondary structure algorithm in the program DNASIS
          version 2.0 was used. Transcription factor binding sites
          were identified with MatInspector at
          http://genomatix.gsf.de/cgi-bin/matinspector/matinspector.pl
          [ 39].


```
I've used -C here to print out lines containing "http" and any surrounding lines, effectively letting me see all external references in this text and a brief context of what it was used for.

**Example 2:**
```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/biomed# grep -C 10 Results 1471-213X-1-2.txt
        many copies of that sequence in the array. This sequence
        did not affect all cell migrations, the ALM/BDU cell
        division or the positions of the BDU cells. We conclude,
        therefore, that the sequence is sequestering a factor that
        helps control ALM migrations and PLM axon outgrowth. We
        also suggest that this factor may be differentially
        segregated into touch receptor neurons and that it may help
        specify the touch receptor neuron cell fate.


        Results

          ALM migration and PLM axonal morphology
          defects
          Figure 2shows fluorescence micrographs and bar graphs
          of the positions of the ALMs from strain TU2562, which
          has an integrated
          mec-3gfp (equivalent to pJC8 in
          Figure 4), and strain EA485, which contains a high copy
          extrachromosomal array made from plasmid pJC4 (see Figure
          4and Materials and Methods). In strain TU2562, the ALMs
```
Using -C to search for the results in biomedical papers allows me to jump to what the paper has discovered while letting me skim the conclusion of the paper. 

**Example 3:**
```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/government/Alcohol_Problems# grep -C 2 driving *.txt
DraftRecom-PDF.txt-sets up the expectation that something has to follow. Without
DraftRecom-PDF.txt-screening, there cannot be much intervention. He noted that the
DraftRecom-PDF.txt:recommendation could be seen as a way of driving widespread
DraftRecom-PDF.txt-applications of interventions. If that is the goal, he thought we
DraftRecom-PDF.txt-should be examining how to accomplish screening. There are large
--
Session3-PDF.txt-eligible patients.19 Patients were assigned to a motivational
Session3-PDF.txt-intervention or a standard control of a handout about drinking and
Session3-PDF.txt:driving and a list of alcohol treatment agencies. The intervention,
Session3-PDF.txt-which lasted 30 to 40 minutes, was delivered in the emergency
Session3-PDF.txt-department either immediately or within a couple of days of the
Session3-PDF.txt-visit. About 25% of the eligible patients were discharged before
Session3-PDF.txt-the intervention and another 25% refused to participate.
Session3-PDF.txt:Nevertheless, drinking and driving, moving violations,
Session3-PDF.txt-alcohol-related injuries, and alcohol-related problems were
Session3-PDF.txt-significantly reduced at the six-month follow up, with the
--
Session3-PDF.txt-23. Madden C, Cole TB. Emergency intervention to break the
Session3-PDF.txt-cycle of drunken
Session3-PDF.txt:driving and recurrent injury. Ann Emerg Med 1995;25(2):177-9.
Session3-PDF.txt-
Session3-PDF.txt-24. Soderstrom CA, Dischinger PC, Kerns TJ, Kufera JA, Mitchell
--
Session3-PDF.txt-What outcomes are we measuring? Do they include a decrease in
Session3-PDF.txt-alcohol consumption or decreases in negative consequences, such as
Session3-PDF.txt:drinking and driving violations or school and work problems? A
Session3-PDF.txt-decrease in morbidity and mortality may be more difficult to
Session3-PDF.txt-measure and require a lengthy follow-up period, but it provides
--
Session3-PDF.txt-funded to change six behaviors among youth: not wearing bike
Session3-PDF.txt-helmets, failing to use seat belts, carrying a weapon, binge
Session3-PDF.txt:drinking, riding with a drinking driver, and drinking and driving.
Session3-PDF.txt-However, the protocol did not ask patients which behaviors they
Session3-PDF.txt-were motivated to change. The intervention led to a small change in
--
Session4-PDF.txt-problems stopped drinking, a substantial number of patients with
Session4-PDF.txt-alcohol-related problems would still present to the emergency
Session4-PDF.txt:department. For example, driving while intoxicated overlaps with
Session4-PDF.txt-alcoholism, but it constitutes an important issue in its own right
Session4-PDF.txt-because surveys consistently show that a substantial number of
--
Session4-PDF.txt-information can influence policy changes such as lowering the legal
Session4-PDF.txt-limit of a driver's BAC or extending DWI laws to cover snowmobile
Session4-PDF.txt:driving.
Session4-PDF.txt-Research on changing social norms for alcohol use and abuse is
Session4-PDF.txt-needed for practitioners and patients, given that alcohol-related
```
Suppose I wanted to research drunk driving and I have a series of records at my disposal. I can use the -C option to peruse where and how driving is mentioned to pinpoint areas of interest in these papers.

## -l
The -l option for grep prints out only the filenames of the files that contain the desired pattern.

**Example 1**

```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/plos# grep -l "T-cells" *.txt
journal.pbio.0020307.txt
```
Using -l lets me see that only journal.pbio.0020307.txt mentions T-cells instead of having to go through every document in plos. 

**Example 2**

```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/government/Media# grep -l "New York Times" *.txt
Bias_on_the_Job.txt
Domestic_Violence_Ruling.txt
highlight_Senior_Day.txt
Law_Schools.txt
Using_Tech_Tools.txt
```
Here, I want to find all the text files that were written by the New York Times, which can be done using -l with "New York Times" gives me a clean list of text files that contain "New York Times".

**Example 3**
```
root@LAPTOP-GP790FV2:/mnt/c/Users/steve/Projects/School/CSE 15L/skill-demo1/technical/911report# grep -l "TSA" *.txt
chapter-12.txt
chapter-13.2.txt
chapter-13.5.txt
```
Again, using -l here allows me to generate a list of all the files that contain a term I'm looking for. Here, I want a list of chapters in the 9-11 report that mention the TSA, and the -l option lets me do just that.

