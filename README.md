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
      sha256 "7378efa4c69f0a8bebef0fc21a8aa75eacceb8b569391f5ce20433c7e897e18a"
    end
  ```

# Install Emacs with patches

- Run `brew install emacs-mac --with-no-title-bars` or `brew reinstall emacs-mac --with-no-title-bars` to apply the patch and install Emacs.
