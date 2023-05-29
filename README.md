# GitHub Tracker Application

The app is meant to facilitate software delivery tracking through analysis of the data about the _volume_, _category_
and _speed_ of changes applied to the codebase stored in GitHub.

The app illustrates the answers to the following questions:

- How many changes an engineer is making per day in terms of the number of commits and lines of code (LoC) changed?
- What is the "feature size", i.e. how many commits and LoC changed compose a pull request (PR)?
- How often a PR gets opened?
- How long does it take to comment a PR?
- How long does it take to approve PR?
- How long does it take to merge PR?

The application extracts, aggregates and reports the metrics broken down by the GitHub user, repository and date.

## Dimensions

### User-based

- Date
- UserID
- RepositoryID
- Number of commits
- LoC added
- LoC removed

### Repository-based

- UserID
- RepositoryID
- PrID
- TimestampOpened
- TimestampFirstComment
- TimestampApprove
- TimestampResolved (closed, or merged)

## The Architecture

- Runs on GitHub runner
- Is triggered by GitHub Action, schedule workflow
- Calls GitHub API using RestAPI and GraphQL API
- Stores the reports to GitHub as raw data, and dashboard images
