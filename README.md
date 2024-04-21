# POOGO 💩
Hugo's stinky step-son who won't stop leaving his Markdown on your browser!
Yuck!

A small static site generator for a simple personal blog that utilizes Github's
Markdown to HTML API.

## Usage

Bootstrap a blog skeleton:
```sh
poogo -b -p <path to blog dir>
# edit config.env file (for RSS support only)
```

Add a post:
```sh
cd <path to blog dir>
poogo -n post1
```

Generate HTML:
```sh
cd <path to blog dir>
poogo -g
```

## Local Dev

Start a webserver in the target dir:

```sh
cd test && python -m http.server 8080
```

Modify Markdown files, then regenerate...

### Timestamp Conversion

#### From Hugo
```sh
sed -rn 's/^date: (.*)/\1/p' *.md | xargs -i date -d {} +%s
```

#### From Org
```sh
sed -rn 's/#\+date: <(.*)>/\1/p' *.org | xargs -i date -d {} +%s
```

### Caveats
- Github markdown API mangles up unicode chars
