# Python + Pytest Selenium Framework :snake: :computer:
This repository contains a lightweight Python and Pytest-based Selenium framework for automated web testing of the Google search page. The framework utilizes Selenium WebDriver to interact with web pages and Pytest for test organization and execution as well as for some basic setup to be able to run scripts on multiple browsers. With this framework, you can easily write and run automated tests on CLI or IDEs.  

## Prerequisites
Before using this framework, ensure you have the following prerequisites installed:

Python 3.x: Make sure you have Python 3.x installed on your system.Phyton 3.11.0 was used in this case.
Pip: Ensure you have the latest version of pip installed to manage Python packages. Version 23.2.1 was used in this case.
Chrome/Firefox Browser: Make sure you have either Google Chrome or Mozilla Firefox installed on your system. This comes with a caveat. For Chrome broswer versions ≥ 115.0.XX Chromedriver 114.0.57XX versions are the latest possible supported versions for version 115.0.XX got delayed but the Google team. Chomedriver was configure as default runner for the framework. 

## Setup :computer:
Clone the repository to your local machine:

bash
> git clone https://github.com/KanuHuz/https---github.com-KanuHuz-google_Test.git
> 
> cd your preferred repo otherwise mkdir (new name for folder).
> Install the required dependencies using pip:
> 
>pip install -r requirements.txt
> 
Download the appropriate WebDriver executable (chromedriver or geckodriver) and add it to your system's PATH. (Explained above)

## Running Tests
To execute all the tests in a given directory, simply run the following command from the root of the repository/target folder:
> py.test + name of test case

If you want to run all test on current directory, verbose with logs:

> py.test -v -s
For creating an html report while running test use:

> py.test --html=report.html   -----(a VSCode extension like liveserver is encouraged)

Pytest will automatically discover and run the test files located in the tests directory.

## Improvements & Limitations :children_crossing:
Feel free to extend the framework to suit your specific needs. You can add utility functions, custom fixtures, or implement page object pattern to enhance test maintainability. For the sake of the task and for time and system constraints, some interesting elements were left out for further discussion:
* POM implementation, fetching locators from www.google.com into a base class for posterior reusability and scalability.
* Custom utilities functions like an autocomplete function for using different search terms on the search box.
* Decorators/fixtures
* BDD ??
* A single comprehensive E2E flow comprising all the interactions. (Avoided due to excercise constraints and Atomic design principle)
* Due to task design and involved systems architecture, it was very challenging to get the suggestions the tasks mentioned (teting to Testing) on the browser. This is due to Google fetching and showing different results on screen based on the active session profile. Google constantly targets random accounts with experimental live variations to the Search and Image Search interfaces results. Sometimes the differences are barely noticeable. Other variations are much more obvious so this is a hit or miss. 
* While I was able to manually get 'Testing' as a suggestion when I input 'teting' on search box while logged into my Google user, Selenium was unable to get the same result while on execution on both Chrome and Firefox. A possible workaround would of been adding an extra step to login with credentials and then expect to see the same recommended search suggestions terms. This would add an unnecesary layer of complexity. 
* Due to this limitation, I was only able to test script execution up to a certain point in execution flow and thus were unable to check if posterior code was working as expected. Beside this fact, I added some comments on code itself to serve as a guiding principle for stakeholders and to showcase the logic behind the code blocks. 

## Contributing
If you find any issues or want to add new features, contributions are welcome! Please fork this repository, create a new branch, make your changes, and submit a pull request.

## License
:mage_man: This was coded by Kanu H. :mage_man:
