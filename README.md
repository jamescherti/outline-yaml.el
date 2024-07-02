# outline-yaml.el - Emacs package: Outline and Code folding for YAML files

The `outline-yaml.el` Emacs package provides a minor mode for Emacs that enables **code folding and outlining for YAML files**. It leverages the built-in `outline-minor-mode` to provide a structured view of YAML files, allowing users to fold and unfold YAML files.

This package helps when editing long and complex YAML files, which makes code folding becomes an invaluable tool because it is allowing the collapse and expansion of sections of the file and enhancing readability and navigation.

![](https://raw.githubusercontent.com/jamescherti/outline-yaml.el/main/.screenshot.png)

## Installation

### Install using straight

To install the `outline-yaml` using `straight.el`:

1. Install and configure [yaml-mode](https://github.com/yoshiki/yaml-mode) or `yaml-ts-mode`.

2. If you haven't already done so, [add the straight.el bootstrap code](https://github.com/radian-software/straight.el?tab=readme-ov-file#getting-started) to your init file.

2. Add the following code to your Emacs init file:
```
(use-package outline-yaml
  :ensure t
  :straight (outline-yaml
             :type git
             :host github
             :repo "jamescherti/outline-yaml.el")
  :hook
  ((yaml-mode . outline-yaml-minor-mode)
   (yaml-ts-mode . outline-yaml-minor-mode)))
```

## Usage

To start using outline-yaml.el, enable the minor mode in your YAML buffer:

```
(outline-yaml-minor-mode)
```

You can also enable it automatically for all YAML files by adding the following to your Emacs configuration:

```
(yaml-mode . outline-yaml-minor-mode)
(yaml-ts-mode . outline-yaml-minor-mode)
```

Once enabled, you can use the standard `outline-mode`/`outline-minor-mode` commands to fold and unfold sections of your YAML file.

## How to customize the Ellipsis (...)?

The built-in Emacs outline-mode and outline-minor-mode allow structuring documents with collapsible sections. By default, these modes use an ellipsis (“…”) to indicate folded text.

However, you might want to customize this ellipsis to better suit your needs. Here is an example of how to change the ellipsis in both outline-mode and outline-minor-mode to ▼:
```
(defun my-set-standard-display-table-ellipsis (ellipsis)
  "Set the standard display table ellipsis to ELLIPSIS."
  (let* ((face-offset (* (face-id 'shadow) (lsh 1 22)))
         (value (vconcat (mapcar (lambda (c) (+ face-offset c)) ellipsis))))
    (set-display-table-slot standard-display-table 'selective-display value)))

(my-set-standard-display-table-ellipsis " ▼")
```

Customizing the ellipsis in outline-mode and outline-minor-mode is a simple yet effective way to personalize your Emacs and create a more visually appealing way to handle folds.

## How to change the Ellipsis ("...") to (▼)?

If you want to make the ellipsis of `outline-yaml-mode` look like the screenshot above (▼), use the code snippet in this article: [Changing the Ellipsis (“…”) in outline-mode and outline-minor-mode.](https://www.jamescherti.com/emacs-customize-ellipsis-outline-minor-mode/).

## License

Copyright (C) 2024 [James Cherti](https://www.jamescherti.com)

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program.

## Links

- [outline-yaml.el @GitHub](https://github.com/jamescherti/outline-yaml.el)
