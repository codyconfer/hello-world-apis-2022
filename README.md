# Hello World APIs

## Node

### app.js

```javascript
import { createServer } from 'http';
const hostname = '127.0.0.1';
const port = 3000;

const server = createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

### package.json

```json
{
  "name": "app.js",
  "version": "1.0.0",
  "description": "",
  "main": "app.js",
  "scripts": {
    "serve": "node app.js",
    "dev": "nodemon app.js"
  },
  "author": "",
  "license": "ISC",
  "type": "module",
  "devDependencies": {
    "nodemon": "^2.0.19"
  }
}
```

### Node install and run

```bash
npm i
npm run dev
```

## Python

### main.py

```python
from fastapi import FastAPI

app = FastAPI()


@app.get("/")
async def root():
    return {"message": "Hello World"}
```

### pyproject.toml

```toml
[tool.poetry]
name = "main.py"
version = "0.1.0"
description = ""
authors = ["Your Name <you@example.com>"]

[tool.poetry.dependencies]
python = "^3.10"
fastapi = "^0.79.0"
black = "^22.6.0"

[tool.poetry.dev-dependencies]

[build-system]
requires = ["poetry-core>=1.0.0"]
build-backend = "poetry.core.masonry.api"
```

### Python Install and Run

```bash
poetry install
uvicorn main:app --reload
```

## C#/.NET

### program.cs

```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "Hello World!");

app.Run();
```

### program.csproj

```csproj
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net6.0</TargetFramework>
    <Nullable>enable</Nullable>
    <ImplicitUsings>enable</ImplicitUsings>
  </PropertyGroup>

</Project>
```

### .NET build and run

```bash
dotnet watch
```