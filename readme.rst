Plickers Import
###############

Plickers is a website designed for obtaining feedback from pupils in a classroom environment. The basic process is as follows

1. The teacher sets up multiple choice questions (typically with 4 answers) on the Plickers website to gauge whether or not pupils understand a certain concept.
2. The teacher sets up a mobile device with the plickers app.
3. Pupils are all given an individual QR code like thing in the shape of a square  which they can hold up in any one of four orientations to answer the question presented to them on a classroom projector.
4. The teacher then scans the room with the camera on the mobile device. The app recognises in which orientation each pupil is holding their QR code like thing and stores the data.
5. The teacher can then use this information to plan their next teaching steps. For example they could chose to change the seating in the next lesson to put pupils who understand together with those that don't.

One of the main drawbacks that this website has is that it can't import questions from an outside source or export questions to an outside source. This makes it nigh on impossible for teams of teachers to share questions. To help with this I have written a Python script that can read questions from a CSV file and simulate the necessary mouse clicks to import them into the website. This allows teachers to collaborate by sharing their CSV files and importing each other's into their own Plickers accounts. To run the script you will need to follow these steps. The steps are written for a Ubuntu style operating system. If you are running Windows first follow the extra steps below and then return to this poiint.

1. Download the repository from my GitHub page `here <https://github.com/jpowcode/plickers_import>`__. For windows users use the directory C:\\cycwin64\\home\\"user_name"\\plickers_import

2. Setup a virtual environment for Python, activate it and install dependencies

.. code-block:: bash
  virtualenv plickers_import
  cd plickers_import
  source bin/activate
  pip install selenium

3. Put your Plickers username and password into the first two lines of the file login-details.txt Please make sure your password is not the same as for any other websites you use as it will be stored here in plain text which is not very secure.

4. Write you questions into the CSV file in the example format given in the downloaded file.

   * Column A is the text for the question.
   * Column B should be an M for a multiple choice question and T for a True/False question
   * Column C contains the correct answer A, B, C or D for multiple choice or T or F for a True/False question
   * Columns D, E, F and G contain the answers for the questions

5. Run the script

.. code-block:: bash
  python plickers_import.p

**Extra steps for windows users**

1. Dowload and install `Cygwin <https://www.cygwin.com/>`__ During the install
proceedure make sure to click on the word 'Default' next to Python. 

2. Download and install `Firefox <https://www.mozilla.org/en-US/firefox/new>`__.

3. Download `Gecko Drivers <https://github.com/mozilla/geckodriver/releases>`__ , unzip the file and put it in C:\\cycwin64\\home\\"user_name"\\plickers_import\\Scripts

4. Start Cygwin and run these commands

.. code-block:: bash
  easy_install pip
  easy_install virtualenv

5. Now follow the steps above
