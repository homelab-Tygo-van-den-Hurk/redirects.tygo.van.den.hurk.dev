# [`redirects.tygo.van.den.hurk.dev`](https://redirects.tygo.van.den.hurk.dev/)
> This repository holds the source code for all the links that I need a redirect too. So if there is ever a link that needs to be spread around multiple websites, this is where I will put them. 

Every page added to this, Cannot be removed. Only the link may be altered to redirect some where else. This is to make sure that all links go somewhere. If I ever need to add a link for a project, and I forget about that project, then the link must always work. Which is where this redirect comes in. The redirect goes to github-pages instance for example. 

## How easy is it to set something like this up yourself?
Really easy. If you have `git`, and `docker` installed, then you can clone and compose in as little as 5 minutes. It could be a really useful thing to have.

### How to create this yourself
First install the dependencies:

<details>
    <summary>
        How to install the dependencies on Windows
    </summary>

Install a package manager called `Chocolatey`. See [their install guide](https://chocolatey.org/install) for more information, and make sure that the information is up-to-date.

Run the following command **AS ADMINISTRATOR**:
```PS
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

```

Then install git and docker, still logged in as administrator:
```PS
choco install git docker-cli docker-compose docker-desktop -y
```

</details>

<br>

<details>
    <summary>
        How to install the dependencies on linux
    </summary>

Use your package manager to install the package:
```bash
sudo apt install git docker-cli docker-compose docker-desktop -y
```

</details>

<br>

then, we must copy the repository:
```Bash 
git clone https://github.com/St-H123/redirects.tygo.van.den.hurk.dev.git
```

Then rename the repository as you'd like. I name them their actual URL. 
So for you, that could be something like `redirects.your.domain.tld`.
To do that, we use the following command on linux:
```bash
mv ./redirects.tygo.van.den.hurk.dev/ ./redirects.your.domain.tld/
```
and the following command on windows:
```PS
Rename-Item .\redirects.tygo.van.den.hurk.dev .\redirects.your.domain.tld
```

then we go into that folder and delete the `.git` folder
```bash
cd redirects.your.domain.tld/
rm .git -Rf
```

then we make a new `.git` folder, and commit, and push it to the remote.
```
git init
git add .
git commit -m "initial commit"
git remote add upstream <your_repository_URL>
git push origin main
```

now that we've done the version control part, we must spin up the docker file:
```
docker compose up -d
```

and boom, you're done! Your docker container should be running. You will need to set up either a proxy-manger, or alter the docker compose file for it to be access able.