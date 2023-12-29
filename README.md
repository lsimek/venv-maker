# venv-maker
Bash script to create a virtual environment with given packages and a Jupyter kernel.

## What do the scripts do?
`create-venv` will:
- create a virtual environment in given directory,
- add an alias to activate it of the form `activate-name`,
- install packages listed or given in `.txt` files,
- install a jupyter kernel.

`delete-venv` will reverse all of the above.

## Use examples
`create-venv` takes:
- the environment name (first argument),
- (optional) a list of package names and `.txt` files (like `requirements.txt`, can be multiple),
- (optional) a directory to install to (check first line for default); **must be preceeded with `-d`**.

For example:
```
./create-venv data-env numpy pandas sympy ml_req.txt statsmodels -d '~/python-files'
```

`delete-venv` takes:
- the environment name (first argument),
-  (optional) a directory to look for environment (check first line for default); **must be preceeded with `-d`**.

For example:
```
./delete-venv data-env -d '~/python-files'
```

## How to use
Download or clone the files and make sure they are executable:
```
chmod +x create-venv
chmod +x delete-venv
```
It is recommended to add aliases for ease of use:
```
cd <folder with scripts>
echo -e "alias create-venv=\"$(pwd)/create-venv\"" >> ~/.bash_aliases
echo -e "alias delete-venv=\"$(pwd)/delete-venv\"" >> ~/.bash_aliases
```

## Notes
The scripts were made on Linux Mint 21.2. Those with a different system should modify parts of the code should modify the code as needed. Customization is also expected, such as changing the default folder or getting rid of Jupyter parts if not wanted. It is **strongly recommended** to audit the code yourself, especially if you wish to use `delete-venv`.
