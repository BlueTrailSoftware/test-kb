```yaml
site_name: Knowledge Base
extra:
  generator: false
  consent:
    title: Cookie consent
    description: >-
      We use cookies to recognize your repeated visits and preferences, as well
      as to measure the effectiveness of our documentation and whether users
      find what they're searching for. With your consent, you're helping us to
      make our documentation better.
copyright: Copyright &copy; 2022 - 2024 Rafa Madolell
repo_url: https://github.com/insanerask77/kb
repo_name: insanerask77/kb
theme:
  name: material
  features:
    - header.autohide
    - search.suggest
    - search.highlight
    - search.share
    - navigation.instant
    - navigation.instant.progress
  icon:
    repo: fontawesome/brands/github
    logo: simple/gitkraken
    favicon: simple/fsecure
  font:
    text: Roboto
  palette:
    # Palette toggle for automatic mode
    - media: "(prefers-color-scheme)"
      toggle:
        icon: material/brightness-auto
        name: Switch to light mode

    # Palette toggle for light mode
    - media: "(prefers-color-scheme: light)"
      scheme: default
      toggle:
        icon: material/toggle-switch
        name: Switch to dark mode

    # Palette toggle for dark mode
    - media: "(prefers-color-scheme: dark)"
      scheme: slate
      toggle:
        icon: material/toggle-switch-off-outline
        name: Switch to system preference
plugins:
  - search
#  - optimize
#- mkdocstrings

markdown_extensions:
  - admonition
  - codehilite
#  - mkautodoc
```

```yaml
site_name: Knowledge Base
extra:
  generator: false
  consent:
    title: Cookie consent
    description: >-
      We use cookies to recognize your repeated visits and preferences, as well
      as to measure the effectiveness of our documentation and whether users
      find what they're searching for. With your consent, you're helping us to
      make our documentation better.
copyright: Copyright &copy; 2022 - 2024 Rafa Madolell
repo_url: https://github.com/insanerask77/kb
repo_name: insanerask77/kb

theme:
  name: material
  features:
    - header.autohide
    - search.suggest
    - search.highlight
    - search.share
    - navigation.instant
    - navigation.instant.progress
  icon:
    repo: fontawesome/brands/github
    logo: simple/gitkraken
    favicon: simple/fsecure
  font:
    text: Roboto
  palette:
    # Palette toggle for automatic mode
    - media: "(prefers-color-scheme)"
      toggle:
        icon: material/link
        name: Switch to light mode

    # Palette toggle for light mode
    - media: "(prefers-color-scheme: light)"
      scheme: default
      primary: green
      accent: blue
      toggle:
        icon: material/toggle-switch
        name: Switch to dark mode

    # Palette toggle for dark mode
    - media: "(prefers-color-scheme: dark)"
      scheme: slate
      primary: green
      accent: blue
      toggle:
        icon: material/toggle-switch-off-outline
        name: Switch to system preference
plugins:
  - search
#  - optimize
#- mkdocstrings

markdown_extensions:
  - admonition
  - codehilite
#  - mkautodoc	
```

