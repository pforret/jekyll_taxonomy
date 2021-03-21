![bash_unit CI](https://github.com/pforret/jekyll_taxonomy/workflows/bash_unit%20CI/badge.svg)
![Shellcheck CI](https://github.com/pforret/jekyll_taxonomy/workflows/Shellcheck%20CI/badge.svg)
![GH Language](https://img.shields.io/github/languages/top/pforret/jekyll_taxonomy)
![GH stars](https://img.shields.io/github/stars/pforret/jekyll_taxonomy)
![GH tag](https://img.shields.io/github/v/tag/pforret/jekyll_taxonomy)
![GH License](https://img.shields.io/github/license/pforret/jekyll_taxonomy)
[![basher install](https://img.shields.io/badge/basher-install-white?logo=gnu-bash&style=flat)](https://basher.gitparade.com/package/)

# jekyll_taxonomy

Generate a separate page for each tag/category/author/... pages for Jekyll static site generator (e.g. got Github Pages)

## 🚀 Installation

with [basher](https://github.com/basherpm/basher)

	$ basher install pforret/jekyll_taxonomy

or with `git`

	$ git clone https://github.com/pforret/jekyll_taxonomy.git
	$ cd jekyll_taxonomy

## 🔥 Usage
```
Program: jekyll_taxonomy 0.1.1 by peter@forret.com
Updated: Mar 21 14:36:09 2021
Description: Generate tag and category pages for Jekyll SSG
Usage: jekyll_taxonomy [-h] [-q] [-v] [-f] [-c] [-l <log_dir>] [-t <tmp_dir>] [-p <post_dir>] [-y <layout_dir>] <action> <type?> <output?>
Flags, options and parameters:
-h|--help        : [flag] show usage [default: off]
-q|--quiet       : [flag] no output [default: off]
-v|--verbose     : [flag] output more [default: off]
-f|--force       : [flag] do not ask for confirmation (always yes) [default: off]
-c|--cleanup     : [flag] clean the output folder first [default: off]
-l|--log_dir <?> : [option] folder for log files   [default: /Users/pforret/log/jekyll_taxonomy]
-t|--tmp_dir <?> : [option] folder for temp files  [default: .tmp]
-p|--post_dir <?>: [option] input folder with Jekyll posts  [default: _posts]
-y|--layout_dir <?>: [option] folder with Jekyll layouts  [default: _layouts]
<action>         : [parameter] action to perform generate/check/update
<type>           : [parameter] tag/category/author/... (optional)
<output>         : [parameter] output folder [default: /<type>] (optional)
### TIPS & EXAMPLES
* use jekyll_taxonomy generate tag to generate all tag documents
* use jekyll_taxonomy check to check if this script is ready to execute and what values the options/flags are
* use jekyll_taxonomy env to generate an example .env file
* use jekyll_taxonomy update to update to the latest version
* >>> bash script created with pforret/bashew
```

## 🔥 Examples

* `jekyll_taxonomy generate tag`: generate a tag index page for each unique tag defined by `tag:` or `tags:` in your posts' front matter. All tags are lowercase and slugified (Apple -> apple, FIRST TRY! -> first-try). The index page will list all _posts with that tag, with a title, date and excerpt. Also, a layout `with_tag` is created in `_layouts` and a index page `index.html`, listing all tags, is created in the `tag` folder.
* `jekyll_taxonomy -p _products -y _templates generate age age_group`: generate an age index page in the folder _`age_group` for each unique age group defined by `age:` or `ages:` in your products' front matter. All tags are lowercase and slugified (Adult -> adult, Baby Girl -> baby-girl). Also, a layout `with_age` is created in `_templates` and an index page `index.html` is created in the `age_group` folder.
* `jekyll_taxonomy -c generate category`: first remove all .md pages from the category folder and then recreate them from the posts (defined by `category:` and `categories:`in the front matter). Useful when categories (could) have disappeared because e.g. some posts were deleted or categories were renamed.
* `tag/index.html` can be modified to e.g. separate tag listing on 1st letter, or use a Bootstrap/Tailwind specific layout
* `_layouts/with_tag.html` can be modified to e.g. remove the excerpt or make it longer, to add the author, or use a Bootstrap/Tailwind specific layout

## 📝 Acknowledgements

* script created with [bashew](https://github.com/pforret/bashew)

&copy; 2021 Peter Forret
