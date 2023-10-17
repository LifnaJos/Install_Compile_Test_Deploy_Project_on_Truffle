## Step - 1: Installation of Truffle
**a. On Ubuntu 22.04 LTS**
- Follow the steps to install Truffle as per the [tutorial](https://github.com/LifnaJos/installing-truffle-on-ubuntu-22.04#steps-for-installing-truffle-on-ubuntu-2204-lts)

**b. On Windows**
1. Install Nodejs
- Go to [Nodejs website](https://nodejs.org/en/download) and download the stable version.

![nodejs](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/nodejs_installation.jpg)

2. Install Truffle
- On the command prompt, check the version of nodejs ```node -v```

- Check the version of nvm ```npm -v```

- Type : ```npm install -g truffle```
  
![truffle](https://github.com/LifnaJos/truffle_experiment/blob/main/images/truffle_installation.jpg)

- Check the version of Truffle ```truffle version```
  
- To install Ganache```npm install -g ganache```

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/truffle_version_ganache_installation.jpg)

3. Install VS Code
- Go to the [Visual Studio Code](https://code.visualstudio.com/download) and download the Windows version
  
![vscode](https://github.com/LifnaJos/truffle_experiment/blob/main/images/install_vscode.jpg)

4. Add Solidity extension on VS
![solidity](https://github.com/LifnaJos/truffle_experiment/blob/main/images/vs_solidity_install.jpg)

## Step - 2: Create or Unbox a Truffle project 
### 1 (a). Unbox an existing Truffle Project - MetaCoin
- On the Terminal :  ```mkdir MetaCoin```
- Go to the folder: ```cd MetaCoin```
- Unbox the Truffle Project : ```truffle unbox metacoin```

![unbox](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/install_metacoin_project_truffle_unbox.jpg)

### 1 (b) To create a bare project that doesn’t come with any smart contract or boilerplate code, type:  ```truffle init```

- The following directory structure is created :
```
.
├── contracts           <-- solidity contracts live here
├── migrations          <-- migration scripts live here
├── test                <-- tests (Solidity and JS) live here
└── truffle-config.js   <-- truffle configuration file
```

## Step - 3 : Compile a Truffle Project
- On the VS Terminal : ```truffle compile```

![compile_error](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/truffle_compile_error.jpg)

- To resolve this issue run the following commands on the VS Terminal
  
```set-ExecutionPolicy RemoteSigned -Scope CurrentUser```

```Get-ExecutionPolicy```

```Get-ExecutionPolicy -list```

![compile_error_solution](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/vscode_unauthorizedError_solution.jpg)

* This command generates **.json** files corresponding to each Smart Contract.

![compile](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/truffle_build_files.jpg)

## Step - 4 : Test the Smart Contracts
- The test files are saved in the folder, **test** with an extension **.js**
- For the sample project created the file name : **metacoin.js**

![truffle_test_files](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/truffle_test_files.jpg)

- Run the Command : ```truffle test```

![truffle_test](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/truffle_test.jpg)

## Step - 5 : Deploying the Smart Contract
- In the Project folder there is a configuration file : **truffle-config.js**.
- In this file uncomment the development network parameters and set the port number as **7545** as shown below

![config](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/truffle_ganache_network.jpg)

- Start the Ganache Environment.
- Select a new Workspace and name: **Metacoin**
- Add the Project configuration file: **truffle-config.js**

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/ganache_truffle_project_config.jpg)

- Type the command : ```truffle migrate --reset```

![migrate](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/truffle_migrate_1.jpg)

![migrate](https://github.com/LifnaJos/Install_Compile_Test_Deply_Project_on_Truffle/blob/main/images/truffle_migrate_2.jpg)

## Acknowledgements
* [NodeJS](https://nodejs.org/en/download)
* [VS Code](https://code.visualstudio.com/Download)
* [VSCode Unauthorized Error](https://www.c-sharpcorner.com/article/how-to-fix-ps1-can-not-be-loaded-because-running-scripts-is-disabled-on-this-sys/) article helped to resolve the error
* [Truffle Quickstart](https://docs.linea.build/build-on-linea/quickstart/deploy-smart-contract/truffle)
* [Installing Node JS on Windows](https://phoenixnap.com/kb/install-node-js-npm-on-windows)
* [Truffle Ultimate Guide](https://trufflesuite.com/guides/ultimate-guide-to-truffle-the-gateway-to-full-stack-blockchain-development/#part-five-truffle-dashboard) explains all the ways to deploy smart contracts in Truffle.
