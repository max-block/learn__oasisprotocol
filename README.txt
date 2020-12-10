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







