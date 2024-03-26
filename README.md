This repository is for exercises 11.1-11.19 in Part 11 of Full Stack Open (FSO), "CI/CD" - https://fullstackopen.com/en/part11

Exercises 11.20 and 11.21 require a separate repository, which is located here: https://github.com/djanyreason/FSO_11_20_21

This part of FSO focuses on Continuous Integration / Continuous Delivery ("CI/CD") systems, and is implemented through GitHub Actions. This project is built from a fork of a "pokedex" app repository located here: https://github.com/fullstack-hy2020/full-stack-open-pokedex

All GitHub Actions workflows are stored in /.github/workflows. Two of the files in that folder are not particularly relevant:
* hello.yml - echos 'Hello World!' as an early test exercise
* test.yml - used to test some logical statements

The remaining two files in the /.github/workflows folder are relevant for the project:
* healthCheck.yml - set up to run periodic health checks on the app deployment, and alert if there is an issue
* pipeline.yml - the primary CI/CD pipeline; it checks for appropriate linting, builds the code, checks for success at both Jest tests and end-to-end Cypress tests, then deploys to Fly.io and reports either success or failure; it also is responsible for incrementing and tagging version numbers when appropriate

The deployment is configured to require approved pull requests and successful completion of all status checks before merging. It also integrates a third-party action to push discord notifications based on deployment results.
