# Lab Report 3 - Experimenting with grep
## grep -A n pattern filename
This grep command prints the number n lines after finding the pattern you want within the given file. This command is useful say if you want to know following information of a given pattern.

Example 1:
```
[cs15lsp23jy@ieng6-201]:biomed:334$ grep -A 2 thus rr74.txt
        other hypoxic gas chambers, thus limiting the build-up of
        waste products, including ammonia, that may contribute to
        lung inflammation and induction of iNOS, as the combination
```
Example 2:
```
[cs15lsp23jy@ieng6-201]:biomed:347$ grep -A 2 cham rr74.txt
        housed in sealed hypobaric chambers as opposed to being
        flushed with 10% O
        2 gas. The hypobaric chambers used in
        the present study have a higher rate of air exchange than
        other hypoxic gas chambers, thus limiting the build-up of
        waste products, including ammonia, that may contribute to
        lung inflammation and induction of iNOS, as the combination
```
## grep -m n pattern filename
This command prints the first n instances that the pattern occurs within the file given. This command is useful to use when if you just want to quickly find if the file has the amount of the pattern given that you want.

Example 1:
```
[cs15lsp23jy@ieng6-201]:biomed:340$ grep -m 2 exposed rr74.txt
        present study we exposed wild-type mice to severe hypobaric
          animals that were exposed to hypobaric hypoxia as
```
Example 2:
```
[cs15lsp23jy@ieng6-201]:biomed:341$ grep -m 2 gr rr74.txt
          using 8-16% gradient gels (Invitrogen, Carlsbad, CA,
          experimental groups (positive control was mouse
```

## grep pattern$ filename
"$" means end of line/last in linux, so this command prints every line that contains the pattern at the end of the line. This command could be useful if you are looking for certain properties within a file, say if it is code, you could find all the lines that are statements in java with "grep ;$ filename". 

Example 1:
```
[cs15lsp23jy@ieng6-201]:biomed:342$ grep se$ rr74.txt
          experimental groups (positive control was mouse
        activity in the systemic circulation. However, those
        synthase; PBS = phosphate-buffered saline; PCR = polymerase
```
The pattern se$ meanse we want to find all linds of the file that have "se" at the end of them. So in our example we found three. Notice "se" has to be the last thing of each line, say even if there were a line like "house." within the file this wouldn't be found in our grep search because we did not include the period within the pattern. Vice versa, if we were to include the period within our search, none of the three lines found in example on would be returned.
Example 2:
```
[cs15lsp23jy@ieng6-201]:biomed:345$ grep ing$ rr74.txt
        NOS protein in the lung as assessed using
          Western blotting
          Western blotting
          was lipopolysaccharide-treated mouse spleen) and using
          eNOS expression in the lung, as studied using
          Localization of NOS in mouse lung was determined using
        to hypoxic pulmonary hypertension in younger, developing
        been identified in the eNOS promoter. Recently, altering
        both iNOS mRNA and protein levels in rat lungs following
        housed in sealed hypobaric chambers as opposed to being
        localization of iNOS to the airway did not change following
        In rat lungs, nNOS expression was increased following
```
## grep -l pattern *
In linux "-l" means files with match, so this command prints every file within a directory that contains the given pattern. This command would be especially useful in finding files of topics that you want to explore within a large directory.

Example 1:
```
[cs15lsp23jy@ieng6-201]:biomed:359$ grep -l eNOS *
1471-2121-2-1.txt
1471-230X-1-5.txt
rr74.txt
```
Example 2:
```
[cs15lsp23jy@ieng6-201]:biomed:355$ grep -l fight *
1471-2407-2-19.txt
1472-684X-1-5.txt
1472-6963-3-7.txt
1477-7525-1-10.txt
cc3.txt
gb-2002-4-1-r2.txt
```

# Sources:
I learned how to do all these tricks at this site: https://www.golinuxcloud.com/grep-command-in-linux/#13_Stop_reading_a_file_after_NUM_matching_lines_with_grep_command
