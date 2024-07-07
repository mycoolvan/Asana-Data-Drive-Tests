# Asana-Data-Drive-Tests


## Challenges and Solutions
The first obstacle, was to make a slight change to the skeleton because Playwright would not allow me to have test of the same name. So I used the ID and name from test cases to distinguish them and added it to test parameter in the for each loop.

The second obstacle was selecting the first project on in the test on the left nav “Cross-functional project plan, Project”. I wanted to originally keep it close to Playwrights documentation recommendations and avoid using locators. However, I noticed trying that the Playwright automation reads the label as only “Cross-functional project plan”. I opted to use getByText, but I felt that could be an issue if that project name was anywhere else on the page. So I used getByLabel with “Projects” to anchor it specifically to the project section on the left navigation bar.

The third obstacle that I faced was ultimately having to use xpath to signify the relation between the column header and column items. I was unable to think  of a clean way to do it under Playwrights recommendations. So I just went with the fact that the column header and column items are sibling xpaths.


## Recommendations 
As for recommendations, there’s some to consider. I just inserted mostly in the skeleton and didn’t add any classes or refactored. If we were to automate more or go further, I would definitely go about the page component object model or similar to reuse and have cleaner code. Breaking the page down into parts so if anything were to change down the line we'll know where to change as well.

Although it was mentioned that it would be okay to upload the user senstive data, I would look into better practices to hide that data from being uploaded as well. Setting up environmental variables for local environments or hashing before git commits and unhasing after git pull.

I would also try to increase the speed of the test by removing the login step and putting it in a before all test function, and also adding a before each test function to go back to the main page. This would increase the test speed while also still testing the features that the test cases. Or we can even go about a multithreaded route to save even more time in addition for independent tests.
