**t3rn
Simplifying Cross-Chain Interactions**

Welcome to t3rn, a decentralised framework designed to elevate blockchain interoperability. Whether you're a developer or an end user, t3rn offers a seamless way to execute smart contracts across different chains, bridging the gap between blockchains and creating a more connected ecosystem.

**Overview**
t3rn is a pioneering platform tailored to handle the complexities of cross-chain interactions. By offering secure and decentralised solutions, it allows you to integrate multiple blockchain ecosystems without compromising security or transparency.

**Highlights**
Multi-Chain Compatibility
t3rn enables your smart contracts to interact with multiple blockchain networks, ensuring reliable execution across various platforms.

**Asset Integration**
The platform simplifies asset transfers between chains, enhancing usability and interoperability for diverse blockchain projects.

**Community-Centric Operations**
At t3rn, participation matters. From contributing liquidity to engaging in governance, there’s a role for everyone in shaping the future of this ecosystem.

**Why Choose t3rn?**
Trustless Infrastructure: All operations are carried out transparently without requiring trust in a central entity.
Developer-Friendly: Focus on building your ideas, while t3rn takes care of cross-chain complexities.
Incentivised Participation: Whether you're an Executor or an active member of the community, rewards await those who contribute.

**How to Get Started
**
Ready to dive in? Here's how you can begin:

Explore our tools to write and deploy cross-chain smart contracts.
Use our APIs to bridge assets efficiently.
Join the Executor program to contribute liquidity and earn rewards.
For detailed guides and tutorials,

Download the latest executor release using the wget command:

<pre>
  <code id="code-block">wget https://github.com/t3rn/executor-release/releases/download/v0.34.0/executor-linux-v0.34.0.tar.gz </code>
</pre>

The t3rn executor is a critical component of the t3rn platform, enabling seamless execution of cross-chain smart contracts. This guide walks you through the step-by-step configuration and commands required to set up and run the executor effectively.

Prerequisites
Before proceeding, ensure you have the following:

Linux Environment: This guide assumes you're running commands on a Linux machine.
Private Key: Your private key is necessary for executing operations securely.
Network Information: Details about the blockchain networks you'll be interacting with, including RPC endpoints if you plan to use custom configurations.

Step-by-Step Configuration

Step 1: Download the Executor Package

Download the latest executor release using the wget command:

<pre>
  <code id="code-block">wget https://github.com/t3rn/executor-release/releases/download/v0.34.0/executor-linux-v0.34.0.tar.gz </code>
  
</pre>


Step 2: Extract the Package
Unpack the downloaded tarball file:

tar -xvzf executor-linux-v0.34.0.tar.gz  

<pre>
  <code id="code-block">tar -xvzf executor-linux-v0.34.0.tar.gz </code>
  
</pre>


Step 3: Navigate to the Executor Directory
Move into the executor binary directory:

cd executor/executor/bin  

<pre>
  <code id="code-block">cd executor/executor/bin </code>
  
</pre>

Step 4: Setting Environment Variables
Required Variables
Set up the necessary environment variables to configure the executor: Enter Below command one by one

 
<pre>
  <code id="code-block">export NODE_ENV=testnet  </code>
  
</pre>

<pre>
  <code id="code-block">export LOG_LEVEL=debug  
export LOG_PRETTY=false </code>
  
</pre>


<pre>
  <code id="code-block">export EXECUTOR_PROCESS_ORDERS=true  
export EXECUTOR_PROCESS_CLAIMS=true</code>
  
</pre>

   
<pre>
  <code id="code-block">export EXECUTOR_MAX_L3_GAS_PRICE=1000 </code>
  
</pre>

export EXECUTOR_MAX_L3_GAS_PRICE=1000  (You can reduce the Gas Price to 50 if you want)


<pre>
  <code id="code-block">export PRIVATE_KEY_LOCAL=Your_Private_Key</code>
  
</pre>

 

export ENABLED_NETWORKS='arbitrum-sepolia,base-sepolia,optimism-sepolia,l1rn'  (If you want the executor to handle only specific networks, update the ENABLED_NETWORKS variable. For example, to run the executor for Base and Optimism Sepolia: export ENABLED_NETWORKS='base-sepolia,optimism-sepolia,l1rn')

<pre>
  <code id="code-block">export EXECUTOR_PROCESS_PENDING_ORDERS_FROM_API=false</code>
  
</pre>

Step 5: ./executor  (Once all configurations are complete, execute the following command to start the executor)
<pre>
  <code id="code-block">./executor</code>
  
</pre>
 

Completed, - Below are optional step if you want to customize executor
_________________________________________________________________________________________________________________________________________________________________________________________

Optional: Running Specific Networks
If you want the executor to handle only specific networks, update the ENABLED_NETWORKS variable. For example, to run the executor for Base and Optimism Sepolia:

export ENABLED_NETWORKS='base-sepolia,optimism-sepolia,l1rn'  

_________________________________________________________________________________________________________________________________________________________________________________________
Configuring Custom RPC Endpoints
You can add custom RPC URLs for specific networks. This step is optional; the executor will use default RPC URLs if you skip this.

Adding Custom RPC URLs
Replace NETWORK_NAME with the appropriate network identifier and specify the URLs: export RPC_ENDPOINTS_${NETWORK_NAME}='https://url1.io,https://url2.io'  

Example for Arbitrum Sepolia:
export RPC_ENDPOINTS_ARBT='https://arb-sepolia.g.alchemy.com/v2/your_id,https://url2.io'  

Supported Network Names:
arbt: Arbitrum Sepolia
bssp: Base Sepolia
blss: Blast Sepolia
opsp: Optimism Sepolia
Example for Supported Networks

export RPC_ENDPOINTS_BSSP='https://base-sepolia.g.alchemy.com/v2/your_id'  
export RPC_ENDPOINTS_BLSS='https://blast-sepolia.g.alchemy.com/v2/your_id'  
export RPC_ENDPOINTS_OPSP='https://opt-sepolia.g.alchemy.com/v2/your_id'  
export RPC_ENDPOINTS_ARBT='https://arb-sepolia.g.alchemy.com/v2/your_id'  
_________________________________________________________________________________________________________________________________________________________________________________________

export EXECUTOR_PROCESS_PENDING_ORDERS_FROM_API=false  

Running the Executor
Once all configurations are complete, execute the following command to start the executor:

./executor  



Notes
1.  Ensure all environment variables are set correctly before running the executor.
2.  For private keys and sensitive information, use secure storage mechanisms to avoid accidental exposure.
3.  If you encounter issues, double-check the network and RPC configurations.



