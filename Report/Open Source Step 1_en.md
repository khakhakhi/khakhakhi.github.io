## Open Source Step 1: Start with dynamic gradients and start on the path to optimization

## 1 Project Background

**1.1 Project objectives**: Practice data visualization, be familiar with the GitHub environment, be familiar with git operations, and understand open source projects.

**1.2 Report date**: March 5, 2025

**1.3 Project Leader**: 11

## 2 Project Process

### 2.1 Create a project repository

**2.1.1 Project source**: GitHub 

**2.1.2 Open source project**: [PythonDataScienceHandbook](https://github.com/jakevdp/PythonDataScienceHandbook)

**2.1.3 Creation process**

2.1.3.1 Remote repository: Select an open source project you are interested in and fork the original repository to create a copy of the remote repository.

- (1) This allows you to copy the main part of the project to a newly created repository, and the copied project is located in its own independent repository, and the modification will not affect the open source project.
- (2) If you want to submit a new feature to the original repository after developing it, you can create a PR to submit the changes to the original author for review, and after the review is passed, you can become one of the contributors, and the original repository of the project will be merged into a new branch.

2.1.3.2 Local repository: Use git clone to download a copy of the remote repository to the local computer and create a local repository.

- The remote repository interface provides online editing, but it is not recommended because of possible format conflicts that may cause the preview to fail. It is recommended that you edit the file in an environment that you are familiar with.

### 2.2 Open the file

#### 2.2.1 Open the repository

2.2.1.1 JupyterLab: 
After switching to the popular virtual environment from the conda command line, install the Git extension, go to the repository folder, and open JupyterLab.

Other opening methods: VSCode, PyCharm and other common software can open local repositories, and the specific opening method depends on the file format and the editors I use. Considering that the language of this project is Jupyter Notebook, we use JupyterLab to open the project repository.

About Git extensions: Since you have not used JupyterLab to open repositories before, you can install Git extensions before opening JupyterLab to facilitate subsequent branch management. You can also manage branches with terminal commands. Command to install the 'jupyterlab-git' extension: 'pip install jupyterlab-git'

2.2.1.2 Create branches: colorful and colorful_act

To create, view, and switch branches, you can use Git to expand, or you can use terminal commands to close the file refresh interface when you are stuck, and there is a probability that there will be file caching, resulting in modification errors.

#### 2.2.2 Open the file
 - colorful: After confirming that the current branch is colorful instead of main or master, open the IPYNB file and find the file that contains the histogram.

### 2.3 Modify the file

#### 2.3.1 Confirm the current branch: 

You can check the lower left corner of the interface, view the Git extension, and type '`git branch`' in the terminal.

#### 2.3.2 Edit the content of the file
- (1) Branch main: Add a tag
 - - Added tags such as diagram name and axis name to facilitate image reading.

- (2) Branch colorful: Gradient color
 - -  Changed the rainfall map from a normal blue bar chart to a gradient of orange on top and blue on bottom.

- (3) Branching colorful_act: Dynamic gradient
 - -  Changed the rain map from a normal blue column chart to a gradient color with high orange and low blue, and changed the color scheme from pure decoration to quantity and size cues.

### 2.4 Submit your documents

#### 2.4.1 File push

After the file is edited, 

(1)[save] saves the file 

→ (2)[add, staged] to stage the changes (commit to the staging area) 

→ (3)[commit] commits the local repository and name the changes (you can add a description) 

→ (4)[push] push the local update of the current branch (commit to the remote repository).

### 2.5 Add description

In addition to the naming when the update was committed, a visual description of the optimization has been added to the README of the colorful_act branch, including the content and scope of optimization.

## 3 Project Results

### 3.1 Visual optimization

#### 3.1.1 The replica of the remote repository contains 3 branches at the end: 

(1) Branch main: Add tag ★★☆☆☆
- Added tags such as diagram name and axis name to facilitate image reading.

(2) Branch colorful: Gradient color ★★★☆☆
- Changed the rainfall map from a normal blue bar chart to a gradient of orange on top and blue on bottom.

(3) Branch colorful_act: Dynamic gradient ★★★★★
- Changed the rain map from a normal blue column chart to a gradient color with high orange and low blue, and changed the color scheme from pure decoration to quantity and size cues.

#### 3.1.2 Update instructions

- Added a description to the README of the final product branch colorful_act, and the optimized scope in the update description can be synchronized with subsequent updates.

- Write project reports as a personal backup record, and at the same time make it easier for other newcomers to avoid detours.

## 4 Problems & Solutions

### 4.1 About file commits and branch switching

Correct operation: In JupyterLab, the normal operation is to modify and save the file and submit it to the local repository before switching branches.

Problem description: If the modified file is not committed and the branch switch is performed, two scenarios will occur:
- 1: The branch is switched smoothly, but the files remain unchanged, the files in each branch are the latest files, and the old version is suspected to be missing.

 Solution:
 This is stuck, it may be caused by file caching, you can try to restore it to normal by closing the file, refreshing the web page, restarting kernal, restarting JupyterLab, etc.

- 2: Git prompt: Requires a commit to the modified file before you can switch branches.

 Solution:
 Follow the prompts to name your changes and commit or discard the action.

### 4.2 About the gradient effect

Version 0: [Waiver]
- Performance: Histogram color gradient from left to right, blue on the left and orange on the right,
- Problem: Not an ideal gradient effect, color changes are meaningless
- Solved: Plan to change to orange and blue

Version 1: [Waiver]
- Performance: The entire bottom of the picture is covered with color, and at the same time the top orange and bottom blue gradient
- Problem: Histograms disappear
- Solution: Precise control of each column fill

Version 2: [Waiver]
- Representation: The entire bottom of the image is covered in color, and all of it is blue
- Issue: The histogram disappears and no gradient colors appear
- Solution: Precise control of each column fill

Version 3: [Reserved]
- Performance: Each bar is a gradient of orange on top and blue on the bottom
- Problem: Not the best gradient effect
- Solved: Dynamically adjust the proportion of orange in the gradient based on the height of the column: the taller the column has more orange parts, and the shorter column has less orange parts (or even none)

Version 4: [Reserved]
- Performance: Tall pillars fade from blue to orange, and short pillars are mostly blue with little to no orange

### 4.3 About file editing and merging conflicts

#### 4.3.1 problem and solution

- Problem 1: After creating a colorful branch in a remote repository, I edit a file online, but an error is reported and the file cannot be previewed.
 Solution: Create a local repository, open the file correctly locally, make file modifications, and then submit the push.

- Problem 2: An error occurs when pushing a colorful branch of a local repository to a remote repository, indicating that it is not the latest version, and a double error occurs after pulling, that is, it cannot be pulled or pushed, and the files of the local repository and the files of the remote repository are conflicting.
 Solution: 
 Force push. Once you have determined that the changes to the remote branch are incorrect, force push the correct and latest local file to the remote repository, overwriting the changes in the remote branch: 'git push - force' (Use with caution, it will easily lead to data loss.) 
 This conflict was later handled when supplementing the Readme description with VSCode, merging the two versions of the file (Ignore the changes of the remote branch, accept all the changes of the local branch, and finally merge the results.) .

#### 4.3.2 Conclusion

It is not recommended to edit directly online in a remote repository, as it is easy to make mistakes due to improper operation.

## 5 Project Summary

### 5.1 harvest

- Learned how to work with open source projects, including collecting open source projects and creating copies of repositories.

- Practiced the optimization of data visualization and refined the optimization assumptions in the process of practice, so that the results presented better results than originally envisaged.

- Solved a number of problems in the process of Git operation, put the theoretical knowledge of Git learned before into practice, and became more proficient in Git.

### 5.2 prospect

- Keep updating until the charts are optimized throughout the project.

- Find other open source projects, try to create PRs and submit them after optimization, and strive to become an open source community contributor.

### 5.3 URL: [khakhakhi](https://github.com/khakhakhi/PythonDataScienceHandbook/tree/colorful_act)