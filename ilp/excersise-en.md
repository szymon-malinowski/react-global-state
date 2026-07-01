# Individual Learning Phase: Building Global State with the React Context API

## Your Goal

You will build a small React 19 application where multiple components access shared data. You will consciously decide which data remains local and which is managed globally. In the end, you will have a functioning Context-based state management for a small dashboard with user information, theme, and notifications.

## What You Need

- A running React 19 project
- Node.js and npm
- An editor like VS Code
- A browser with DevTools
- Basic knowledge of components, props, `useState`, and `useContext`

## Time Schedule

- 10 minutes: Create project or prepare existing React project
- 20 minutes: Basic Task 1
- 20 minutes: Basic Task 2
- 25 minutes: Basic Task 3
- 25 minutes: Basic Task 4
- 20 minutes: Basic Task 5
- Optional 20–30 minutes: Extension tasks

## Basic Tasks

### Task 1:

Create initial application with local state  
**Goal:** You create a small application where non-global state initially appears in multiple components.  
**Instruction:** Create an application with at least these components:
- `App`
- `Header`
- `Dashboard`
- `SettingsPanel`
- `NotificationBar`

Include the following data:
- Username
- Current theme (`light` or `dark`)
- Number of unread notifications

Initially, manage this data locally or via props, so you can feel where passing data becomes impractical. Also, build in a small interaction:
- Toggle theme
- Change username
- Increment or reset notification counter

**Expected Result / Target State:** Your application runs and shows that shared data is currently still awkwardly passed between components or managed multiple times.

### Task 2:

Cleanly separate local and global state  
**Goal:** You consciously decide which data should be global and which remains local.  
**Instruction:** Analyze your application practically in the code and make a decision for each piece of state:
- What should be globally available?
- What remains local within a single component?

Implement this separation directly. At least one state should remain local, for example:
- The input value of a form field
- An open/closed status of a small UI element

Briefly document your decision in comments or in a `README.md` with 3–5 bullet points.

**Expected Result / Target State:** Your application contains both local and globally intended state, and you have implemented a clear, comprehensible separation.

### Task 3:

Create and provide your own Context  
**Goal:** You set up your own React Context for global data.  
**Instruction:** Create your own Context, for example `AppContext`, and a suitable Provider, for example `AppProvider`. Store the global data within it:
- Username
- Theme
- Notifications

Additionally, provide functions to change these values, for example:
- Update username
- Toggle theme
- Increment notifications
- Reset notifications

Wrap your application so that all necessary components have access to the Context.

**Expected Result / Target State:** There is a functional Context with a Provider, and global data is managed centrally in one place.

### Task 4:

Use global data in multiple components  
**Goal:** You read global data in different components and visibly use it in the UI.  
**Instruction:** Replace the previous prop drilling in at least three places with `useContext`. Use the global data in multiple components, for example:
- `Header` displays username and theme
- `NotificationBar` displays the number of unread notifications
- `SettingsPanel` offers buttons or input fields to change values

Ensure that changes in one component are immediately visible in other affected components.

**Expected Result / Target State:** Multiple components read the same global data from the Context without you having to pass it through multiple levels via props.

### Task 5:

Clean up the application and use Context meaningfully  
**Goal:** You check whether your Context is used effectively and improve the structure of your application.  
**Instruction:** Clean up your code and check:
- Are there props you no longer need?
- Is there data that should better remain local after all?
- Is your Provider clearly structured?
- Are the names for Context, values, and functions clearly understandable?

Additionally, add a small section to the application with the title "Why Global?", in which you explain in 2–4 short sentences directly in the UI why exactly this data is global and other data remains local.

**Expected Result / Target State:** Your application is structured, comprehensible, and practically demonstrates when Context is useful and when it is not.

## Extension Tasks

### Extension Task 1: Create a custom Hook for the Context

**Goal:** You simplify access to the Context.  
**Instruction:** Create a custom Hook, for example `useAppContext`, that encapsulates access to your Context. Use this Hook instead of direct `useContext` in your components. Ensure that you get a clear error message if the Hook is used outside the Provider.

**Expected Result / Target State:** Your components access the global state uniformly and cleanly via a custom Hook.

### Extension Task 2: Split Context into multiple areas

**Goal:** You structure global state more finely and avoid unnecessary coupling.  
**Instruction:** Split your existing Context into at least two Contexts, for example:
- `ThemeContext`
- `UserContext`
- optional `NotificationContext`

Adjust the Provider and components so that each component only retrieves the data it truly needs.

**Expected Result / Target State:** Your global state is better organized and divided into logically separate areas.

### Extension Task 3: Make global state persistent

**Goal:** You make your global state more useful in everyday life.  
**Instruction:** Permanently store at least one global value in the browser, for example:
- Theme
- Username

Load the saved value again when the application starts. Test the behavior after a page reload.

**Expected Result / Target State:** At least one global state persists after a reload.

## Important Notes

- Work step by step and test after each task.
- Keep the UI deliberately small so you can focus on the state.
- For global data, only use values that are truly needed in multiple components.
- Keep purely local UI states within their respective components.
- If you are unsure, decide pragmatically and then check in the running code whether the decision proves effective.
- Use clear names for Context, Provider, Hook, and update functions.

## Reflection Questions

- Which data in your application was truly global?
- For which data was Context helpful, and for which was it rather unnecessary?
- Where did you previously pass props that you no longer need?
- Which states did you consciously leave local and why?
- How would you extend your Context structure if the application grows larger?

---