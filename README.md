# typescript-build-check-workflow

Sample Github Action workflow to guarantee TypeScript code has been built in PR.

## Usage

Put the [ts-build-check.yml file](./ts-build-check.yml) in your .github directory. Modify the steps under to fit your project. `Clone and Build Pull Request` should install all dependencies for your project (it currently uses npm). It can be easily modified to fit your project's dependency installation process. `Compare Built Directories` checks the out of your repo's TypeScript build. Modify the `diff` command path to match your output directory. The example's TypeScript is compiled to a root-level `lib` directory in the repo.

## Planned Updates

- Fix comment on other step failing bug
- Shorten `diff` flags (figure out which ones are key)
