# Voting App (microservices version)

## Quick Start

Install [Docker](https://docs.docker.com/get-docker/).
This app will work with versions from either the Stable or the Edge channels.

> If you're using [Docker for Windows](https://docs.docker.com/docker-for-windows/) on Windows 10 pro or later, you must also switch to [Linux containers](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).

In the project's root directory, run:

    $ docker-compose up

You can test it with the `voter` CLI:

```
$ docker run -it --rm --network=host subfuzion/voter vote
? What do you like better? (Use arrow keys)
  (quit)
❯ cats
❯ dogs
```

You can print voting results:

```
$ docker run -it --rm --network=host subfuzion/voter results
Total votes -> cats: 0, dogs: 1 ... DOGS WIN!
```

When you are finished:

Press `Ctrl-C` to stop the stack, then enter:

    $ docker-compose -f docker-compose.yml rm -f

### Docker Swarm

You can also run it on a [Docker Swarm](https://docs.docker.com/engine/swarm/).
If you haven't initialized one yet, run:

    $ docker swarm init

Once you have initialized a swarm, then deploy the stack:

    $ docker stack deploy --compose-file docker-stack.yml vote

You can test it the same way as described for docker-compose. When finished, you
can stop the stack by entering:

    $ docker stack rm vote

## About the Voting App

![Voting app architecture](https://raw.githubusercontent.com/subfuzion/voting-app/master/images/voting-app-arch-1.1.png)

This app is based on the original [Docker](https://docker.com) [Example Voting App](https://github.com/dockersamples/example-voting-app).

For an orientation, see this [presentation](http://bit.ly/voting-app-with-docker).

## License

The Voting App is open source and free for any use in compliance with the terms of the
[MIT License](LICENSE).
