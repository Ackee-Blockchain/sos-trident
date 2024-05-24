# Fuzz Test Example for Trident Fuzzer

---

## Program and Errors Description

- ### Initialize
    In this function, we initialize an Escrow Account and lock the entered amount within the Escrow. The Receiver's PubKey is stored within the Account.

- ### Withdraw
    - The Receiver, meant to withdraw funds from the Escrow, can call this Instruction. It will close the Escrow Account and transfer all funds (locked amount + rent) to the Receiver.
    - ❗ **NOTE:** 🐛 We do not correctly perform a check to ensure that the **Signer** is the corresponding receiver in the Escrow Account, **resulting in the 🚨unauthorized withdrawal🚨**.
