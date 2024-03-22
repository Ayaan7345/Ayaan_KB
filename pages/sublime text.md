- To install Sublime Text in Kali Linux, you can follow the steps below:
- 1. Open the terminal in Kali Linux.
  2. Add the GPG key for Sublime Text by running the following command:
  ```
  wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
  ```
- 3. Add the Sublime Text repository to the sources list by running the following command:
  ```
  echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
  ```
- 4. Update the package list by running the following command:
  ```
  sudo apt-get update
  ```
- 5. Install Sublime Text by running the following command:
  ```
  sudo apt-get install sublime-text
  ```
- 6. After the installation is complete, you can launch Sublime Text by typing `subl` in the terminal.
- Alternatively, you can also install Sublime Text using the Snap Store or by downloading the package from the official website[3][5]. However, the above method is the recommended way to install Sublime Text in Kali Linux.
- It's important to note that Sublime Text is not included in the Kali Linux repositories by default, and you need to add the Sublime Text repository manually to install it.
- Citations:
  [1] https://www.linuxhelp.com/how-to-install-sublime-on-kali-linux
  [2] https://www.youtube.com/watch?v=8vbLfUYz-28
  [3] https://www.makeuseof.com/how-to-install-sublime-text-on-linux/
  [4] https://www.tecmint.com/sublime-text-editor-for-linux/
  [5] https://snapcraft.io/sublime-text
  [6] https://www.sublimetext.com/docs/linux_repositories.html