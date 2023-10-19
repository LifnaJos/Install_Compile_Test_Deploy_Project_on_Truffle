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

## Step - 5 a: Deploying the Smart Contract via Truffle Command Line Interface
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

- On the Ganache Environment - Account Tab: 5 transactions are reported corresponding to the deployment

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Project_on_Truffle/blob/main/images/truffle_project_ganache_deploy_1.jpg)

- On the Ganache Environment - Blocks tab, 5 blocks are created in the Ganache environment

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Project_on_Truffle/blob/main/images/truffle_project_ganache_deploy.jpg)

- On the Ganache Environment - Transactions Tab: Contract creation details are listed

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Project_on_Truffle/blob/main/images/truffle_project_ganache_deploy_2.jpg)

- On the Ganache Environment - Contracts Tab: Contract deployment details are listed

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Project_on_Truffle/blob/main/images/truffle_project_ganache_deploy_3.jpg)

- On Ganache Environment - Events Tab: Contract registered event is reported
![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Project_on_Truffle/blob/main/images/truffle_project_ganache_deploy_4.jpg)

## Step - 5 b: Deploy Project via Truffle Dashboard
1. Run the command ```truffle dashboard``` on the VSCode Terminal

![truffle_dashboard](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/Screenshot%20from%202023-10-19%2020-33-27.png)

- Truffle Dashboard is running on ```http://localhost:24012/rpc```

2. Login to the Metamask Wallet and select the Network as Sepolia Testnet
   
![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_1.jpg)

3. Run the commnad ```truffle migrate --network dashboard
 
![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_2.jpg)

- This command starts to deploy the smart contract : **ConvertLib.sol**
- On the Truffle Dashboard, there will be a prompt to confirm the deployment of the smart Contract : **ConvertLib.sol**
- Click the **Confirm button**

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_3.jpg)

- Metamask extension will popup for confirmation.
- Click the **Confirm** button
  
![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_4.jpg)

- The status of the transaction is displayed on the Metamask popup window
  
![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_5.jpg)

- Next the migrate command starts to deploy the smart contract : **MetaCoin.sol**
- On the Truffle Dashboard, there will be a prompt to confirm the deployment of the smart Contract : **MetaCoin.sol**
- Click the **Confirm button**

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_6.jpg)

- Metamask extension will popup for confirmation.
- Click the **Confirm** button

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_7.jpg)

- The status of the transaction is displayed on the Metamask popup window

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_8.jpg)

- Deployment details on the VScode Terminal as follows:
  
![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_2b.jpg)

![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_2c.jpg)

- The transacrion details are displayed on Etherscan.io : Sepolia Testnet
  
![ganache](https://github.com/LifnaJos/Install_Compile_Test_Deploy_Truffle_Project_on_Ganache/blob/main/images/truffle_dashboard_9.jpg)

![ganache]()

## Acknowledgements
* [NodeJS](https://nodejs.org/en/download)
* [VS Code](https://code.visualstudio.com/Download)
* [VSCode Unauthorized Error](https://www.c-sharpcorner.com/article/how-to-fix-ps1-can-not-be-loaded-because-running-scripts-is-disabled-on-this-sys/) article helped to resolve the error
* [Truffle Quickstart](https://docs.linea.build/build-on-linea/quickstart/deploy-smart-contract/truffle)
* [Installing Node JS on Windows](https://phoenixnap.com/kb/install-node-js-npm-on-windows)
* [Truffle Ultimate Guide](https://trufflesuite.com/guides/ultimate-guide-to-truffle-the-gateway-to-full-stack-blockchain-development/#part-five-truffle-dashboard) explains all the ways to deploy smart contracts in Truffle.
