# hakyll-template

This is an empty hakyll website template which is based on FLOLAC2018.

## build

To build this site, you need [HaskellStack](https://docs.haskellstack.org/en/stable/README/). We are using  **lts-10.5** as the working resolver here. It's kinda outdated but it can get things done without any dependency problem. If you want to use newer resolver, please change the setting in file: `stack.yaml`.

### steps

For the first time, you probably need to check if your stack env is ok.

```bash
stack steup
```

After that, you just simple build:

```bash
stack build
stack exec site build
```

For testing locally, you can also run

```bash
stack exec site watch
```

This will setup a local http server listening to `localhost:8000`.

## customize

1. To edit a current page, you don't need to rebuild the whole haskell program, just run the followinf command for updating website content.

```
stack exec site rebuild
```

2. To create a new page, you need to add a new markdown file under `content/`. If so, you need to tell hakyll how to handle it in `src/Main.hs`, Just like the `page1.md` and `page2.md`.

Hoever, if you add a new under `content/courses/`, you don't need to do it because there is already a rule for handling all files under `content/courses/`.

3. The generated site will be placed in folder: `_site`. If you want to deploy manually, just copy everything from there and paste to your github or gitlab page repo.
