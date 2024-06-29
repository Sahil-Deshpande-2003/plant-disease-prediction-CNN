# This sets up the container with Python 3.10 installed.
FROM python:3.10-slim 
# This specifies the base image for the container, which is a lightweight version of Python 3.10. The slim version is chosen to keep the container size small.

# This copies everything in your current directory to the /app directory in the container.
COPY . /app

# This sets the /app directory as the working directory for any RUN, CMD, ENTRYPOINT, or COPY instructions that follow.
WORKDIR /app

# This runs pip install for all the packages listed in your requirements.txt file.
RUN pip install -r requirements.txt

# This tells Docker to listen on port 80 at runtime. Port 80 is the standard port for HTTP.
EXPOSE 80
# This informs Docker that the container will listen on port 80 at runtime. This is the standard port for HTTP traffic

# This command creates a .streamlit directory in the home directory of the container.
RUN mkdir ~/.streamlit

# This copies your Streamlit configuration file into the .streamlit directory you just created.
RUN cp config.toml ~/.streamlit/config.toml

# Similar to the previous step, this copies your Streamlit credentials file into the .streamlit directory.
RUN cp credentials.toml ~/.streamlit/credentials.toml

# These commands copy config.toml and credentials.toml into the .streamlit directory. These files configure Streamlit settings and credentials.

# This sets the default command for the container to run the app with Streamlit.
ENTRYPOINT ["streamlit", "run"]

# This command tells Streamlit to run your app.py script when the container starts.
CMD ["main.py"]

# This tells Streamlit to run the main.py script when the container starts. main.py should contain the code for your Streamlit application.
