# My DefaultKeyBinding.dict

The MacOS text system provides a [key rebinding mechanism](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/EventOverview/TextDefaultsBindings/TextDefaultsBindings.html) that users can use to redefine some keyboard shortcuts for editing in text fields. The mechanism does not work in all applications – it only works in those that use the appropriate Apple text-editing APIs.

I use this to create more Emacs-style editing shortcuts in MacOS text editing fields. Many emacs bindings (such as control-o, control-a, control-e, control-k, and others) are already built into the system, but this adds many more. Some of them are only approximations to Emacs behavior, and in some applications their behavior can be a bit wonky.

**Warning**: I use the option key as a meta key. This overrides some default MacOS bindings (mainly for some accented or special characters).

The [`DefaultKeyBinding.dict`](DefaultKeyBinding.dict) file needs to be put in `~/Library/KeyBindings/`. On a fresh MacOS installation, the directory may not exist, and you may need to create it (`mkdir -p ~/Library/KeyBindings/`).

The following commands also need to be run in a shell (and applications restarted) before the kill ring behavior works:

```bash
defaults write -g NSTextKillRingSize -int 20
defaults write -g NSRepeatCountBinding -string "^u"
```

Some sources that I used for ideas:

* <https://developer.apple.com/documentation/appkit/nsstandardkeybindingresponding>
* <http://www.lsmason.com/articles/macosxkeybindings.html>
* <http://www.lorax.com/FreeStuff/TextExtras.html>
* <https://github.com/jrus/cocoa-text-system>
* <http://xahlee.info/kbd/osx_keybinding_key_syntax.html>
* <https://github.com/ttscoff/KeyBindings>
