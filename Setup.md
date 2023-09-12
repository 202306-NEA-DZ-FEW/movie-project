# Setup the project

The steps that are laid out in the file will include setting up the following:

1. Next.JS - This will be used as the main framework for the frontend.
2. TailwindCSS [Optional]- This comes as an option when setting up NextJS
3. Eslint - Also comes with Next.js. Enforces code quality.
4. Prettier - Enforces code format.
5. Commitizen + Commitlent - Used to follow the correct method of commiting your code
6. Husky - Used to run prettier + eslint before commiting the code. Saves time and ensures the code is formatted correctly and follows the correct coding standards.
7. Lintstaged - Gives us the ability to run commands on staged files (ie: files that have not been commited yet)

## Instructions

1. Next.js

```shell
npx create-next-app@latest
```

In the options make sure to chose the following

```shell
What is your project named?  [your team name comes here]
Would you like to use TypeScript?  No
Would you like to use ESLint?  Yes
Would you like to use Tailwind CSS?  No / Yes [This is optional]
Would you like to use `src/` directory?  Yes
Would you like to use App Router? (recommended)  No
Would you like to customize the default import alias?  Yes
```

The above steps will take care of steps 1, 2, and 3. Now lets go to the next point.

2. Prettier
Prettier is used to enforce a certain coding format. This way everyone codes in the same code style which creates consistency in the project.

```shell
npm install --save-dev prettier
```

Create a new file called `.prettierrc.js` and put the following inside of it

```js
module.exports = {
  semi: false,
  singleQuote: false, // Do you want to use double or single quotations?
  trailingComma: 'all',
}
```

Add the following to `package.json` in the script property

```js
    "scripts": {
      ..., // [DONT COPY THIS LINE] Previous scripts
        "format": "prettier --check --ignore-path .gitignore .",
        "format:fix": "prettier --write --ignore-path .gitignore ."
      ..., // [DONT COPY THIS LINE] Next scripts
    }
```

3. Commitizen + Commitlint
Commitizen and Commitlint are used to force correct code commit messages in the project.
