# ejson-mode
Emacs major mode for editing ejson files

Extends js-mode to add ejson encryption support

# Default Keybindings
* `C-c C-e` Encrypt the saved file
* `C-c C-d` Decrypt the file into the current buffer

# Hooks

On save, ejson files are automatically checkes for the `_public_key` key, if it doesn't exist users are prompted to automatically generate one and add it to the file. It is then encrypted with ejson after being saved to disk.

# Variables
* `ejson-binary-location` Manually specify the location of the ejson binary
* `ejson-keystore-location` Specify an alternate location for the ejson keystore
* `ejson-encrypt-on-save` Disable automatic encryption on save
