# Jekyll CLF template

This repository is a starter Jekyll site that uses the
[`jekyll-clf-theme`](https://github.com/ubc-cpsc/jekyll-clf-theme).

## Local development

Install Ruby and Bundler, then install the locked dependencies:

```sh
bundle install
```

Build the site once:

```sh
bundle exec jekyll build
```

Or run the local development server:

```sh
bundle exec jekyll serve
```

The development site is available at <http://localhost:4000> by default.

## Updating dependencies

`Gemfile` defines the allowed dependency versions and `Gemfile.lock` records the
exact versions used by the project. Commit changes to both files whenever an
update changes them.

1. Start from a clean working tree and check the installed tool versions:

   ```sh
   git status --short
   ruby --version
   bundle --version
   ```

2. List updates that fit the current `Gemfile` constraints:

   ```sh
   bundle outdated --strict
   ```

3. Update all dependencies, including the Git-based theme:

   ```sh
   bundle update --all
   ```

   For a smaller change, update only the named dependency instead:

   ```sh
   bundle update DEPENDENCY_NAME
   ```

4. Review the resolved version and source changes:

   ```sh
   git diff -- Gemfile Gemfile.lock
   bundle list
   ```

5. Verify that the site still builds:

   ```sh
   bundle exec jekyll build
   ```

If a desired release is excluded by a constraint in `Gemfile`, update that
constraint deliberately, run `bundle update DEPENDENCY_NAME`, and repeat the
review and build steps. Avoid editing `Gemfile.lock` by hand.

When the installed Bundler major version changes the `BUNDLED WITH` entry in
`Gemfile.lock`, make that toolchain upgrade explicit in the change description
so other contributors and CI can use a compatible Bundler version.
