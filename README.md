## Init using flask:

1. Navigate to directory "lifi_serve"
2. Activate virtual environment

    `$ . .venv/bin/activate `

3. Install flask in the environment

    ` pip install Flask `

4. Host app w/ flask during development period

    ` export FLASK_APP = lifi_flask.py `

    `flask run --host-0.0.0.0 --port=8000`
## Copy to RPI

1. on local machine
    ` scp /path/to/local/file <username>@<pi>.local:/home/<username> `

2. Host w/ gunicorn + install dependencies

    `sudo apt-get install gunicorn`

    `gunicorn -w 4 -b 0.0.0.0:8000 lifi_flask:app `

    -w is workers, can increase for more throughput. -b is binding to an IP address on port 8000.
