# truffle-sca2t-test Audit Report
- [1 Overview](#1-overview)
  * [1.1 Audit Details](#11-audit-details)
  * [1.2 Number of vulnerabilities per severity](#12-number-of-vulnerabilities-per-severity)
- [2 Report | lib/vulnerablemath.sol: vulnerablemath](#2-report--libvulnerablemathsol-vulnerablemath)
  * [2.1 The binary addition can overflow. (High :scream:)](#21-the-binary-addition-can-overflow-high-scream)
  * [2.2 A floating pragma is set. (Medium :fearful:)](#22-a-floating-pragma-is-set-medium-fearful)
- [3 Report | MetaCoin.sol: MetaCoin](#3-report--metacoinsol-metacoin)
  * [3.1 Use of tx.origin is deprecated. (Medium :fearful:)](#31-use-of-txorigin-is-deprecated-medium-fearful)
  * [3.2 Multiple sends are executed in one transaction. (Medium :fearful:)](#32-multiple-sends-are-executed-in-one-transaction-medium-fearful)
- [4 Report | origin.sol: Origin](#4-report--originsol-origin)
  * [4.1 A floating pragma is set. (Medium :fearful:)](#41-a-floating-pragma-is-set-medium-fearful)
  * [4.2 Use of tx.origin is deprecated. (Medium :fearful:)](#42-use-of-txorigin-is-deprecated-medium-fearful)
  * [4.3 Use of tx.origin is deprecated. (Medium :fearful:)](#43-use-of-txorigin-is-deprecated-medium-fearful)
  * [4.4 Use of &#34;tx.origin&#34; as a part of authorization control. (Medium :fearful:)](#44-use-of-%2334txorigin%2334-as-a-part-of-authorization-control-medium-fearful)
  * [4.5 Use of &#34;tx.origin&#34; as a part of authorization control. (Medium :fearful:)](#45-use-of-%2334txorigin%2334-as-a-part-of-authorization-control-medium-fearful)

## 1 Overview
### 1.1 Audit Details
* **Project Name:** truffle-sca2t-test
* **Tools:** [MythX](https://mythx.io/)

### 1.2 Number of vulnerabilities per severity
|       |  Num  |
| :---: | :---: |
|  High | 1 |
|  Medium |  8 |


## 2 Report | lib/vulnerablemath.sol: vulnerablemath
* **MythX Error:**  
N/A  
* **MythX Log:**  
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


## 3 Report | MetaCoin.sol: MetaCoin
* **MythX Error:**  
N/A  
* **MythX Log:**  
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


## 4 Report | origin.sol: Origin
* **MythX Error:**  
N/A  
* **MythX Log:**  
N/A  
  
### 4.1 A floating pragma is set. (Medium :fearful:)
#### SWC
* **SWC-ID**: SWC-103
* **SWC-TITLE**: Floating Pragma
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-103

#### Description
It is recommended to make a conscious choice on what version of Solidity is used for compilation. Currently any version equal or greater than &#34;0.5.0&#34; is allowed.  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/origin.sol  
source (0:23)  :  
```solidity
pragma solidity ^0.5.0;  
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
source (353:362)  :  
```solidity
tx.origin  
```
### 4.3 Use of tx.origin is deprecated. (Medium :fearful:)
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
### 4.4 Use of &#34;tx.origin&#34; as a part of authorization control. (Medium :fearful:)
#### SWC
* **SWC-ID**: SWC-115
* **SWC-TITLE**: Authorization through tx.origin
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-115

#### Description
Using &#34;tx.origin&#34; as a security control can lead to authorization bypass vulnerabilities. Accessing the origin information has been discovered in a conditional statement. It is recommended to use &#34;msg.sender&#34; instead.  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/origin.sol  
source (353:362)  :  
```solidity
tx.origin  
```
### 4.5 Use of &#34;tx.origin&#34; as a part of authorization control. (Medium :fearful:)
#### SWC
* **SWC-ID**: SWC-115
* **SWC-TITLE**: Authorization through tx.origin
* **URL**: https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-115

#### Description
Using &#34;tx.origin&#34; as a security control can lead to authorization bypass vulnerabilities. Accessing the origin information has been discovered in a conditional statement. It is recommended to use &#34;msg.sender&#34; instead.  

#### Locations
file: /mnt/c/workdir/vscode_project/truffle-sca2t-test/contracts/origin.sol  
source (386:395)  :  
```solidity
tx.origin  
```

 

***
***Powered By [truffle-sca2t](https://github.com/tagomaru/truffle-sca2t)***
