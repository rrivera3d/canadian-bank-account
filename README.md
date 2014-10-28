# canadian-bank-account

Validate transit and account numbers of common Canadian banks.

## Usage

```javascript
var tdBankAccount = new CanadianBankAccount({institution: "003", transit: "12345", account: "1234567"});
tdBankAccount.isTransitValid(); // Returns true
tdBankAccount.isAccountValid(); // Returns true

var invalidAccount = new CanadianBankAccount({institution: "001", transit: "123", account: "123456789"});
invalidAccount.isTransitValid(); // Returns false
invalidAccount.isAccountValid(); // Returns false
invalidAccount.transitErrors(); // Returns ["Transit number must be 5 digits long."]
invalidAccount.accountErrors(); // Returns ["Bank of Montreal account number must be 7 digits long."]
```

## Acknowlegments

Validation rules based on the following article:
https://squareup.com/help/en-ca/article/5173-bank-account-troubleshooting
