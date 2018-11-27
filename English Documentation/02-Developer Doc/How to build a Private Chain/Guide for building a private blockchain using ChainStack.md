# Guide for building a private blockchain using ChainStack
This article presents the method in the ubuntu operation system.
## DataBase Installing   
Use the following command to install MySQL Database    
```
1. sudo apt-get install mysql-server  
2. sudo apt-get install mysql-client    
```

After installation, execute the following command:   
```
netstat -tap | grep mysql    
```

If it shows the following result on the screen, then the installation of MySQL is successful.     

<image src="https://github.com/ChainStack-Official/ChainStack/blob/master/English%20Documentation/07-Others/pic/private%20blockchain/test_guide1.png">
## ToolBox Installing   
### 1.Download the ChainStack toolbox    
1) download chainstack_tool.tgz   
2) execute the command:   
```
mkdir ~/softwares     
``` 
to create a directory   

3) execute the command:    
```
cp chainstack_tool.tgz ~/sofewares     
``` 
to put the toolbox under this directory   


4) enter this directory and execute the command:   
```
tar xzvf chainstack_tool.tgz   
``` 

to uncompress this file.       

After that, we see the content by the command “ls”:    
<image src="https://github.com/ChainStack-Official/ChainStack/blob/master/English%20Documentation/07-Others/pic/private%20blockchain/test_guide2.png">
### 2. install the ChainStack toolbox    
Under the same directory, execute   
```
sudo ./chainstack.sh installation    
```
to  install the chainstack toolbox.   

## Configuration of the environment   
1. Set the bootnode   
```
cd ~/softwares/chainstack-deploy   
./chainstack.sh bn -ip “bootnode ip address”     
```
- e.g.    
```
./chainstack.sh bn -ip 192.168.2.3   
If the ip configuration is left unsettled, then the default ip address would be “127.0.0.1”     
```

2. Modify the genesis block configuration file    
```
Open ~/softwares/chainstack_deploy/genesis.json by editor and modify the parameters inside.    
Notice: The users sharing the same private blockchain should use the same genesis block.    
```

3. Set the number of nodes of all kind    
```
Open ~/softwares/chainstack_deploy/nodeCfg.json by editor, and set the parameters inside.   
In this file, “normal” means the number of normal nodes, miner means the number of miners, and verifier means the number of verifiers.    
```

## Running Chainstack   
1. The first time running or resetting the blockchain, execute the initialization script   
```
cd ~/softwares/chainstack_deploy   
./reset_local_env.sh     
```
2. Launch the deployment tool    
```
cd ~/softwares/chainstack_deploy     
```
3. surf 127.0.0.1:8889 on internet explorer     
<image src="https://github.com/ChainStack-Official/ChainStack/blob/master/English%20Documentation/07-Others/pic/private%20blockchain/test_guide3.png">
-  choose “node management”   
<image src="https://github.com/ChainStack-Official/ChainStack/blob/master/English%20Documentation/07-Others/pic/private%20blockchain/test_guide4.png">
-  click on “Launch” button and start chainstack   
<image src="https://github.com/ChainStack-Official/ChainStack/blob/master/English%20Documentation/07-Others/pic/private%20blockchain/test_guide5.png">
-  and click on “stop” button to stop chainstack    
<image src="https://github.com/ChainStack-Official/ChainStack/blob/master/English%20Documentation/07-Others/pic/private%20blockchain/test_guide6.png">
4. run private node in the command line    
  
```
boots_env=chainstack chainstackcli    
```

For the use of command line tool please refer to the command line tool guide.   
