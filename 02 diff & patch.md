#### Git resources available online
The Book - [ProGit](https://git-scm.com/book/en/v2) and [Tutorial](https://git-scm.com/docs/gittutorial)

Def. **Version Control System** - It keep track of the changes in our files + the changes which are made by others when working in collaborations.

#### Diffing Files 
How to find the difference between [rearrange1.py](file:////Users/saqibali/Documents/git/git_course/rearrange1.py) and [rearrange2.py](file:////Users/saqibali/Documents/git/git_course/rearrange2.py).
![[diff1.png]]

Diff when multiple lines are changed or added in the file
![[diff2.png]]

Diff in unified format - u
![[diff3.png]]

Other tools: 
wdiff (highlights the words that have changed in the file), meld, KDiff3, vimdiff

##### Applying Changes
```shell
diff -u old_file new_file > change.diff
patch old_file < change.diff
```
For example we have [disk_usage_original.py](file:////Users/saqibali/Documents/git/git_course/code/disk_usage_original.py) and [diskusage_fixed.py](file:////Users/saqibali/Documents/git/git_course/code/disk_usage_fixed.py) Now we use path command to apply the changes in the diff file to the original file.
```shell
 diff -u disk_usage_original.py disk_usage_fixed.py > disk_usage.diff
 cat disk_usage.diff
 pathch disk_usage_original.py < disk_usage.diff
 cat disk_usage_original.py
 ````
![[patch.png]]

**Diff Examples:**
```shell
~$ cat menu1.txt
Menu1:
Apples
Bananas
Oranges
Pears

~$ cat menu2.txt
Menu:
Apples
Bananas
Grapes
Strawberries

~$ diff -u menu1.txt menu2.txt

\--- menu1.txt 2019-12-16 18:46:13.794879924 +0900
+++ menu2.txt 2019-12-16 18:46:42.090995670 +0900
@@ -1,6 +1,6 @@

\-Menu1:
+Menu:
Apples
Bananas
\-Oranges
\-Pears
+Grapes
+Strawberries
```
**Patch Examples:**
```shell
~$ cat hello_world.txt
Hello World
~$ cat hello_world_long.txt
Hello World
It's a wonderful day!

~$ diff -u hello_world.txt hello_world_long.txt
--- hello_world.txt 2019-12-16 19:24:12.556102821 +0900
+++ hello_world_long.txt 2019-12-16 19:24:38.944207773 +0900
@@ -1 +1,3 @@
Hello World
+
+It's a wonderful day!

~$ diff -u hello_world.txt hello_world_long.txt > hello_world.diff
~$ patch < hello_world.diff
patching file hello_world.txt

~$ cat hello_world.txt
Hello World
It's a wonderful day!
```
