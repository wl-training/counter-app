counter-app
============
Simple flask app that counts web site visits and stored in a default Redis backend. This example is taken from the book "Docker Deep Dive" by Nigel Poulton. It's a nice and up to date book about docker, if you want to know more about docker I recommend reading it ;).

Step 1
------
* build and run the application using `docker-compose up –d`
* notice how compose creates a (named) volume that‘s defined in the `docker-compose.yml` before creating the actual containers. You will also see that the volume‘s lifetime is independent from the lifetime of the containers
- use `docker-compose logs –f`  to attach to see what‘s going on inside the containers
- access the website (see grey button for the port 5000) and see how the counter is working (see it increasing when you refresh the page)

Step 2
------
- restart the containers, the counter should not be reset to 0
- use docker-compose down and docker-compose up again. 
- Take a look at the `docker-compose-yml` file: Why was the counter set to 0 now?

Step 3
------
- make sure all related containers are gone again (`docker-compose down`)
- list all volumes using docker and use inspect to take a look at the volume created from the compose-file
- adapt the text of the Website and start new containers. You'll see that the changed state will be used.

Step 4 (for quick people)
--------------------------
- find a way to make the counter state survive the container change :)
