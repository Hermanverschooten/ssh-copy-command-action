# ssh-copy-command-action
Copy a file over SSH and execute a command afterwards.

```yaml
  - name: Deploy
    uses: Hermanverschooten/ssh-copy-command-action@v1
    env:
      SSH_PRIVATE_KEY: ${{ secrets.SSH_KEY }}
      SOURCE: "./source.tar.gz"
      REMOTE_HOST: my_host.example.org
      REMOTE_USER: root
      TARGET: "/opt/dest"
      CMD: "./deploy"
```

This action uses scp to copy the file to the remote destination, then reuses that master
control socket to run the given command over ssh.
