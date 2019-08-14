# Template for W3C Working Group home page

## What is it?

This is a template for a W3C Working Group. It follows the style of the Working Group pages that are used these days; the special features are:

* The page is fully [jekyll](https://jekyllrb.com/) based. What this means in practice that the content of the pages are in Markdown (more exactly, a variant called [“Kramdown”](https://kramdown.gettalong.org/syntax.html)); it is therefore easy to update and change for all WG members who have the right to do so.
* The page incorporates the usage of my own minute generating tool called [scribejs](https://github.com/w3c/scribejs). This means that the minutes are fully integrated into pages, i.e., are also in Kramdown.

An example for an active Working Group using an earlier version of this template: [JSON-LD WG Home page](https://www.w3.org/2018/json-ld-wg/)


## Using the template

The template is meant to be cloned for a new Working Group and used to set up as the Workshop's home page through the suitable modification of the content. Here are some notes on adapting the content:

- The template is to be used in conjunction with [jekyll](https://jekyllrb.com/). This means that the main content of the pages are provided in Markdown (to be more precise, a dialect called [“Kramdown”](https://kramdown.gettalong.org/syntax.html)), and jekyll converts those on the server side into a static Web site. You can install jekyll locally (which is probably a good idea for testing), but the best way of deploying the website is to keep it as a github repository, turning on the `Settings/Github Pages` option. Jekyll is automatically ran by github, and the Web site will be available as a `https://w3c.github.io/yourreponame/index.html` (provided that cloned repository is kept within the W3C organization).
- The jekyll site generation is based on template HTML files in the `_layouts` folder, and may refer to html snippets in the `_includes` folder. They can probably run out of the box, but your taste might differ
- You must use a bona fide W3C URL for the Working Group; this can be done by setting a redirection to the `github.io` page. Do a `curl` on, for example, `https://www.w3.org/2018/json-ld-wg/.htaccess` for a pattern.
- A number of variables should be set in the `_config.yml` file; these are then re-used in the template to set things like the WG mailing list names. If the default results do not work for you, you will have to go into the files above to modify them. These variables are:
  - `baseurl`: the "path" part of the WG's final (W3C) home page address. Note that this URL is used to, e.g., refer to the css files and the js files in the HTML headers (otherwise one gets problems).
  - `groupid`: the identification number of the Working Group, set ad the creation time of the WG by the system team. Used for, e.g., setting the URL for the Patent Policy. Should also be used for the `w3c.json` file.
  - `charter`: the "path" part of the WG's final charter
  - `wgname_lc`: WG's name in lower case form; used to set, e.g., the mailing list names and archive URL-s
  - `wgname_uc`: WG's name in Upper Case form; used to set, e.g., the titles
  - 'mission': The short mission statement of the WG; set in the preambles of the pages.
  
  These variables do _not_ handle all necessary changes. Look for the `TBD` string in the files... Also, these variable do not affect the accompanying files like `w3c.json`, `README.md`, etc; you should check them.


## Testing locally

The repository content (or a clone thereof) can be tested locally by running [jekyll](https://jekyllrb.com/) locally (see [jekyll's start docu](https://jekyllrb.com/docs/)). Note that running jekyll locally requires the presence of the `Gemfile` and `Gemfile.lock` files which are generated when initializing a local jekyll site. Because these files are usually put on the `.gitignore` (or `~/.gitignore_global`) files (ie, they are ignored by git), a "template" versions of these files have been put on the repository if you want to bypass the "official" installation steps.

# Acknowledgement

This template evolved a lot when used for the JSON-LD Working Group, thanks to the contributions of Benjamin Young, and also some text from Rob Sanderson. Thanks for that!

---

Ivan Herman, ivan@w3.org
