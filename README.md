# commit-blame-ignore-demo
A demonstration of ignoring specific commits in git blames.

By introducing a `.git-blame-ignore-revs` file, we can ignore specified commits from affecting git blame.<br>
This repository has the file control_code.py and test_code.py. Both files have identical code.<br>
In the case of the control: the commit that reformatted the file **is not** ignored.<br>
In the case of the test: the commit that reformatted the file **is** ignored.<br>

By checking the blame of both files we can see the effects.<br>
Every line is blamed on the reformatting commit:
![control code](images/control_code_blame.png)
The formatting commit is ignored:
![test code](images/test_code_blame.png)

Modern IDEs will automatically use `.git-blame-ignore-revs` if it is present.<br>
If your IDE does not, you can run the following to modify your git config: `git config blame.ignoreRevsFile .git-blame-ignore-revs`.<br>
