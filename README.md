# NeoVim

## Intallation

https://github.com/neovim/neovim/wiki/Installing-Neovim

```bash
curl https://github.com/neovim/neovim/releases/latest/download/nvim-linux64.tar.gz
# vi ~/.bashrc
export PATH=$PATH:/new/path
```

Add path to env

## Plugin

第一次不熟悉安装的时候建议先体验一下 [Astronvim](https://astronvim.com/).
等以后有闲工夫再慢慢折腾。

Astronvim 允许用户进行一定程度上的配置: [AstroNvim Config](https://github.com/AstroNvim/user_example).
例如可以用它来取消 relative line number 等不想要的特性。

### Theme
对于 Astronvim 自带的 [astrotheme](https://github.com/AstroNvim/astrotheme) 我觉得不是很满意, 主要是在 Visual 模式下选中的文本不凸出, 所以想把这部分文本调亮一些。

观察到 astrotheme 中对于颜色的配置, 见 [Line-164](https://github.com/AstroNvim/astrotheme/blob/main/lua/astrotheme/groups/base.lua#L164).
我们可以在 `~/.config/nvim/lua/user/highlights` 路径下创建 `<theme-name>.lua` 来 override 默认的颜色配置。
由于我们想要修改的是默认配置, 所以就创建 `~/.config/nvim/lua/user/highlights/astrodark.lua`, 写入

```lua
return { -- a table of overrides/changes to the astrodark theme
  Visual = { bg = "#515c65" },
}
```


如果是用的 lazy.nvim 进行插件管理, 那么你安装的 plugin 位置在 `~/.local/share/nvim/lazy/`。
如果想要进行一些 HACK 可以从这个路径下操作试试。
