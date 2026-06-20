**CONTRIBUTING Guide (Simple Urdu + English technical terms)**

- Use simple Urdu explanations while keeping technical terms in English.
- Provide copy-paste-ready code snippets.
- Follow industry best practices for MERN projects.

**Quick Project Structure (recommended)**

- server/
  - package.json
  - server.js
  - routes/
  - models/
- client/
  - package.json
  - src/
    - App.js
    - index.js
- README.md

**Short Urdu guidance (نمونہ)**

- Project structure: `server` backend, `client` frontend رکھیں تاکہ code organized رہے.
- Use `git` feature branches: نیا فیچر یا bug کے لیے الگ branch بنائیں (`feature/...` یا `fix/...`).
- Write clear `commit` messages: subject line پھر body (اگر needed)۔

**Minimal `server.js` (Express + Mongoose) — copy-paste-ready**

```js
// server/server.js
const express = require("express");
const mongoose = require("mongoose");
const cors = require("cors");

require("dotenv").config();

const app = express();
app.use(cors());
app.use(express.json());

const PORT = process.env.PORT || 5000;
const MONGO_URI =
  process.env.MONGO_URI || "mongodb://localhost:27017/mern_demo";

mongoose
  .connect(MONGO_URI, { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => console.log("MongoDB connected"))
  .catch((err) => console.error("MongoDB connection error:", err));

app.get("/api/ping", (req, res) => res.json({ msg: "pong" }));

app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
```

**Minimal `package.json` for server**

```json
{
  "name": "server",
  "version": "1.0.0",
  "main": "server.js",
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js"
  },
  "dependencies": {
    "express": "^4.18.0",
    "mongoose": "^6.0.0",
    "cors": "^2.8.5",
    "dotenv": "^16.0.0"
  },
  "devDependencies": {
    "nodemon": "^2.0.0"
  }
}
```

**Minimal React `App.js`**

````jsx
// client/src/App.js
import React, { useEffect, useState } from 'react';

function App() {
  const [msg, setMsg] = useState('loading...');

  useEffect(() => {
    fetch('/api/ping')
      .then(r => r.json())
      .then(data => setMsg(data.msg))
      .catch(() => setMsg('error'));
  }, []);












































**If you want:** I can also create `README.md` starter or a small runnable MERN template repo here.4. Deploy a full MERN app (Heroku / Vercel + MongoDB Atlas).3. Learn testing: `Jest` + `React Testing Library` + backend tests.2. Add authentication with JWT and refresh tokens.1. Learn `React` advanced patterns (hooks, context, performance).**Next learning steps (Suggested)**- Keep `node_modules` out of repo; add `.gitignore`.- Write small, testable modules; add unit tests for critical logic.- Use `git` hooks: `husky` + `lint-staged` for pre-commit checks.- Add linting: `eslint` + `prettier` for consistent style.- Use environment variables (`.env`) for secrets.**Best practices (Industry standards)**- Port conflicts: change `PORT` in env or kill existing process using the port.- CORS issues: enable `cors()` in Express or set allowed origins.- Mongo connection error: verify `MONGO_URI`, ensure MongoDB running. Use `console.error(err)` to inspect.**Common errors and fixes (خلاصہ)**(If using CRA, `proxy` in client `package.json` can forward `/api` to backend in development.)```npm startnpm install```powershell- In `client`:```npm run devnpm install```powershell- In `server`:**Run locally (recommended commands)**```export default App;}  );    </div>      <p>API says: {msg}</p>      <h1>MERN Demo</h1>    <div>n  return (
````
