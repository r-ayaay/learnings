#sail #docker #laravel 
By default, to run Sail commands, the line **_vendor/bin/sail_** should precede the commands. We can, however, configure a bash alias that’s just one word to make our commands shorter.

Basically, we’ll replace the line **_vendor/bin/sail_** with a word **_sail_**:
_alias sail='bash vendor/bin/sail'_

Run all the containers in docker-compose.yml
_sail up_

Start containers in bg
_sail up -d_

Once your application is up and running, you can visit [http://localhost](http://localhost/) to view it.

To stop the containers, press Control + C on your keyboard. If they are running in the background, then run:
_sail down_