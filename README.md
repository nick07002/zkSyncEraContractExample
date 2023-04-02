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
    这个命令返回会给出部署好合约的地址 拷贝下来
7. 在浏览器检查合约

    到
    https://goerli.explorer.zksync.io/
    输入第六步得到的合约地址，就可以到达你刚部署好的合约界面
8. 验证合约

    在以上页面中点击contract,

    Contract name填入 CoinFlip

    Zksolc version选择v1.3.5

    Solc version 选择 0.8.17   

    代码栏把 contracts/CoinFlip.sol 的内容拷贝进去 

    验证合约

9. 合约验证成功之后，就可以直接从网页端调用合约了。

   比如这个合约 read可以读consecutiveWins, write可以写flip
    
    
