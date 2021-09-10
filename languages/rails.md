find_each
returns nil

distinct values from db
```rb
Sondermind::Billing::FinancialEntry.select('DISTINCT memo').map(&:memo)
```