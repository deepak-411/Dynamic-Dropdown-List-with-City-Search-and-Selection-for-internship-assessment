# Dynamic-Dropdown-List-with-City-Search-and-Selection-for-internship-assessment

# This project is a dynamic dropdown menu that allows users to select a country, state, and city. The dropdown options are populated using JSON data.

1. Setting up the React app:
            The project is created using Create React App, which provides a pre-configured development environment for                 projects.
   
            The initial setup creates a basic file structure with the main component in App.js and the entry point in                  index.js.

3. JSON data:
           The provided JSON data is stored in a separate file called data.json.
   
           The JSON data represents a list of countries, each with an ID, name, and a list of states.
   
           Each state has an ID, name, and a list of cities.

5. App component:
               The main component, App.js, is a functional component that uses React hooks to manage the state of the                     selected country, state, and cities.
   
               The component renders a form with three dropdown menus: Country, State, and Cities.
   
               The selected values are stored in state variables using the useState hook.
   
               Event handlers are defined to update the selected values when the dropdown options are changed.

7. Dropdown menus:
                The Country dropdown menu is populated using the jsonData array. Each item in the array represents a                       country, and the country name is used as the option value.
   
                When a country is selected, the State dropdown menu is dynamically populated based on the selected                        country. The getStatesByCountry function filters the JSON data to find the matching country and returns                   an array of state names.
   
                When a state is selected, the Cities dropdown menu is dynamically populated based on the selected state.                  The getCitiesByState function filters the JSON data to find the matching country and state, and returns                   an array of city names.
   
                The Cities dropdown menu allows multiple selections, and the selected city names are stored in an array.

9. Submitting the form:
                     When the form is submitted, the handleSubmit function is called.
   
                     The selected country, state, and cities are logged to the console for demonstration purposes. You                         can modify this function to perform other actions with the selected data.

10. Rendering the app:
                   The ReactDOM.render function is called in index.js to render the App component in the root                                element of the HTML document.

11. Running the project:
                     The project can be run locally by executing npm start in the terminal.
   
                     This starts the development server and opens the app in a web browser.
   
                     Any changes made to the code will automatically trigger a hot-reload, allowing you to see the                             changes in real-time.

This project demonstrates how to create a dynamic dropdown menu in React using JSON data. It showcases how to populate dropdown options based on user selections and handle form submissions. You can further customize and extend this project to meet your specific requirements
