# Online shop (Django + PayPal)

Shop with product catalogue, cart, orders, login and PayPal (sandbox) payment.

> Status: minimal runnable version. Parts that were incomplete are marked with `TODO` in the code; external services are mocked.

## Quick start (Docker)

```sh
make docker-run        # builds the image and serves http://localhost:8000
```

## Quick start (local Python 3.5)

```sh
make setup             # creates .venv and installs requirements.txt
make run               # migrates SQLite and serves http://localhost:8000
make superuser         # optional: admin user for /admin
```

## Mocks

Controlled by `USE_MOCKS` (default `1`), added at the end of `myshop/settings.py`:

- PayPal stays in sandbox mode with a placeholder receiver email; no real payments.
- TODO: payment completion relies on PayPal IPN callbacks, which cannot reach localhost. Orders stay unpaid locally.

## TODO

- Order payment status is never updated locally (PayPal IPN).
- TODO: move `SECRET_KEY` out of source control before any deployment.
