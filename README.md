# Git Static

Serve static files backed by Git.

## Installation

After running `npm install`, you'll want to initialize a bare Git repository to hold the static files:

```bash
mkdir repository
cd repository
git init --bare
```

Then, push from your source Git repository the files you want to serve:

```bash
cd ~/Development/other
git remote add static ~/Development/git-static/repository
git push static master
```

Now you can launch the server!

```bash
node node_modules/git-static/examples/server --repository repository
```

Go to <http://localhost:3000/HEAD/path/to/file.html> to view a file from the source repository. You can replace `HEAD` with a specific commit version, or with short names and aliases for commits such as "0ad4156" or "HEAD~1".
