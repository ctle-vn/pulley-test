# ShakeSearch Challenge

Welcome to the Pulley Shakesearch Challenge! This repository contains a simple web app for searching text in the complete works of Shakespeare.

## Prerequisites

To run the tests, you need to have [Go](https://go.dev/doc/install) and [Docker](https://docs.docker.com/engine/install/) installed on your system.

## Your Task

Your task is to fix the underlying code to make the failing tests in the app pass. There are 3 frontend tests and 3 backend tests, with 2 of each currently failing. You should not modify the tests themselves, but rather improve the code to meet the test requirements. You can use the provided Dockerfile to run the tests or the app locally. The success criteria are to have all 6 tests passing.

## Instructions

<img width="404" alt="image" src="https://github.com/ProlificLabs/shakesearch/assets/98766735/9a5b96b5-0e44-42e1-8d6e-b7a9e08df9a1">

---

**Do not open a pull request or fork the repo**. Use these steps to create a hard copy.

1. Create a repository from this one using the "Use this template" button.
2. Fix the underlying code to make the tests pass
3. Include a short explanation of your changes in the readme or changelog file
4. Email us back with a link to your copy of the repo

## Running the App Locally

This command runs the app on your machine and will be available in browser at localhost:3001.

```bash
make run
```

## Running the Tests

This command runs backend and frontend tests.

Backend testing directly runs all Go tests.

Frontend testing run the app and mochajs tests inside docker, using internal port 3002.

```bash
make test
```

Good luck!

## Test Fixes:

### Backend:

1. Case Sensitive: Search function was case sensitive, which failed the test case since the text did not match the exactly.

Fix: Modified the Load function to convert the complete works to lowercase when loading the file. The search query is also converted to lowercase in the Search function.

2. Too many results: The search returned too many results, in TestSearchDrunk case.

Fix: Implemented a limitResults function to restrict the number of results to a maximum of 20, addressing the specific test case requirements.

### Frontend:

1. Problem: The test case 'should return search results for "romeo, wherefore art thou"' was not passing.

Fix: This issue was addressed by modifying the backend Go code. The change ensured that the search functionality could correctly handle and return results for specific queries like "romeo, wherefore art thou".

2. Problem: The test 'should load more results for "horse" when clicking "Load More"' was failing.

Fix: Resolved by updating the Go backend to support a new page query parameter, thereby enabling paginated results.
