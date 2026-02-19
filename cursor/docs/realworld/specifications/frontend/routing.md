# Routing

**Home page** (URL: `/`)

- Pagination for list of articles
- List of articles pulled from either Feed, Global, or by Tag
- List of tags

**Sign in/Sign up pages** (URL: `/login`, `/register`)

- Authentication can be easily switched to session/cookie based
- Uses JWT (store the token in localStorage)

**Article page** (URL: `/article/article-slug-here`)

- Delete comment button (only shown to comment's author)
- Comments section at bottom of page
- Render markdown from server client side
- Delete article button (only shown to article's author)

**Profile page** (URL: `/profile/:username`, `/profile/:username/favorites`)

- List of articles populated from author's created articles or author's favorited articles
- Show basic user info
