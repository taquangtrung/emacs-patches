# Patch Emacs MacPort

- Run `brew edit emacs-mac` to open the Formula file of Emacs MacPort

  ```
  /usr/local/Homebrew/Library/Taps/railwaycat/homebrew-emacsmacport/Formula/emacs-mac.rb
  ```

- Insert this code into `emacs-mac.rb`

  ```rb
    patch do
      url "https://raw.githubusercontent.com/taquangtrung/emacs-patches/main/patches/emacs-mac-29-remove-line-number-left-margin.diff"
      sha256 "b11865d0fed8df22e368e8be583ee078ec9cfc66bf20b916d1fb238512d27e35"
    end
  ```

- Run `brew install emacs-mac --with-no-title-bars` or `brew reinstall emacs-mac --with-no-title-bars` to apply the patch and install Emacs.
