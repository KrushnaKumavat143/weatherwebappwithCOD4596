# weatherwebappwithCOD4596



Weather Application Documentation

Introduction:
The Weather Application is a web-based tool designed to provide users with current weather information for a specified city. It fetches data from the OpenWeatherMap API and dynamically displays it on the user interface. The application features a simple and intuitive interface for ease of use.

Technologies Used:

HTML
CSS
JavaScript
Functionality:

HTML Structure:

The HTML structure defines the layout of the weather application interface.
It consists of elements such as headers, input boxes, and containers for displaying weather information.
CSS Styling:

The CSS file provides styling for various elements of the weather application.
It defines the layout, colors, fonts, and responsiveness of the user interface.
Key styling aspects include background images, font families, gradients, padding, and margins.
JavaScript Logic:

The JavaScript file contains the logic for fetching weather data from the OpenWeatherMap API and displaying it on the interface.
It handles user input, API requests, data processing, error handling, and dynamic content generation.
Weather Data Display:

Upon entering a city name and pressing Enter, the application fetches weather data from the API.
The weather data includes information such as temperature, weather condition, min/max temperature, humidity, pressure, and wind speed.
The fetched data is dynamically displayed on the interface, providing users with up-to-date weather information.
Error Handling:

The application handles various error scenarios, such as empty input or invalid city names.
Error messages are displayed using the SweetAlert library, providing a user-friendly notification system.
Background Image Update:

The background image of the application changes dynamically based on the current weather condition.
Different background images are associated with different weather conditions, enhancing the visual appeal of the interface.
Usage:

Open the Weather Application in a web browser.
Enter the name of a city in the input box.
Press Enter to fetch weather data for the specified city.
View the dynamically updated weather information displayed on the interface.
Conclusion:
The Weather Application provides a convenient way for users to access current weather information for any city. With its intuitive interface, error handling capabilities, and dynamic content generation, the application offers a seamless user experience.

HTML Structure:

<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Meta tags and title -->
  </head>
  <body>
    <!-- Main container for the application -->
    <div class="app-main">
      <!-- Header -->
      <div class="header">
        <h4>Get Weather</h4>
      </div>
      <!-- Search input box -->
      <div class="searchInputBox">
        <input type="text" name="" id="input-box" class="input-box" placeholder="enter city name" />
      </div>
      <!-- Container for weather information -->
      <div class="weather-body" id="weather-body">
        <!-- Weather information will be appended here -->
      </div>
    </div>
    <!-- Script tags for JavaScript files -->
  </body>
</html>

1.Defines the basic structure of the weather application interface.
2.Consists of a header, input box for city name, and container for displaying weather information.

CSS Styling:

/* Reset styles and global settings */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Body styles */
body {
  /* Background image and other properties */
}

/* Styles for app-main container */
.app-main {
  /* Dimensions, margins, background color, etc. */
}

/* Input box styles */
.input-box {
  /* Styles for input box */
}

/* Styles for weather-body container */
.weather-body {
  /* Styles for weather information container */
}

/* Additional styles for various elements */

1.Provides styling for different elements of the weather application interface.
2.Defines layout, colors, fonts, and responsiveness for a visually appealing UI.


JavaScript Logic:

// Object to store API key and base URL
const weatherApi = {
  key: 'YOUR_API_KEY',
  baseUrl: 'https://api.openweathermap.org/data/2.5/weather'
}

// Event listener for key press on input box
searchInputBox.addEventListener('keypress', (event) => {
  if (event.keyCode == 13) {
    getWeatherReport(searchInputBox.value);
  }
});

// Function to fetch weather data from API
function getWeatherReport(city) {
  // Fetch weather data using fetch API
  fetch(`${weatherApi.baseUrl}?q=${city}&appid=${weatherApi.key}&units=metric`)
    .then(weather => {
      return weather.json(); // Convert response to JSON
    })
    .then(showWeatherReport); // Call function to display weather report
}

// Function to display weather report on the interface
function showWeatherReport(weather) {
  // Display weather information dynamically in HTML
}

// Other utility functions for formatting date, time, etc.

1.Handles user input, API requests, data processing, and dynamic content generation.
2.Fetches weather data from the OpenWeatherMap API and displays it on the interface.


Error Handling:

function showWeatherReport(weather) {
    let city_code = weather.cod;
    if (city_code === '400') {
        // Display error message for empty input
        swal("Empty Input", "Please enter any city", "error");
        reset(); // Reset input box
    } else if (city_code === '404') {
        // Display error message for invalid city name
        swal("Bad Input", "Entered city didn't match", "warning");
        reset(); // Reset input box
    } else {
        // Display weather information on the interface
    }
}


1.Handles error scenarios such as empty input or invalid city names.
2.Uses the SweetAlert library to display user-friendly error messages.
3.Resets the input box after displaying the error message.

Background Image Update:


function showWeatherReport(weather) {
    // Display weather information dynamically in HTML

    // Update background image based on weather condition
    changeBg(weather.weather[0].main);
}

function changeBg(status) {
    // Update background image based on weather condition
}


1.Dynamically updates the background image of the application based on the current weather condition.
2.Different background images are associated with different weather conditions to enhance the visual appeal of the interface


Media Query:



@media screen and (max-width: 800px) {
  .app-main {
    width: 95%;
    padding: 10px;
  }
  body {
    min-height: 94vh;
  }
}



1.Applies responsive styles when the screen width is less than or equal to 800px.
2.Adjusts the width and padding of the main container to ensure better usability on smaller devices.



Utility Functions:


// Function to format the last update time
function getTime(todayDate) {
    let hour = addZero(todayDate.getHours());
    let minute = addZero(todayDate.getMinutes());
    return `${hour}:${minute}`;
}

// Function to format the date
function dateManage(dateArg) {
    // Format the date
}

// Function to dynamically change the background based on weather condition
function changeBg(status) {
    // Change background image based on weather condition
}

// Function to get the class name of the weather icon based on weather condition
function getIconClass(classarg) {
    // Return class name of weather icon based on condition
}

// Function to reset the input box
function reset() {
    // Clear input box
}

// Function to add zero to single-digit numbers for formatting time
function addZero(i) {
    // Add zero if the number is single-digit
}


1.Provides utility functions for various tasks such as formatting date and time, resetting input box, and adding zero to single-digit numbers.
2.These functions enhance the readability and maintainability of the code by encapsulating repetitive tasks into reusable functions.



