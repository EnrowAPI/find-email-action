# Find Email Action

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/EnrowAPI/find-email-action)](https://github.com/EnrowAPI/find-email-action)
[![Last commit](https://img.shields.io/github/last-commit/EnrowAPI/find-email-action)](https://github.com/EnrowAPI/find-email-action/commits)

GitHub Action to find professional email addresses. Powered by [Enrow](https://enrow.io).

## Usage

```yaml
- name: Find email
  uses: EnrowAPI/find-email-action@v1
  id: enrow
  with:
    api_key: ${{ secrets.ENROW_API_KEY }}
    full_name: 'John Doe'
    company_domain: 'apple.com'

- name: Use the result
  run: echo "Found email: ${{ steps.enrow.outputs.email }}"
```

## Inputs

| Name             | Required | Default | Description                              |
| ---------------- | -------- | ------- | ---------------------------------------- |
| `api_key`        | Yes      |         | Your Enrow API key                       |
| `full_name`      | Yes      |         | Full name of the person                  |
| `company_domain` | No       |         | Company domain (e.g. `apple.com`)        |
| `company_name`   | No       |         | Company name (alternative to domain)     |
| `country_code`   | No       |         | ISO 3166-1 alpha-2 country code          |
| `wait`           | No       | `true`  | Poll until the result is ready           |

## Outputs

| Name            | Description                          |
| --------------- | ------------------------------------ |
| `email`         | The found email address              |
| `qualification` | Result qualification (`valid`, `invalid`) |
| `id`            | The search ID                        |
| `raw`           | Full JSON response from the API      |

## Pricing

Enrow gives you **50 free credits** when you sign up. Each email lookup costs **1 credit**.

[Create a free account](https://app.enrow.io/sign-up)

## Links

- [Enrow website](https://enrow.io)
- [API documentation](https://docs.enrow.io)
- [Dashboard](https://app.enrow.io)
