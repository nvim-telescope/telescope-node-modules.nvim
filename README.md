# telescope-node-module.nvim

`telescope-node-modules` is an extension for [telescope.nvim][] that provides its users with node packages under `node_modules/` dir.

[telescope.nvim]: https://github.com/nvim-telescope/telescope.nvim

## Installation

```lua
use{
  'nvim-telescope/telescope.nvim',
  requires = {
    'nvim-telescope/telescope-node-modules.nvim',
  },
  config = function()
    require'telescope'.load_extension'node_modules'
  end,
}
```

## Usage

### list

`:Telescope node_modules list`

List packages under `node_modules` of the current directory. In default, it does actions below when you input keys.

| key              | action               |
|------------------|----------------------|
| `<CR>` (edit)    | `builtin.find_files` |
| `<C-x>` (split)  | `:chdir` to the dir  |
| `<C-v>` (vsplit) | `:lchdir` to the dir |

#### options

##### `cwd`

Transform the result paths into relative ones with this value as the base dir.

Default value: `vim.fn.getcwd()`

## TODO

* [ ] Asynchronous directory reading
* [x] Show dependency levels of packages
* [ ] More info from `package.json`
