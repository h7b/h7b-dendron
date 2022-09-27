---
id: c6dftlhb80rzzps1phxf950
title: Espanso - Text Expander
desc: ''
updated: 1649955369538
created: 1649954834541
---
# [Espanso](https://espanso.org/) - text expander

I've just discovered an open source text expander. Looks great, free and easy to use.

The config folder is located at `C:\Users\user\AppData\Roaming\espanso`. Read [here](https://espanso.org/docs/get-started/#configuration) to learn for other OS.

## My config

I modified my match config in the `match/base.yml` file as follows.

```yaml
  # Print the current date
  - trigger: ":date"
    replace: "{{mydate}}"
    label: "Insert current date, such as 2022-01-30 Sunday"
    vars:
      - name: mydate
        type: date
        params:
          format: "%F %A"
```

```yaml
  # Print the current time
  - trigger: ":now"
    replace: "{{mytime}}"
    label: "Insert current time with timezone, such as 13:59:59+02:00"
    vars:
      - name: mytime
        type: date
        params:
          format: "%T%:z"
```

## Plan

I should find time to setup the [sync config file](https://espanso.org/docs/sync/) using GitHub.