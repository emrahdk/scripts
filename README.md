# Scripts and helpful commands

##  Git

### Syncing

#### Push all branches to remote
```bash
git push --all
```

#### Push all tags to remote
```bash
git push --tags
```

#### Fetch and remove non-existing branches on remote
```bash
git fetch -p
```

#### Prune and fetch tags
```bash
git tag -l | xargs git tag -d && git fetch -t
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

## Environment paths (on Windows)

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

#### Pack using `dotnet`
```bash
dotnet pack --include-symbols -c <configuration>
```

### Update assembly redirects

_In Package Manager Console_
```powershell
Get-Project -All | Add-BindingRedirect
```

---

## WSL (Windows Subsystem Linux)

### Setup with Windows Credentials Manager

```bash
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-wincred.exe"
```

### Fix file line breaks
```bash
dos2unix.exe -b <FILE>
```

---

## Linux specific things

### Enable ports on RHEL / CentOS

#### List currently open ports
```bash
firewall-cmd --list-ports
```

#### List zones
```bash
firewall-cmd --get-zones
```

#### List the zone containing eth0
```bash
firewall-cmd --get-zone-of-interface=eth0
```

#### Open TCP port
```bash
firewall-cmd --add-port <PORT>/tcp
```

#### Open TCP port permenantly
```bash
firewall-cmd --permanent --add-port 1191/tcp
```

#### Open a range of TCP ports
```bash
firewall-cmd --permanent --add-port 60000-61000/tcp
```

#### Restart the firewall
```bash
systemctl stop firewalld
systemctl start firewalld
```

---

## BASH

### Create multiple files at once
```bash
touch somefile.{js,css,txt}
touch product-{image,description,options}.js
```

---

## WCF / SOAP things
_Use `Developer Command Prompt for VS 2019` to get af hold of `svcutil`_
```bash
svcutil http://example.service.dk/?wsdl=wsdl2 /out:MyService.cs /ct:System.Collections.Generic.List`1 /n:http://example.service.dk/Something/2020/10/,Some.Namespace.MyService
```
