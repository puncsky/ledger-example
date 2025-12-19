# Family Ledger

A Beancount ledger for tracking family finances.

## Structure

- `main.beancount` - Main ledger file containing all accounts and transactions

## Accounts

### Assets
- **Assets:US:JPMorgan:Checking** - JPMorgan Chase checking account (starting balance: $5,000.00)
- **Assets:US:Cash** - Cash on hand

### Liabilities
- **Liabilities:CreditCard** - Credit card balances

### Income
- **Income:Salary** - Regular salary income
- **Income:Bonus** - Bonus income
- **Income:Other** - Other income sources

### Expenses
Organized by category:
- **Groceries** - Food shopping
- **Dining** - Restaurant and takeout
- **Transportation** - Gas, public transit, parking
- **Housing** - Rent/mortgage, insurance, maintenance
- **Utilities** - Electric, gas, water, internet, phone
- **Healthcare** - Medical, dental, pharmacy, insurance
- **Entertainment** - Streaming services, movies, hobbies
- **Shopping** - Clothing, electronics, home goods
- **Education** - Tuition, books, supplies
- **Childcare** - Childcare expenses
- **Pets** - Pet food and veterinary
- **Subscriptions** - Various subscriptions
- **Insurance** - Auto and life insurance
- **Travel** - Accommodation, transportation
- **Fitness** - Gym memberships
- **Personal** - Haircare and personal care
- **Gifts** - Gift expenses
- **Charity** - Charitable donations
- **Fees** - Bank fees and other fees
- **Taxes** - Federal, state, property taxes
- **Other** - Miscellaneous expenses

## Usage

### Adding Transactions

Add transactions to `main.beancount` in the format:

```beancount
2025-12-18 * "Store Name" "Description"
  Assets:US:JPMorgan:Checking    -45.32 USD
  Expenses:Groceries              45.32 USD
```

### Validate Ledger

```bash
bean-check main.beancount
```

### Generate Reports

```bash
# Balance sheet
bean-report main.beancount balances

# Account statement
bean-query main.beancount "SELECT date, narration, position WHERE account = 'Assets:US:JPMorgan:Checking'"
```

### Web Interface

```bash
fava main.beancount
```

Then open http://localhost:5000 in your browser.

## Getting Started

1. Install Beancount: `pip install beancount`
2. (Optional) Install Fava for web interface: `pip install fava`
3. Start adding your transactions to `main.beancount`
4. Validate with `bean-check main.beancount`
