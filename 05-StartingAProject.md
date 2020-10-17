# Starting A Totality Works Project

## Apps
With the exception of WordPress, all of the work done by Totality Works is exclusively in Javascript.
This is intentional.
Currently, WordPress controls about 30% of indexable websites and so the market cannot be ignored.
Offering premium WordPress development is a necessity in the current climate.
At the same time, it is no doubt that Javascript is the language of the future.
With the advent of Node.js almost a decade ago, Javascript can be run anywhere and not just in the browser.
Facebook's React and React Native have made it the go-to language for developing mobile apps with web complements.
Adding Electron to the mix to build desktop apps makes Javascript the truly universal language for business in the 21st century.
In this modern world, the focus isn't on who can do it the best with the smallest file size and all the technical lingo us developers love.
The focus is on swiftness to market and quick iterations.
We at Totality Works believe that Javascript is uniquely equipt to handle this expectation today.

NOTE: We use `npm` whenever possible. No `yarn`. No `pnpm`.

### WordPress


### Lerna
If your project contains multiple self-developed apps or packages, then you should run lerna to maintain your code in a monorepo.
Lerna gives you the ability to share code between projects using `lerna bootstrap`.
This will allow your apps to import code from other directories as if you had installed them as node modules.
Similarly, Lerna allows us to run scripts from our multiple apps from the root directory.
This way, we can format, lint, and test all of the code we altered in all apps from the root at once.

Run `npx lerna init` to initialize a new lerna project.

Add the following scripts to your `package.json` file:
* `".:prettier": "lerna run prettier"`
* `".:lint": "lerna run lint"`
* `".:lint:fix": "lerna run lint:fix"`
* `".:format": "lerna run format"`
* `".:test": "lerna run test"`
* `".:test:coverage": "lerna run test:coverage"`
* `".:test:watch": "lerna run test:watch"`

NOTE: These scripts will run in all directories in your `packages` directory, but only if the `package.json` file in these directories include the script that you're calling.
For example, `npm run .:test` will only run `lerna run test` in each directory that has a `test` script.

If your project includes npm packages to be published, you should not change the name of the `packages` directory.
If your project is just a collection of apps with shared code and packages that will not be published, then you should change the name of `packages` to something more appropriate like `apps`.

After you have begun your project, if you find that you have code that you would like to share between apps or packages, you can run `lerna bootstrap`.
This will allow you to import this code as if you had installed it as a dependency.

### Next.js
Many of the projects here at Totality Works will be apps developed with Next.js, as it gives us a lot of freedom regarding rendering and other such essentials.
It also supports server APIs, and thus is very useful in developing full stack apps.

To start a new Next.js project, run `npx create-next-app [name]` where [name] is the name of the app.
If you are developing in a Lerna supported monorepo, it is suggested that the name of your Next.js app be `browser` so as to distinguish it from the other apps you may also be developing: i.e. `mobile` or `desktop`.

### Gatsby.js
While Next.js handles most of our frontend/fullstack apps, Gatsby.js is the heart of our website service.

To start a new Gatbsy.js project, run `npx gatsby new [site-name]` where [site-name] is the name of the website.
If you are developing in a Lerna supported monorepo, it is suggested that the name of your Gatsby.js project be `website` so as to distinguish it from the other projects in the repo.

### React Native


### Electron Forge

## Testing

## Formatting & Linting

## CI/CD Pipeline

## 