# Dynamic Form Generator

A dynamic form generator that takes a JSON schema and generates a styled, functional form in real-time. This application features a split-screen interface with a JSON editor on the left and a form preview on the right.

## Features

- Real-time JSON validation
- Error messages for invalid JSON
- Responsive form layout
- Support for various field types (text, email, select, radio, textarea)
- Dark mode support
- Tailwind CSS for styling

## Setup Instructions

To set up the project locally, follow these steps:

### Prerequisites

Make sure you have [Node.js](https://nodejs.org/) installed on your machine.

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/dynamic-form-generator.git
cd dynamic-form-generator
```

### 2. Install Dependencies

Run the following command to install the required dependencies:

```bash
npm install
```

### 3. Configure Tailwind CSS

If you haven't already configured Tailwind CSS, follow these steps:

1. Install Tailwind CSS and its dependencies:

   ```bash
   npm install -D tailwindcss postcss autoprefixer
   npx tailwindcss init -p
   ```

2. Update `tailwind.config.js` to include paths to your template files:

   ```javascript
   /** @type {import('tailwindcss').Config} */
   module.exports = {
     content: [
       "./src/**/*.{js,jsx,ts,tsx}",
     ],
     theme: {
       extend: {},
     },
     darkMode: 'class', // Enable class-based dark mode
     plugins: [],
   }
   ```

3. Add the following lines to your `src/styles/index.css` file:

   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;

   /* Additional custom styles can go here */
   ```

### 4. Start the Development Server

Run the following command to start the application:

```bash
npm start
```

Visit `http://localhost:3000` in your browser to view the application.

## Example JSON Schemas

Here are some example JSON schemas you can use in the JSON editor:

### Example 1: Basic User Registration Form

```json
{
  "formTitle": "User Registration",
  "formDescription": "Please fill out this registration form.",
  "fields": [
    {
      "id": "username",
      "type": "text",
      "label": "Username",
      "required": true,
      "placeholder": "Enter your username"
    },
    {
      "id": "email",
      "type": "email",
      "label": "Email Address",
      "required": true,
      "placeholder": "you@example.com",
      "validation": {
        "pattern": "^[^\\s@]+@[^\\s@]+\\.[^\\s@]+$",
        "message": "Please enter a valid email address"
      }
    },
    {
      "id": "password",
      "type": "text",
      "label": "Password",
      "required": true,
      "placeholder": "Enter your password"
    }
  ]
}
```

### Example 2: Project Requirements Survey

```json
{
  "formTitle": "Project Requirements Survey",
  "formDescription": "Please fill out this survey about your project needs.",
  "fields": [
    {
      "id": "name",
      "type": "text",
      "label": "Full Name",
      "required": true,
      "placeholder": "Enter your full name"
    },
    {
      "id": "companySize",
      "type": "select",
      "label": "Company Size",
      "required": true,
      "options": [
        { "value": "1-50", "label": "1-50 employees" },
        { "value": "51-200", "label": "51-200 employees" },
        { "value": "201-1000", "label": "201-1000 employees" },
        { "value": ">1000", "label": ">1000 employees" }
      ]
    },
    {
      id: 'comments',
      type: 'textarea',
      label: 'Additional Comments',
      required: false,
      placeholder: 'Any other details you\'d like to share...'
    }
  ]
}
```

## Local Development Guide

### Running the Application

To run the application locally:

1. **Start the Development Server**:
   Make sure you are in the project directory and run:
   
   ```bash
   npm start
   ```

2. **Accessing the Application**:
   Open your web browser and go to `http://localhost:3000`. You should see the application running.

### Making Changes

You can modify components located in the `src/components` directory. The main application logic is in `src/App.tsx`. 

### Testing Changes

Whenever you make changes to your code, save them, and the development server will automatically reload to reflect those changes.

### Building for Production

To create a production build of your application, run:

```bash
npm run build
```

This will generate static files in a `build` directory that can be deployed to any static file server.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```