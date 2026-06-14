# Charles Schwab GraphQL Schema

## Overview

This conceptual GraphQL schema represents the Charles Schwab Trader API and Market Data API surface. Charles Schwab operates one of the largest retail brokerage platforms in the United States, offering individual investors access to equities, options, bonds, ETFs, mutual funds, and futures. The Schwab Developer Portal exposes OAuth 2.0-secured REST endpoints under the Trader API v2 and Market Data API that enable third-party applications to manage accounts, place orders, retrieve positions and transactions, and consume real-time and historical market data.

This schema captures the domain model implied by the published REST endpoints and translates it into a GraphQL type system suitable for client applications that prefer a declarative, graph-oriented query interface over REST.

## Schema Source

- **Developer Portal**: https://developer.schwab.com/
- **Trader API Docs**: https://developer.schwab.com/products/trader-api--individual
- **Getting Started**: https://developer.schwab.com/user-guides/get-started
- **Authentication**: https://developer.schwab.com/user-guides/get-started/authenticate-with-oauth
- **Base URL (Trader)**: https://api.schwabapi.com/trader/v1
- **Base URL (Market Data)**: https://api.schwabapi.com/marketdata/v1

## Authentication

Charles Schwab uses OAuth 2.0 with PKCE for both the Trader API and Market Data API. Access tokens expire after 30 minutes and are refreshed using a refresh token valid for 7 days. All GraphQL queries and mutations require a valid Bearer token in the Authorization header.

## Domain Areas

### Account Management

Types covering linked brokerage accounts, balances, purchasing power, margin information, and account-level settings. Supports individual, IRA, Roth IRA, 401(k), margin, and cash account variants.

### Positions and Holdings

Instrument-level position data within each account including quantity, average cost, market value, unrealized gain/loss, and day gain/loss. Positions reference underlying instrument symbols including equities, options, ETFs, mutual funds, and fixed income.

### Orders

Full order lifecycle covering placement, retrieval, cancellation, and replacement. Supports market, limit, stop, stop-limit, trailing stop, and OCO (one-cancels-other) order types. Orders are composed of one or more order legs, each referencing an instrument and a quantity/instruction pair.

### Transactions

Historical account activity including trades, dividends, interest credits, transfers, and journal entries. Each transaction links to the initiating order where applicable.

### Market Data

Real-time and delayed quotes for equities, options, indices, and ETFs. Price history (OHLCV) with configurable frequency and date range. Option chains with full strike/expiration grids. Market hours for major US exchanges. Instrument search and fundamental data.

### Streaming and Webhooks

Streaming token provisioning for the Schwab Streaming Service (websocket-based level 1 quotes, account activity). Webhook subscription management for order fill notifications.

### Watchlists

User-defined watchlists containing symbol collections with optional display ordering.

### User and Authentication

User principal data, linked account associations, streaming credentials, and OAuth token metadata.

## Types Summary

The schema defines 67 named types across the following categories:

| Category | Types |
|---|---|
| Authentication & User | Authentication, AccessToken, RefreshToken, UserPrincipals, UserAccount, UserSubscription, Preference, StreamingToken |
| Accounts | Account, BrokerageAccount, IRAAccount, RothIRA, Account401k, MarginAccount, CashAccount, AccountBalance, PurchasingPower |
| Positions | Position, Holding |
| Orders | OrderRecord, OrderLeg, MarketOrder, LimitOrder, StopOrder, StopLimitOrder, TrailingStop, OCOOrder, Trade |
| Transactions | Transaction |
| Instruments | Instrument, Stock, Bond, ETF, Index, MutualFund, Option, Equity, Forex, Future, Crypto, Symbol |
| Market Data | Quote, OptionQuote, OptionChain, OptionExpiration, OHLCV, HistoricalData, MarketHour, MoversData, Fundamental |
| Research | News, Research, AnalystRating, EarningEstimate |
| Screening | Screener, Filter |
| Watchlists | WatchList, WatchListInstrument |
| Customer | Customer |

## Query Entry Points

- `account(accountId: ID!)` — fetch a single linked account
- `accounts` — list all accounts linked to the authenticated user
- `order(accountId: ID!, orderId: ID!)` — fetch a single order
- `orders(accountId: ID!, filter: OrderFilter)` — list orders within an account
- `transaction(accountId: ID!, transactionId: ID!)` — fetch a single transaction
- `transactions(accountId: ID!, filter: TransactionFilter)` — list transactions
- `quote(symbol: String!)` — real-time or delayed quote for a symbol
- `quotes(symbols: [String!]!)` — batch quotes
- `optionChain(symbol: String!, filter: OptionChainFilter)` — full option chain
- `priceHistory(symbol: String!, filter: PriceHistoryFilter)` — OHLCV history
- `marketHours(markets: [Market!]!, date: String)` — exchange hours
- `movers(index: String!, direction: Direction, change: ChangeType)` — market movers
- `instrument(cusip: String!)` — instrument by CUSIP
- `searchInstruments(symbol: String!, projection: Projection)` — symbol search
- `watchlists(accountId: ID!)` — user watchlists
- `watchlist(accountId: ID!, watchlistId: ID!)` — single watchlist
- `userPrincipals` — authenticated user metadata and streaming credentials
- `news(symbols: [String!])` — news headlines
- `screener(filter: ScreenerFilter)` — equity screener

## Mutation Entry Points

- `placeOrder(accountId: ID!, input: OrderInput!)` — place a new order
- `cancelOrder(accountId: ID!, orderId: ID!)` — cancel an existing order
- `replaceOrder(accountId: ID!, orderId: ID!, input: OrderInput!)` — replace an order
- `createWatchlist(accountId: ID!, input: WatchListInput!)` — create a watchlist
- `updateWatchlist(accountId: ID!, watchlistId: ID!, input: WatchListInput!)` — update a watchlist
- `deleteWatchlist(accountId: ID!, watchlistId: ID!)` — delete a watchlist
- `updatePreferences(accountId: ID!, input: PreferenceInput!)` — update account preferences
