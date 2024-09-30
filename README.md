```markdown
# Optimizing Your Shell Configuration with Fastfetch and Starship

## Introduction
If you are a terminal user spending a lot of time in the shell, having an attractive display and good functionality can enhance your experience. In this article, we will discuss how to use `config.jsonc` for Fastfetch and `starship.toml` for Starship.

## What are Fastfetch and Starship?
- **Fastfetch** is a tool for displaying system information in an appealing format in your terminal.
- **Starship** is a customizable and fast shell prompt designed to enhance your terminal efficiency and aesthetics.

---

## Steps to Use Fastfetch and Starship

### 1. Install Fastfetch
Before you start, make sure Fastfetch is installed. You can install it using `git` and `cargo` (if you're using Rust):

```bash
git clone https://github.com/LorenzoSeni/fastfetch.git
cd fastfetch
cargo install --path .
```

### 2. Configure Fastfetch
Fastfetch uses a configuration file called `config.jsonc`. Here’s how to create and edit this file.

- **Create Configuration File**:
  Create a file named `config.jsonc` in the Fastfetch configuration directory, typically at `~/.config/fastfetch/`.

- **Sample Configuration**:
  Here’s a basic example configuration for `config.jsonc`:

  ```jsonc
  {
    "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
    "logo": {
        "type": "builtin",
        "color": {
            "1": "white",
            "2": "cyan"
        }
    },
    "display": {
        "separator": " → ",
        "color": "cyan"
    },
    "modules": [
        {
            "type": "custom", // HardwareStart
            "format": "┌─────────── \u001b[1mHardware Information\u001b[0m ───────────┐" // \u001b is \033, or \e
        },
        {
            "type": "host",
            "key": "  󰌢"
        },
        {
            "type": "cpu",
            "key": "  "
        },
        {
            "type": "gpu",
            "detectionMethod": "pci",
            "key": "  "
        },
        {
            "type": "display",
            "key": "  󱄄"
        },
        {
            "type": "memory",
            "key": "  "
        },
        {
            "type": "custom", // SoftwareStart
            "format": "├─────────── \u001b[1mSoftware Information\u001b[0m ───────────┤"
        },
        {
            "type": "os",
            "key": "  " // Just get your distro's logo off nerdfonts.com,
        },
        {
            "type": "kernel",
            "key": "  ",
            "format": "{1} {2}"
        },
        {
            "type": "wm",
            "key": "  "
        },
        {
            "type": "shell",
            "key": "  "
        },
        {
            "type": "custom",
            "format": "|──────────────\u001b[1mUptime / Age\u001b[0m──────────────────|"
        },
        {
            "type": "command",
            "key": "  OS Age ",
            "keyColor": "magenta",
            "text": "birth_install=$(stat -c %W /); current=$(date +%s); time_progression=$((current - birth_install)); days_difference=$((time_progression / 86400)); echo $days_difference days"
        },
        {
            "type": "uptime",
            "key": "  Uptime ",
            "keyColor": "magenta"
        },
        {
            "type": "custom", // InformationEnd
            "format": "└────────────────────────────────────────────┘"
        },
        {
            "type": "colors",
            "paddingLeft": 2,
            "symbol": "circle"
        }
    ]
}
  ```

- **Explanation**:
  - `theme`: Sets the display theme.
  - `show`: Determines which information will be displayed.
  - `colors`: Sets the colors for text and background.

### 3. Install Starship
Installing Starship is straightforward. Use the following command:

```bash
sh -c "$(curl -fsSL https://starship.rs/install.sh)"
```

### 4. Configure Starship
Starship uses a configuration file called `starship.toml`. Create this file in your configuration directory:

- **Create Configuration File**:
  Create a file named `starship.toml` in the `~/.config/starship/` directory.

- **Sample Configuration**:
  Here’s a basic example configuration for `starship.toml`:

  ```toml
  # starship.toml
  [bun]
  format = "via [$symbol]($style)"

  [buf]
  format = "via [$symbol]($style)"
  
  [cmake]
  format = "via [$symbol]($style)"
  
  [cobol]
  format = "via [$symbol]($style)"
  
  [crystal]
  format = "via [$symbol]($style)"
  
  [daml]
  format = "via [$symbol]($style)"
  
  [dart]
  format = "via [$symbol]($style)"
  
  [deno]
  format = "via [$symbol]($style)"
  
  [dotnet]
  format = "[$symbol(🎯 $tfm )]($style)"
  
  [elixir]
  format = 'via [$symbol]($style)'
  
  [elm]
  format = 'via [$symbol]($style)'
  
  [erlang]
  format = 'via [$symbol]($style)'
  
  [fennel]
  format = 'via [$symbol]($style)'
  
  [gleam]
  format = 'via [$symbol]($style)'
  
  [golang]
  format = 'via [$symbol]($style)'
  
  [gradle]
  format = 'via [$symbol]($style)'
  
  [haxe]
  format = 'via [$symbol]($style)'
  
  [helm]
  format = 'via [$symbol]($style)'
  
  [java]
  format = 'via [$symbol]($style)'
  
  [julia]
  format = 'via [$symbol]($style)'
  
  [kotlin]
  format = 'via [$symbol]($style)'
  
  [lua]
  format = 'via [$symbol]($style)'
  
  [meson]
  format = 'via [$symbol]($style)'
  
  [nim]
  format = 'via [$symbol]($style)'
  
  [nodejs]
  format = 'via [$symbol]($style)'
  
  [ocaml]
  format = 'via [$symbol(\($switch_indicator$switch_name\) )]($style)'
  
  [opa]
  format = 'via [$symbol]($style)'
  
  [perl]
  format = 'via [$symbol]($style)'
  
  [php]
  format = 'via [$symbol]($style)'
  
  [pulumi]
  format = 'via [$symbol$stack]($style)'
  
  [purescript]
  format = 'via [$symbol]($style)'
  
  [python]
  format = 'via [$symbol]($style)'
  
  [quarto]
  format = 'via [$symbol]($style)'
  
  [raku]
  format = 'via [$symbol]($style)'
  
  [red]
  format = 'via [$symbol]($style)'
  
  [rlang]
  format = 'via [$symbol]($style)'
  
  [ruby]
  format = 'via [$symbol]($style)'
  
  [rust]
  format = 'via [$symbol]($style)'
  
  [solidity]
  format = 'via [$symbol]($style)'
  
  [typst]
  format = 'via [$symbol]($style)'
  
  [swift]
  format = 'via [$symbol]($style)'
  
  [vagrant]
  format = 'via [$symbol]($style)'
  
  [vlang]
  format = 'via [$symbol]($style)'
  
  [zig]
  format = 'via [$symbol]($style)'



  ```

- **Explanation**:
  - `character`: Specifies symbols for success and error prompts.
  - `directory`: Sets the style for the directory display.
  - `git_branch`: Defines the display format for the Git branch.

---

## Tips for Writing a Blog
1. **Use Clear Language**: Ensure readers can understand each step without difficulty.
2. **Include Images or Screenshots**: Show before and after examples of the configurations.
3. **Provide Real-life Examples**: Demonstrate how configurations can enhance productivity in the terminal.
4. **Encourage Reader Interaction**: Invite readers to share their own configurations in the comments.

---

## Conclusion
By following this guide, you can customize your terminal with Fastfetch and Starship for a better user experience. Happy experimenting, and feel free to explore your own configurations!

```

Feel free to modify it as needed! If you have any further requests, just let me know.
