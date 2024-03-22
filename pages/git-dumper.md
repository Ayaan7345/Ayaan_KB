- Git-dumper is a tool used to dump a Git repository from a website. It allows you to retrieve the contents of a Git repository, including the commit history, branches, and files, from a remote website[1][2][3].
- The tool works by checking if directory listing is available on the website. If directory listing is available, it recursively downloads the `.git` directory using methods similar to using `wget` [1]. If directory listing is not available, it uses various techniques to find and retrieve as many files as possible from the Git repository[1].
- To use git-dumper, you can install it easily with pip by running the following command:
  ```
  pip install git-dumper
  ```
- After installation, you can run git-dumper with the URL of the website containing the Git repository and specify the output directory where the repository will be dumped. For example:
  ```
  git-dumper http://website.com/.git ~/website
  ```
- It's important to note that when using git-dumper, you should be cautious and use it at your own risk. If the repository you are downloading is controlled by an attacker, it could potentially lead to remote code execution on your machine[1].
- Please exercise caution and ensure that you have proper authorization and permission before using git-dumper on any website.
- Citations:
  [1] https://github.com/arthaud/git-dumper
  [2] https://kalilinuxtutorials.com/git-dumper/
  [3] https://securityonline.info/git-dumper-dump-a-git-repository-from-a-website/
  [4] https://lib.rs/crates/git-dumper
  [5] https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/git
  [6] https://en.kali.tools/all/?tool=2754