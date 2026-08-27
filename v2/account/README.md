# Animal Company API - Account Endpoint

**Endpoint:** `https://animalcompany.us-east1.nakamacloud.io/v2/account`

## Authorization: `Bearer yourAuthToken`

## METHOD: `GET`

## Default Response

```json
{
  "user": {
    "id": "00000000-0000-0000-0000-000000000000",
    "username": "ABCDE-FGHIJKLMNO",
    "display_name": "null.client",
    "lang_tag": "en",
    "metadata": "{}",
    "steam_id": "00000000000000000",
    "edge_count": 0,
    "create_time": "2026-08-14T16:02:11Z",
    "update_time": "2026-08-27T12:43:01Z"
  },
  "wallet": "{\"hardCurrency\": 0, \"researchPoints\": 0}"
}
```

## Response Despripition

| Field | Type | Description |
|-------|------|-------------|
| `id` | `string` (UUID) | Unique user identifier |
| `username` | `string` | Randomly generated alphanumeric string |
| `display_name` | `string` | User's display name (from Meta/Steam) |
| `lang_tag` | `string` | Language tag for the user's game client (e.g., `en`, `fr`, `es`) |
| `metadata` | `string` (JSON) | Developer-only metadata (enabled in dev mode) |
| `steam_id` | `string` | Steam ID — only present if authenticated via Steam token |
| `edge_count` | `integer` | Maximum number of friends the user has ever had |
| `create_time` | `string` (ISO 8601) | Account creation timestamp |
| `update_time` | `string` (ISO 8601) | Last account update timestamp |
| `wallet` | `string` (JSON) | Contains `hardCurrency` (Company Coins) and `researchPoints` |

## Notes

- All timestamps are in **ISO 8601 UTC** format (`YYYY-MM-DDTHH:mm:ssZ`).
- The `wallet` is a escaped json, it is a json but just a string
