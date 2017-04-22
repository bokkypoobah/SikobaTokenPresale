## SikobaPresale.sol Deployment

The main risk in the deployment of the SikobaPresale contract is that ethers are sent with the deployment process. Steps have been taken to reduce this risk, but it is advisable to test out the deployment on a dev or testnet environment before deploying to mainnet.

<br />

<hr />

## Steps Before Deployment Of The Contract To Mainnet

1. Confirm MINIMUM_PARTICIPATION_AMOUNT and MAXIMUM_PARTICIPATION_AMOUNT below
2. Adjust PRESALE_MINIMUM_FUNDING and PRESALE_MAXIMUM_FUNDING to desired EUR equivalents
3. Adjust PRESALE_START_DATE and confirm the presale period
4. Update TOTAL_PREALLOCATION to the total preallocations received
5. Add each preallocation address and funding amount from the Sikoba bookmaker to the constructor function
6. Test the deployment to a dev blockchain or Testnet to confirm the constructor will not run out of gas as this will vary with the number of preallocation account entries
7. A stable version of Solidity has been used. Check for any major bugs in the Solidity release announcements after this version.
8. Remember to send the preallocated funds when deploying the contract!
