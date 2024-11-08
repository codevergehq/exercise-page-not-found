# Exercise: Page Not Found

## Learning Goals

By completing this exercise, you will be able to:

- Implement a modern styling solution in React
- Create a responsive and visually appealing error page
- Apply consistent styling patterns using your chosen method
- Structure and organize styles in a React application

## Introduction

In this exercise, you’ll be creating a 404 - Not Found page. Your task is to create a visually stunning and user-friendly 404 page that now only informs users they’ve reached a dead end but also guides them back to safety.

Imagine you’re a developer at a company that takes user experience seriously. Even when users get lost, you wan to provide them with a delightful experience and helpful resources. You’ll be using your React skills and your chosen styling method to create a page that turns a potential frustration into an opportunity to showcase your design and development capabilities.

Choose your weapon: Global Styles, CSS Modules, CSS-in-JS, or Tailwind CSS.

We’ll provide you with a couple of 404 Pages you can use for inspiration. You can find them in the `examples` folder. If you don’t like them, feel free to come up with a 404 Page on your own, or take inspiration from the world wide web yourself.

But don’t spend too much time choosing the perfect 404 page design. The key is to create something functional and visually appealing without overcomplicating it. Remember, the main goal is to guide users back to useful content on your site.

## Getting Started

Follow the instructions below to get started:

1. Fork this repository
2. Clone the repository to your computer
3. Open the repository in VS Code
4. Start the Live Server in VS Code
5. Follow instructions

## Instructions

### Task 1: Setup your Weapon of Choice

Before diving into creating your 404 page, you'll need to set up your chosen styling method.

Depending on your selection:

- For Global Styles: Create a new CSS file in your styles directory and import it in your main JavaScript file.
- For CSS Modules: Create a new .module.css file for your 404 component.
- For CSS-in-JS: Install and set up your preferred CSS-in-JS library (e.g., styled-components, Emotion).
- For Tailwind CSS: Ensure Tailwind is properly configured in your project.

### Task 2: Component Structure

Create a new component called `NotFound`. This component should include:

1. A main heading (”404 - Page Not Found”)
2. A subheading with a friendly message (e.g. “Sorry, we couldn’t find the page you’re looking for.”)
3. A “Go Back to Home” button
4. Optional: Resource links (e.g. Documentation, API Reference, Guides, Blog, etc.)

Your basic component structure could look something like this:

```jsx
function NotFound() {
  return (
    <main>
      <h1>404 - Page Not Found</h1>
      <p>Oops! Looks like you've ventured into unknown territory.</p>

      <div>
        <h2>Helpful Resources</h2>
        <nav>
          <a href="/docs">Documentation</a>
          <a href="/api">API Reference</a>
          <a href="/guides">Guides</a>
          <a href="/blog">Blog</a>
        </nav>
      </div>

      <button onClick={() => (window.location.href = "/")}>
        Go Back to Home
      </button>
    </main>
  )
}

export default NotFound
```

Make sure to import the `NotFound` component in your `App.jsx` and use it accordingly.

### Task 3: Implementing Your Chosen Styling Method

Depending on Part 1 , implement your chosen styling method to create a visually appealing and responsive 404 page.

**Option A: Global CSS**

```css
/* index.css or App.css */
.container {
  /* Your styles here */
}

.title {
  /* Your styles here */
}

/* ... */
```

**Option B: CSS Modules**

```css
/* NotFound.module.css */
.container {
  /* Your styles here */
}

.title {
  /* Your styles here */
}

/* ... */
```

**Option C: CSS-in-JS (styled-components)**

```jsx
import styled from "styled-components"

const Container = styled.main`
  // Your styles here
`

const Title = styled.h1`
  // Your styles here
`

// ...
```

**Option D: Tailwind CSS**

```jsx
<main className="min-h-screen flex flex-col items-center justify-center p-4">
  <h1 className="text-4xl font-bold text-gray-800 mb-4">
    404 - Page Not Found
  </h1>
  {/* Add more Tailwind classes */}
</main>
```

### Task 4: Design Requirements

Your 404 page should include the following styling features:

1. It should be responsive (follow the mobile-first approach)
2. Centered content both horizontally and vertically on the page
3. A large, bold heading with an accent color
4. A smaller subheading with a softer color to complement the main heading
5. Consistent spacing between elements
6. Accessibility for interactive elements (hover states, focus indicators)

## Submission

When you’ve completed the exercise:

1. Push your code to GitHub:

```jsx
git add .
git commit -m "Completed 404 page exercise"
git push origin main
```

2. Create a Pull Request and submit your assignment.

## Bonus Challenges

If you finish early, or you want to push your skills further, here are some bonus challenges to explore:

### Task 5 (optional): Add a Creative Illustration

Consider adding a creative illustration or animation to your 404 page.

This could be a custom image, SVG, or even a simple CSS animation that adds visual interest and personality to the page. The illustration should be relevant to the 404 concept or your brand identity. Remember to keep it lightweight to ensure fast loading times.

### Task 6 (optional): Implement a Dark Mode

Add a toggle for switching between light and dark mode on your 404 page.

This will require you to create two sets of color schemes and implement the logic to switch between them. Consider using CSS variables or a theming solution that works well with your chosen styling method. Remember to persist the user's preference using local storage for a seamless experience across page reloads.

Here are some tips to get you started:

- Define a set of CSS variables for both light and dark themes
- Create a toggle button or switch component
- Use JavaScript to change the theme and update the DOM
- Store the user's preference in local storage

## Frequently Asked Questions

<details>
<summary>How can I implement responsive design for the 404 page using my chosen styling method?</summary>

Implement responsive design using media queries in CSS, responsive utility classes in Tailwind, or by leveraging the theming capabilities of CSS-in-JS libraries. Ensure your layout adjusts smoothly for different screen sizes, particularly focusing on mobile-first design principles.

</details>

<details>
<summary>What's the best practice for organizing styles when using CSS Modules in a React application?</summary>

When using CSS Modules, create a separate .module.css file for each React component. Use local class names to avoid global namespace conflicts. Import the styles object in your component and reference classes using the styles object (e.g., className={styles.myClass}).

</details>

<details>
<summary>How can I ensure consistent theming across components when using CSS-in-JS?</summary>

Create a theme object that defines your color palette, typography, and other design tokens. Use a ThemeProvider component (available in libraries like styled-components or Emotion) to wrap your application. Access theme values in your styled components using props.theme.

</details>

<details>
<summary>What's the most efficient way to handle hover and focus states for accessibility in Tailwind CSS?</summary>

Utilize Tailwind's pseudo-class variants like `hover:` and `focus:` to apply styles for different states.
For example, `className="text-blue-500 hover:text-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-opacity-50"`.

</details>

<details>
<summary>How can I optimize the performance of my styled components when using CSS-in-JS?</summary>

To optimize performance with CSS-in-JS, use static styles where possible instead of dynamic props. Leverage the use of the useMemo hook for complex style computations. For libraries like styled-components, use the babel-plugin-styled-components for server-side rendering and smaller bundles.

</details>
