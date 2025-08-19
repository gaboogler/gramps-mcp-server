# Gramps MCP Server for Gramps
## Using Gramps Web.

[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/flask-2.0%2B-green)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)

---

## Overview

This project is a **custom Flask-based MCP (Modular Control Point) Server** designed to serve as an intelligent proxy for the [Gramps Web API](https://gramps-project.org/), the premier open-source genealogy platform.

The key feature of this server is **automatic access token renewal**, allowing seamless, uninterrupted interaction with Gramps Web API endpoints for genealogical data management.

---

## Why This Matters

Gramps Web provides robust genealogical data management through a RESTful API, but managing API tokens and secure authentication can be cumbersome for developers.

This MCP Server acts as a **middleware layer to abstract token handling** including:

- Transparent authentication with token fetching and renewal on expiration
- Proxying of CRUD operations for all major Gramps objects (`people`, `families`, `events`, `places`, `sources`, `citations`, `repositories`, `media`, `notes`)
- Added convenience endpoints such as `search` and metadata access
- Simplifies integration for client applications by exposing a consistent and easy-to-use Flask endpoint interface

---

## Features

- **Auto-refresh of expired access tokens** without developer intervention
- Dynamic route generation for all standard Gramps Web API resources
- Full CRUD support (`GET`, `POST`, `PUT`, `DELETE`)
- JSON request/response compliance
- Detailed error handling with informative messages
- Search and metadata proxy endpoints built-in
- Easy environment configuration with `.env` support for credentials and API URLs

---

## Installation

1. Clone the repository

```
git clone https://github.com/yourusername/gramps-flask-mcp-server.git
cd gramps-flask-mcp-server
```

2. Create and activate a Python virtual environment

```
python -m venv venv
source venv/bin/activate       # Linux/macOS
venv\Scripts\activate          # Windows
```

3. Install dependencies

```
pip install -r requirements.txt
```

4. Create a `.env` file with the following variables:

```
GRAMPS_API_URL=http://your-gramps-web-instance/api
GRAMPS_USER=your_username
GRAMPS_PASSWORD=your_password
```

---

## Usage

Run the Flask server:

```
python app.py
```

This will start the Flask MCP Server locally, usually on `http://127.0.0.1:5000`.

You can now interact with it, for example:

- Fetch all people: `GET /people`
- Search genealogies: `GET /search?q=Smith`
- Fetch metadata: `GET /metadata`

The server automatically handles token authentication and renews tokens when they expire.

---

## Contribution

This project is built to serve the Gramps Community and welcomes contributions! Whether you want to add features, improve documentation, or fix bugs, your input is valuable.

- Fork the repo
- Create a feature branch
- Submit a pull request

---

## License

This project is licensed under the MIT License.

---

## Acknowledgments

- [Gramps Project](https://gramps-project.org/)
- Flask, Requests, python-dotenv communities

---

Thank you for supporting open-source genealogy software!

---

*If you have questions or want to share your integration with Gramps Web using this MCP Server, feel free to open an issue or start a discussion.*
