# typescript-build-check-workflow

Github workflow to guarantee TypeScript code has been built in a pull request.

This has a few clear advantages:

- Code doesn't have to be reviewed twice (TypeScript and compiled JavaScript)
- Compiled JavaScript need to be completely reviewed since we know whether the TypeScript has been compiled (compiled JavaScript is often difficult to read)
- Catches the common error of not compiling to TypeScript before a pull request
- Prevents a malicious actor from slipping extra code into the "compiled" JavaScript undetected

## Usage

Copy the [ts-build-check.yml file](./ts-build-check.yml) to your `.github` directory. Modify the steps under to fit your project.

`Clone and Build Pull Request` should install all dependencies for your project (it currently uses npm). It can be easily modified to fit your project's dependency installation process.

`Compare Built Directories` checks the out of your repo's TypeScript build. Modify the `diff` command path to match your output directory. The example's TypeScript is compiled to a root-level `lib` directory in the repo.

The comment left on failed PRs can be modified under the `body` section of the `Comment Unbuilt TypeScript` step.

## Planned Updates

- Shorten `diff` flags (figure out which ones are key)
