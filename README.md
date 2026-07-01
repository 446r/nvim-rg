# nvim-rg

Use rg in Neovim.

## Installation インストール

Clone (place it in your startup plugins or use `vim.pack.add`).

```
cd ~/.config/nvim/pack/xxx/start/
git clone https://github.com/446r/nvim-rg.git
```

init.lua

```
require("nvim-rg").setup()
```

Customize.

```
require("nvim-rg").setup({
  options = { "--vimgrep", "-i" },
  command = "Ripgrep",
})
```

## Usage 使い方

```
:Rg keyword
```

```
:Rg keyword target_dir
```


## Memo

:grep で rg コマンドが使われればよいだけであれば、以下でよいです。プラグインは不要です。

```
vim.opt.grepprg = "rg --vimgrep -uu"
```

neovimはrgが利用可能な環境であれば、自動でgrepprgを変更して、:grep コマンドでrgを使用するので、何も設定しないのもよいです。

また、従来のgrepの癖で :grep -r をすると、-r はrgにとって違う意味のオプションなので、検索結果の見た目がおかしくなります。今どきのrgを使う :grep では、 :grep キーワード だけで使うのがよいです。

:grep は :grep のまま残したい。rg は別のコマンドで使いたい。そんなときのプラグインです。

