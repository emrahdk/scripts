# Scripts and helpful commands

[TOC]

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
