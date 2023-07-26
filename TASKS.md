# Test Assignment for Junior Angular Developer Position

## Table of Contents

- [Continuous Learning, Assistance and Motivation](#continuous-learning-assistance-and-motivation)
- [Introduction](#introduction)
    - [Project Overview](#project-overview)
    - [Process of completing the tasks](#process-of-completing-the-tasks)
    - [Check list to be completed before submitting the assignment](#check-list-to-be-completed-before-submitting-the-assignment)
- [Tasks](#tasks)
  - [Task 0 — Project Creation and Setup](#task-0--project-creation-and-setup)
  - [Task 1 — Navigation Service Implementation](#task-1--navigation-service-implementation)
  - [Task 2 — Navigation Display](#task-2--navigation-display)
  - [Task 3 — Creating Card Components](#task-3--creating-card-components)
  - [Task 4 — Implementation of Level 3 Navigation and Filling Cards with Content](#task-4--implementation-of-level-3-navigation-and-filling-cards-with-content)

## Continuous Learning, Assistance and Motivation

**Please note**, as this assignment is targeted at a Junior Angular Developer, learning on the go is completely acceptable and expected. Feel free to access any educational resources to complete the task successfully. Should you encounter any difficulties during the process, don't hesitate to reach out to @thekiba for consultation and assistance.

Remember, it's completely normal to face challenges along the way, especially when you're learning something new. These obstacles are part of the process, helping you grow as a developer. Don't get discouraged if things seem difficult initially. Persistence and resilience are key to overcoming these hurdles.

At our company, we believe in the power of learning and growing together. We understand that this assignment might be challenging for you, but we have complete faith in your capabilities. Keep going, stay curious, and always strive for improvement. Remember, you've got this!

## Introduction

This test assignment is designed to evaluate the knowledge and skills necessary for the Junior Angular Developer position. Within the assignment, you will demonstrate your abilities to work with Angular and RxJS, as well as some of the main concepts of development on these technologies, including working with Git, tree-like data structures, navigation, component creation, and the use of basic Angular classes and directives.

**_Note:_** In this assignment, you will work in a single repository, performing several interconnected tasks.

### Project Overview

The goal of this project is to create an Angular application with a structured navigation system. The application will consist of multiple tasks where each task builds upon the previous one.

The primary focus of the project is to design an efficient navigation service, represent the navigation hierarchy using card components, and finally present the navigation items (up to Level 3) on a page titled "Accounts and Symbols".

Below is the structure of the pages:

1. **Dashboard**: This is the main page of the application.
2. **Accounts and Symbols**: This is a parent page for managing both accounts and symbols. It contains two cards: "Accounts" and "Symbols", which lead to respective pages.
    - **Accounts**: This is a standalone page that also contains Level 3 navigation items leading to the following subpages:
        - Related Profiles
        - Accounts Groups
    - **Symbols**: This is a standalone page that also contains Level 3 navigation items leading to the following subpages:
        - Contracts
        - Symbols Groups

This navigation structure reflects the hierarchical relationship between the different pages in the application, with the "Accounts and Symbols" page acting as a hub for accessing different functionalities related to accounts and symbols.

Your tasks will involve implementing these structures, starting with the navigation service, followed by the card components, and finally displaying them on the page with the Level 3 navigation.

### Process of completing the tasks:

1. For each task, create a new branch with the task number (`feat/1`, `feat/2`, `feat/3`).
2. After each advancement in the task, mark the completed criteria in TASKS.md.
3. After finishing the task, merge it into the `main` branch.

Remember about the necessity to follow the [git commit convention](https://www.conventionalcommits.org/en/v1.0.0/) and to include the task number in the commit message.

**Commit examples:**

- Adding new functionality: `feat: added route enrichment functionality (Issue: FRONT-1)`
- Fixing a bug: `fix: fixed a bug in breadcrumb generation (Issue: FRONT-1)`
- Updating documentation: `docs: updated TASKS.md with task progress (Issue: FRONT-1)`
- Other (updating configuration, installing packages, etc.): `chore: installed rxjs (Issue: FRONT-1)`

All tasks should be completed in the same repository. After completing all tasks, there should be a README.md file in the repository describing the work that has been done, instructions on how to run the application, as well as the code that can be run following the instructions.

### Check list to be completed before submitting the assignment

Please make sure that you have completed all the tasks and that the application runs without errors. Also, make sure that you have completed all the acceptance criteria for each task.

- [ ] All tasks should be completed in the same repository:
    - [ ] Task 0 — Project Creation and Setup
    - [ ] Task 1 — Navigation Service Implementation
    - [ ] Task 2 — Navigation Display
    - [ ] Task 3 — Creating Card Components
    - [ ] Task 4 — Implementation of Level 3 Navigation and Filling Cards with Content
- [ ]  After completing all tasks, there should be a README.md file in the repository. This file should include:
    - [ ] A description of the work that has been done,
    - [ ] Instructions on how to run the application,
    - [ ] The executable code that can be run following the instructions.

## Tasks

___

### Task 0 — Project Creation and Setup

Before undertaking the main tasks, you need to set up your project's working environment. In this task, we will discuss the basic steps for creating a new project, setting up its structure, and importing the necessary resources.

**Steps:**

1. Create a new **private repository** on GitHub. Use `junior-angular-developer-tasks` as the repository name.

2. Share the repository with the `@thekiba` user.

3. Create a new project using Angular CLI. Use `junior-angular-developer-tasks` as the project name. For styles, use `css`. Enable Routing.

4. Carefully transfer all necessary resources into your project.
    - Start by copying the layout from the `assets/index.html` file. When working with this file, take extra caution to ensure the `<app-root>` and `<router-outlet>` elements are not inadvertently affected or modified. It's recommended to strategically divide the layout content between `index.html` and `app.component.html` for better structure and organization.
    - All styles should be moved into the `assets/styles.css` file.
    - All SVG images should be housed in the `assets/sprites.svg` file.

5. Copy the `TASKS.md` file from this repository to your project.

6. Create the `README.md` file in the root of your project. After completing all tasks, this file should include:
    - A description of the work that has been done (few sentences)
    - Instructions on how to run the application,
    - The executable code that can be run following the instructions.

**_Note:_** All styles and sprites should remain in the `assets` folder; there is no need to move them to the components.

**Acceptance Criteria:**

- [ ] A new project has been successfully created.
- [ ] All necessary resources have been imported and are located in the appropriate places.
- [ ] The project runs and works without errors, the opened page displays the existing layout.

---

### Task 1 — Navigation Service Implementation

Your first task is to implement a navigation service based on the abstract class and initial code we provide. The service should handle navigation data and provide functionality for their retrieval.

**Starter code:**

We provide you with the starter code for this task. It includes types and an abstract class for the navigation service. Your task is to implement this abstract class, filling it with methods and data.

**_Tip:_** Use RxJS features to implement the service methods.

```typescript
/**
 * Route data structure
 */
type NavigationRoute = {
  /**
   * Route title, used for display in navigation and breadcrumbs
   */
  title: string;

  /**
   * Route path, used for opening the route
   */
  path: string;

  /**
   * Route icon, used for display in navigation, fill only for first level routes
   */
  icon?: string;

  /**
   * Child routes, used for displaying nested routes
   */
  children?: NavigationRoute[];
}

/**
 * Enhanced structure of navigation route
 */
type EnhancedNavigationRoute = NavigationRoute & {
  /**
   * Parent route, used for simplifying the walking of the route tree
   */
  parent?: EnhancedNavigationRoute | null;

  /**
   * Enchaced child routes, used for displaying nested routes
   */
  children?: EnhancedNavigationRoute[];
}

/**
 * Token that provides all available routes for navigation
 */
const NavigationRoutes = new InjectionToken<NavigationRoute[]>(`Navigation Routes`, {
  providedIn: 'root',
  factory: (): NavigationRoute[] => [
    // TODO: You need to fill in the data
  ]
});

/**
 * Enhancement function type for navigation routes
 */
type NavigationEnhancement = (routes: Observable<NavigationRoute[]>) => Observable<EnhancedNavigationRoute[]>;

/**
 * Token that provides all available enhancements for navigation routes
 */
const NAVIGATION_ENHANCEMENTS = new InjectionToken<NavigationEnhancement[]>(`Navigation Enhancements`, {
  factory: (): NavigationEnhancement[] => [
    // TODO: You need to implement the enhancement of navigation data and put it in this array
  ]
});

/**
 * Abstract navigation service, used to provide navigation data
 *
 * TODO: You need to implement this class
 */
export abstract class NavigationService {
  /**
   * Returns enhanced navigation data
   */
  abstract getRoutes(): Observable<EnhancedNavigationRoute[]>;

  /**
   * Returns enhanced navigation data for the specified path
   */
  abstract getRoute(routeUrl: string): Observable<EnhancedNavigationRoute | null>;

  /**
   * Returns breadcrumbs for the specified path, the result is an array of routes starting with the parent and ending with the current one
   */
  abstract getBreadcrumbs(routeUrl: string): Observable<EnhancedNavigationRoute[] | null>;
}
```

**Acceptance Criteria:**

- [ ] Navigation is represented as a separate module
- [ ] The navigation config is filled
- [ ] Route enrichment is implemented
- [ ] Retrieval of all routes that have been previously enriched is implemented
- [ ] Retrieval of a route by the specified path is implemented
- [ ] Retrieval of breadcrumbs for the specified path is implemented
- [ ] Multiple subscriptions to streams should not lead to duplicate calculations
- [ ] Service methods and route enrichment are implemented using RxJS
- [ ] There are no memory leaks

---

### Task 2 — Navigation Display

Your next task will be to display the first and second level navigation menus based on the data provided by the navigation service you implemented in the previous task.

**_Note:_** The layout and styles for the navigation components will be provided to you. Your task is to convert them into Angular components and use them to display the navigation.

**Acceptance Criteria:**

- [ ] Navigation is displayed in accordance with the provided layout and styles
- [ ] All links in the navigation menu work correctly and lead to the corresponding placeholder pages
- [ ] Clicking on first-level items leads to the corresponding page
- [ ] If the active first-level item has child items, they should be expanded
- [ ] Clicking on second-level items leads to the corresponding page
- [ ] When clicking on second-level and third-level items, the menu should remain expanded
- [ ] Third-level items should not be displayed in the menu
- [ ] Each page displays its path in breadcrumbs (styles for breadcrumbs are arbitrary)
- [ ] There are no memory leaks

---

### Task 3 — Creating Card Components

In this task, you need to implement components that will represent cards for display on the "Accounts and Symbols" page. Each of these components must be implemented according to the layout provided to you:

1. `app-page-cards`: A general component for displaying cards on the page.
2. `app-page-card-item`: A component representing a single card.
3. `app-page-card-item-heading`: A component for displaying the card's heading.
4. `app-page-card-item-content`: A component for displaying the card's content.

**_Tip:_** Use `<ng-template>`, `<ng-content>` (or directives) and ContentChild to implement the components.

**Acceptance Criteria:**

- [ ] Card components and their elements are implemented in accordance with the provided layout
- [ ] Card components and their elements are correctly displayed on the page
- [ ] There are no memory leaks

---

### Task 4 — Implementation of Level 3 Navigation and Filling Cards with Content

In this task, you need to implement an additional component, the Level 3 navigation, and then integrate it within the card components that were created in the previous task. Upon opening the "Accounts and Symbols" page, two cards named "Accounts" and "Symbols" should display with their respective Level 3 navigation items.

Each card should contain Level 3 navigation items, populated from the corresponding section of the navigation configuration. You can pass an additional navigation element to each card using `ng-content`, which should be inserted at the beginning of the navigation.

Please note that within the navigation of both the "Accounts" and "Symbols" cards, there are items labeled "Find Account" and "Find Symbol". These items are simply aliases for the "Accounts" and "Symbols" pages, respectively. They do not correspond to unique pages but instead provide another way to reach the "Accounts" and "Symbols" pages from within the navigation structure.

**_Note:_** The card components and Level 3 navigation should be designed in a way that allows for easy reuse on other pages and navigation structures.

**Acceptance Criteria:**

- [ ] When opening the "Accounts and Symbols" page, two cards: "Accounts" and "Symbols" are displayed
- [ ] Each card contains Level 3 navigation, populated from the corresponding section of the navigation configuration
- [ ] An additional navigation element can be passed to each card using `ng-content`
- [ ] The additional navigation element is correctly displayed within the card
- [ ] There are no memory leaks
