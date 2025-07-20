Web Testing with Robot Framework + SeleniumLibrary
This is a very simple project that shows how to use Robot Framework with SeleniumLibrary to test websites. It also helps you understand how Robot Framework works, how to run tests, and how the logs and reports look after.

How to Get This Project
You can get this project by downloading it here or cloning it using Git. When you do that, you will get a folder called WebDemo, and inside it there are two folders: demoapp and login_tests.

You can also just check out the test cases and results online if you don’t want to run anything yourself.

About the Demo App
The demo app is a basic login page. If you enter the username demo and password mode, you get a welcome page. If you use anything else, you get an error. You need to run this app before running the tests. You can see how to start it in the section below.

Test Files
All the tests are inside the login_tests folder. Here's what each file does:

valid_login.robot: One test to check if login works with the correct info.

invalid_login.robot: Tests wrong login info. It tries different cases using the same test keyword. It also shows how to set things up before and clean up after tests.

gherkin_login.robot: Same idea as the valid login test, but uses Gherkin style (Given/When/Then).

resource.robot: A file with extra stuff used by the other tests. It has keywords and variables to make writing tests easier.

Test Results
When you run the tests, you get a report and log in HTML. If you don’t want to run them, you can still check them online:

report.html

log.html

How to Run the Demo
What You Need First
You need to install Robot Framework and SeleniumLibrary. They also need Python. The easiest way to install everything is using pip. Just run this in your terminal:

nginx
Copiar
Editar
pip install -r requirements.txt
Start the Demo App
Before running tests, start the app inside the demoapp folder. You can do it in two ways:

Double-click the file server.py

Or run it in the terminal like this:

bash
Copiar
Editar
python demoapp/server.py
The app will open on http://localhost:7272 — you can test it manually too (login is demo/mode). Keep it open while running the tests.

To stop it:

If you double-clicked: just close the window.

If using terminal: press Ctrl + C.

Running the Tests
Go to the project folder and run this:

nginx
Copiar
Editar
robot login_tests
Or run a specific test file like this:

bash
Copiar
Editar
robot login_tests/valid_login.robot
Or choose one test and add options:

css
Copiar
Editar
robot --test InvalidUserName --loglevel DEBUG login_tests
Use robot --help to see more options.

Changing the Browser
The default browser is Firefox. But you can change it like this:

lua
Copiar
Editar
robot --variable BROWSER:Chrome login_tests
robot --variable BROWSER:IE login_tests
You can check SeleniumLibrary docs to see which browsers are supported.
