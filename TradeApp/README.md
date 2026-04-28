# Trade App PH (XAMPP Version)

Simple trading app with frontend + backend + API + MySQL database.

## Project Structure

- `public/` - frontend pages and assets
- `public/assets/css/` - CSS files
- `public/assets/js/` - JavaScript files
- `api/` - REST API endpoints
- `config/` - database config
- `database/` - SQL schema for setup

## Requirements

- XAMPP (Apache + MySQL)
- PHP 8+

## Setup Steps

1. Put this folder inside your XAMPP `htdocs` (example: `C:/xampp/htdocs/TradeApp`).
2. Start `Apache` and `MySQL` in XAMPP Control Panel.
3. Open phpMyAdmin (`http://localhost/phpmyadmin`).
4. Import `database/schema.sql`.
5. Open app at:
   - `http://localhost/TradeApp/public/index.php`

If you already imported an older schema, re-import the updated one so `users` table and `user_id` in `trades` are available.

## API Endpoint

- `POST /TradeApp/api/auth.php?action=register` - create account
- `POST /TradeApp/api/auth.php?action=login` - login
- `POST /TradeApp/api/auth.php?action=logout` - logout
- `GET /TradeApp/api/auth.php?action=me` - current session
- `GET /TradeApp/api/trades.php` - list trades (supports filters)
- `POST /TradeApp/api/trades.php` - create trade
- `PUT /TradeApp/api/trades.php?id=1` - update trade
- `DELETE /TradeApp/api/trades.php?id=1` - delete trade
- `GET /TradeApp/api/trades.php?export=csv` - export CSV

Filter params:
- `asset`
- `search`
- `from_date` (YYYY-MM-DD)
- `to_date` (YYYY-MM-DD)
- `page` (default 1)
- `page_size` (default 10, max 100)

## Features Included

- Create trade
- Edit/update trade
- Delete trade
- Filter by asset/date
- Search for large trade history
- Pagination for large trade history
- CSV export
- Profit summary in PHP
- Profit-over-time chart
- User accounts (register/login/logout)
- Realized P/L per asset (average cost method)
