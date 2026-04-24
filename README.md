# Node.js File Server

A simple HTTP server built with **pure Node.js** — no frameworks, no dependencies. Serves HTML pages based on the request URL and returns a custom 404 page for any unknown routes.

## Project Structure

```
node-server/
├── index.js          # Server entry point
├── index.html        # Home page
├── about.html        # About page
├── contact-me.html   # Contact page
└── 404.html          # Not found page
```

## Routes

| URL | Page |
|---|---|
| `localhost:8080` | `index.html` |
| `localhost:8080/about` | `about.html` |
| `localhost:8080/contact-me` | `contact-me.html` |
| Any other URL | `404.html` |

## Getting Started

No installation required. Node.js is the only prerequisite.

**1. Clone or download the project**

```bash
git clone <your-repo-url>
cd node-server
```

**2. Start the server**

```bash
node index.js
```

**3. Open your browser**

```
http://localhost:8080
```

## How It Works

The server uses Node's built-in `http`, `fs`, and `path` modules. Incoming request URLs are matched against a routes object:

```js
const routes = {
  "/":           "index.html",
  "/about":      "about.html",
  "/contact-me": "contact-me.html",
};
```

If the URL matches a route, the corresponding file is served with a `200` status. If not, `404.html` is served with a `404` status. Any failure to read a file returns a `500` plain-text error.

## Requirements

- [Node.js](https://nodejs.org/) v14 or higher
- No npm packages required
