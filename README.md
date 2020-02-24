# Scripts and helpful commands

##  Git

### Syncing

#### Push all branches to remote
```bash
git push <REMOTE> --all
```

#### Push all tags to remote
```bash
git push <REMOTE> --tags
```

#### Fetch and remove non-existing branches on remote
```bash
git fetch -p
```

#### Clean up repo
_Dry run_
```bash
git clean --dry-run
```

_Force and remove directories_
```bash
git clean -f -d
```

### Branch

#### Delete local branch
```bash
git branch -d <branch-name>
```

#### Delete remote branch
```bash
git push origin :<remote-branch-name>
```

#### Rename local branch
```bash
git branch -m <new-name>
```

#### Create and checkout branch
```bash
git checkout -b <branch_name>
```

### Commits

#### Reset to head

```bash
git reset --hard HEAD
```

#### Reset to commit

```bash
git reset --hard <commit sha>
```

#### Partially revert commit

```bash
git revert <bad-commit-sha> --no-commit
git reset
<edit/recover bad file(s)>
git add <bad-files>
git checkout .
git commit
```

#### Stage all changes and commit

```bash
git commit -a -m <message>
```

### Remote

#### List remotes
```bash
git remote -v
```

#### Remove remote
```bash
git remote rm <REMOTE>
```

---

##  Environment paths (on Windows)

### Set environment variable for user
```powershell
setx <key> <value>
```

### Set environment variable system wide
```powershell
setx <key> <value> /M
```

---

## NuGet

### Pack and build release with symbols

```powershell
nuget pack <project>.csproj -Build -Symbols -Properties Configuration=<configuration>
```

### Update assembly redirects

_In Package Manager Console_
```powershell
Get-Project -All | Add-BindingRedirect
```

## WSL (Windows Subsystem Linux)

### Setup with Windows Credentials Manager

```bash
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-wincred.exe"
```

### Fix file line breaks
```bash
dos2unix.exe -b <FILE>
```
