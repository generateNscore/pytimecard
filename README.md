# pytimecard
This Python package records employee clock-in and clock-out times and stores them locally on a PC for future analysis.
## Where to get it

<pre lang=sh>py -m pip install --index-url https://test.pypi.org/simple/ pytimecard</pre>

## Dependencies
<ul><li>cv2 # pip install opencv-python # for taking pictures via local webcam</li>
  <li>PIL # pip install Pillow # for displaying the pictures</li>
  <li>keyring # pip install keyring # for the adminstrator's password</li>
</ul>

## Features
<ul><li>A complete package to record timestamps locally for unlimited number of employees.</li>
<li>Employer can setup the parameters needed for the python program.</li>
<li>All timestamps are organized on a weekly basis.</li>
  <li>On Sunday, a new week data is initialized and all the pictures taken during the previous week are moved to the pre-assigned folder (details will be explained later). </li>
  <li>During the execution of the program, only employer who knows the password can exit the program.</li>
</ul>

## How to use
<ul>

```python

import pytimecard
a = pytimecard.Admin()
a.hw.mainloop()

```

<img width="662" height="851" alt="image" src="https://github.com/user-attachments/assets/fd380481-30dc-4278-9add-f80a40f40c6a" />

<li>The captured image above displays the first program of the 2 programs; setting up program.</li>
<li>This program enables employer to setup another program to run properly.</li>
<li>This GUI program is divided into 2 columns; the left column displays the data of timestamps in unit of weeks.</li>
<li>Currently the data shown was generated virturally; but it could be the real one later.</li>
<li>Select one of the weeks shown and click the button "Weekly Performance" in the right column, then another window is popped up to display the whole timestamps of employees.</li>
<li>The list of employees can be found in the white combobox.</li>
<li>Click the combobox to select one employee and click the button "user Performance" to see all the timestamps he had over the entire weeks shown in the left column.</li>
<li>The button "Add User" enables employer to add users, one at a time.</li>
<li>The button "Remove User" enables employer to delete users, one at a time.</li>
<li>The button "change Admin password" enables employer to set or change his password. The password prevents any employee from closing another program to record timestamps.</li>
<li>The button "change pickle file" enables employer to setup the full path of the pickle file which is a python file that stores all timestamps.</li>
<li>The button "change folder#1" enables employer to setup the folder where the pictures taken with any timestamps are stored temporarily.</li>
<li>The button "change folder#2" enables employer to setup the folder where the pictures taken with any timestamps are stored permanently.</li>
<li>The button "change Company name" enables employer to setup the name of the company to display here and there. Try to change the company name as "Company Name", and see the resulting appearance.</li>
<li>The button "change PayPeriod reference" enables employer to setup the reference date for pay periods. Any employers might know the meaning of this. Try to change the date to a different value and see the resulting appearance.</li>
<li>The button "save pickle" save all information in the pickle file shwon in the button of "change pickle file". </li>
<li>The checkbutton in the red square is to be either chedcked or not checked as one wishes. For the virtual data, it would be better to check the checkbutton, and not for your own data later.</li>

```python

import pytimecard
a = pytimecard.Admin(pikl = r"D:\xyz\abc.pickle")
a.hw.mainloop()

```

<li>The python code above is slightly different from the previous one.</li>
<li>If the argument pikl is used when the module Admin() is called, the value for the argument pikl is the full path of the pickle file where all the information as well as all timestamps are stored.</li>
<li>Please try the example as many times as you want until one you like is decided.</li>
</ul>

<ul>

```python

import pytimecard
a = pytimecard.PunchCards(pikl = r"D:\xyz\abc.pickle")
a.hw.mainloop()

```



<img width="642" height="932" alt="image" src="https://github.com/user-attachments/assets/15a45f2c-687a-49d6-94e4-e749f902925e" />

</ul>
## Changes
<br>


```python

```

<br>
