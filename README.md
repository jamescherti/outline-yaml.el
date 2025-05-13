# outline-yaml.el - Emacs package: Outline and Code folding for YAML files

_Recommendation:_ I recommend you to try a similar package from the same author: [outline-indent.el](https://github.com/jamescherti/outline-indent.el), which provides a minor mode for Emacs that enables **code folding and outlining based on indentation levels** for various indent-based text files such as YAML, Python, and others. In addition to code folding, it allows moving indented subtrees up/down, customizing the ellipsis, and inserting a heading that creates a new line with the same indentation level/depth as the current line, among other features.

## Introduction

The `outline-yaml.el` Emacs package provides a minor mode for Emacs that enables **code folding and outlining for YAML files**. It leverages the built-in `outline-minor-mode` to provide a structured view of YAML files, allowing users to fold and unfold YAML files.

This package helps when editing long and complex YAML files, which makes code folding becomes an invaluable tool because it is allowing the collapse and expansion of sections of the file and enhancing readability and navigation.

![](https://raw.githubusercontent.com/jamescherti/outline-yaml.el/main/.screenshot.png)

## Installation

### Install with straight

To install `outline-yaml` with `straight.el`:

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

### Vanilla Emacs

Once installed with `use-package` and activated with `outline-yaml-minor-mode` in a YAML buffer, you can use the standard `outline-mode`/`outline-minor-mode` commands to fold and unfold sections of your YAML file:
- `outline-hide-body`: Hide all body lines in buffer, leaving all headings visible.
- `outline-hide-other`: Hide everything except current body and parent and top-level headings.
- `outline-hide-entry`: Hide the body directly following this heading.
- `outline-hide-leaves`: Hide the body after this heading and at deeper levels.
- `outline-hide-subtree`: Hide everything after this heading at deeper levels.
- `outline-show-children`: Show all direct subheadings of this heading.
- `outline-hide-sublevels`: Hide everything but the top LEVELS levels of headers, in whole buffer.
- `outline-show-all`: Show all of the text in the buffer.
- `outline-show-entry`: Show the body directly following this heading.
- `outline-show-subtree`: Show everything after this heading at deeper levels.
- `outline-show-branches`: Show all subheadings of this heading, but not their bodies.
- `outline-show-children`: Show all direct subheadings of this heading.

### Evil mode

In Evil mode, `outline-yaml` works out of the box, and you can use the Evil keyboard mappings: zo, zc, zO, zC, za, zr, and zm to manage folds.

## Frequently asked questions

### How to change the Ellipsis (...) to (▼)?

If you want to make the ellipsis of `outline-yaml-mode` look like the screenshot above (▼), use the code snippet in this article: [Changing the Ellipsis (“…”) in outline-mode and outline-minor-mode](https://www.jamescherti.com/emacs-customize-ellipsis-outline-minor-mode/).

### Maintaining blank lines between folded sections

The `outline-blank-line` variable can be set to `t` (true) to maintain blank lines between folded sections, making it easier to distinguish between folds:

```
(setq outline-blank-line t)
```

I recommend you read [Enhancing up and down subtree movement in outline-mode and outline-minor-mode](https://www.jamescherti.com/outline-mode-enhance-move-subtree-up-down/) to make `outline-move-subtree-up` and `outline-move-subtree-down` ignore the `outline-blank-line` variable, which allows moving the whole block up and down, including the blank line.

### Why not use origami.el?

The `origami.el` package is no longer actively maintained and has known bugs that can affect its reliability and performance.

On the other hand, `outline-yaml.el` leverages the built-in `outline-minor-mode`, which is actively maintained by the Emacs developers.

### Why not use ts-fold or treesit-fold?

The ts-fold or treesit-fold can be a good alternative for Tree Sitter users.

The `outline-yaml.el` Emacs package, on the other hand, is more suited for:
- Users of `yaml-mode` who have not yet switched to tree-sitter,
- Users who prefer `outline-minor-mode` because it works out of the box with Emacs Evil key mapping (although adding Emacs Evil support for treesit-fold is straightforward),
- Users who have extensively customized `outline-minor-mode` to fit their needs.

## License

Copyright (C) 2024-2025 [James Cherti](https://www.jamescherti.com)

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program.

## Links

- [outline-yaml.el @GitHub](https://github.com/jamescherti/outline-yaml.el)
- Similar package from the same author: [outline-indent.el @GitHub](https://github.com/jamescherti/outline-indent.el)

Other Emacs packages by the same author:
- [compile-angel.el](https://github.com/jamescherti/compile-angel.el): **Speed up Emacs!** This package guarantees that all .el files are both byte-compiled and native-compiled, which significantly speeds up Emacs.
- [outline-indent.el](https://github.com/jamescherti/outline-indent.el): An Emacs package that provides a minor mode that enables code folding and outlining based on indentation levels for various indentation-based text files, such as YAML, Python, and other indented text files.
- [easysession.el](https://github.com/jamescherti/easysession.el): Easysession is lightweight Emacs session manager that can persist and restore file editing buffers, indirect buffers/clones, Dired buffers, the tab-bar, and the Emacs frames (with or without the Emacs frames size, width, and height).
- [vim-tab-bar.el](https://github.com/jamescherti/vim-tab-bar.el): Make the Emacs tab-bar Look Like Vim's Tab Bar.
- [elispcomp](https://github.com/jamescherti/elispcomp): A command line tool that allows compiling Elisp code directly from the terminal or from a shell script. It facilitates the generation of optimized .elc (byte-compiled) and .eln (native-compiled) files.
- [tomorrow-night-deepblue-theme.el](https://github.com/jamescherti/tomorrow-night-deepblue-theme.el): The Tomorrow Night Deepblue Emacs theme is a beautiful deep blue variant of the Tomorrow Night theme, which is renowned for its elegant color palette that is pleasing to the eyes. It features a deep blue background color that creates a calming atmosphere. The theme is also a great choice for those who miss the blue themes that were trendy a few years ago.
- [Ultyas](https://github.com/jamescherti/ultyas/): A command-line tool designed to simplify the process of converting code snippets from UltiSnips to YASnippet format.
- [dir-config.el](https://github.com/jamescherti/dir-config.el): Automatically find and evaluate .dir-config.el Elisp files to configure directory-specific settings.
- [flymake-bashate.el](https://github.com/jamescherti/flymake-bashate.el): A package that provides a Flymake backend for the bashate Bash script style checker.
- [flymake-ansible-lint.el](https://github.com/jamescherti/flymake-ansible-lint.el): An Emacs package that offers a Flymake backend for ansible-lint.
- [inhibit-mouse.el](https://github.com/jamescherti/inhibit-mouse.el): A package that disables mouse input in Emacs, offering a simpler and faster alternative to the disable-mouse package.
- [quick-sdcv.el](https://github.com/jamescherti/quick-sdcv.el): This package enables Emacs to function as an offline dictionary by using the sdcv command-line tool directly within Emacs.
- [enhanced-evil-paredit.el](https://github.com/jamescherti/enhanced-evil-paredit.el): An Emacs package that prevents parenthesis imbalance when using *evil-mode* with *paredit*. It intercepts *evil-mode* commands such as delete, change, and paste, blocking their execution if they would break the parenthetical structure.
- [stripspace.el](https://github.com/jamescherti/stripspace.el): Ensure Emacs Automatically removes trailing whitespace before saving a buffer, with an option to preserve the cursor column.
- [persist-text-scale.el](https://github.com/jamescherti/persist-text-scale.el): Ensure that all adjustments made with text-scale-increase and text-scale-decrease are persisted and restored across sessions.
