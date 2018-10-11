# lambda-depdock
Simple Ubuntu container with stuff in it to make dependencies for Lambda

## Usage
`docker run -v <directory with your code>:/working -it --rm wahlfeld/lambda-depdock`

`pip install -t . <library>`

### For example
`docker run -v /Users/Curtis/projects/gkeep-evernote-sync/lambda/code/:/working -it --rm lambda-depdock`

`pip install -t . gkeepapi \
evernote \
textile`