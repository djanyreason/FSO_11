In a hypothetical situation where we have an application developed in
Ruby being worked on by a team of about 6 people, that is in active
develoopment and will be released soon:

What are the specific tools for linting, testing, and building in the
Ruby environment?

- Linting: RuboCop is widely used and seems to be standard
- Testing: RSpec is good for unit tests, and with a small team
  ought to be fine. If there is a particularly hands-on clinet, it
  may be wise to also use Cucumber for integration testing.
- Building: Ruby is an interpreted language, so there is no need
  for a build step. However, Capistrano is a useful tool for
  automating deployment.

What alternatives are there to set up the CI besides Jenkins and
GitHub Actions?

- CircleCI is a common and popular cloud-based alternative

Would this setup be better in a self-hosted or a cloud-based
environment? Why? What information would you need to make that
decision?

- In all likelihood, this would be better in a cloud-based
  environment. This is a small development team and Ruby doesn't
  inherently require any special requirements. Devoting resources to
  configuring and managing a self-hosted CI setup would require a
  significant percentage of the available person-hours, and is not
  justifiable in a team of this size.
- If the project had particular security concerns, hardware
  requirements, or other special considerations a self-hosted CI
  setup might be necesary.
