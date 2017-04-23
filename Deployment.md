## SikobaPresale.sol Deployment

The SikobaPresale contract deployment process has just been separated into two parts - the first to deploy the contract and check the parameters, and the second to send the preallocation funding to the contract.

This documents list the steps required to deploy this contract to Mainnet.

<br />

<hr />

## Steps Before Deployment Of The Contract To Mainnet

* [] Update the contract parameters
  * [] Confirm MINIMUM_PARTICIPATION_AMOUNT and MAXIMUM_PARTICIPATION_AMOUNT below
  * [] Adjust PRESALE_MINIMUM_FUNDING and PRESALE_MAXIMUM_FUNDING to desired EUR equivalents
  * [] Adjust PRESALE_START_DATE and confirm the presale period
  * [] Adjust OWNER_CLAWBACK_DATE as appropriate
  * [] Update TOTAL_PREALLOCATION to the total preallocations received
  * [] Add each preallocation address and funding amount from the Sikoba bookmaker to the constructor function
* [] A stable version of Solidity ^0.4.8 has been used. Check for any major bugs in the Solidity release announcements after this version.
* [] Test the deployment to a dev blockchain or Testnet to confirm the constructor will not run out of gas as this will vary with the number of preallocation account entries
  * [] Deploy this contract
  * [] Change owner account to another designated owner account
  * [] New owner accounts calls `fundPreallocation()`, sending the necessary ethers with the transaction
* [] Deploy to Mainnet
  * [] BK to deploy contract. Fill in the address below
  * [] BK to add verified source to the contract on EtherScan
  * [] BK to call `transferOwnership(...)` with the parameter being account [0x9b3b0e006b0f840588DA04b9B05F5C378785bAf3](https://etherscan.io/address/0x9b3b0e006b0f840588DA04b9B05F5C378785bAf3)
  * [] AK/RK to check source code matches Github code
  * [] AK/RK to confirm that the owner account is correct
  * [] BK/AK/RK to check the following contract parameters
    * [] `PRESALE_START_DATE`
    * [] `PRESALE_END_DATE`
    * [] `OWNER_CLAWBACK_DATE`
    * [] `totalFunding` matches `TOTAL_PREALLOCATION`
  * [] AK to call `fundPreallocation()`, sending the necessary ethers
  * [] BK/AK/RK to check the following live contract parameters
    * [] `preallocationFunded` must be true

<br />

<hr />

## Interactiving With The SikobaPresale Contract On Mainnet

* Contract address: {to be updated}
* Contract ABI:
  > [{"constant":false,"inputs":[{"name":"value","type":"uint256"}],"name":"participantWithdrawIfMinimumFundingNotReached","outputs":[],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"TOTAL_PREALLOCATION","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"MINIMUM_PARTICIPATION_AMOUNT","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"value","type":"uint256"}],"name":"ownerWithdraw","outputs":[],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"PRESALE_MINIMUM_FUNDING","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"OWNER_CLAWBACK_DATE","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"PRESALE_MAXIMUM_FUNDING","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"MAXIMUM_PARTICIPATION_AMOUNT","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"balanceOf","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"preallocationFunded","outputs":[{"name":"","type":"bool"}],"payable":false,"type":"function"},{"constant":false,"inputs":[],"name":"ownerClawback","outputs":[],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"PRESALE_END_DATE","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":false,"inputs":[],"name":"fundPreallocation","outputs":[],"payable":true,"type":"function"},{"constant":true,"inputs":[],"name":"PRESALE_START_DATE","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"totalFunding","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"inputs":[],"payable":false,"type":"constructor"},{"payable":true,"type":"fallback"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":false,"name":"value","type":"uint256"},{"indexed":false,"name":"timestamp","type":"uint256"}],"name":"LogParticipation","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"}],"name":"OwnershipTransferred","type":"event"}]