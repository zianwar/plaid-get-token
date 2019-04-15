## Server to retreive Plaid Developlemnt token

This code was copied and adapted from:
[https://github.com/plaid/quickstart/tree/master/node](https://github.com/plaid/quickstart/tree/master/node)


## Disclaimer

This project was built for personal finance purposes, all the code does is talks to [Plaid](https://plaid.com) API and write tokens to your local file system.
If you decided to use it, please be sure to go through the code yourself to make sure it does what it says in case you don't feel safe entering your bank credentials.

## Usage

- Sign up for [Plaid](https://plaid.com/) and apply for the development plan (It's free and limited to 100 items (i.e. banks)). You might need to wait to get approved.

- Once approved, fill out the following in `.env` from your [Plaid dashboard](https://dashboard.plaid.com/account/keys):

  - `PLAID_CLIENT_ID`
  - `PLAID_SECRET`
  - `PLAID_PUBLIC_KEY`

- Now you need to connect to your financial institutions to generate access tokens, run the following command:
```bash
npm run get-token <account_name> <output_token_path>
```

 - `account_name`: is a name for the bank you want to connect, it's for your personal reference, so you can name it anything.
 - `output_token_path`: a path where to store the retrieved token, e.g: `./token_chase.txt`.

 **What the command will do is:**

>>Start a local server at [http://localhost:3333](http://localhost:3333) which you can visit in your browser and go through the authentication flow. Once you've linked the bank, its associated access token will be saved in the path you provided `<output_token_path>`.  
This process needs to be repeated for each bank you want to connect. Make sure to run each with a different `account` name.

- After than you can use your access token, to talk with the [Plaid](https://plaid.com/) API to retreive your balance, transactions....
