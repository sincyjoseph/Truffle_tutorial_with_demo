# Truffle_tutorial_with_demo

1. Create a folder

2. cd in to that folder

3. >truffle init

4. contract, migration, and test folder generated

5. cd contract folder

6. paste yout smart contract inside that folder with .sol extension
	
	// SPDX-License-Identifier: MIT
  
	pragma solidity  >=0.4.18 < 0.9.0;

	contract Coursetro {
    
   	string fName;
    
   	uint age;
   
  	function setInstructor(string memory _fName, uint _age) public {
       		fName = _fName;
          
       		age = _age;
   	}
   
   	function getInstructor() public view returns (string memory, uint) {
    		return (fName, age);
        
   	}
    
	}

7. cd migration folder

8. create new file 2_deploy_contract.js

	var Coursetro = artifacts.require("Coursetro");

		module.exports = function (deployer) {
    
 		deployer.deploy(Coursetro);
    
		}
    
9.Save it 

10.>>truffle compile

11. Generate a build file containing Coursetro.json file

12. Open terminal  >>ganache-cli -p 8545

13. Open another terminal

	 >>truffle migrate
   
	 >>truffle console
   
	 >>var instance = await Coursetro.deployed()
   
	 >>instance
   
   	 >>instance.setInstructor("Sincy Joseph",22) 	//To interact with the smart contract use the instance, It will generate a transaction reciept.
   
	 >>instance.getInstructor()
