# plasma-client
`plasma-client` is a lightweight plasma chain client that allows you to make transactions on a plasma chain.
You can think of it like the equivalent of [parity](https://www.parity.io/ethereum/) or [geth](https://github.com/ethereum/go-ethereum/wiki/geth) for Ethereum.

---

**Just looking to make your first transaction?**
Skip ahead to the [Getting Started](#getting-started) section!

---

## Contributing
Welcome! If you're looking to contribute to `plasma-client`, you're in the right place.

### Contributing Guide and CoC
Plasma Group follows a [Contributing Guide and Code of Conduct](https://github.com/plasma-group/plasma-client/blob/master/.github/CONTRIBUTING.md) adapted slightly from the [Contributor Covenant](https://www.contributor-covenant.org/version/1/4/code-of-conduct.html).
All contributors are expected to read through this guide.
We're here to cultivate a welcoming and inclusive contributing environment, and every new contributor needs to do their part to uphold our community standards.

### Contributor Setup
#### Requirements
`plasma-client` has a few requirements:

- `git`
- `Node.js`

You'll find detailed instructions on installing these requirements in our [Getting Started](#getting-started) section.

#### Packages
`plasma-client` makes use of several `npm` packages.

Install all required packages with:

```
npm install
```

### Running Tests
`plasma-client` makes use of a combination of [`Mocha`](https://mochajs.org/) (a testing framework) and [`Chai`](https://www.chaijs.com/) (an assertion library) for testing.

Run all tests with:

```
npm test
```

**Contributors: remember to run tests before submitting a pull request!** Code with passing tests makes life easier for everyone and means your contribution can get pulled into this project faster. :-)

---

## Getting Started
Running `plasma-client` is pretty simple.
Here we'll take you through the steps to get started with `plasma-client` and make your first plasma transactions!

### Running a Terminal
Before you keep going, it's probably good to become familiar with using the terminal on your computer.
Here are some resources for getting started:

- [Windows: Command Prompt: What It Is and How to Use It](https://www.lifewire.com/command-prompt-2625840)
- [MacOS: Introduction to the Mac OS X Command Line](https://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line)
- [Linux: How to Start Using the Linux Terminal](https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/)

### Installing Git
`git` is an open source version control system.
You don't really need to know how it works, but you *will* need it in order to install `plasma-client`.

#### Windows
Atlassian has a [good tutorial](https://www.atlassian.com/git/tutorials/install-git#windows) on installing `git` on Windows.
It's basically just installing an `.exe` and running a setup wizard.

#### MacOS
Installing `git` on a Mac is [pretty easy](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
You basically just need to type `git` into your terminal.
If you have `git` installed, you'll see a bunch of output.
Otherwise, you'll get a pop-up asking you to install some command-line tools (including `git`).

#### Linux
Installing `git` on Linux is also pretty easy.
However, the exact install process depends on your distribution.
[Here's a guide](https://gist.github.com/derhuerst/1b15ff4652a867391f03#file-linux-md) for installing on some popular distributions.

### Installing Node.js
Most of the Plasma Group apps are built in JavaScript and make use of a tool called [Node.js](https://nodejs.org/en/).
In order to run our tools, including `plasma-client`, you'll need to make sure that you’ve got `Node.js` installed.

Here's a list of ways to install `Node.js` on different operating systems:

#### Windows
If you're on a windows computer, you can download the latest Long-term Support (LTS) version of `Node.js` [here](https://nodejs.org/en/download/).
You'll just need to install the `.msi` file that `Node.js` provides and restart your computer.

#### MacOS
You have some options if you want to install `Node.js` on a Mac.
The simplest way is to download the `.pkg` file from the `Node.js` [downloads page](ps://nodejs.org/en/download/).
Once you've installed the `.pkg` file, run this command on your terminal to make sure everything is working properly:

```
node -v
```

If everything is working, you should see a version number pop up that looks something like this:

```
v10.15.1
```

##### Homebrew
**Note**: If you've already installed `Node.js` with the above steps, you can skip this section!

You can also install `Node.js` using [Homebrew](https://brew.sh/).
First, make sure Homebrew is up to date:

```
brew update
```

Now just install `Node.js`:

```
brew install node
```

#### Linux
There are different ways to install `Node.js` depending on your Linux distribution.
[Here's an article](https://nodejs.org/en/download/package-manager/) that goes through installing `Node.js` on different distributions.

### Installing `plasma-client`

Once you've got `Node.js` installed, installing `plasma-client` is as simple as running this command in your terminal:

```
npm install -g plasma-client 
```

You might get an error that looks like this:

```
npm ERR! Error: EACCES: permission denied, access '/usr/local/lib/node_modules'
npm ERR!  { [Error: EACCES: permission denied, access '/usr/local/lib/node_modules']
npm ERR!   stack:
npm ERR!    "Error: EACCES: permission denied, access '/usr/local/lib/node_modules'",
npm ERR!   errno: -13,
npm ERR!   code: 'EACCES',
npm ERR!   syscall: 'access',
npm ERR!   path: '/usr/local/lib/node_modules' }
```

Don't worry, you're not doing anything wrong!
This has to do with how `Node.js` installs things -- sometimes it tries to install stuff in places it doesn't have permission to install.
There are a few ways to get around this problem.
First, try following [these instructions](https://github.com/sindresorhus/guides/blob/master/npm-global-without-sudo.md), then restart your terminal and try installing `plasma-client` again.
If you can't get that to work, you can also try installing as root:

```
sudo npm install -g plasma-client
```

Once you get `plasma-client` install, you'll have access to two commands from your terminal, `plasma-client` and `plasma-cli`.
`plasma-client` is the actual software that allows you to make transactions and see your balances.
`plasma-cli` is a [command-line interface](https://en.wikipedia.org/wiki/Command-line_interface) that talks to `plasma-client` and makes it easy to quickly start sending transactions using your terminal.

### Launching the Client
Now that you've installed `plasma-client`, it’s easy to connect to a plasma chain!
If you’re looking to quickly get started, you just run the following command in your terminal:

```
plasma-client
```

This will connect you to the [Plasma Group plasma chain](http://plasma-testnet.surge.sh) by default.
You can also connect to another plasma chain by running this command instead:

```
plasma-client —-operator https://link.to.operator
```

If everything goes to plan, you should see something like this:

```
Plasma Client v0.0.4-beta.4

Available Accounts
==================

Client Information
==================
Operator: http://107.22.13.89/api

Listening on: http://localhost:9898

Logs
====
  service:operator Successfully connected to operator +0ms
```

That means your client is running and ready to start sending and receiving transactions. Congrats!

#### Common Errors
The Plasma Group plasma chain currently uses a single party, called an operator, to aggregate transactions into blocks.
The cool thing about plasma is that your funds are always safe, even if the operator tries to steal them!
However, this does mean that we’re susceptible to the occasional outages that any software service will have.
As a result, you might see a message like this:

```
service:operator ERROR: Cannot connect to operator. Attempting to reconnect... +1ms
```

This usually means that you're not connected to the internet or, more likely, that the Plasma Group plasma chain operator is currently down and unable to receive transactions.
We’re working really hard to beef up our operator and keep these outages minimized, but failures do happen.
You can check our [Twitter](http://twitter.com/plasma_group) for updates on outages.

If the program says something else when you run it, or you spot another error, please submit a [bug report](https://github.com/plasma-group/plasma-client/issues/new?assignees=&labels=&template=bug_report.md&title=) on GitHub.
If you’re not familiar with GitHub and could use some more information about how to submit your first bug report, check out our [resources] page.

### Making your First Transaction
**Note**:
You **must** keep `plasma-client` running in order to send an receive transactions using `plasma-cli`.
Make sure not to close the terminal that's running `plasma-client` during this tutorial.
Open up a new terminal window before you keep going.

Once you’ve got the client running, it’s time to make your first transaction!
Before you can send money on the plasma chain, you’ll need to deposit money into the plasma chain smart contract.
Basically this just means that you’re sending some funds from your Ethereum wallet to the plasma chain smart contract’s address.

#### Creating an Account
You can use the command line interface to send funds over to the plasma chain.
If you've never used `plasma-client` before, you're going to need to create your first account.
Here's the command for doing that:

```
plasma-cli createaccount
```

You should see something like this:

```
Created new account: 0x4AF55746D15991230df040EDf21aDEef5Be78043
```

For this tutorial **you're going to want to create at least two accounts** using the above command.
Feel free to create more than two accounts if you'd like.
You can see all of your available accounts with `listaccounts`:

```
plasma-cli listaccounts
```

Hopefully you'll see a list of your accounts!

```
(0) 0x20a229b0677D7fe42214c15942B6c40cD1340249
(1) 0x4AF55746D15991230df040EDf21aDEef5Be78043
```

#### Submitting a Deposit
You're almost ready to submit a deposit!
Our plasma chain is currently deployed to the Ethereum test network (Rinkeby).
Before you can deposit, you're going to need some testnet ETH.
You can quickly get some using the [Rinkeby testnet faucet](https://faucet.rinkeby.io/) or by tweeting at us on [Twitter](https://twitter.com/plasma_group).

**Note**:
We recommend using the faucet to send testnet ETH to a [MetaMask](https://metamask.io/) wallet.
This makes it easier to send ETH to other accounts.
**You need to send a little ETH to each account that you've created.**

Once you've got some testnet ETH, you can submit your first deposit.
The format of the deposit command looks like this (don’t copy this one): 

```
plasma-cli deposit <account> <token> <amount>
```

In place of `<account>` you’ll want to insert the account you’re depositing with.
This can either be the “index” of the account (the number you see in front of the address when you run `listaccounts`) or the address of the account.
In place of `<token>`, you can put the contract address of the token you're depositing (ETH is just "0").
We support [ERC20](https://en.wikipedia.org/wiki/ERC-20) tokens, but for now we're just going to leave `<token>` as 0 and deposit some ETH.
Finally, `<amount>` is the total amount of ETH you're going to deposit, denominated in [wei](https://www.investopedia.com/terms/w/wei.asp).
You can use [this Ethereum unit converter](https://etherconverter.online/) to easily calculate how much testnet ETH you'll be depositing.

Let's go ahead and deposit a few hundred wei:

```
plasma-cli deposit 0 0 500
```

That'll create an Ethereum transaction that you can view on a block explorer:

```
Sending deposit transaction...
Deposit successful!
View deposit on Etherscan: https://rinkeby.etherscan.io/tx/0xa066eb33b4d613ca4f06334d1867428c7788d44465afd92ae002a0242ec33b55
```

This is going to submit a deposit transaction for 500 wei from the `0th` (first) account.

You can check that the deposit was successful by looking at your balance with the `getbalance` command:

```
plasma-cli getbalance <account>

```

Let's try it:

```
plasma-cli getbalance 0
```

Your balance should (ideally) be 500:

```
0: 500
```

#### Sending a Transaction
We're almost there!
Sending a transaction is as simple as running one command that looks like this:

```
plasma-cli send <from> <to> <token> <amount>
```

`<from>` is the account you're going to send money from.
As with `deposit`, you can either put the full address or use the account index.
`<to>` is the address you're sending money to.
If you want to just try sending money to yourself, you can use an account index.
Otherwise you can also use an Ethereum address (e.g. `0x4cdC4f412355F296C2cf261210Cc9274404E442b`).

Let's go ahead and send 500 wei to your other account.

```
plasma-cli send 0 1 0 500
```

If everything goes according to plan, you'll see a transaction receipt:

```
Transaction receipt: 0000039a0120a229b0677D7fe42214c15942B6c40cD1340249d42b2b067cD2B2EDA3F7D3AdC9d3b400665CE8140000000000000000000000000000012c000000000000000000000190011c800cdbe44ebac984fa84e093ed1c8fa61ca14d4d5eb0e97b82d9dc54ada3f5d903dbb99d8f5aa8ecc765a5a329f4b557419ba7639ba4481b9e7e8108604e9138
```

This means you've just sent a plasma transaction! 🎉🎉🎉🎉

You'll probably have to wait a few second for the transaction to be detected and imported.
Take a look at the other terminal where you're running `plasma-client`.
After about thirty seconds, you should see a message saying a new transaction has been imported:

```
service:sync Detected new transaction: 0xee208ad1f181b909c4ee969f999da990cd65f0f9d90f6ef2e1169929f5c96602 +443ms
service:sync Attemping to pull information for transaction: 0xee208ad1f181b909c4ee969f999da990cd65f0f9d90f6ef2e1169929f5c96602 +1ms
service:sync Successfully imported transaction: 0xee208ad1f181b909c4ee969f999da990cd65f0f9d90f6ef2e1169929f5c96602 +10ms
```

Now, if you check the balance of your first account, you'll notice that it's empty:

```
plasma-cli getbalance 0
```

However, if you check the balance of your second account...

```
plasma-cli getbalance 1
```

You should see a result!

```
0: 500
```

#### Starting an Exit
Sending a transaction is fun, but it's meaningless if you can't get your money back out.
Now we're going to try doing exactly that.
You can easily withdraw (or "exit" your funds using the command line).
The command looks like this:

```
plasma-cli exit <account> <token> <amount>
```

This command will automatically start one or more "exit transactions".
Let's try withdrawing the funds we just sent to our second accont:

```
plasma-cli exit 1 0 500
```

Rememver, this means that we're withdrawing 500 wei from the account at index 1 (the second account, it's a little confusing).
You should get a notification that your exit transactions were submitted:

```
Sending exit transaction(s)...
Exited in 1 transaction(s)
View exit(s) on Etherscan:
(0) https://rinkeby.etherscan.io/tx/0xfa23433c145d3ffc222dd1504bd388a4bfc993a08647edc5988e70f18b8b4918
```

The decrease in your balance will be immediately reflected:

```
plasma-cli getbalance 1
```

However, if you click on those Etherscan links you'll notice that you aren't actually withdrawing any money.
This is because withdrawals from plasma chains don't get processed right away.
Instead, each withdrawal needs to wait out a "challenge period" before it can be processed.
You can see the status of your withdrawal using this command:

```
plasma-cli getexits <account>
```

Since we sent funds to our second account, use:

```
plasma-cli getexits 1
```

Your withdrawal should pop up in the results:

```
(0) Exit #X: IN CHALLENGE PERIOD
```

#### Finalizing an Exit
We've set challenge periods to be pretty short for now, about 20 Ethereum blocks (5 minutes).
That means you get to take a break and/or [tweet at us](https://twitter.com/plasma_group) if you have any feedback so far!

After ~5 minutes, go ahead and check on your exit again:

```
plasma-cli getexits 1
```

You should see that your exit is ready to be processed:

```
(0) Exit #X: READY TO BE FINALIZED
```

If it's not ready yet, wait a few more minutes and try again.
Otherwise, you're ready to finalize your withdrawals.
You just need to run one simple command:

```
plasma-cli finalizeexits <account>
```

Again since we started our deposit from the second account, we're going to set `<account>` to "1":

```
plasma-cli finalizeexits 1
```

Hopefully you'll see something like this:

```
Sending exit finalization transaction(s)...
Finalized 1 exit(s)
View finalization(s) on Etherscan:
(0) https://rinkeby.etherscan.io/tx/0x2f6dcf6f556eaf23682c42172dade96426ef84b55bea397bdc956ed7e3c36504
```

Congrats, you've just gone through the entire flow of using a plasma chain!
Hopefully it didn't break too many times.
