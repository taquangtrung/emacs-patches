# Patching Emacs MacPort

- Run `brew edit emacs-mac` to open the Formula file of Emacs MacPort

  ```
  /usr/local/Homebrew/Library/Taps/railwaycat/homebrew-emacsmacport/Formula/emacs-mac.rb
  ```

## Patch displaying buffer

- This patch will fix the following:
  + Remove the unnecessary left margin when displaying line numbers in buffers
  + Compute the maximum line number more precisely when displaying line numbers
  + Vertically center lines with extra line spacing
  + Draw the filled cursor to

- Insert this code into the section installing Emacs 29 `emacs-mac.rb`:

  ```rb
    patch do
      url "https://raw.githubusercontent.com/taquangtrung/emacs-patches/main/patches/emacs-29-display-prettier.diff"
      sha256 "3344645138c9515d34d88363157d810e1d2d1b7ea321bc0c3d5ada87bf7d9892"
    end
  ```

# Install Emacs with patches

- Run `brew install emacs-mac --with-no-title-bars` or `brew reinstall emacs-mac --with-no-title-bars` to apply the patch and install Emacs.
