
## About Bookdocker

Bookdocker is a tool that makes a Docker container that runs Bookbinder.

Bookdocker does the following:

1. Checks if Docker is installed
1. Checks that you are in a `book` directory.
1. Creates a custom container with the following:
    1. Ruby v2.3.0
    1. Your book's dependencies, including Bookbinder
1. Runs Bookbinder in the Docker container

## Prerequisites

Before you can run bookdocker, you must have Docker installed and running.

To install Docker, do the following:
- To download Docker for Mac, see [Install Docker for Mac](https://docs.docker.com/docker-for-mac/install/).
- To download Docker for Windows, see [Install Docker for Windows](https://docs.docker.com/docker-for-windows/install/).

After you install Docker, start the application and wait for Docker to indicate that it is running successfully.

## How to Install

To install bookdocker, do the following:

1. Clone the bookdocker repository.
   ```
   git clone https://github.com/pivotal-cf-experimental/bookdocker.git
   ```

1. Copy the `bookdocker` file into your executable path.
   For example:
   ```
   cp ~/workspace/bookdocker/bookdocker /usr/local/bin
   ```

## How to Update

To install updates to bookdocker, do the following:

1. Go to your bookdocker repository. For example:
   ```
   cd ~/workspace/bookdocker
   ```

1. Pull changes.
   ```
   git pull
   ```

1. Copy the `bookdocker` file into your executable path.
   For example:
   ```
   cp ~/workspace/bookdocker/bookdocker /usr/local/bin
   ``` 

## How to Run

After you installed bookdocker, do the following:

1. Go to your book directory.

1. Run bookdocker. Bookdocker takes the same commands and arguments that Bookbinder takes.

   Example 1, to watch a single repo of the book:
   ```
   bookdocker watch MY-CONTENT-REPO
   ```
   
   Example 2, to watch all the repos of the book:
   ```
   bookdocker watch
   ```
   
   **Note:** The first time you run bookdocker in a new `book` repository, the bookdocker creates the Docker image and takes a long time to execute. Bookdocker is faster in following runs.

## Troubleshooting

| Symptom | Solution |
|---|---|
| Error message `Get https://registry-1.docker.io/v2/library/ruby/manifests/2.3: unauthorized: incorrect username or password` | Enter `docker logout` and type original command again. |


## Known Issues

### Bookdocker is Slow on Mac

On large books, bookdocker is slow enough to become unusable on Mac machines. To mitigate this issue, you can do the following:
- Watch a single repository at a time. For example, run `bookdocker watch MY-CONTENT-REPO`.
- Watch small books that bind few content repos.

## License

bookdocker is licensed under the MIT license.  See the LICENSE file for more information.
