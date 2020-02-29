FROM alpine:3.6

# Set up environment vars
ENV APP_DIR=/service

RUN mkdir -p $APP_DIR
WORKDIR $APP_DIR

# Install dependencies
RUN apk add --no-cache python3

RUN pip3 install pytest

RUN touch testfile.txt

# run the container
CMD tail -f /dev/null
