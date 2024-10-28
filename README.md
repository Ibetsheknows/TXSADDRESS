# TXSADDRESS
TXSADDRESS
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
    <script src="./../../../dist/mempool.js"></script>
    <script>
      const init = async () => {
        try {
          const {
            bitcoin: { addresses },
          } = mempoolJS();
          
          const address = 'bc1qhvfzaal0cv0s79egzrc5jxu9wvv3ftwgs7rvfa';
          
          const myAddress = await addresses.getAddress({ address });
          console.log(myAddress);
          
          const addressTxs = await addresses.getAddressTxs({ address });
          console.log(addressTxs);
          
          const addressTxsChain = await addresses.getAddressTxsChain({ address });
          console.log(addressTxsChain);
          
          const addressTxsMempool = await addresses.getAddressTxsMempool({
            address,
          });
          console.log(addressTxsMempool);
          
          const addressTxsUtxo = await addresses.getAddressTxsUtxo({ address });
          console.log(addressTxsUtxo);
        } catch (error) {
          console.log(error);
        }
      };
      init();
    </script>
  </head>
  <body></body>
</html>
