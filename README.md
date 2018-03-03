# Curve Coin
Shell script to install a [Curve Masternode](http://curvecoin.co/) on a Linux server running Ubuntu 16.04. Use it on your own risk.

***
## Installation:
```
wget -q https://raw.githubusercontent.com/zoldur/CurveCoin/master/curve_install.sh  
bash curve_install.sh  
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Curve Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **25000** **CURV** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:

```
curve-cli mnsync status
curve-cli getinfo
curve-cli masternode status
```

Also, if you want to check/start/stop **Curve** , run one of the following commands as **root**:

```
systemctl status Curve #To check the service is running.
systemctl start Curve #To start Curve service.
systemctl stop Curve #To stop Curve service.
systemctl is-enabled Curve #To check whetether Curve service is enabled on boot or not.
```
***

## Sentinel

**Sentinel** is installed in **/root/.curvecore/sentinel/** and added to **crontab** file.  
Sentinel log file is **/root/curve_sentinel.log**  
Test the config by running the following commands:
```
cd /root/.curvecore/sentinel
./venv/bin/py.test ./test
```
***

## Donations:  

Any donation is highly appreciated.  

**BTC**: 1BzeQ12m4zYaQKqysGNVbQv1taN7qgS8gY  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LXrWbfeejNQRmRvtzB6Te8yns93Tu3evGf
