# Contributing guidelines to Awesome jQuery

Contributing to this project is very simple. You can open an [issue](https://github.com/petk/awesome-jquery/issues).

Pull requests are welcome as well:

* Fork this project over GitHub

* Set up your repository and set a remote branch for potential future updates

  ```bash
  $ git remote add upstream git://github.com/petk/awesome-jquery.git
  $ git config branch.master.remote upstream
  ```

  That way you can update your repository (when the `upstream` gets updated) and automatically pull `upstream` commits:

  ```bash
  $ git pull
  ```

* Create a new Git branch for instance `patch-1`:

  ```bash
  $ git checkout -b patch-1
  ```

  This ensures that your repository will not need rebasing when the `upstream` gets updated.

* Make changes to the `patch-1` branch

  Changes should include libraries or resources that are in a way related to [jQuery](http://jquery.com/).
  It would be nice if added plugins meet [plugin's guidelines](awesome-plugin.md). Fixing typos and grammatical
  corrections are perfectly fine as well.

* Commit and push to your GitHub repository

  ```bash
  $ git add .
  $ git commit -m "my new changes"
  $ git push origin
  ```

* Send a pull request
