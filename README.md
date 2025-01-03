<p align="center">
<img src="https://i.imgur.com/R1SaANh.png" alt="Microsoft Active Directory Logo"/>
</p>
 <h3 align="center;">Video demonstration</h3>
<p>
  https://www.youtube.com/watch?v=K_8dZYvLNmo
</p>

<h1>Automated Backup Script(Windows VM)</h1>
This tutorial outlines how to create and autumate powershell scripts
<br />
<br />
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
<h2>languages used</h2>
<li>Powershell</li> 
<h2>Operating Systems Used </h2>

- Windows 10
  <h2>Creating and Automating Steps</h2>
  <lu></lu>
<li> Prepare vm(windows 10)</li>
<li> Creating folders</li>
<li> Creating script</li>
<li>  Using task scheduler</li>
<li> General,Trigger,Action,Condition,Setting Tab</li>
<li> Test task</li>
 <li> Monitor task</li>
  </lu>
  <br />
  <br />
  <h3 align="center;">Prepare Enviroment using Windows10 VM.</h3>

<p>
  <img src="https://i.imgur.com/jiyaWQA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
 <h3 align="center;">Enter the VM via RDC and create 2 folders.</h3>
 <lu>
  <li>a folder or file you want to backup example: C:\Important Files</li>
   <li>destination folder example: D:\Backup</li>
 </lu>
<img src="https://i.imgur.com/WmVn9tJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/JBWQ6v9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/WPxRGQJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
 <h3 align="center;">Create a Folder named Scripts then Open NotePad and create the powershell script for windows,and click save as backup-script.ps1 inside scripts folder.(it has to have .ps1)</h3>
  <img src="https://i.imgur.com/4tFnj3l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <img src="https://i.imgur.com/wkg6EWf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
  <h3 align="center;">Before running cd command check manually navigate to directory in fire explorer if the path is correct.</h3>
   <h3 align="center;">if it is run the script in powershell as an administrator using(.\backup script.ps1)</h3>
   <img src="https://i.imgur.com/VeLUX5o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <br />
   <br />
   <h2 align="center;">Automating the powershell script using task scheduler.</h2>
   <h3 align="center;">Open task bar and type task scheduler and open it.</h3>
   <img src="https://i.imgur.com/XTxSOnh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/3ATdO13.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <br />
   <h3 align="center;">Create Folder.</h3>
   <img src="https://i.imgur.com/Jz81DYr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
  <br />
  <h2 align="center;">Create a new task</h2>
  <h3 align="center;">1.General</h3>
  <lu>
    <li>Enter name for the Task</li>
    <li>Description (optional)add a description Daily Backup of Important Files.</li>
    <li>Run with the highest privileges: check this box</li>
</lu>
<img src="https://i.imgur.com/tsw8uZx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br />
<h3 align="center;">2.Triggers Tab:</h3>
<lu>
  <li>Click on new to create a new trigger.</li>
  <li>begin the task: select on a schedule</li>
  <li>daily,weekly or monthly</li>
  <li>Click ok to save trigger.</li>
</lu>
<img src="https://i.imgur.com/HtyrPy8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h3 align="center;">3.Action Tab</h3>
<lu>
  <li>Click new to create new action </li>
  <li>Action: select <mark>start a program</mark></li>
  <li>Program/script: Enter powershell.exe.</li>
  <li>Add argument(optional):Enter:<mark>-File "c:\scripts\backup-script.ps1</mark></li>
  <li>Click ok</li>
</lu>
<img src="https://i.imgur.com/JSSXicL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h3 align="center;">Condition Tab</h3>
<lu>
  <li>Uncheck the option start the task only if computer is on AC power(if you are in a laptop and want to run it in battery power.</li>
</lu>
<img src="https://i.imgur.com/4Tw9vvw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h3 align="center;">Settings Tab</h3>
  <lu>
    <li>CheckAllow task to be run on demand.</li>
    <li>check if the task fails,restart every 3 to 5 and configure retries as needed.</li>
    <li>Click OK to create task</li>
    </lu>
    <img src="https://i.imgur.com/JEytUCD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
    <br />
    <br />
    <h2 align="center;">Test the Task</h2>
    <h3 align="center;">In task scheduler find your task,right-click and select run and verify that it worked</h3>
  <lu>
    <li>Check the D:\backup directory</li>
    <li>Review log file(log.txt)in the backup file</li>
  </lu>
  <img src="https://i.imgur.com/81DDauf.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/N2YL48a.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
    <h2 align="center;">Monitor Task</h2>
    <h3 align="center;">To check task history: Right-click the task and select Properties,under the history tab,verify the task execution status.</h3>
    <img src="https://i.imgur.com/qXhBrMz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <h3 align="center;">Thanks you for taking the time to learn how to autmate scripts in powershell with mi project.This demonstrates not only mi technical skills
  in scripting and task automation but also my ability to create practical and reliable solutions in common IT challenges.</h3>
   
   

   
