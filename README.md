# Alluvial Diagram Generator

## Setup

Install [yarn](https://yarnpkg.com) and execute the following in the project's
root directory to download all dependencies:

	yarn

[npm](https://www.npmjs.com/) may also be used, but doesn't respect yarn's
lock file. Download dependencies using `npm install`.

## Usage

The project directory must be hosted using a web server.

For example: The node [http-server](https://www.npmjs.com/package/http-server)

	yarn global add http-server
	# or
	npm install -g http-server

	http-server

`http-server` will serve the current directory listening on port
8080 by default (change by using the `-p <port>` flag).

Python also ships with a http server, the following serves the working
directory listening on port 8000:

	python -m SimpleHTTPServer 8000

The repository exposes two end points: `static.html` and `draggable.html`.
Both draw an alluvial diagram of the data provided in `data.json`.
Simply replace the file and reload the page to display changed data.
In some cases `data.json` is cached by the browser, in such cases a hard
reload (and cache emptying) may be necessary.

`draggable.html` displays the same diagram as `static.html`, but a bit more
interactive.


## Expected JSON Format

`data.json` is expected to have this format:

	{
		"nodes": [
			{
				"spec": "p_1_1",
				"value": 13
			},
			{
				"spec": "c_2_1"
			},
			{
				"spec": "p_2_1",
				"value": 45
			},
			...
		],
		"links": [
			{
				"source": "p_1_1",
				"target": "c_2_1",
				"value": 12
			},
			{
				"source": "c_2_1",
				"target": "p_2_1",
				"value": 12
			},
			...
		]
	}

Also see the `data.json` file in this repository for reference.
