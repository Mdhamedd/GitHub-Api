# GitHub User Lookup (Vanilla JS)

A minimal web app that lets you search for a GitHub username and instantly see basic profile details using the public GitHub Users API.

## Features

- Search any GitHub user by username
- Displays:
  - Avatar
  - Name and username
  - Bio (with sensible fallback)
  - Public repos, followers, following counts
  - Location, blog, Twitter handle, and company (with fallbacks)
- Simple UI with plain HTML, CSS, and JavaScript

## Demo

Open `index.html` directly in your browser, or use a local server (e.g., VS Code Live Server).

## Getting Started

1. Clone or download this repository.
2. Open the project folder.
3. Launch the app:
   - Option A: Double-click `index.html` to open in your default browser
   - Option B: Serve locally (recommended during development)
     - With VS Code: Install and use the "Live Server" extension
     - With Node (any static server works):
       ```bash
       npx serve .
       ```
4. Type a GitHub username in the input and click "Search".

## Project Structure

```
Github Api/
├─ index.html      # UI markup
├─ style.css       # Styling
└─ index.js        # Fetch + render GitHub user details
```

## How It Works

- `index.js` reads the username from the input and calls:
  - `GET https://api.github.com/users/{username}`
- On success, it renders profile details into the page and makes the details section visible.
- On failure (e.g., user not found), it shows the API error message.

## API Notes

- Unauthenticated requests to the GitHub API are rate-limited (about 60 requests/hour per IP).
- If you hit the limit, try again later or add authentication.
- To add a token (optional), include an `Authorization: Bearer <TOKEN>` header in the fetch.

## Browser Support

- Works in all modern browsers. No build tools or transpilers required.

## Possible Enhancements

- Show recent repositories or pinned repos
- Add dark/light theme toggle
- Add loading and error states inline (instead of alert)
- Link to the user’s blog, Twitter, and company pages when available
- Input debouncing and pressing Enter to search

## License

MIT
