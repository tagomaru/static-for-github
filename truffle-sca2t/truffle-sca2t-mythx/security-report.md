# Audit Report
## 1 Overview
#### 1.1 Audit Details
* **Project Name:** truffle-sca2t-test
* **Tools:** [MythX](https://mythx.io/)


## 2. Report | lib/vulnerablemath.sol: vulnerablemath
#### MythX Error 
N/A  
#### MythX Log
N/A  
  
### 2.1 The binary addition can overflow. (High :scream:)
#### SWC
* **SWC-ID**: SWC-101
* **SWC-TITLE**: Integer Overflow and Underflow
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-101

#### Description
The operands of the addition operation are not sufficiently constrained. The addition could therefore result in an integer overflow. Prevent the overflow by checking inputs or ensure sure that the overflow is caught by an assertion.  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/lib/vulnerablemath.sol  
source (109:114)  :  
```solidity
a + b  
```
### 2.2 A floating pragma is set. (Medium :fearful:)
#### SWC
* **SWC-ID**: SWC-103
* **SWC-TITLE**: Floating Pragma
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-103

#### Description
It is recommended to make a conscious choice on what version of Solidity is used for compilation. Currently any version equal or greater than &#34;0.5.0&#34; is allowed.  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/lib/vulnerablemath.sol  
source (0:23)  :  
```solidity
pragma solidity ^0.5.0;  
```


## 3. Report | MetaCoin.sol: MetaCoin
#### MythX Error 
N/A  
#### MythX Log
N/A  
  
### 3.1 Use of tx.origin is deprecated. (Medium :fearful:)
#### SWC
* **SWC-ID**: SWC-111
* **SWC-TITLE**: Use of Deprecated Solidity Functions
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-111

#### Description
The smart contract retrieves the transaction origin (tx.origin) using msg.origin. Use of msg.origin is deprecated and the instruction may be removed in the  future. Use msg.sender instead.
See also: https://solidity.readthedocs.io/en/develop/security-considerations.html#tx-origin  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/MetaCoin.sol  
source (523:532)  :  
```solidity
tx.origin  
```
### 3.2 Multiple sends are executed in one transaction. (Medium :fearful:)
#### SWC
* **SWC-ID**: SWC-113
* **SWC-TITLE**: DoS with Failed Call
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-113

#### Description
Consecutive calls are executed at the following bytecode offsets:
Offset: 506
Offset: 690
Try to isolate each external call into its own transaction, as external calls can fail accidentally or deliberately.
  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/MetaCoin.sol  
source (815:975)  :  
```solidity
function getBalanceInEth(address addr) public view returns(uint){
		ConvertLib2.convert(getBalance(addr),2);
		return ConvertLib.convert(getBalance(addr),2);
	}  
```


## 4. Report | origin.sol: Origin
#### MythX Error 
N/A  
#### MythX Log
N/A  
  
### 4.1 Use of tx.origin is deprecated. (Medium :fearful:)
#### SWC
* **SWC-ID**: SWC-111
* **SWC-TITLE**: Use of Deprecated Solidity Functions
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-111

#### Description
The smart contract retrieves the transaction origin (tx.origin) using msg.origin. Use of msg.origin is deprecated and the instruction may be removed in the  future. Use msg.sender instead.
See also: https://solidity.readthedocs.io/en/develop/security-considerations.html#tx-origin  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/origin.sol  
source (353:362)  :  
```solidity
tx.origin  
```
### 4.2 Use of tx.origin is deprecated. (Medium :fearful:)
#### SWC
* **SWC-ID**: SWC-111
* **SWC-TITLE**: Use of Deprecated Solidity Functions
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-111

#### Description
The smart contract retrieves the transaction origin (tx.origin) using msg.origin. Use of msg.origin is deprecated and the instruction may be removed in the  future. Use msg.sender instead.
See also: https://solidity.readthedocs.io/en/develop/security-considerations.html#tx-origin  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/origin.sol  
source (386:395)  :  
```solidity
tx.origin  
```

 

***
powered by [truffle-sca2t](https://github.com/tagomaru/truffle-sca2t)
