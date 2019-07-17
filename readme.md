# Account Contract

## Release Note：

**1.0.0**

Script Hash: [0x5fa5aa68cf3330923463351f336f8caf95188ab5]

Contract Address: AYKmPJNRvZm46hvS2VgUXF5fkZF2Cfq9Pf

### Overview:

Account refer to account contract assets issued by Alchemint. Account applys some methods for alias name.  

### Descriptions:

Methods defined in account contract:

| Methods     | Parameters                         | Return value | Descriptions                                                 |
| ----------- | ---------------------------------- | ------------ | ------------------------------------------------------------ |
| openAccount | byte[] addr,string name            | bool         | Create the alias account by addr.                            |
|getAccountInfo| string name                       | byte[]       | Get the account info by alias name.                          |
| recharge    |byte[] addr,string name,string type,string assetName,BigInteger mout| bool| Transfer asset to account by name.    |
| withdraw    |byte[] addr,string name,string type,string assetName,BigInteger mout| bool| Transfer asset from account to itself by name.|
| getBalance  | string name,string type,string assetName| int      | Get the balance of name..                                   |
| approveTransfer|byte[] addr,string srcName,string destName,string type,string assetType,string asset,BigInteger mout| bool| A approveTransfer method that approves some other accounts transfer. |
| approveOneKey| byte[] addr,string srcName,string destName,string assetType,string asset, BigInteger totalMount,BigInteger singleMount,BigInteger hzMount| bool|  A approveOneKey method that approves some other accounts transfer. |
| getApproveInfo| string srcName,string destName, string type, string assetType, string asset | byte[]    | getApproveInfo method that query approve info. |
| userTransfer| byte[] addr, string srcName, string destName,string assetType, string assetName, BigInteger mount| bool| A userTransfer method that transfers asset by name.|
| transfer    | byte[] addr, string srcName, string destName, string assetType, string assetName, BigInteger mount | bool| A transfer method that transfers asset by name. |
| setAccount  | string key, byte[] address                                                                         | bool| A setAccount method that set some account by admin,such as:business_account\admin_account\fee_account\sdusd_account. |
| getAccount  | string key                       | byte[]          | getAccount by the key.                                      |
| getUserName | byte[] addr                      | string          | getUserName by addr.                                        |
| setConfig   | string key, BigInteger value     | bool            | A setConfig method that set some system config.             |
| getConfig   | string key                       | int             | getConfig by the key.                                       |

Notification defined in Contract:

| Notification | Parameters                        | Descriptions                                                 |
| ------------ | --------------------------------- | ------------------------------------------------------------ |
| accOperator  | byte[] from, byte[] name,BigInteger optype, BigInteger value | Notification contains the four elements of accOperator: addr(from), name(to),operator type ,operator value.|
| accApproveOperator  | byte[] from, byte[] to,byte[] srcName,byte[] destName,byte[] type,byte[] assetType,byte[] asset,BigInteger mount | Notification contains the eight elements of accApproveOperator.|
| accUserTransfer  | byte[] from, byte[] to, byte[] srcName, byte[] destName,byte[] assetType, byte[] asset, BigInteger mount| Notification contains the eight elements of accUserTransfer.|
