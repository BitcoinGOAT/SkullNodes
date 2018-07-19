# SkullNodes
Shell script to install a [SkullNodes Masternode](https://skullnodes.io) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -N https://raw.githubusercontent.com/BitcoinGOAT/SkullNodes/master/contrib/mn-install/skullnodes_install.sh
bash skullnodes_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the SkullNodes Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **10000** SKX to **MN1**. You need to send all 10000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Tools -> "Debug Console"**  
6. Type the following command: **masternode outputs**  
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start-alias MN1
```
14. Login to your VPS and check your masternode status by running the following command to confirm your MN is running:
```
skullnodes-cli masternode status
```
***

## Usage:
```
skullnodes-cli masternode status
skullnodes-cli getinfo
skullnodes-cli mnsync status
```
Also, if you want to check/start/stop **SkullNodes**, run one of the following commands as **root**:

```
systemctl status SkullNodes #To check if SkullNodes service is running  
systemctl start SkullNodes #To start SkullNodes service  
systemctl stop SkullNodes #To stop SkullNodes service  
systemctl is-enabled SkullNodes #To check if SkullNodes service is enabled on boot  
```  
***

Based on awesome install scripts by [Zoldur][https://github.com/zoldur]