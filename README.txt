https://oasismonitor.com/



--> generate a new account
mkdir new-account
cd new-account
oasis-node registry entity init
ll
-rw------- 1 root root  259 Dec 10 08:47 entity_genesis.json
-rw------- 1 root root   59 Dec 10 08:47 entity.json
-rw------- 1 root root  160 Dec 10 08:47 entity.pem

--> get address from public key
cat entity.json
{"v":1,"id":"3QASq0j00YmMn1WvRHIhT1eYrgzRdF8M9nnNVDFnN9Q="}
oasis-node stake pubkey2address --public_key 3QASq0j00YmMn1WvRHIhT1eYrgzRdF8M9nnNVDFnN9Q=
oasis1qpjz5w0eq3rj9uz5hr8hmpynmlxftzpewqlel2af


--> get account info
oasis-node stake account info -a unix:/oasis/data/internal.sock --stake.account.address oasis1qpjz5w0eq3rj9uz5hr8hmpynmlxftzpewqlel2af

--> send a tx
oasis-node stake account info -a unix:/oasis/data/internal.sock --stake.account.address oasis1qpjz5w0eq3rj9uz5hr8hmpynmlxftzpewqlel2af
# get nonce

# amount 10 ROSE = 10 * 10^9
oasis-node stake account gen_transfer \
  --genesis.file /oasis/genesis.json \
  --signer.dir /path/to/entity \
  --stake.amount 10000000000 \
  --stake.transfer.destination oasis1qppw9y8xg003zcrx37dqxrgqx22n0eql3qafnjyc \
  --transaction.file tx_transfer.json \
  --transaction.nonce 1 \
  --transaction.fee.gas 2000 \
  --transaction.fee.amount 2000

oasis-node consensus submit_tx -a unix:/oasis/data/internal.sock --transaction.file tx_transfer.json




