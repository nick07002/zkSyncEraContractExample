# zkSyncEraContractExample

##
### 预先准备工作
1. mac上安装了 yarn, npm
  ```
  npm install --global yarn
  ```
2. 一个测试钱包，小狐狸。zksync testnet上有0.02 goerli eth 测试币

### How to deploy zkSync Era smart contract to testnet in 15mins.
### 如何用15分钟部署一个zksync era 智能合约
1. 克隆这个repo
2. 进入 greeter-example 
    ```
    cd greeter-example
    ```
3. 安装依赖库
    ```
    yarn init -y
    yarn add -D typescript ts-node @types/node ethers@^5.7.2 zksync-web3 @ethersproject/hash @ethersproject/web hardhat @matterlabs/hardhat-zksync-solc   @matterlabs/hardhat-zksync-deploy
    ```
4. 编译合约
    ```
    yarn hardhat compile
    ```
5. 填上你自己的私钥，准备部署合约
   
   打开 `deploy/deploy.ts`文件
   在第11行，把 `Your Private Key, Get It From Meta Mask` 替换成你的 metamask钱包私钥。
   
   如何找到私钥：
   在钱包右边点三个点的图标-> account details -> export private key.

   ！！注意：这里不要用有资产的大钱包，用专门来测试的小钱包。
6. 部署合约到测试网：
    ```
    yarn hardhat deploy-zksync
    ```
