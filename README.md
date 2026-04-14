# pytimecard
This Python package records employee clock-in and clock-out times and stores them locally on a PC for future analysis.
## Where to get it

<pre lang=sh>py -m pip install --index-url https://test.pypi.org/simple/ pytimecard</pre>

## Dependencies
<ul><li>cv2 # pip install opencv-python # for taking pictures via local webcam</li>
  <li>PIL # pip install Pillow # for displaying the pictures</li>
  <li>keyring # pip install keyring # for the adminstrator's password</li>
  <li>openpyxl # pip install openpyxl # for Microsoft Excel sheet generation</li>
</ul>

## Features
<ul>
  <li>A complete package for recording timestamps locally for an unlimited number of employees.</li>
  <li>The employer can configure all necessary program parameters.</li>
  <li>Timestamps are organized on a weekly basis, with new weekly data automatically initialized every Sunday. At that time, all images captured during the previous week are transferred to a designated folder (details provided later).</li>
  <li>During operation, only the employer—protected by a password—can exit the program.</li>
</ul>

## If you are new to Python ...
<ul>
  <li>Install Python on Your PC</li>
  <ol>
    <li>Visit http://www.python.org</li>
    <li>Go to the Downloads tab</li>
    <li>Click the gray button labeled “Download Python 3.14.4” (or the latest available version). The installer will begin downloading.</li>
    <li>Once the download is complete, run the installer file.</li>
    <li>Check the option “Add Python to PATH.”</li>
    <li>Select "Install Now".</li>
  </ol>
  <li>When the installation finishes, you should see the message “Setup was successful.”</li>
<li>You’re halfway there! Next, you’ll need to install some third-party libraries, including the package you’ll be using.</li>
<ol>
<li>Right-click the Start button and select Windows Terminal (or Windows Terminal (Admin)).</li>
<li>In the terminal window, type pip list and press Enter. You should see a list of installed packages. If not, consider reaching out for help. My email address is smlee@inha.ac.kr.</li>
<li>At the next prompt, type pip install opencv-python and press Enter. Wait until the installation completes successfully.</li>
<li>Then type pip install Pillow and press Enter, and wait for it to finish.</li>
<li>Next, type pip install keyring and press Enter, and wait for completion.</li>
  <li>Lastly, type py -m pip install --index-url https://test.pypi.org/simple/ pytimecard and press Enter, and wait for completion.</li>
<li>Finally, type pip list again to confirm that the new libraries are installed.</li>
</ol>
<li>You’re now all set to go!</li>
  
  <li>Open the Start menu, find “IDLE (Python 3.14 64-bit)” among your installed applications, and launch it.</li>
</ul>

## How to use
<ul>

<li>The package consists of 2 parts; the first part is for adminstrator to setup the environment and the second part is for employees to clock-in and clock-out.</li>
<li>Below is the first part.</li>
<li>Make a folder in your PC, save the file with the python code below in the folder. You can name the file anything. Run it to see the graphical user interface, as shown below:</li>

```python

import pytimecard
a = pytimecard.Admin()
a.hw.mainloop()

```

<img width="662" height="851" alt="image" src="https://github.com/user-attachments/assets/fd380481-30dc-4278-9add-f80a40f40c6a" />

<li>The image above shows the first of the two programs—the setup application. This program allows the employer to configure the main time-recording system so it operates correctly.</li>

<li>The graphical interface is divided into two columns. The left column displays timestamp data organized by week. The data currently shown is simulated, which is different from yours, but it can later be replaced with real records. By selecting a week and clicking the “Weekly Performance” button in the right column, a Microsoft Excel sheet for the weekly performance is generated and opened if you have a Microsoft Excel, like below:</li>
<img width="719" height="852" alt="image" src="https://github.com/user-attachments/assets/c70b8e1a-16a8-4591-b219-12254a8ef96a" />


<li>A list of employees is provided in the white combobox. Select an employee from the dropdown menu, select a week, and click the “User Performance” button to view all timestamps associated with that individual over the week selected in an Excel sheet as shown below:</li>
<img width="683" height="975" alt="image" src="https://github.com/user-attachments/assets/9663a816-dd1e-4f61-8a94-53f96e87a4e1" />



<li>The available controls provide the following functionality:</li>
<ol>
<li>“Add User”: Add employees one at a time.</li>
<li>“Remove User”: Remove employees one at a time.</li>
<li>“Change Admin Password”: Set or update the administrator password. This password prevents unauthorized users from closing the main timestamp-recording program.</li>
<li>“Change Pickle File”: Specify the full path to the pickle file, which stores all timestamp data.</li>
<li>“Change Folder #1”: Set the folder where images captured with timestamps are temporarily stored.</li>
<li>“Change Folder #2”: Set the folder where images are permanently stored.</li>
<li>“Change Company Name”: Define the company name displayed throughout the application. For example, try setting it to “Company Name” to see how it appears.</li>
<li>“Change Pay Period Reference”: Set the reference date for pay periods. Adjusting this value will change how pay periods are calculated and displayed.</li>
<li>“Save Pickle”: Save all current data to the pickle file specified under “Change Pickle File.”</li>
</ol>

<li>The checkbox highlighted in red can be toggled as desired. For testing with simulated data, it is recommended to keep it checked; for real-world use, it may be left unchecked.</li>

<li>A new revised python code:</li>

```python

import pytimecard
a = pytimecard.Admin(pikl = r"D:\xyz\abc.pickle")
a.hw.mainloop()

```

<li>This code differs slightly from the previous one. When the pikl argument is provided to Admin(), it specifies the full path to the pickle file where all configuration data and timestamps are stored.</li>

<li>Feel free to experiment with different configurations until you find the setup that best suits your needs.</li>
</ul>

<br><br>

<ul>
<li>The second python program, main recording timestamps, can be called by a python code below:</li>

```python

import pytimecard
a = pytimecard.PunchCards(pikl = r"D:\xyz\abc.pickle")
a.hw.mainloop()

```

<li>And the snapshot of the program is shown below:</li>


<img width="642" height="932" alt="image" src="https://github.com/user-attachments/assets/15a45f2c-687a-49d6-94e4-e749f902925e" />

<li>The program refreshes every second.</li>
<li>Employees select their name from the combobox list and click one of the two available buttons: “IN” or “OUT.”</li>
<li>As shown in the program, each employee is allowed a maximum of six clock-in/out actions per day. Each button click triggers the capture of the employee’s photo.</li>
<li>All timestamps are recorded and saved to a file, and the corresponding photos are stored in a designated folder.</li>
<li>Clock-in actions must occur before clock-out actions; otherwise, the system will not respond.</li>
</ul>

## For any issues
Please send your emails about the issues to me (smlee@inha.ac.kr).
## Changes
Nothing yet.


<br>
