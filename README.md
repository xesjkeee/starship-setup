# starship-setup
Config for Starship Prompt https://starship.rs/

### Show git user email
Very useful when you're working for several organizations with difference git settings

<img width="420" alt="Снимок экрана 2021-03-14 в 22 40 39" src="https://user-images.githubusercontent.com/17751886/111081842-4e0a3a80-8516-11eb-97f5-d457b79e37d1.png">

```toml
# ~/.config/starship.toml

format = """
...
$custom\
$cmd_duration\
${custom.git_email}\
$line_break\
...
"""

[custom.git_email]
command = "git config user.email"
when = "git rev-parse --git-dir 2> /dev/null"
format = "by [$output]($style) "
style = "bright-yellow bold"
```
