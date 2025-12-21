# Basic Linux Commands

<details>
  <summary>⭐ F.U.C.K. - Frequently Used Commands in Konsole</summary>
  &nbsp;&nbsp;&nbsp;   

  <details>
  <summary>history - See Command History</summary>
  &nbsp;  
    
  ## List Command History
  ```
  history
  ```   

  ## history -d - Delete Entry from Command History
  ```
  history -d 4
  ```   
  </details>

  &nbsp;&nbsp;&nbsp;   
</details>



<details>
  <summary>📁 File & Directory Management</summary>
  &nbsp; &nbsp; &nbsp;

<details>
  <summary>ls - List Contents of a Directory</summary>
  &nbsp;   

  <span style="color:blue">some *blue* text</span>.
  ## ${\color{lightgreen}\mathtt{ls \space -a}}$
  The <b>-a</b> switch stands for <b>ALL</b> Entries ( including the hidden ones )   
  <b>Note:</b> Hidden Entries have a dot ( . ) as a Starting Character

  ```   
  [mateo@archipelago ~]$ ls -a
.   .bash_history  .bash_profile  .cache   Desktop    Downloads   .icons  .mozilla  Pictures  Templates  Videos
..  .bash_logout   .bashrc        .config  Documents  .gtkrc-2.0  .local  Music     Public    .var       yay
  ```   

  ## ${\color{lightgreen}\mathtt{ls \space -l}}$
  The <b>-l</b> switch stands for <b>LONG</b> Listing with all Attributes.   
  <b>Note:</b> There are multiple columns listed here with different purpose.   
  The entry at the top "total 654910" tells what's the total size of the directory in kilobyte sized blocks.   

  ### Column Breakdown: ( From left to right )   
  <b>  - Permissions</b>: The first character shows the file type (- for file, d for directory, l for link)   
  The next 9 characters show read (r), write (w), and execute (x) permissions for the owner, group, and others   
  <b>  - Links</b>: The number of hard links to the file or directory   
  <b>  - Owner</b>: The username of the person who owns the file   
  <b>  - Group</b>: The name of the group that owns the file   
  <b>  - Size</b>: The size of the file in bytes
  <b>  - Timestamp</b>: The date and time the file was last modified
  <b>  - Name</b>: Name of the file / directory / link

  <img width="938" height="287" alt="image" src="https://github.com/user-attachments/assets/c6878eba-276c-4c60-891b-8935763840d0" />
  
  ## ${\color{lightgreen}\mathtt{ls \space --color}}$
  The <b>--color</b> switch will list elements with different colors   
  <b>Note:</b> This is a built-in ( aliased ) functionality in most modern distros. See: "alias" command!   
  In the below sample, there are following colors:

  - blue: folder
  - cyan ( light blue ): symbolic link
  - white: file   
  &nbsp; <img width="1385" height="52" alt="image" src="https://github.com/user-attachments/assets/7d66c9c4-e7c8-4d98-afcd-b57303e27041" />


  ## ${\color{lightgreen}\mathtt{ls \space -h}}$
  The <b>-h</b> switch will print file sizes in a human readable format   
  
  
</details>


<details>
  <summary>pwd - Print Working Directory</summary>
  &nbsp;   

</details>


<details>
  <summary>cd - Change Directory</summary>
  &nbsp;   

</details>


<details>
  <summary>mkdir - Make Directory</summary>
  &nbsp;   

</details>


<details>
  <summary>mv - Move / Rename Files & Directories</summary>
  &nbsp;   

</details>


<details>
  <summary>cp - Copy Files & Directories</summary>
  &nbsp;   

</details>


<details>
  <summary>rm - Remove Files & Directories</summary>
  &nbsp;   

</details>
  
&nbsp; &nbsp; &nbsp; 
</details>


<details>
  <summary>📝 Search & Edit Files</summary>
  &nbsp;   


<details>
  <summary>vi / vim - File Editor</summary>
  &nbsp;   

</details>


<details>
  <summary>nano - File Editor</summary>
  &nbsp;   

</details>


<details>
  <summary>find - Search Files</summary>
  &nbsp;   

</details>


<details>
  <summary>grep - Search & Filter Files</summary>
  &nbsp;   

</details>

</details>

<details>
  <summary>⚙️ Network Specific Commands</summary>
  &nbsp;   

</details>



</details>
