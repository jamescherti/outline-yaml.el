# outline-yaml.el - Outline and Code folding for Yaml files

The `outline-yaml.el` Emacs package provides a minor mode for Emacs that enables code folding and outlining for YAML files. It leverages the built-in `outline` package to provide a structured view of YAML files, allowing users to collapse and expand sections based on indentation levels.

It creates a structured view of your YAML files for better navigation and readability. You can use all the `outline-minor-mode` functions to fold and unfold sections of YAML files.

## Installation

### Install using straight

To install the `outline-yaml` using `straight.el`:

1. If you haven't already done so, [add the straight.el bootstrap code](https://github.com/radian-software/straight.el?tab=readme-ov-file#getting-started) to your init file.

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

## License

Copyright (C) 2024 [James Cherti](https://www.jamescherti.com)

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program.

## Links

- [outline-yaml.el @GitHub](https://github.com/jamescherti/outline-yaml.el)
