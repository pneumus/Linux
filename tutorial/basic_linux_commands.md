# Basic Linux Commands

This page is intended to describe and explain <b>Basic Linux Commands</b>   
and their <b>switches (flags)</b>, and <b>parameters (options)</b>   

<details>
  <summary>📁 File & Directory Management</summary>
  &nbsp; &nbsp; &nbsp;      

<details>
  <summary>ls - List Contents of a Directory</summary>
  &nbsp;   

  <details>
  <summary>${\color{lightgreen}\mathtt{ls \space\space -a}}$ </summary>
  
  The <b>-a</b> switch stands for <b>ALL</b> Entries ( including the hidden ones )   
  <b>Note:</b> Hidden Entries have a dot ( . ) as a Starting Character

  ```   
  [mateo@archipelago ~]$ ls -a
.   .bash_history  .bash_profile  .cache   Desktop    Downloads   .icons  .mozilla  Pictures  Templates  Videos
..  .bash_logout   .bashrc        .config  Documents  .gtkrc-2.0  .local  Music     Public    .var       yay
  ```   
    
  </details>
  
  <details>
    <summary>${\color{lightgreen}\mathtt{ls \space\space -l}}$</summary>
  
  The <b>-l</b> switch stands for <b>LONG</b> Listing with all Attributes.   
  <b>Note:</b> There are multiple columns listed here with different purpose.     

  &nbsp; <img width="943" height="328" alt="image" src="https://github.com/user-attachments/assets/1630db75-a250-4851-8ca9-64278f3cd306" />

  The entry at the top "total 654910" tells what's the total size of the directory in kilobyte sized blocks. 

  ### Column Breakdown: ( From left to right )   
  <b>  - Permissions</b>:   
  &ensp;&ensp;The first character shows the file type (<b>-</b> for file, <b>d</b> for directory, <b>l</b> for link)   
  &ensp;&ensp;The next 9 characters show read (r), write (w), and execute (x) permissions for the owner, group, and others   
  <b>  - Links</b>: The number of hard links to the file or directory   
  <b>  - Owner</b>: The username of the person who owns the file   
  <b>  - Group</b>: The name of the group that owns the file   
  <b>  - Size</b>: The size of the file in bytes   
  <b>  - Timestamp</b>: The date and time the file was last modified   
  <b>  - Name</b>: Name of the file / directory / link   
  
  </details>
  

  <details>
    <summary>${\color{lightgreen}\mathtt{ls \space\space\space --color}}$</summary>

    
  The <b>--color</b> switch will list elements with different colors   
  <b>Note:</b> This is a built-in ( aliased ) functionality in most modern distros. See: "alias" command!   
  In the below sample, there are following colors:

  - blue: folder
  - cyan ( light blue ): symbolic link
  - white: file   
  &nbsp; <img width="1385" height="52" alt="image" src="https://github.com/user-attachments/assets/7d66c9c4-e7c8-4d98-afcd-b57303e27041" />
  
    
  </details>
  
  
  <details>
    <summary>${\color{lightgreen}\mathtt{ls \space\space -h}}$</summary>

  The <b>-h</b> switch will print file sizes in a <b>HUMAN</b> readable format   
  <b>Note</b>: The <b>-h</b> switch needs to be combined with the <b>-l</b> switch to show <b>file sizes</b>   
  The order of switches do not matter, thus <b>ls -lh</b> and <b>ls -hl</b> will have the same effect.   

  &nbsp; <img width="879" height="331" alt="image" src="https://github.com/user-attachments/assets/9b403500-9229-4c0d-8461-8d017666afe9" />

  <b>Note</b>: Compare the file size column with the column in the output of <b>ls -l</b>   
  Instead of bytes, file sizes are displayed in K (kilobytes) or M (megabytes)

  <details>
    <summary>${\color{lightgreen}\mathtt{ls \space\space\space --sort}}$</summary>

     The <b>--sort</b> Option will sort files by the desired need   
  <b>Note</b>: If the Option is not specified, the <b>ls</b> Command will list alphabetically, by default   
  Every Option has a corresponding Switch ( short version )

  | Option (Param) | Switch (Flag)  | Sorted By          | 
  | -------------  | -------------- | ------------------ | 
  | No Option      | No Switch      | Alphabetical       |
  | --sort=time    | -t             | Modification Time  |
  | --sort=ctime   | -c             | Change Time        |
  | --sort=atime   | -u             | Access Time        |
  | --sort=size    | -S             | File Size          |

<b>Note</b>: The Difference between <b>Modification Time (mtime)</b> and <b>Change Time (ctime)</b>   
is that <b>mtime</b> will update only when the actual content of the file is changed   
and <b>ctime</b> updates whenever the file's <b>inode</b> (metadata) changes   

  </details>

  
 
    
  </details>
  
  <details>
    <summary>${\color{lightgreen}\mathtt{ls \space\space -R}}$   </summary>

  
  The <b>-R</b> Switch will list Files recursively:   
  In other words, it steps into every Subdirectory of every Subdirectory (maximum depth)

  ### Example Folder Structure

  &nbsp; <img width="434" height="362" alt="image" src="https://github.com/user-attachments/assets/bc33349f-412b-4c5b-9e9c-410ee4f0586a" />

  If <b>ls -R</b> is executed in the <b>Project_Root</b> Folder:

  &nbsp; <img width="463" height="460" alt="image" src="https://github.com/user-attachments/assets/ca77919f-b4fb-47f4-b114-d8752f9b0a86" />

  ### Alternative Solution
  Alternatively, you can install the <b>tree</b> package to Pretty Print the <b>Folder Structure</b>   
  To install it execute the following Command:
  - Arch Linux:

        sudo pacman -S tree

  - Ubuntu Linux:

        sudo apt install tree

  - Fedora Linux:

        sudo dnf install tree

  &nbsp; <img width="457" height="349" alt="image" src="https://github.com/user-attachments/assets/e1d60a93-c66f-4f23-8319-47cb38977bd4" />

    
  </details>  

  
  
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
