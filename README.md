# Free Email Domains

A maintained JSON list of free email provider domains. Originally based on [free-email-domains](https://github.com/Kikobeats/free-email-domains) by [Kiko Beats](https://kikobeats.com), which was based on [HubSpot blocked domains](https://knowledge.hubspot.com/forms/what-domains-are-blocked-when-using-the-blocked-email-domains-feature).

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

## Related

- [free-email-domains](https://github.com/Kikobeats/free-email-domains) - The original list by Kiko Beats (npm package).
- [email-providers](https://github.com/Kikobeats/email-providers) - Top 3k common emails by Alexa rank.

## License

MIT - See [LICENSE](LICENSE) for details.

Originally created by [Kiko Beats](https://kikobeats.com), released under the MIT License.
