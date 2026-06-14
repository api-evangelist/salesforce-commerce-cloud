# Salesforce Commerce Cloud GraphQL Schema

## Overview

This is a conceptual GraphQL schema for Salesforce Commerce Cloud (SFCC), derived from the
Salesforce Commerce API (SCAPI) and Open Commerce API (OCAPI) REST interfaces. SFCC does not
currently expose a native GraphQL endpoint, but this schema represents the full surface of the
B2C Commerce domain in GraphQL terms to enable tooling, federation mapping, and AI-assisted
development against SCAPI.

- **Provider**: Salesforce Commerce Cloud (formerly Demandware)
- **GitHub**: https://github.com/SalesforceCommerceCloud
- **API Reference**: https://developer.salesforce.com/docs/commerce/commerce-api/references
- **API Explorer**: https://api-explorer.commercecloud.salesforce.com
- **Schema file**: `salesforce-commerce-cloud-schema.graphql`

---

## Domain Coverage

### Catalog and Product

Types covering the full B2C product hierarchy: `Catalog`, `Category`, `Product`, `ProductVariant`,
`ProductType`, `ProductImage`, `VariationAttribute`, `VariationAttributeValue`, `BundledProduct`,
`ProductRecommendation`, and `ProductConnection`.

Products map to SCAPI Shopper Products and Data Catalogs APIs. Variation attributes, bundled
products, and set products are supported. Prices are embedded via the `Price` and `PriceBook` types.

### Pricing

`PriceBook`, `Price`, `PriceType`, `Schedule` — price books can be hierarchical via
`parentPriceBook`, scheduled with start/end dates, and scoped to a currency. Prices are
multi-tiered and carry both list and sale values.

### Promotions and Campaigns

`Campaign`, `Promotion`, `PromotionData`, `PromotionClass`, `DiscountType`, `Coupon`, `Schedule` —
the full promotion pipeline from campaign scheduling to coupon redemption and discount application.
Campaigns link to customer groups and can carry multiple promotion types: product, shipping, and
order-level.

### Cart (Basket)

`Cart`, `CartItem`, `CartTax`, `CartCoupon`, `PriceAdjustment`, `ShippingItem`, `GiftCardItem`,
`GiftCard`, `Note`, `OptionItem`, `Shipment` — maps directly to SCAPI Shopper Baskets. Supports
multi-shipment baskets, price adjustments from promotions, coupon items, gift certificates, and
custom attributes.

### Checkout and Orders

`Checkout`, `CheckoutStatus`, `Order`, `OrderStatus`, `OrderItem`, `OrderPayment`,
`OrderShipment`, `OrderShipmentStatus`, `ChannelType` — the full post-basket order lifecycle
through SCAPI Shopper Orders and Data Orders. Tracks fulfillment status, payment authorization
state, and channel attribution (storefront, call center, API, marketplace).

### Payment

`PaymentMethod`, `PaymentCard`, `PaymentCardType`, `PaymentInstrument`, `TaxCalculation`,
`TaxLineItem` — payment methods, tokenized card data (masked), and tax calculation line items
for integration with payment processors and tax engines.

### Customers

`Customer`, `CustomerAddress`, `Address`, `CustomerBasket`, `CustomerOrderConnection`,
`CustomerGroup`, `CustomerList`, `WishList`, `WishListItem`, `CustomerGender` — maps to SCAPI
Shopper Customers and Data Customers. Supports registered and guest customer flows, address books,
payment instruments, customer groups for segmentation, and wish lists.

### Inventory

`InventoryList`, `InventoryRecord`, `Inventory` — ATP (Available to Promise), backorderable,
preorderable, perpetual, and on-order inventory states per product per inventory list.

### Search

`ProductSearch`, `ProductSearchHit`, `ContentSearch`, `ContentSearchHit`, `StoreSearch`,
`SearchRefinement`, `SearchRefinementValue`, `SortOption`, `SearchSuggestions`,
`SuggestedPhrase`, `SuggestedTerms`, `SuggestedTerm`, `ProductSuggestions`,
`CategorySuggestions` — covers SCAPI Shopper Search including product search, content search,
store search, faceted refinements, sort options, and type-ahead suggestions.

### Stores

`Store` — physical store locations including geolocation, hours, inventory list linkage, POS
enablement, and store pickup support.

### Site and Configuration

`Site`, `SiteStatus`, `SiteConfig`, `SearchPreferences`, `CheckoutPreferences`,
`CartPreferences` — multi-site configuration, locale and currency lists, catalog and inventory
list assignments, and storefront preferences.

### Content

`ContentSlot`, `ContentAsset`, `Slot`, `SlotContent`, `SlotConfiguration`, `Page`, `PageType`,
`PageRegion`, `PageComponent` — SFCC content management including slots, content assets, and
Page Designer pages with component regions and data payloads.

### Forms

`Form`, `FormField`, `FormFieldType`, `FormFieldOption`, `FormFieldValidation`, `FormError` —
SFCC server-side form validation schema representation for checkout and account forms.

### Custom Objects

`CustomObject` — SFCC's custom object framework for extending the platform data model with
arbitrary key-value attributes.

### Einstein Recommendations

`EinsteinRecommendation`, `EinsteinContext`, `EinsteinContextInput` — product recommendations
via Salesforce Einstein for Commerce, supporting context signals like viewed products, category,
and search phrase.

### A/B Testing

`ABTest`, `ABTestGroup` — SFCC A/B testing configuration for storefront experience experiments.

### Session and Authentication

`Session`, `ShopperToken`, `OAuthToken` — SLAS (Shopper Login and API Access Service) tokens
for guest and registered shopper flows, and OAuth 2.0 tokens for B2B/Admin access via
Salesforce Account Manager.

---

## Schema Statistics

| Category | Types |
|---|---|
| Catalog & Product | 12 |
| Pricing | 4 |
| Promotions & Campaigns | 7 |
| Cart | 11 |
| Checkout & Orders | 9 |
| Payment & Tax | 6 |
| Customers | 10 |
| Inventory | 3 |
| Search | 12 |
| Stores | 1 |
| Site & Config | 5 |
| Content | 8 |
| Forms | 6 |
| Custom Objects | 1 |
| Einstein | 2 |
| A/B Testing | 2 |
| Session & Auth | 3 |
| Scalars & Enums | 18 |
| Input Types | 5 |
| Root (Query/Mutation) | 2 |
| **Total** | **127** |

---

## Mapping to SCAPI Endpoints

| GraphQL Type / Query | SCAPI Endpoint Family |
|---|---|
| `productSearch` | Shopper Search |
| `product`, `products` | Shopper Products |
| `category` | Shopper Products / Data Catalogs |
| `cart`, `createCart`, `addToCart` | Shopper Baskets |
| `createOrder` | Shopper Orders |
| `order`, `orders` | Data Orders |
| `customer`, `createCustomer` | Shopper Customers |
| `getShopperToken` | Shopper Login (SLAS) |
| `store`, `storeSearch` | Shopper Stores |
| `einsteinRecommendations` | Einstein |
| `contentAsset`, `contentSlot` | Shopper Experience |
| `page` | Page Designer (Shopper Experience) |
| `inventoryRecord` | Data Inventory |
| `priceBook`, `promotion` | Data Pricing / Data Promotions |

---

## References

- SCAPI Overview: https://developer.salesforce.com/docs/commerce/commerce-api/overview
- SCAPI Reference: https://developer.salesforce.com/docs/commerce/commerce-api/references
- OCAPI Reference: https://developer.salesforce.com/docs/commerce/b2c-commerce/references
- API Explorer: https://api-explorer.commercecloud.salesforce.com
- GitHub Organization: https://github.com/SalesforceCommerceCloud
- PWA Kit (headless reference): https://github.com/SalesforceCommerceCloud/pwa-kit
- Postman Collection: https://www.postman.com/salesforce-developers/salesforce-developers/documentation/1qkzgik/salesforce-commerce-b2c
