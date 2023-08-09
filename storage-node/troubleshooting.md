# Possible Issues During Installation

<details>
  <summary>Unable to download docker image</summary>
  During the installation process, docker is used to download cess image. If the following exception occurs when installing the <pre>cess-nodeadm</pre>:

  <img alt="Docker Daemon Issue" src="../assets/storage-node/troubleshooting/docker-daemon-issue.png" width="100%" height="auto" decoding="async"/>

  Make sure cmds are in the root privilege or with sudo command.
  Start docker on your system:

  ```bash
  systemctl start docker
  ```

  Reinstall the `cess-nodeadm`:

  ```bash
  ./install.sh
  ```

  ⚠️ Note that all CESS program commands must have sudo privileges.
</details>
