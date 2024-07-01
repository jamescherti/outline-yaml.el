# outline-yaml.el - Outline and Code folding for Yaml files

The `outline-yaml.el` Emacs package provides a minor mode for Emacs that enables code folding and outlining for YAML files. It leverages the built-in `outline` package to provide a structured view of YAML files, allowing users to collapse and expand sections based on indentation levels.

![](https://raw.githubusercontent.com/jamescherti/outline-yaml.el/main/.screenshot.png)

## Features

- Code Folding: Collapse and expand sections of YAML files based on indentation, helping you to focus on the parts of the file that matter most at any given time.
- Outlining: Create a structured view of your YAML files, enhancing readability and making it easier to navigate through different sections.
- Seamless Integration: Works seamlessly with Emacs' outline-minor-mode, providing a familiar and consistent user experience.

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

## License

Copyright (C) 2024 [James Cherti](https://www.jamescherti.com)

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program.

## Links

- [outline-yaml.el @GitHub](https://github.com/jamescherti/outline-yaml.el)
