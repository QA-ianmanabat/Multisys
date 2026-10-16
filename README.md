# Cypress Automation (TypeScript)

Automated tests for http://the-internet.herokuapp.com covering Login, Dynamic Content and Checkboxes.

## Project structure

```
cypress.config.ts                          Cypress config (baseUrl, reporter)
tsconfig.json                              TypeScript config
cypress/
  e2e/
    login.cy.ts                            Scenario 1 - Login Functionality
    dynamicContent.cy.ts                   Scenario 2 - Dynamic Content
    checkboxes.cy.ts                       Scenario 3 - Checkboxes Interaction
  fixtures/
    loginData.json                         Login test data
    dynamicContentData.json                Dynamic content test data
    checkboxData.json                      Checkbox test data
  support/
    commands.ts                            Custom commands
    elements/
      loginElements.ts                     Login and secure area locators
      dynamicContentElements.ts            Dynamic content locators
      checkboxElements.ts                  Checkbox locators
    e2e.ts                                 Support file (loads commands and reporter)
```

## Test cases

| Scenario | ID | Description |
|---|---|---|
| 1 Login | TC01 | Successful login with valid credentials |
| 1 Login | TC02a | Login fails with an invalid username |
| 1 Login | TC02b | Login fails with an invalid password |
| 1 Login | TC03 | Login fails with empty credentials |
| 1 Login | TC04 | Bonus: logout after a successful login |
| 2 Dynamic Content | TC01 | Content changes on page refresh |
| 2 Dynamic Content | TC02 | Click “click here” and verify static content is visible |
| 3 Checkboxes | TC01 | Modify the state of each checkbox |
| 3 Checkboxes | TC02 | Bonus: restore each checkbox to its original state |

## Prerequisites

- Node.js 18 or later
- npm

## How to run

```bash
npm install                                   # install dependencies
npm run cy:open                               # interactive mode
npm test                                      # headless run of all specs
npx cypress run --spec cypress/e2e/checkboxes.cy.ts   # run a single spec
npm run typecheck                             # optional TypeScript check
```

## Test report

After a headless run, open `cypress/reports/html/index.html` in a browser.
Failure screenshots are saved in `cypress/screenshots/`.
