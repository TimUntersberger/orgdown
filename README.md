# orgdown
Tries to make markdown feel like orgmode

## Ideas (WIP)

### Editing speed

The plugin will provide automatic list continuation and so on.

### Visual appeal

Markdown in plain text is boring and plain. I want to use the conceal feature of vim to replace headers, lists and so on with some nice unicode alternatives.
I don't know whether it is possible to make text conditionally bold using conceal, but I want to do it.

Every "group", meaning something like a header, is by default a fold. This fold will just look like the normal line (this depends on [this](https://github.com/neovim/neovim/pull/12515) pr to be merged into neovim, else there is no color)

### Code execution

When someone talks about how awesome orgmode is, they almost always mention that you can execute codeblocks in org files. I want to support this by parsing the code block and sending the content to a function defined in userland. This function then returns the resulting output of the code block.

The function for a filetype has to be defined in the config file of vim.

example
```lua
orgdown.code_executors['lua'] = function(content)
  -- content is a list of lines
end
```

When the cursor is inside a code block you can execute it by using the OrgdownExecute command.

For now I'm thinking about just opening a split/floating window that shows the output.
