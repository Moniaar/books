<div align="center" markdown="1">
<br/>

![logo](https://github.com/user-attachments/assets/5c92ea81-d081-4e3d-8d78-4580cf62ddbd)

<br/>

<h1>Calcify</h1>

**Accounting has never been easy**

</div>

## Calcify

Frappe Books is an open-source accounting software aimed at simplifying financial management for businesses. With its clean and user-friendly interface, it streamlines accounting tasks for small and medium-sized enterprises, offering a seamless solution for modern businesses to manage their finances with ease.

<details>
<summary>Screenshots</summary>
<br/>
<img  alt="Pos" src="https://github.com/user-attachments/assets/f75116b4-cf5f-45ee-9927-ba380fa56a46" />
    <br/><br/>
    <img  alt="General Ledger" src="https://github.com/user-attachments/assets/58d8bcdf-1576-4008-b010-7054fb64a12d" />
    <br/><br/>
    <img  alt="Profit and Loss" src="https://github.com/user-attachments/assets/11bd67d1-d808-496b-ac4d-ef68c18b9419" />

</details>

### Motivation

Calcify addresses a market gap where small businesses face expensive, complex accounting tools. It offers an intuitive, open-source solution that combines simplicity with essential features, empowering businesses to manage finances effectively—even offline.

### Key Features

- **Dashboard**: Provides an overview of key financial data and performance metrics.
- **Point of Sale**: Simplifies retail transactions with an integrated POS system for easy sales processing.
- **Works Offline**: Enables users to continue working without an internet connection and sync later.
- **Double-entry accounting**: Ensures accurate financial tracking by recording each transaction in two accounts.
- **Entries**
  - **Invoicing**: Allows businesses to create and manage professional invoices effortlessly.
  - **Billing**: Billing processes by generating bills and tracking payments.
  - **Payments**: Records and tracks payments received and made.
  - **Journal Entries**: Records financial transactions in the general ledger with detailed notes and adjustments.
- **Financial Reports**
  - **General Ledger**: Centralized record of all financial transactions, providing a comprehensive view of accounts.
  - **Profit and Loss Statement**: Summarizes revenues, costs, and expenses to show business profitability.
  - **Balance Sheet**: Displays a company’s assets, liabilities, and equity at a specific point in time.
  - **Trial Balance**: Verifies the accuracy of accounting records by ensuring that debits and credits are balanced.
    <br/>

### Under the Hood

- **Vue.js**: In Calcify, Vue.js powers the front-end, enabling a reactive and component-based UI. It ensures seamless interactions and dynamic updates, giving users a modern, responsive experience.

- **Electron**: Electron is used to package Frappe Books as a standalone desktop application, allowing it to run offline and provide a native-like experience across Windows, macOS, and Linux.

- **SQLite**: Calcify uses SQLite as its local database. All financial data, transactions, and configurations are stored securely in an SQLite file on the user's machine.

## Production Setup

### Manual

## Development Setup

### Pre-requisites

To get the dev environment up and running you need to first set up Node.js `v20.18.1` and npm. For this, we suggest using
[nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

Next, you will need to install [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable).

### Clone and Run

Once you are through the Pre-requisites, you can run the following commands to
setup Calcify for development and building:

```bash
clone the repository

# change directory
cd Calcify

# install dependencies
yarn
```

To run Calcify in development mode (with hot reload, etc):

```bash
# start the electron app
yarn dev
```

**Note: First Boot**

When you run `yarn dev` electron will run immediately but the UI will take a
couple of seconds to render this because of how dev mode works. Each file is
individually served by the dev server. And there are many files that have to be
sent.

**Note: Debug Electron Main Process**

When in dev mode electron runs with the `--inspect` flag which allows an
external debugger to connect to port 5858. You can use chrome for this by
visiting `chrome://inspect` while Frappe Books is running in dev mode.

See more [here](https://www.electronjs.org/docs/latest/tutorial/debugging-main-process#external-debuggers).

#### Build

To build Frappe Books and create an installer:

```bash
# start the electron app
yarn build
```

**Note: Build Target**
By default the above command will build for your computer's operating system and
architecture. To build for other environments (example: for linux from a windows
computer) check the _Building_ section at
[electron.build/cli](https://www.electron.build/cli).

So to build for linux you could use the `--linux` flag like so: `yarn build --linux`.
