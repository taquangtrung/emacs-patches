# Patch Emacs MacPort

- Run `brew edit emacs-mac` to open the Formula file of Emacs MacPort

  ```
  /usr/local/Homebrew/Library/Taps/railwaycat/homebrew-emacsmacport/Formula/emacs-mac.rb
  ```

## Patch displaying line numbers
- Insert this code into `emacs-mac.rb`

  ```rb
    patch do
      url "https://raw.githubusercontent.com/taquangtrung/emacs-patches/main/patches/emacs-mac-29-remove-line-number-margin.diff"
      sha256 "b11865d0fed8df22e368e8be583ee078ec9cfc66bf20b916d1fb238512d27e35"
    end
  ```

## Patch displaying buffer
- Insert this code into `emacs-mac.rb`

  ```rb
    patch do
      url "https://raw.githubusercontent.com/taquangtrung/emacs-patches/main/patches/emacs-29-display-buffer-prettier.diff"
      sha256 "82663298ea2994ce71927ff78d9ba4d98c90923f06404ff41080c5627e2081f6"
    end
  ```

# Install Emacs with patches

- Run `brew install emacs-mac --with-no-title-bars` or `brew reinstall emacs-mac --with-no-title-bars` to apply the patch and install Emacs.
