# OpReturnData

We analyse the usage of OP_RETURN throughout the Bitcoin blockchain, collecting a total of 1,566,192 OP_RETURN transactions.
Specifically, we gather all the OP RETURN transactions from the origin block up to the block number 438,000 (added on 2016/11/09).

We investigate to which protocols OP_RETURN transactions belong, identifying 23 distinct protocols (associated to 55% of these transactions).
We find that 19% of this total are empty transactions, that use the OP RETURN instruction with no data attached.
Finally, the unknown category contains 26% of the OP_RETURN transactions.

This repository contains the experimental data analysed as MySQL dumps.
  - The explorer_block.sql dump collects all blocks that contains at least one OP_RETURN transaction.
    For each block we save:
      - hash;
      - timestamp.

  - The explorer_emptytransactions.sql contains all empty transactions.
  - The explorer_unknowntransactions.sql contains all unknown transactions.
  - Each remaining dump is dedicated to the transactions of one of the 23 protocols found.
    For each transaction we save:
      - hash of the transaction;
      - metadata appended after the OP_RETURN instruction; 
      - hash of the block containing the transaction.
