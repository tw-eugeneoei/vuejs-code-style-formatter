# vuejs-code-style-formatter

Base skeleton repository for Vue3 project with automated code style formatter using [pre-commit](https://pre-commit.com/).

# Getting Started

1. Clone repository
2. Run `brew install pre-commit`
3. In root folder of repository, run `pre-commit install`
 <!-- 4. In root folder of repository, run `npm run setup` -->

# Recommended IDE Setup

-   Recommended to use VSCode as your IDE for development
-   Install following extensions:
    -   TypeScript Vue Plugin (Volar)
    -   Vue Language Features (Volar)
    -   Prettier - Code formatter

You can consider creating a `settings.json` file in `.vscode` folder and use these configuration for your development.

```json
{
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "[vue]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[javascript]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    }
}
```

# Notes

During the pre-commit hook phase, if there are files that have been reformatted by Prettier due to code styles issues, you will see a warning like this:

```bash
> vuejs-code-style-formatter@0.0.0 format
> prettier --write -c .

Checking formatting...
[warn] src/App.vue
[warn] src/components/__tests__/HelloWorld.spec.ts
[warn] Code style issues found in 2 files. # ---> this !!!
```

The files that have been reformatted by Prettier will **NOT** be staged. You will have to stage these files and commit again. This is the intended behaviour. See response by author of `pre-commit` [here](https://stackoverflow.com/questions/64309766/prettier-using-pre-commit-com-does-not-re-stage-changes#answers). So do take note whenever you make a commit.
