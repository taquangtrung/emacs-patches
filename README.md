# Patch Emacs MacPort

- Run `brew edit emacs-mac` to open the Formula file of Emacs MacPort

  ```
  /usr/local/Homebrew/Library/Taps/railwaycat/homebrew-emacsmacport/Formula/emacs-mac.rb
  ```

- Insert this code into `emacs-mac.rb`

  ```rb
    patch do
      url "https://raw.githubusercontent.com/taquangtrung/emacs-patches/main/patches/emacs-mac-29-remove-line-number-left-margin.diff"
      sha256 "cfb64003bb43155d87a0a1c1885a577535bbb715f7781cef3055531dc6128bd3"
    end
  ```

- Run `brew install emacs-mac` or `brew reinstall emacs-mac` to appy the patch and install Emacs.
