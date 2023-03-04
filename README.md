## 📝 Documentation for Angular Demo Project with Husky Integration 🐶

To automate Git hooks in your Angular app, you can use Husky. Here are the steps to integrate Husky into your project:

1. Install Commitizen and cz-conventional-changelog as dev dependencies:
```
npm install commitizen cz-conventional-changelog --save-dev
```

2. Add the "commit" script to your package.json file:
```
"scripts": {
  "commit": "cz"
}
```

This will allow you to use Commitizen for creating standardized commit messages.

3. Install Husky as a dev dependency:
```
npm install husky --save-dev
```

4. Run the command to set up Husky in your project:
```
npx husky install
```

5. Add a "postinstall" script to your package.json file to ensure Husky is installed after node module installation:
```
"scripts": {
  "postinstall": "husky install"
}
```

6. Add a "test:headless" script to your package.json file to run tests in a headless browser:
```
"scripts": {
  "test:headless": "ng test --watch=false --browsers=ChromeHeadless"
}
```

7. Add a pre-commit hook that runs the "test:headless" script by running the following command:
```
npx husky add .husky/pre-commit "npm run test:headless"
```

This will ensure that your tests are run before each commit.

## Initialize your commit messages with Commitizen

To initialize your commit messages with Commitizen, run the following command:
```
npm run commit
```
