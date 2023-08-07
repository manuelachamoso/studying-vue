# Comment System Vue.js App

This is a simple comment system application built using Vue.js. It allows users to submit comments and view them in a list. The application showcases key Vue.js concepts such as data binding, component communication, and event handling.

## Project Overview

The application is structured as follows:

- `App.vue`: The main application component that manages the comment submission form and the list of comments.

- `FormTodo.vue`: A reusable child component responsible for the comment submission form.

- `CommentItem.vue`: A child component responsible for rendering individual comments.

The project demonstrates the Model-View-Controller (MVC) architecture:

- **Model**: Manages the data for comments.

- **View**: Displays the user interface, including the comment form and list of comments.

- **Controller**: Handles user interactions, such as adding and removing comments.

### Components and Communication

Vue.js components are used to create modular and reusable UI elements. The application includes the following components:

- `App.vue`: Manages the overall structure and interaction of the application.

- `FormTodo.vue`: Displays the comment submission form and emits an event when a new comment is added.

- `CommentItem.vue`: Renders individual comments based on the provided data.

### Data Binding and Event Handling

The application leverages Vue.js's two-way data binding to keep the UI and data synchronized. When a user enters their name and comment in the form, the data is automatically updated in real-time.

Event handling is achieved using Vue.js directives, such as `@click` to handle button clicks. The `.prevent` modifier is used to prevent default behavior when adding comments to the list.

## Getting Started

1. Clone the repository to your local machine.

2. Open the project in your preferred code editor.

3. Install dependencies using `npm install`.

4. Run the development server using `npm run serve`.

5. Open your web browser and navigate to the provided local development URL (usually `http://localhost:8080`).

6. Interact with the comment submission form to add comments.

## About Vue.js

Vue.js is a progressive JavaScript framework that simplifies building interactive web interfaces. It features reactive data binding, component-based architecture, and an intuitive API. For more information, visit the [Vue.js documentation](https://vuejs.org/).

