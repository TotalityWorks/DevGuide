# Totality Works Development Style Guide

## Code Formatting

No one wants to see commit differences that include spaces vs tabs, or added/subtracted semicolons, or changing whitespaces.
This takes up precious space that could be devoted to seeing real commit differences at a glance.
At the same time, with each developer programming with their own personal formatting preferences, the chances for creating bugs increase seeing as we would be guaranteeing that project code would look and be different on different machines. 
To avoid this and any other issues that come with individual code formatting preferences, we at Totality Works will be using Prettier in all of our projects.
Prettier is an opinionated code formatter that will help every Totality Works developer align their code to the style guide.

Installing prettier as a devDependency is as easy as `npm i -D prettier`.
After installing prettier, a `.prettierrc.json` file should be added to the root of the project and a new script added to package.json:

`"prettier": "prettier --write *"`

In the new `.prettierrc.json` file, add the following lines:

```
{
    "singleQuote": true,
    "jsxSingleQuote": true
}
```

Be sure to also add an `.editorconfig` file with the following settings as well:

```
root = true

[*]
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = false
insert_final_newline = false
```

## Code Linting

Linting is a venerable and time-tested helper in the developer's battle against bugs.
A good linter will comb through the written code looking for syntax issues, possible problems, and even formatting concerns.
Depending on how you've configured your linter, it could also fix these issues, problems, and concerns for you.
Since most of our work here at Totality Works is in Javascript, in one form or another, we heavily rely on eslint.
Totality Works uses most of the Airbnb style guide with a few changes.

To install eslint as a devDependency simply run `npm i -D eslint`.
To configure the linter in a new project, run `npx eslint --init`:
Select the following options:
* To check syntax, find problems, and enforce code style
* JavaScript modules (import/export)
* React
* (Select if your project is using Typescript)
* (Select where your code will run)
* Use a popular style guide
* Airbnb: https://github.com/airbnb/javascript
* JSON

These options require installing the following npm packages:
* eslint-config-airbnb
* eslint-plugin-import
* eslint-plugin-jsx-a11y
* eslint-plugin-react
* eslint-plugin-react-hooks

After installing the above packages, be sure to add the following scripts:
* `"lint": "eslint '**/*.{js,jsx}'"`
* `"lint:fix": "npm run lint -- --fix"`
* `"format": "npm run prettier && npm run lint:fix"`

The first one will show you all of the files that need to be linted.
The second will fix all of the errors found in each javascript or jsx file.
The third script will run `prettier --watch` to format your files and then run the linter to fix any issues afterwards.

## Style Guide

The above sections dealt with the how of the Totality Works Style Guide.
With the above, you almost never have to worry about the details of the Totality Works Style Guide, as such.
The above scripts will mostly format and fix your code whenever it is outside of our style boundaries.
For those who are more thorough and require a detailed explanation of the actual Style Guide, you will enjoy the following.

### Distinctions

In this secion, we'll cover those points at which Totality Works has departed from the above standards.

#### Single Quotes

The Airbnb style guide makes a distinction between quotes in plain Javascript files and those in JSX files.
We at Totality Works prefer consistency of rules across all Javascript files, including JSX files.
For this reason, we have configured Prettier to expect single quotes.
We have also altered the eslint rules to expect single quotes in JSX files as well.

### One JSX Expression Per Line

Likewise, the Airbnb style guide expects a single JSX expression per line and the linter will add lines to code to abide by this rule.
We find this to be difficult to read at times, and unnecessary for most files.
While having an excess of JSX expressions would similarly cause difficulty, we find it prudent to allow more than one expression per line for our purposes.

### Styles

Apart from the distinctions above, we strictly follow the formatting provided by Prettier and the linting standards expected by the Airbnb style guide. Below is a thorough walkthrough for each.

#### Formatting


#### Style Standard