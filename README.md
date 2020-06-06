# EthDeployer
A simple react app for automatically compiling &amp; deploying Solidity language Ethereum smart-contracts

Easily deploy your Solidity smart-contracts against the Mainnet without actually needing shell/rpc access to a synced ethereum server!

###dependencies

(install nodejs and npm, latest versions if you can)

npm i -g truffle             # a useful Solidity-language tool

Metamask browser plugin      # for auto-signing of contracts (manual private-key signing not enabled yet)

### How to install

git clone https://www.github.com/Tectract/EthDeployer

cd EthDeployer

npm i

npm start     # for testing mode

npm run build     # for live server hosting mode, use apache/httpd/nginx or similar routing tool for local path/URL customization

my lines in /etc/httpd/conf/httpd.conf (should be the same for /etc/apache2/sites-enabled/default.conf)

note: extra lines to catch case-sensitivity on linux path spellings :)

Alias /EthDeployer /home/ec2-user/EthDeployer/build

Alias /ethdeployer /home/ec2-user/EthDeployer/build  

Alias /ethDeployer /home/ec2-user/EthDeployer/build

Alias /Ethdeployer /home/ec2-user/EthDeployer/build

<Directory /home/ec2-user/EthDeployer/build>

  PassengerEnabled off

</Directory>

### Notes

   fixed browser-solc.js / browser-solc.min.js to support solidity 0.5.x+ versions
   not working in chrome or brave browsers right now!


### How to Use

install metamask browser plugin (see https://metamask.io), and connect to either mainnet, or localhost:8545 (local node / testrpc server)

note: metamask seems bad at remembering your password! remember to keep your 12-word-passphrase!!

make sure you can see accounts in metamask, and they should either be live accounts with real ether, or match your testrpc local testing accounts

'npm start' will tell you the local port number and try to open the browser to the test server hosted page

otherwise, 'npm run build', customize path via passenger/apache, and visit the page

copy/paste your solidity contract into the box and press 'Compile & Deploy', you will be prompted for gas payment via metamask plugin

if you are running testrpc on localhost:8545, you can turn metamask off, or connect it to localhost:8545 and it will prompt you for testnet gas payment! (see notes below)

Your Solidity language contract is now deployed on either testnet or Ethereum mainnet (if you paid real ether!)

links are displayed for the TXID and Contract address. You will need to WAIT about 30s for the next block, for the tx/address to appear, on mainnet

use the web console debugger tool for console messages and debugging, please submit updates/upgrades, bug reports, feature requests THROUGH THE GITHUB ISSUES TOOL FOR THIS REPO!


Useful tool info and examples for learning to write Ethereum smart-contracts, to accompany my BlockGeeks article

truffle commands:

truffle init

truffle compile

truffle migrate

truffle console
