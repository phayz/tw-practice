# Use SSH keys to communicate with GitLab

Git is a distributed version control system, which means you can work locally,
then share or *push* your changes to a server. In this case, the server you push to is GitLab.

GitLab uses the SSH protocol to securely communicate with Git.
When you use SSH keys to authenticate to the GitLab remote server,
you don't need to supply your username and password each time.

To use SSH to communicate with GitLab, you need:

- The OpenSSH client, which comes pre-installed on GNU/Linux, macOS, and Windows 10.
- SSH version 6.5 or later. Earlier versions used an MD5 signature, which is not secure.
- To view the version of SSH installed on your system, run `ssh -V`.
SSH uses two keys, a public key and a private key.

- The public key can be distributed.
- The private key should be protected.

Make sure your private key has the right permissions, otherwise it could be stolen.

If you do not have an existing SSH key pair, generate a new one:

1. Open a terminal.

2. Run `ssh-keygen -t` followed by the key type and an optional comment.
   This comment is included in the `.pub` file that's created.
   You may want to use an email address for the comment.

   For example, for ED25519:

   ```shell
   ssh-keygen -t ed25519 -C "<comment>"
   ```

3. Press <kbd>Enter</kbd>. Output similar to the following is displayed:

   ```plaintext
   Generating public/private ed25519 key pair.
   Enter file in which to save the key (/home/user/.ssh/id_ed25519):
   ```

4. Accept the suggested filename and directory, unless you are generating a [deploy key](project/deploy_keys/index.md)
   or want to save in a specific directory where you store other keys.

5. Specify a [passphrase](https://www.ssh.com/academy/ssh/passphrase):

   ```plaintext
   Enter passphrase (empty for no passphrase):
   Enter same passphrase again:
   ```

   A confirmation is displayed, including information about where your files are stored.

A public and private key are generated. [Add the public SSH key to your GitLab account](#add-an-ssh-key-to-your-gitlab-account)
and keep the private key secure.


NOTE:
Treat a private key like a password. Keep it in a safe place. Don't let anyone know its value.

To communicate with GitLab, you can use the following SSH key types:

- ED25519
- ED25519_SK
- ECDSA_SK
- RSA
- DSA
- ECDSA

You really shouldn't use a DSA or ECDSA key type because they're no longer considered secure.



Remember that every time the Git client communicates with GitLab, it needs to provide the private key as proof of your identity. So you need to always keep the private key on your computer.



