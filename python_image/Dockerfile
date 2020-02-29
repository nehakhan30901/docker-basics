FROM python:2

# installing a dependency
RUN pip install pytest

# copying source code
ADD hello_world.py /

# run the container
CMD ["python",  "hello_world.py"]