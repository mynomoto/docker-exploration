# SAWS image
This is a Ubuntu image with [SAWS][saws].

## Usage
To build the image:
    $ .build.sh

To run (after building):
    $ docker run -it --rm -e AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY -e AWS_DEFAULT_REGION=$AWS_DEFAULT_REGION -v $(realpath .):/project mynomoto/saws

[saws]: https://github.com/donnemartin/saws
