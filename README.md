# Free Email Domains

A maintained JSON list of free email provider domains (e.g., gmail.com, yahoo.com, outlook.com).

Useful for detecting signups with free/personal email addresses vs. business/corporate domains.

## Usage

### Direct URL

```
https://raw.githubusercontent.com/srworksllc/free-email-domains/main/domains.json
```

### JavaScript / Node.js

```js
const domains = require('./domains.json');

function isFreeEmail(email) {
  const domain = email.split('@').pop().toLowerCase();
  return domains.includes(domain);
}
```

### PHP

```php
$domains = json_decode(file_get_contents('domains.json'), true);

function isFreeEmail(string $email): bool {
    $domain = strtolower(explode('@', $email)[1] ?? '');
    return in_array($domain, $GLOBALS['domains'], true);
}
```

## Data

- **File:** `domains.json`
- **Format:** JSON array of lowercase domain strings, sorted alphabetically
- **Count:** ~4,778 domains

## Contributing

To add or remove domains, edit `domains.json` and submit a pull request. Keep the list sorted alphabetically.

## License

MIT
