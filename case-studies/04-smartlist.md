# SmartList: Smart Shopping & Shared Expenses

**Type:** my own product (Al Hussain Smart Solution) · **Live on [Google Play](https://play.google.com/store/apps/details?id=com.alhussain.smartlist)**
**Role:** solo founder and engineer: product, mobile, backend, cloud and release
**Showcase:** [smartlist-showcase](https://github.com/alhussaintalukder/smartlist-showcase)

---

## Why I built it
I shared groceries and expenses with 14 housemates, and spreadsheets caused confusion and disputes. In South Asia, many families also settle shop bills monthly instead of paying per purchase. SmartList solves both problems.

## Product
- **Tree organisation:** Groups → Lists → Sub-lists → Items
- **Real-time collaboration** over WebSocket, with group admins, members, shops and customers
- **Price analytics:** trends, budget forecasting, and location-based price comparison
- **Receipt OCR and reverse geocoding built in-house, with no third-party APIs**
- **Offline-first** with automatic sync · voice entry · English + বাংলা

## Architecture
```mermaid
flowchart LR
    APP[React Native · Expo<br/>TypeScript · RTK Query] -- REST + WebSocket --> NG[Nginx · SSL]
    NG --> API[Spring Boot · Java 21<br/>JPA · WebSocket · JWT]
    API --> DB[(MySQL)]
    API --> R[(Redis cache)]
    AUTH[Firebase Auth] -.-> APP
    subgraph Oracle Cloud · Docker
      NG
      API
      DB
      R
    end
```

## Engineering
- 276 commits, built solo, as a mobile + backend monorepo
- Release pipeline: EAS Build → Google Play
- Started as my BUET PGD final project (6 credits) and grew into a full product

**Stack:** React Native · Expo · TypeScript · Redux Toolkit · Java 21 · Spring Boot · MySQL · Redis · Docker · Nginx · Oracle Cloud · Firebase Auth
