# [Recipe Database](https://joans-recipe-database.herokuapp.com/)

This is a recipe database that users can search using a range of search terms. They can also add and edit recipes.


## Database Schema

Please [click here](https://github.com/joanms/recipe-database/blob/master/static/plans/recipe-database_schema.pdf) to see the database schema.

The database is set up to make it as easy as possible for users to add and edit their own recipes, with minimal limitations on the type of data 
that they can input. I considered separate values for the quantities and names of ingredients so that users would input them consistently, but 
decided against this for three reasons. Firstly, it would be very tedious for a user who wanted to copy and paste a list of ingredients from 
elsewhere. Secondly, I might not think of all possible units a user might want to input. Thirdly, it wouldn't allow for subsets of ingredients, 
such as those for sauces, marinades, icing, etc. 

 
## UX

### User Stories

As a user, I want to:
- **Add my own recipes.**
The site has a recipe input form which is intuitive and easy to use. Users can type recipes into it, or copy and paste them from elsewhere. 
The database is structured to allow users maximum flexibility and ease of use when inputting and updating recipes, as outlined in the database 
schema explanation above. The HTML templates are set up to format the recipes neatly once they are input.

- **Edit and delete recipes.**
Each recipe page has an edit and delete button. When the delete button is clicked, a warning displays. This prevents users from deleting recipes 
accidentally.

- **Search for recipes according to a wide range of criteria.**
There is a search field in the navbar enabling users to search for recipes by keyword. The home page has links to lists of recipes in each category 
(bread, starters, mains, sides, sauces and desserts) and to vegetarian, vegan and gluten-free recipes. The home page also has a dropdown menu that 
enables users to search for recipes with common allergens excluded.

- **Edit and delete recipes.**
Each recipe page has buttons that users can click if they wish to edit or delete recipes. When the delete button is clicked, a warning appears telling 
the user that this action is permanent. The button to cancel deletion appears above the button to confirm it. This reduces the risk of accidentally 
deleting recipes.


### Design

Please [click here](static/plans/recipe_database_wireframes.pdf) to view the wireframes. 

I kept the layout as simple as possible to make it easy for users to find their way around the site. None of the pages are too cluttered - they 
have all the information that the user needs and no more. The buttons that users need to click to perform various actions are easy to find.

The colour scheme of orange-red and yellow with green accents is intended to be warm and appetising. The background image was selected to 
harmonise with this colour scheme. The heading font is calligraphy style to give the site a classic, graceful look and the body text font is a 
simple sans-serif to maximise legibility and elegance.


## Features

### Existing Features
- Search field in the navbar to search for recipes by keyword.
- Links to all recipe categories and to vegetarian, vegan and gluten-free recipes on the home page.
- Dropdown menu on the home page to search for recipes with common allergens excluded.
- Recipe input form in add_recipe.html enables users to add their own recipes to the database and display them on the site.
- Page listing summary details of either all recipes in the database, or recipes returned from a user's search.
- Page for each recipe displaying its ingredients, method and information such as suitability for restricted diets.
- Edit button on the recipe display page, linking to a form that enables users to edit the recipe.
- Delete button for deleting recipes.
- A warning that displays when the delete button is clicked, in case the user clicks it accidentally.

### Features Left to Implement
- Login feature that only allows users to input recipes when logged in, and prevents them from editing or deleting other users' recipes.


## Technologies Used

- **[MongoDB](https://www.mongodb.com/)** was used as the database program.
- **[mLab](https://mlab.com/home)** was used to set up the database.
- **[Pencil](https://pencil.evolus.vn/)** was used to create the wireframes.
- **[HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)** was used to set up the templates for the site.
- **[CSS3](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS3)** was used to style the site content.
- **[Materialize](https://materializecss.com//)** was used as the basis for the site's design and responsiveness.
- **[JavaScript](https://www.javascript.com/)** was used to initialise some of the Materialize elements and ensure that they worked correctly.
- **[Python](https://www.python.org/)** was used to write the app's logic.
- **[Flask](http://flask.pocoo.org/)** was used to create routes and render the HTML templates.
- **[unittest](https://docs.python.org/2/library/unittest.html)** was used for automated testing of the Python code.
- **[Heroku](https://www.heroku.com/)** was used to deploy the project.


## Testing

### Code Validity

I used the [W3C Markup Validation Service](https://validator.w3.org/) to check the HTML and the [W3C CSS Validation Service](https://jigsaw.w3.org/css-validator/) to check the CSS. 
The W3C Markup Validation Service gives error messages for Flask Jinja code in the HTML files. I disregarded those error messages and checked the code visually.

### Automated Tests

I conducted automated testing of the app routes with unittests, and the tests are in test.py at the root directory. Run the tests by typing "python3 test.py" in the terminal. 

### Manual Tests

I conducted manual tests of the application as follows:

1. Cross-browser and Device Compatibility
    1. Test the app on Chrome, Edge, Firefox and Opera browsers to ensure that it works on all of them.
    2. Test the app on a desktop, laptop, tablet and smartphone to ensure that it works on all devices.

2. Responsiveness
    1. View the app in responsive mode with Chrome Developer Tools to ensure that the size and position of elements adjusts correctly.
    2. View the app on a desktop, laptop, tablet and smartphone to ensure that it displays correctly.

3. Adding Recipes
    1. Click on the "Add a Recipe" link in the navbar.
    2. Ensure that the form appears correctly.
    3. Attempt to submit the form with required fields blank and ensure that I'm prompted to fill them.
    4. Submit a fully completed form.
    5. Click on the link to the new recipe in the list of recipes that appears.
    6. Ensure that the page showing that recipe loads correctly, with all entered details appearing.
    7. Ensure that all the recipe details have been saved in the database.

4. Searching for Recipes
    1. Enter various search terms in the search bar.
    2. Ensure that all recipes with those words, and only recipes with those words, are displayed in the results.
    3. Click on each image on the home page.
    4. Ensure that all recipes in that category, and only recipes in that category, are displayed in the results.
    5. Select allergens in the allergen dropdown menu on the home page and click on Search.
    6. Ensure that all recipes without those allergens, and only recipes without those allergens, are displayed in the results.
 
5. Viewing Recipes
    1. Click on the 'View All Recipes' link in the navbar.
    2. Ensure that all recipes in the database are listed on the page that loads.
    3. Click on each recipe in the list in turn
    4. Ensure that all the recipe details are displayed correctly on the page that loads.

6. Editing Recipes
    1. Click on the Edit button at the bottom of a page displaying a recipe.
    2. Ensure that the form for editing the recipe loads.
    3. Edit the recipe details.
    4. Click the Submit button.
    5. Ensure that the recipe reloads and the edits have been saved to the database.
    6. Click on the Edit button at the bottom of a page displaying a recipe.
    7. Ensure that the form for editing the recipe loads.
    8. Edit the recipe details.
    8. Click the Cancel button.
    9. Ensure that the recipe reloads with none of the cancelled changes saved to the database.
    10. Repeat for all recipes.

7. Deleting Recipes
    1. Click the Delete button at the bottom of the recipe display page.
    2. Ensure that a warning message appears, along with buttons to cancel or confirm the deletion.
    3. Click Cancel.
    4. Ensure that the page reloads correctly.
    5. Click the Delete button again.
    5. Click Confirm.
    6. Ensure that the recipe is deleted from the database.
    7. Repeat for all recipes.


## Deployment

I deployed the project on Heroku as follows:
1. Create a new app on Heroku and name it joans-riddle-game.
2. Create a Heroku remote.
3. Ensure that the project included a Procfile and requirements.txt.
4. Push the project to the Heroku remote.
6. Start a web process by typing heroku ps:scale web=1 in the Cloud9 terminal.
5. Set the IP to 0.0.0.0 and the PORT to 5000 in the app settings on Heroku.
7. Restart all dynos.
8. Open the app on Heroku and check to ensure that it's working correctly.

### Running the Code Locally
1. Clone the GitHub Repo and run it in your code editor.
2. Set the IP address to 127.0.0.1 and the PORT to 5000.
3. Install the packages in requirements.txt by typing pip install -r requirements.txt in the command line.


## Credits

### Content and Media

- The recipes and their illustrations are from [BBC Good Food](https://www.bbcgoodfood.com/recipes).
- The logo and background image are free stock images from [Pixabay](https://pixabay.com/).

### Acknowledgements

- I received inspiration for this project from [BBC Good Food](https://www.bbcgoodfood.com/recipes).
- My mentor, Chris Zielinski and my tutors Niel McEwen, Nakita McCool and Haley Schafer provided 
valuable help and advice on the project.
