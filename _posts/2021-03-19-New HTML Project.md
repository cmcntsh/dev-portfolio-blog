---
layout: post
comments: false
title: Start a New HTML Project in GitHub with VSCode
categories: [GitHub, HTML]
---

# Create a new repository in GitHub.

- GitHub - Repositories - New
- Name your repository
- Make the repository public (to be able to use GitHub Pages later)
- Add a README file

![New Repository](/assets/images/GHCreateNew.png)

# Clone your new repository with VSCode

- GitHub - Navigate to your repository - Code - Clone - Click on the clipboard icon to copy the path for your repository

![Clone](/assets/images/GitHubZip.png)

- VSCode - View - Command palette... - Git:Clone - paste the path into the dialog box - Enter - Navigate to where you want repository - Select Repository Location - Open

# Add files to your project with VSCode

- Add index.html, style.css, script.js files for a basic project.
- Hover over the name of your new repository and select New File from the options that appear next to the name.

![New File](/assets/images/VSCNewFile.png)

- Type out the complete name of the new file, including the file extension. Repeat this for each file.
  - index.html
  - style.css
  - script.js

- Add the following code to your .html file to include the .css and .js files in the page.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Document</title>
</head>
<body>
    
    <script src="script.js"></script>
</body>
</html>
```

# Push your changes to GitHub

- VSCode - Click on the Source Control icon on the left 
- Enter a commit message in the Message field right under the SOURCE CONTROL heading.
  - Something like "First Commit" or "Add Files" should be fine.

![New File](/assets/images/VSCcommit.png)

- Click on the Commit checkmark next to the SOURCE CONTROL heading.

![New File](/assets/images/VSCMoreActions.png)

- Click on the three dots next to the SOURCE CONTROL heading for Views and More Actions.
- Select Pull, Push - Sync

![New File](/assets/images/VSCsync.png)

- Give the application a few seconds to do its work.
- This will pull any new items from your GitHub repository and push any new changes you made to your remote repository.

# Turn on GitHub Pages



Keeping this as a nice demo.

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
