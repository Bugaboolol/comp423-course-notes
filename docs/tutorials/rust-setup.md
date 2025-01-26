# Setting up a dev container for Rust

1. **Prerequisites**
    1. You need the following softwares: VSCode and Docker
    2. Install the Dev Containers extension on VSCode 

2. **Setting up a Dev Container in VSCode**
    1. Create a new project 
    ```
    mkdir rust-dev-container
    ```
    and
    ```
    cd rust-dev-container
    ```
    and 
    ```
    git init
    ```
    2. Open **VSCode** and navigate to the `rust-dev-container` directory
    3. Type `Cmd+Shift+P` on Mac and `Ctrl+Shift+P` on Windows type `Dev Containers: Add Development Container Configuration Files`.
    4. Press `Add configuration to workspace`. Search for **Rust**. Press `Rust, devcontainers` from from the list of container configurations and choose the version you want to run. Keep the default configurations.
    5. Now you should have a default `.devcontainers/devcontainers.json` file



    6. Now you have set up the Go Container environment. To start the container, press `Cmd+Shift+P` on mac or `Ctrl+Shift+P` on windows. Click `Dev Containers: Rebuild and Reopen in Container`. This will take a while.
    7. To customize your Dev Container, you can modify the `devcontainer.json` file as follows. The name of the container is in the `name` field. The `image` is the default Docker base environment. With the `customizations`, you can modify the settings or the extensions used in the environment. And finally there are further settings such as `postCreateCommand` which are commands that run after the container is built. Further documentation exists at [Create a Dev Container](https://code.visualstudio.com/docs/devcontainers/create-dev-container).
    8. In the terminal, once the container is running you can type ```rustc --version``` and ```cargo --version```

<ins>**Step E Code**</ins>
```json
    {
	"name": "Rust",
	"image": "mcr.microsoft.com/devcontainers/rust:1-1-bullseye",
	"features": {
		"ghcr.io/devcontainers/features/rust:1": {}
	}

	[
```
<ins>**Step G Code**</ins>
```json
        {
            "name": "COMP423 Course Notes",
            "image": "mcr.microsoft.com/devcontainers/python:latest",
            "customizations": {
                "vscode": {
                    "settings": {},
                    "extensions": ["ms-python.python"]
                }
            },
            "postCreateCommand": "pip install -r requirements.txt"
        }
```
    
3. **Now let us actually create in Rust!**
    1. Now type in the terminal ```cargo new testing```
    2. This should create a file which should initialize Rust 'src/main.rs' directory.
    3. In this new file we will code our program as follows.
    4. In the terminal type `cargo build` and `cargo run` this should result in a "Hello COMP423!" outputted.

<ins>**Step D Code**</ins>
```Rust
    fn main() {
    println!("Hello COMP423!");
}
```


* Primary author: [Tianyi Zhou](https://github.com/Bugaboolol)

* Reviewer: [Pranav Turlapati](https://github.com/pranavturlapati28)