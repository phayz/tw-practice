# Adding a file to a repository

To add files larger than 100 MB, you must use Git Large File Storage.

Git LFS handles large files by storing references to the file in the repository, but not the actual file itself. To work around Git's architecture, Git LFS creates a pointer file which acts as a reference to the actual file (which is stored somewhere else). GitHub manages this pointer file in your repository. When you clone the repository down, GitHub uses the pointer file as a map to go and find the large file for you.


WARNING:
Files that you add to a repository via a browser are limited to 25 MB per file. You can add larger files, up to 100 MB each, via the command line. For more information, see "Adding a file to a repository using the command line."

## Adding a file to a repository on GitHub

- You can upload multiple files to GitHub at the same time.

1. On GitHub.com, navigate to the main page of the repository.
2. Above the list of files, select the Add file dropdown menu and click Upload files. Alternatively, you can drag and drop files into your browser.
3. To select the files you want to download, drag and drop the file or folder, or click choose your files.
4. In the "Commit message" field, type a short, meaningful commit message that describes the change you made to the file. You can attribute the commit to more than one author in the coommit massage. For more information, see "Creating a commit with multiple authors."
5. Below the commit message fields, decide whether to add your commit to the current branch or to a new branch. If your current branch is the default branch, you should choose to create a new branch for your commit and then create a pull request. For more information, see "Creating a pull request."
6. Click Propose changes.

WARNING:
If a repository has any protected branches, you can't edit or upload files in the protected branch using GitHub. For more information, see ["About protected branches."](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)

## Adding a file to a repository using the command line

You can upload an existing file to a repository on GitLab.com using the command line.

Tip: You can also add an existing file to a repository from the GitHub website.

**The command line instructions below assume you're using macOS.**


1. On your computer, move the file you'd like to upload to GitHub into the local directory that was created when you cloned the repository.
2. Open Terminal.
3. Change the current working directory to your local repository.
4. Stage the file for commit to your local repository.
   ```
   $ git add .
   # Adds the file to your local repository and stages it for commit. To unstage a file, use 'git reset HEAD YOUR-FILE'.
   ```
5. Commit the file that you've staged in your local repository.
   ```
   $ git commit -m "Add existing file"
   # Commits the tracked changes and prepares them to be pushed to a remote repository. To remove this commit and modify the file, use 'git reset --soft HEAD~1' and commit and add the file again.
   ```
6. Push the changes in your local repository to GitHub.com.
   ```
   $ git push origin YOUR_BRANCH
   # Pushes the changes in your local repository up to the remote repository you specified as the origin
   ```

NOTE:
If you're adding a file from the command line, you must have already created a repository on GitHub, or have an existing repository owned by someone else you'd like to contribute to, and cloned the repository locally on your computer.
