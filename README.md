# ejson-mode
Emacs major mode for editing [ejson](https://github.com/Shopify/ejson) files

Extends js-mode to add ejson encryption support

# Default Keybindings
* `C-c C-e` Encrypt the saved file (run on save by default)
* `C-c C-d` Decrypt the file into the current buffer

# Hooks
On the `before-save-hook` ejson-mode runs `ejson-prompt-generate-key` to detect if the file has a public key, and prompts the user to generate and insert one if one isn't detected. It then runs `ejson-encrypt-and-reload` on the `after-save-hook` to encrypt the file using ejson and reload the encrypted file into the buffer. Both of these are disabled if `ejson-encrypt-on-save` is set to `nil`.

# Variables
* `ejson-binary-location` Manually specify the location of the ejson binary
* `ejson-keystore-location` Specify an alternate location for the ejson keystore
* `ejson-encrypt-on-save` Disable automatic encryption on save
