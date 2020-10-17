# Totality Works Clean Code Standard

## Monorepos

To help maintain clean code, Totality Works makes use of monorepos for our projects.
In several companies, a monorepo is the single repository that hosts all of the code developed in that company.
For Totality Works, a monorepo refers to all of the code related to a single project and all related projects.
For example, the project OrthodoxQuotes is being developed as a mobile, browser, and desktop app.
The code for all of these projects are maintained in the single repo: OrthodoxQuotes.
It is in this way that Totality Works defines Monorepo.

### Lerna

To help us maintain our monorepos, we use Lerna. Installing Lerna is no trouble at all.
You simply run `npx lerna init`.
We find it helpful here at Totality Works to rename the given `packages` directory to something more semantically relevant to your current project.
For example, in the project OrthodoxQuotes above the directory is renamed to `apps` seeing as this project contains no npm packages.
In those cases that your project will contain npm packages to be published, the name `packages` is appropriate.

After initializing your lerna project, you should add these scripts to your root directory's `package.json`:
* `".:prettier": "lerna run prettier"`
* `".:lint": "lerna run lint"`
* `".:lint:fix": "lerna run lint:fix"`
* `".:format": "lerna run format"`
* `".:test": "lerna run test"`
* `".:test:coverage": "lerna run test:coverage"`
* `".:test:watch": "lerna run test:watch"`

The `lerna run [script]` command will run the command in every package in your monorepo.
The above scripts will allow us to format, lint, and test all from the root directory.
This is incredibly powerful for projects that have multiple apps using shared code and a shared server.
For example, if the mobile/native and broswer/frontend code already drew data from the server API and a change needed to be made to the server, you could make this change and then run tests for the mobile, broswer, and server all from the root directory.
The `.` in the scripts above means `root`.
It was added to make a sharp distinction between running scripts within a single app and running the lerna script from the root directory.

## Code Testing

Installing Jest as a devDependency is simple.
Run `npm i -D jest` and `npx jest --init` to install the package and walk through the configuration wizard.
Select these answers for the correct configuration settings:
* Y
* jsdom
* Y
* babel
* Y


### Testing Philosophy

### Unit Tests

### Integration Tests

### End to End Tests

### UI Tests

## React PropTypes & Typescript

## Code Comments

## CI/CD Pipeline