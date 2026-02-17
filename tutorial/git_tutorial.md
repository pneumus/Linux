# A Simple Git Tutorial

### The top most used Git Commands

<details>
  <summary>Create a Local Repository</summary>
  <br>
  <ul>
  <li>Create a Folder and Open it</li>
    
    mkdir repo
    cd repo
    
  <li>Initialize Git Repository</li>
    
    git init

  <ul>
</details>

<details>
  <summary>Push Local Repo to Server</summary>
  <br>
  <ul>
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

      git branch -M main

  <li>Push the committed Files to the Server</li>

      git push -u origin main
      
</details>

<details>
  <summary>Clone Remote Repo from the Server</summary>
  <br>
  <ul>
    <!-- Cloning is the "other way around" when you start from the Server -->
    <li>Login to GitHub / GitLab / BitBucket ...etc.</li>
    <li>Create a New Repository (and populate it)</li>
    <li>Clone the Repository</li>

      git clone https://github.com/your-username/your-repo-name.git
    
  </ul>
</details>
