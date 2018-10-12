# lambda-depdock
Simple Ubuntu container with stuff in it so you can easily obtain compatible dependencies for Lambda

## Usage
Say that you're currently working in directory with your Lambda function(s) in it on your laptop (something like `~/repo/code/`). To obtain your function dependencies and ensure they're compiled properly for Lambda just run:

`docker run --mount type=bind,source="$(pwd)",target=/working -it --rm wahlfeld/lambda-depdock`

This will run a container and plop you in a directory called `/working/` which is mounted to your present working directory (so in this example that would be `~/repo/code/`). You you should see your function(s) in there.

Now  install your packages (for example in Python):

`pip install -t . package1 \
package2 \
package3`

Because you're inside an Ubuntu container, the packages will be installed/compiled for Ubuntu which is compatible with Amazon Linux (the contains the Lambda functions run on).

Finally you can .zip them up and when you exit the container you'll have a .zip ready to be pushed to Lambda:

`zip -r lambda.zip *`
