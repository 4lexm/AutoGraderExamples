[![Build Status](https://travis-ci.org/AgileVentures/AutoGraderExamples.png)](https://travis-ci.org/AgileVentures/AutoGraderExamples)

AutoGraderExamples
==================

Example Assignments for Use with the Ruby AutoGrader

**Usual platform:** linux or mac, ruby 1.9.3, git

### **Install:**
- Fork on github, clone it, and cd there.
- install ruby '1.9.3' with rvm and `rvm use` use it
- `git checkout develop` or consider it for the latest.
- `gem install cucumber`
- `gem install rspec`
- `bundle install`
- `cucumber install`

#### **Git-immersion Note:** For deployment, and feature tests using Octokit.client over 60/hr, you must do this!
- The OAuth ENV var `GIT_IMMERSION_TOKEN` used in mvp_spec.rb allows 5000/hr rate limit, whereas anonymous Octokit calls allow 60/hr.
- If not set, it will try to use anonymous connect. Pull requests from forks to AgileVentures/AutoGraderExamples are detected and try to use the anonymous connect.

#### To gain access to a higher rate limit:
- Generate the token on GitHub > Settings > Applications > Personal API Token with **Zero Scopes**. Uncheck all boxes to allow only read access of public data.
- For production deployment and Your local, it is set by admin (you?), eg in /etc/environment and start a new shell.
- For travis CI, it has been encrypted and added to .travis.yml under env:global:secure
- It is encrypted with `gem install travis && travis encrypt GIT_IMMERSION_TOKEN=<a token>`

### **Run:**
- `cucumber` runs a feature per homework.
- `cucumber features/git_immersion_testing.feature` runs a single feature.

==================

**Directories:**
- git-immersion: homework added by instructor
  - autograder: tests run on student submissions, one per courseware section
  - public: skeletons and readmes included in courseware
  - solutions: instructor answers to homework problems, one with full score
- features: integration testing features, one per homework added by instructor
  - step_definitions: one per feature with similar name
- install: autograder installer infrastructure

**Naming conventions:**
 - top-level homework directory: 'boxcar-case'
 - integration features: 'snake_case' ending in 'testing'
