Vue.js Calculator
=================

A simple and intuitive calculator built using Vue.js. This project allows users to perform basic arithmetic operations, including addition, subtraction, multiplication, and division, as well as advanced functions such as square roots and trigonometric calculations.

Table of Contents
-----------------

*   [Installation](#installation)
*   [Folder Structure](#folder-structure)
*   [How to Run](#how-to-run)
*   [Usage](#usage)
*   [Features](#features)
*   [Contributing](#contributing)
*   [License](#license)

Installation
------------

1.  **Clone the Repository**:
    
        git clone https://github.com/sujanshresthanet/vue-calculator-app.git
        cd vue-calculator-app
    
2.  **Install Dependencies**:
    
    Make sure you have [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/) installed. Then run:
    
        npm install
    
3.  **Run the Development Server**:
    
        npm run serve
    
    The application will be available at `http://localhost:8080` by default.
    

Folder Structure
----------------

    vue-calculator-app/
    ├── node_modules/         # Project dependencies
    ├── public/               # Public assets
    │   ├── index.html        # Main HTML file
    │   └── favicon.ico       # Favicon
    ├── src/                  # Source files
    │   ├── assets/           # Assets (images, icons, etc.)
    │   ├── components/       # Vue components
    │   ├── App.vue           # Main Vue component
    │   └── main.js           # Entry point of the application
    ├── package.json          # Project configuration
    └── README.md             # Project documentation
    

How to Run
----------

After installing the dependencies, you can run the application locally using the command `npm run serve`. Open your browser and go to `http://localhost:8080`.

Usage
-----

Enter numbers and operations in the input field at the top. The results will be displayed directly below the input as you perform calculations.

Features
--------

*   Basic arithmetic operations: Addition, Subtraction, Multiplication, Division
*   Advanced functions: Square Root, Sine, Cosine, Tangent
*   Responsive design with modern UI
*   Clear and delete buttons for input management

Contributing
------------

If you'd like to contribute, please fork the repository and submit a pull request with your changes. Make sure to follow the coding standards and add tests for new features.

License
-------

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.