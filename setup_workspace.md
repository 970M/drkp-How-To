# Setup Workspace

[README.md](README.md)


## Passwords directory

[**PWD**](https://drive.google.com/file/d/1KGY1lcKBndP06hiHwM6mFu_4kNgewG5O/view?usp=drive_link)

## Configuration

### bashrc

https://drive.google.com/file/d/1PriqQO7hdQg6INLFp1unzFPB6AhtMYn4/view?usp=drive_link

### conky

https://doc.ubuntu-fr.org/conky

```
apt-get update && apt-get install conky-all
```

https://drive.google.com/file/d/1y0f1O_efGmTNCJJqoi-EW4M2Ogs49AD9/view?usp=drive_link

## Softwares / Applications

### Terminator

https://doc.ubuntu-fr.org/terminator

```
sudo apt install terminator
```

### Chrome

https://www.google.fr/chrome/

```
sudo dpkg -i google-chrome-stable_current_amd64.deb
```
```
sudo apt update
sudo apt install google-chrome-stable_current_amd64.deb
```

### VSCode

https://code.visualstudio.com/download

```
sudo dpkg -i code_*.deb
```

### KeePassXC

https://drive.google.com/file/d/1KGY1lcKBndP06hiHwM6mFu_4kNgewG5O/view?usp=drive_link

```
snap install keepassxc
```

## Security

### Network / Wifi

https://drive.google.com/file/d/1d5NMchPzMjDW7MUoM6XGKOr7DtyyZtGu/view?usp=drive_link

### Pulse Secure (VPN)

https://drive.google.com/file/d/1f0imn6AJ1UYiHIb9u1a66kTZPKkO-F3l/view?usp=drive_link

*Update*

https://drive.google.com/file/d/1NMNY3li75DeEQ0qIJBM8CMv4Wb7Ku2qT/view?usp=drive_link


### Generate an SSH key pair for Gitlab

https://docs.gitlab.com/ee/user/ssh.html#generate-an-ssh-key-pair
https://docs.gitlab.com/ee/user/ssh.html#add-an-ssh-key-to-your-gitlab-account


```
cd $HOME/.ssh
ssh-keygen -t ed25519
xclip -sel clip < ~/.ssh/id_ed25519.pub
```

https://gitlab.ateme.net/-/user_settings/ssh_keys


### Amaint certificat

https://ssh-ca.ateme.net/

```
alias newcert='K=~/.ssh/id_ed25519; curl -f -F "pubkey=@$K.pub" <https://ssh-ca.ateme.net/si
```

## Test environement installation

### Creation of virtual environments

https://docs.python.org/fr/3/library/venv.html

```
sudo apt install python3.9
cd $HOME
mkdir venv-dvr
cd venv-dvr
sudo apt install python3.9-venv
/usr/bin/python3.9 -m venv .
cd bin
./pip3.9 install --upgrade pip
./pip3.9 install pytest
source activate
```


```
gdaguet@LPC643FR:[12:44:13]:~/src/venv-dvr/bin$ ltr
total 156K
lrwxrwxrwx 1 gdaguet gdaguet   16 sept. 10 22:31 python3 -> /usr/bin/python3
lrwxrwxrwx 1 gdaguet gdaguet    7 sept. 10 22:31 python -> python3
lrwxrwxrwx 1 gdaguet gdaguet   18 sept. 10 22:43 python3.9 -> /usr/bin/python3.9
-rwxrwxr-x 1 gdaguet gdaguet  254 sept. 10 22:43 easy_install-3.9
-rwxrwxr-x 1 gdaguet gdaguet  254 sept. 10 22:43 easy_install
-rwxrwxr-x 1 gdaguet gdaguet  245 sept. 10 22:43 pip
-rwxrwxr-x 1 gdaguet gdaguet  245 sept. 10 22:43 pip3.9
-rwxrwxr-x 1 gdaguet gdaguet  245 sept. 10 22:43 pip3
-rwxrwxr-x 1 gdaguet gdaguet  245 sept. 10 22:48 pytest
...
```

### Clone functional testing for NEA-DVR

```
git clone --recurse-submodule git@gitlab.ateme.net:qas/tests-neadvr.git 

cd ~/src/tests-neadvr/pytest
~/src/venv-dvr/bin/pip3.9 install -r requirements.txt

```

### Configuration files for host

https://drive.google.com/drive/folders/1ZtS3OFbwxpJKgV8CB__zBvFfdPSoAJ-z?usp=drive_link


### VSCode debugger configuration

https://myateme.atlassian.net/wiki/x/0IDCzw

https://drive.google.com/drive/folders/1ZtS3OFbwxpJKgV8CB__zBvFfdPSoAJ-z?usp=drive_link


*tests-neadvr.code-workspace*

```
{
  "folders": [
    {
      "path": "/home/gdaguet/src/tests-neadvr"
    },
    {
      "path": "/home/gdaguet/src/tests-neadvr/pytest"
    }
  ],
  "settings": {
    // if you want to exclude folders from your search by default
    "search.exclude": {
      "**/titanlive_test_framework": true,
      "**/node_modules": true
    },
    "python.envFile": "${workspaceFolder}/.env",
    "python.terminal.activateEnvInCurrentTerminal": true,
    "python.defaultInterpreterPath": "/home/gdaguet/src/venv-dvr/bin/python3.9",
    "python.testing.unittestEnabled": false,
    "python.testing.pytestEnabled": true,
    "python.testing.pytestPath": "/home/gdaguet/src/venv-dvr/bin/pytest",
    "python.testing.cwd": "${workspaceFolder}",
    "python.testing.pytestArgs": [
      "--ignore=third_party", //ignore third_party folder containing tests from titan live
      "--config=configs/gda.cfg"
      //"--update-version=http://firmware.anevia.com/roms-dev/nea-dvr-sw-4.19.0-rc3.afi"
      //"--update-version=4.14.1-rc4", //if you want to update your firmware version
      //"--update-version"
      
    ],
    "testing.defaultGutterClickAction": "debug",
    "debug.allowBreakpointsEverywhere": true,
    "editor.defaultFormatter": "ms-python.black-formatter",
    "editor.formatOnSave": true,
    //"terminal.integrated.env.linux": {
    //  "GTK_PATH": null
    //}
  }
}

```

*launch.json*

```
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python : Current File",
      "type": "debugpy",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal",
      "purpose": ["debug-test"],
      "justMyCode": false
    },
    {
      "name": "Python: Debug Tests",
      "type": "debugpy",
      "request": "launch",
      "program": "${file}",
      "purpose": ["debug-test"],
      "console": "integratedTerminal",
      "justMyCode": false,
      "args": [
        "--config",
        "/home/gdaguet/src/tests-neadvr/pytest/configs/gda.cfg"
        //"--update-version"
      ],
      //"pythonArgs": [],
      "env": {},
      "cwd": "${workspaceFolder}"
    }
  ]
}

```

### Pytest

#### Set up environment

https://gitlab.ateme.net/qas/tests-neadvr/-/blob/master/pytest/README.md

```
cd ~/src/tests-neadvr/pytest
```

#### Launch tests

```
pytest tests/live/test_add_live_channel.py --config configs/gda.cfg
```

#### Launch only one test

```
pytest --config configs/gda.cfg test_file::test_case
```

Ex:
```
pytest tests/live/test_add_live_channel.py -k "test_add_generic_live_channel" --config configs/gda.cfg

pytest --config configs/gda.cfg tests/live/test_add_live_channel.py::test_add_generic_live_channel
```

Collect only :
```
cd ~/src/tests-neadvr/pytest
pytest --config configs/gda-3.cfg --test-environments firmware --priority_marker highest --feature_marker sa --collect-only tests
pytest --config configs/gda-3.cfg --test-environments firmware --collect-only tests
```

Look for tests that have specific markers :

```
pytest --config configs/gda-3.cfg --test-environments firmware --feature_marker flaky,failed  --collect-only tests| grep '<Function' | sed -e 's/^ */%/g' | cut -d' ' -f2 | sed -e 's/>$//g' | sort

pytest --config configs/gda-3.cfg --test-environments firmware --feature_marker flaky,failed  --collect-only tests | grep '<Function' | sed -e 's/^ */%/g' | sed -e 's/n t/%t/g' | cut -d'%' -f3 | sed -e 's/>$//g' | sort

```

### Cypress


#### Set up environment

Installer Node.js et npm

```
cd $HOME
curl -L https://git.io/n-install | bash
. .bashrc
cd ~/src/tests-neadvr/cypress
sudo apt install npm
npm install
```

https://gitlab.ateme.net/qas/tests-neadvr/-/blob/master/cypress/README.md


(sudo apt install nodejs)

#### Launch tests


Generate cypress configuration file
```
cd ~/src/tests-neadvr/scripts
./configure_host.py --config gda.cfg create-cypress-config-js
./scripts/configure_host.py --config pytest/configs/gda.cfg create-cypress-config-js
```


```
npx cypress run
```

To run in CLI and select a specific test:

```
npx cypress run --spec cypress/e2e/profiles/sa_create_edit.cy.js
```

To run in CLI and select several tests:

```
npx cypress run --spec cypress/e2e/profiles/*.cy.js
```

Use Google Chrome like browser is required for scrambled output. To select it, we must use this command:

```
npx cypress run --spec cypress/e2e/player/player_live.cy.js --browser chrome --headed
```