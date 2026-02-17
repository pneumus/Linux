# A Simple Git Tutorial

### The top most used Git Commands

<details>
  <summary>🪪 Set your Identity</summary>
  <br>
  <ul>
  <li>Set your Name ( Visible to Collaborators )</li>
  
    git config --global user.name "John Smith"
  
  <li>Set your Contact ( Visible to Collaborators )</li>

    git config --global user.email "john.smith@mail.com"

  <li>Check your Config</li>

    git config --list

  <blockquote>Sample Response:</blockquote>

    user.name=John Smith
    user.email=john.smith@mail.com
  
  </ul>
</details>



<details>
  <summary>⏫ Create a Local Repository and push it to the Server</summary>
  <br>
  <ul>
  <li>Create a Folder and Open it</li>
  
    mkdir repo
    cd repo
  
  <li>Initialize Git Repository</li>
  
    git init
    
  <li>Add some Source Files</li>
  
    touch source.c
    touch source.java
  
  <li>Add full Folder Content to the Repo</li>
  
    git add .

  <li>Initial commit with a message</li>
  
    git commit -m "Initial Commit Message"
  
  <li>Create a Remote Repository</li>
  <br>
    <ul>
      <li>Login to GitHub / GitLab / BitBucket ...etc.</li>
      <li>Create an Empty Repository</li>
      <li>Optionally: Add your SSH / GPG Key or Personal Access Token </li>
    </ul>
  <br>
  <li>Link the Local Repo to the Remote Repo</li>
  
    git remote add origin https://github.com/your-username/your-repo-name.git
  
  <li>Recommended: Rename your Branch to "main"</li>
  
    git branch -m main
  
  <li>Push the committed Files to the Server</li>
  
    git push -u origin main

  </ul>
</details>

<details>
  <summary>⏬ Clone Remote Repository from the Server</summary>
  <br>
  <blockquote>Cloning is the "other way around" when you start from the Server</blockquote> 
  <ul>
    <li>Login to GitHub / GitLab / BitBucket ...etc.</li>
    <li>Create a New Repository (and populate it)</li>
    <li>Clone the Repository</li>

      git clone https://github.com/your-username/your-repo-name.git
    
  </ul>
</details>

<details>
  <summary>👁️ Watching your Repository - Aka "lookie lookie"</summary>
  <br>
  <ul>
  <li>See your Current State</li>

    git status
    
  <blockquote>Note: You can see your Current Branch, and also if there is something to Commit. 
    <br>
    Sample Response:
  </blockquote>
    
    On branch main
    Your branch is up to date with 'origin/main'.    
    nothing to commit, working tree clean


  <li>Download (Sync) all data from the Server</li>
  <br>
    
    git fetch

  <blockquote>Recommended: Start every day with a good fresh fetching! - It's Safe. Nothing can go Wrong!</blockquote>
  <li>List all Remote Branches</li>
  
    git branch -r

  <blockquote>Note: "origin" means it is a remote branch. 
    <br>
    The remote "HEAD" points to the default branch. 
    <br>
    Sample Response:
  </blockquote>
    
    origin/HEAD -> origin/main
    origin/SampleBranch1
    origin/SampleBranch2
    origin/main
  
  <li>List all Local Branches</li>

    git branch

  <blockquote>Note: The "current local" Branch is highlighted with an asterisk.
    <br>
    The local HEAD points to this Branch.
    <br>
    Sample Response:
  </blockquote>

    SampleBranch1
    SampleBranch2
    * main

  <li>See Commit History - Your Time Machine</li>

    git log

  <blockquote>
    The Commit History will show you 
    <ul>
      <li>The "Commit Hash" ( long alphanumeric ID )</li>
      <li>The local HEAD state as well ( HEAD -> main ), See the Output of: git branch</li>
      <li>All other local branches</li>
      <li>Dates and Authors of each Commit - Who Commited What and When</li>
    </ul>
    
  </blockquote>
    
  </ul>
</details>

<details>
  <summary>🗒️ Adding & Removing Files</summary>
  <br>
  <ul>
  <li>Adding New File(s) to the Repository</li>
  <blockquote>
    If you create New File(s) locally, 
    <br>
    Git will not "see" it
    <br>
    because they are not tracked yet,
    <br>
    therefore you need to add it to the Repo
  </blockquote>

  <li>Adding a Single File to the Repo</li>
    
    git add file.txt

  <li>Adding Multiple Files to the Repo</li>

    git add source.java
    git add config.xml

  <li>Adding all Untracked Files ( NOT RECOMMENDED! )</li>
  
    git add .
  
  <blockquote>
    This command is only useful if you created a 
    <br>
    brand new repository and want to add all files in your folder
    <br>
    or you know exactly what you're doing
  </blockquote>
  
  
  
  <li>Deleting Files</li>
  <blockquote>
    If you delete a file in your OS, it is not removed from the Repo yet
    <br>
    <b>git rm</b> will remove it from the Repo and also Delete it from your Hard Drive
  </blockquote>
  
    git rm config.xml

  <li>Untracking Files</li>
  <blockquote>The local copy stays untouched, but won't be part of the Repo anymore</blockquote>

    git rm --cached config.xml
  
  <li>Committing the Tracked Files - Untracked Files are ignored</li>
  <blockquote>
    After Adding / Editing / Deleting Files from the Repo
    <br>
    Committing the Files is Necessary
  </blockquote>
  
  <li></li>
  </ul>
</details>

<details>
<summary>🔀 Switching between Branches</summary>
<ul>
  <br>
  <details>
  <summary>🥰 The Happy Path - Nothing to Commit</summary>
  <br>  
  <li>Before doing anything, check the Current Status</li>
  
    git status
  
  <li>The "happy response" if your are on the <b>main</b> Branch:</li>
  
    On branch main
    Your branch is up to date with 'origin/main'.    
    nothing to commit, working tree clean
  
  <li>If nothing to commit, Update your Repo</li>

    git fetch

  <li>List Remote Branches</li>

    git branch -r

  <li>Note the Name of the Branch you want to switch to</li>

    origin/HEAD -> origin/main
    origin/SampleBranch1
    origin/SampleBranch2
    origin/main

  <li>Switch to the Branch ( SampleBranch2 in the below Sample )</li>

    git switch SampleBranch2

  <blockquote>Note: We don't use git checkout since August 2019 to switch between branches. It's safer!</blockquote>
  
  <li>Update your Local Branch with any New Commits from the Server</li>

    git pull
  
  </details>
</ul>
</details>
