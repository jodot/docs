Installing Jodot
========================

There are many ways to install Jodot.

npm
---

npm is probably the simplest way::

  $ npm install -g jodot

This gets you jodot on your command-line. Obviously, you'll need to have
`npm <https://nodejs.org/en/download/>`_ to install this way.

Docker
------

A `Jodot Docker image <https://hub.docker.com/r/jodot/jodot/>`_ is available via `Docker Hub <https://hub.docker.com/r/jodot/jodot/>`_.

You can use this directly by creating a containerised environment. The following is an example of how you can do so.

1. Create your duties.hjson file defining the duties that you will want Jodot to run.

2. Create a Dockerfile in the same directory, this is similar to::

    FROM jodot/jodot

    ENV APP_DIR ~/src
    COPY . $APP_DIR

    WORKDIR ${APP_DIR}

    ENTRYPOINT ["jodot", "duties.hjson"]

3. Build and run the container in the background::

    $ docker build -t my_jodot .

    $ docker run -d my_jodot
