// We need solidity to work with ethereum
// openzeppelin- Free contracts

// https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/access/Ownable.sol";
contract DTCToken is ERC20, Ownable {
    constructor() ERC20("DTC Token", "DT") Ownable(msg.sender) {} 

    function mintFifty() public onlyOwner {
        _mint(msg.sender, 50 * 10**decimals());
    }
}
