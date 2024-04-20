# Patching Emacs MacPort

- Run `brew edit emacs-mac` to open the Formula file of Emacs MacPort

  ```
  /usr/local/Homebrew/Library/Taps/railwaycat/homebrew-emacsmacport/Formula/emacs-mac.rb
  ```

## Patch displaying buffer

- This patch will fix the following:
  + Remove the unnecessary left margin when displaying line numbers in buffers
  + Vertically center lines with extra line spacing

- Insert this code into the section installing Emacs 29 `emacs-mac.rb`:

  ```rb
    patch do
      url "https://raw.githubusercontent.com/taquangtrung/emacs-patches/main/patches/emacs-29-display-prettier.diff"
      sha256 "eaa093a7c42196114be64ff8d0a065533b5cf18d6c42aab41a6385f254055269"
    end
  ```

# Install Emacs with patches

- Run `brew install emacs-mac --with-no-title-bars` or `brew reinstall emacs-mac --with-no-title-bars` to apply the patch and install Emacs.
