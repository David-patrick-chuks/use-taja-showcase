# Taja User Flows and Bot Messages

This document captures the live WhatsApp and web user journeys for Taja.

It is written for product, design, engineering, QA, support, and operations teams.

## How to Read This Doc

- `User message` means the exact kind of message a user can send to Taja.
- `Bot response` means the canonical message Taja sends back in the current implementation.
- Some bot responses are dynamic and change based on user data, products, orders, or configuration.
- Where a flow uses buttons, lists, or WhatsApp Flows, the user still receives the same underlying intent, but the UI may be interactive instead of plain text.

## 1. New User Flow

This is the first journey for someone who has not fully joined yet.

### 1.1 First Contact

| Step | User Message | Bot Response | Next State |
|---|---|---|---|
| Welcome detection | `Hi` or any first message | `🎉 Welcome to Taja!` with the onboarding options | `onboarding` |
| Menu choice | `1` or `customer` | Customer onboarding path | `awaiting_account_creation` |
| Menu choice | `2` or `seller` | Seller onboarding path | `awaiting_account_creation` |
| Menu choice | `3` or `faqs` | FAQ response | `onboarding` |
| Menu choice | `4` or `support` | Support flow | `support_mode` |

### 1.2 Exact Onboarding Menu Copy

The bot shows this message when a first-time user enters onboarding:

```text
🎉 Welcome to Taja!

I'm your AI-powered shopping assistant, here to make your e-commerce experience seamless and enjoyable.

What would you like to do today?

1️⃣ Customer – Browse and shop for amazing products
2️⃣ Seller – Start selling your products online
3️⃣ FAQs – Learn more about our platform
4️⃣ Contact Support – Get help from our friendly team

💡 Tip: Simply reply with 1 or customer to get started!
```

### 1.3 FAQ Copy

When the user sends `3`, `faq`, `faqs`, or similar, the bot sends the FAQ text:

```text
❓ Frequently Asked Questions (FAQs)

About Taja:
Taja helps small businesses like yours sell online easily — right inside WhatsApp! We provide digital storefronts, automated orders, and easy payment options to streamline your sales.

1. How do I create an account?
- Just type create account or signup and follow the link!

2. Is Taja free to use?
- Yes! Taja is completely free for both sellers and customers. There are no hidden fees or charges for using our platform.

3. How do I contact support?
- Reply with 4 or Contact Support at any time.

Type "back" to return to the main menu.
```

### 1.4 Support Intro Copy

When the user sends `4`, `support`, or similar, the bot can send:

```text
🛟 Contact Support

I'm here to help! Please ask your question and I'll do my best to assist you.

For urgent issues, I'll automatically escalate to our human support team.

Type "back" to return to the main menu.
```

If official WhatsApp Flows are enabled, support opens inside WhatsApp. If not, the bot stays text-based.

## 2. Customer Flow

This is the flow for a user who shops on Taja.

### 2.1 Customer Menu Copy

```text
🛍️ Customer Menu

What would you like to do?

1️⃣ Browse Trending Products - See what's hot right now
2️⃣ Search Products - Find specific items
3️⃣ View Cart - Check your cart
4️⃣ My Orders - Track your orders
5️⃣ Track Package - Track by tracking number
6️⃣ Returns & Refunds - Request a return or refund
7️⃣ Help - Get support

Type the number or describe what you need!

💡 Tip: Type "menu" at any time to return here.
```

### 2.2 Sample Customer Messages and Bot Replies

| User Message | Bot Reply | Notes |
|---|---|---|
| `1` | Trending products list | Sets `browsing_trending_products` |
| `browse trending products` | Trending products list | Same as above |
| `2` | Product search prompt | Sets `searching_products` |
| `search laptops` | Search results | Text, image, video, or voice-note search may be used |
| `3` | Cart flow | Shows cart actions | Sets `cart_management` |
| `4` | Order history | Shows recent orders | Returns order history text |
| `5` | Track package prompt | Requests tracking number | Sets `tracking_package` |
| `6` | Return request flow | Starts return request | Sets `return_request` |
| `7` | Help | Support answers or AI support | Sets `customer_support` |
| `menu` | Customer menu again | Returns to menu |
| `back` | Customer menu again | Returns to menu |

### 2.3 Search Prompt Copy

When the user chooses product search, the bot sends:

```text
🔍 Product Search

What are you looking for? Please describe the product you want to find.

You can search in multiple ways:
• Text Search: Type your search query
• Image Search: Send a photo of the product
• Video Search: Send a video of the product
• Image + Text: Send a photo with a caption

Type your search, send an image/video, or "back" to return to menu.
```

### 2.4 Track Package Copy

```text
📦 Track Package

Please enter your tracking number:

Type your tracking number or "back" to return to menu.
```

### 2.5 Customer Support Examples

The support bot gives helpful answers for common requests.

Example user messages:
- `how do i order`
- `how do i track my order`
- `what categories do you sell`
- `how do i pay`
- `delivery fee to ikeja`
- `return item`
- `talk to human`
- `create account`

Example bot replies:
- `🛒 How to order on Taja`
- `📦 Track your order`
- `🗂️ Product Categories`
- `💳 Payments`
- `🚚 Delivery & Shipping`
- `🔁 Returns & Refunds`
- `🙋 Talk to a Human`
- `👤 Account & Access`

### 2.6 Returns and Refunds

When the user chooses returns, the bot starts the guided return flow. The live flow uses order verification and return reasons before escalating to the return service.

Common user messages:
- `returns`
- `returns & refunds`
- `request return`
- `return item`
- `refund request`

## 3. Seller Flow

This is the flow for a user who sells products on Taja.

### 3.1 Seller Menu Copy

```text
🏪 Seller Menu

What would you like to do?

1️⃣ Add Product - Upload new items
2️⃣ My Products - Manage inventory
3️⃣ View Orders - Handle customer orders
4️⃣ Sales Report - Check your performance
5️⃣ Help - Get support

Type the number or describe what you need!
```

### 3.2 Sample Seller Messages and Bot Replies

| User Message | Bot Reply | Notes |
|---|---|---|
| `1` | Add product instructions | Sets `adding_product` |
| `add product` | Add product instructions | Requests 4 photos first |
| `2` | Product management screen | Lists seller products |
| `my products` | Product management screen | Same as above |
| `3` | Seller order view | Shows customer orders |
| `view orders` | Seller order view | Same as above |
| `4` | Sales report | Shows sales summary | Sales analytics flow |
| `5` | Seller support | Help / support flow | Sets `seller_support` |
| `menu` | Seller menu again | Returns to menu |
| `back` | Seller menu again | Returns to menu |

### 3.3 Add Product Copy

When the seller chooses add product, the bot sends:

```text
📦 Add New Product

Please send at least 4 photos of your product to continue.

💡 Tip: You can delete images and send new ones if needed.

After that, I'll ask for:
• Product name
• Price
• Description
• Category

Optional fields (you can skip any):
• Stock quantity
• Weight (in kg)
• Colors (e.g., "Red, Blue, Black")
• Sizes (e.g., "S, M, L" or "10, 11, 12")
• Key features (e.g., "Waterproof, Lightweight, Durable")

Just type "skip" for any optional field you don't need!
```

### 3.4 Seller Support Copy

When the seller asks for help, the bot sends:

```text
🆘 Seller Support

I'm here to help! Please ask your question and I'll do my best to assist you.

For urgent issues, I'll automatically escalate to our human support team.

Type "back" to return to the main menu.
```

### 3.5 Payout and Settlement Copy

If the seller asks about payout details or bank setup, the bot may send:

```text
🏦 Update Payout Account

Use the link below to add or update your settlement (bank) details:
<link>

After saving, you can request withdrawals from your available balance. Type "back" to return to the seller menu.
```

If the official WhatsApp payout flow is enabled, the seller is guided inside WhatsApp instead of leaving the app.

## 4. Checkout Flow

The checkout flow starts when the customer is ready to pay.

### 4.1 Checkout States

| Step | User Action | Bot Response | Next State |
|---|---|---|---|
| Shipping address | Enter delivery details | Saves address or opens WhatsApp Flow | `awaiting_shipping_address` or `flow_in_progress` |
| Shipping rates | Wait for courier options | Shows shipping choices | `awaiting_shipping_selection` |
| Order confirmation | Confirm cart | Creates order | `awaiting_confirmation` |
| Payment start | Open checkout link | Paystack checkout link is sent | `pending payment` |
| Payment success | Paystack confirms | Receipt and success update | `paid` |

### 4.2 Checkout Copy

When the bot asks for shipping details:

```text
📦 Address: Name, Phone, Address, City, State, Postal Code
```

When the user confirms an order:

```text
✅ Confirm your order?

Tap Confirm to place the order.
```

When payment is ready:

```text
💳 Complete your payment

Pay securely here: <paystack link>
```

### 4.3 Payment Success Copy

When a payment is verified:

```text
✅ Payment Verified!

Order ID: <order id>
Amount: ₦<amount>
Your payment has been confirmed successfully!
```

### 4.4 Payment Error Copy

If payment fails or cannot be verified:

```text
Payment issue

We could not complete the payment process.
```

## 5. Withdrawal Flow

This is the seller payout flow after funds become available.

### 5.1 Seller Withdrawal Page

The seller can use the web page for withdrawals and view history.

Supported actions:
- request withdrawal
- review status
- see fees
- see net amount
- see approval or failure reason

### 5.2 Withdrawal Request Copy

When a seller requests withdrawal:

```text
Withdrawal Request Received

Your withdrawal request of ₦<amount> (net: ₦<netAmount>) has been received and is pending review.
```

### 5.3 Withdrawal Approval Copy

When admin approves and pays a withdrawal:

```text
Withdrawal Approved and Paid

Your withdrawal of ₦<amount> has been approved and paid. Transfer reference: <reference>.
```

### 5.4 Withdrawal Rejection Copy

When admin rejects a withdrawal:

```text
Withdrawal Rejected

Your withdrawal request of ₦<amount> was rejected. Reason: <reason>
```

## 6. Return Flow

This is the return and refund journey for customers.

### 6.1 User Messages

Common user messages that trigger return handling:
- `returns`
- `returns & refunds`
- `request return`
- `return item`
- `refund request`
- `start return`

### 6.2 Return Support Copy

```text
🔁 Returns & Refunds

• Eligible items can be returned through the WhatsApp return flow or the Returns page.
• Approved returns can pause payout until the case is resolved.
• Refunds are processed after review and inspection where applicable.

Type "returns" to start a return request, or describe your case here.
```

### 6.3 Return Status Messages

- `requested`
- `approved`
- `rejected`
- `in_transit`
- `completed`
- `lost`

## 7. Exact Bot Messages by User Type

### 7.1 Customer

Customer users commonly see:
- onboarding menu
- customer menu
- product search prompt
- trending products
- cart prompts
- order history
- tracking prompt
- returns and refunds flow
- support answers

### 7.2 Seller

Seller users commonly see:
- onboarding menu
- seller menu
- add product instructions
- product management
- order management
- sales report
- payout or withdrawal prompts
- seller support

### 7.3 Support or Unknown User

Unknown or first-time users usually see:
- welcome banner
- onboarding menu
- FAQs
- support prompt
- signup flow prompt

## 8. Short Sample Conversation

### Customer Example

```text
User: hi
Bot: 🎉 Welcome to Taja!
     [onboarding menu]

User: 1
Bot: Customer signup flow / customer onboarding

User: menu
Bot: 🛍️ Customer Menu
     [customer menu]

User: search shoes
Bot: 🔍 Product Search
     What are you looking for? Please describe the product you want to find.
```

### Seller Example

```text
User: hello
Bot: 🎉 Welcome to Taja!
     [onboarding menu]

User: seller
Bot: Seller signup flow / seller onboarding

User: add product
Bot: 📦 Add New Product
     Please send at least 4 photos of your product to continue.

User: payout
Bot: payout flow or payout update link
```

## 9. Notes for Product and QA

- The exact text above is the current live copy in the codebase where the message is static.
- Search results, order history, receipts, payout amounts, and product details are dynamic and change per user.
- Official WhatsApp Flows replace some plain-text prompts when configured in Meta.
- If a flow is not configured, the bot falls back to text or a web link.

## 10. Recommended Testing Checklist

- First-time user sees onboarding menu.
- Customer signup path opens correctly.
- Seller signup path opens correctly.
- Customer menu sends the correct list.
- Seller menu sends the correct list.
- Product search accepts text and media.
- Checkout creates an order and sends a payment link.
- Payment success updates the receipt and order status.
- Seller withdrawal request reaches admin review.
- Admin approval actually triggers payout transfer.
- Return flow updates refund and payout states correctly.

## 11. Exact Message Library

This section lists the exact live bot text snippets that appear in the codebase today.

### 11.1 Customer Search and Discovery

```text
🔍 Product Search

What are you looking for? Please describe the product you want to find.

You can search in multiple ways:
• Text Search: Type your search query
• Image Search: Send a photo of the product
• Video Search: Send a video of the product
• Image + Text: Send a photo with a caption

Type your search, send an image/video, or "back" to return to menu.
```

```text
🔥 Trending Products:
```

```text
📋 All Search Results
```

```text
🛒 Add to Cart
```

```text
📝 How many would you like?
```

```text
✅ Added to Cart
```

```text
✅ Quantity Updated
```

```text
🔙 Back to Products
```

### 11.2 Customer Cart

```text
Cart Actions
```

```text
Checkout
```

```text
Update Quantities
```

```text
Add More Products
```

```text
Clear Cart
```

```text
Back
```

### 11.3 Customer Orders and Tracking

```text
📋 No Orders Yet
```

```text
📋 Your Order History
```

```text
📦 Package Tracking
```

```text
  Tracking Not Found
```

```text
  Tracking Error
```

### 11.4 Customer Returns

```text
🔁 Return Request
```

```text
📝 Return reason
```

```text
✅ Return request submitted
```

```text
  Return request failed
```

### 11.5 Customer Help

```text
🛟 Contact Support
```

```text
🛒 How to order on Taja
```

```text
📦 Track your order
```

```text
🗂️ Product Categories
```

```text
💳 Payments
```

```text
🚚 Delivery & Shipping
```

```text
🔁 Returns & Refunds
```

```text
🏷️ Discounts & Promotions
```

```text
🕒 Store & Support Hours
```

```text
✅ Product Authenticity & Seller Verification
```

```text
👤 Account & Access
```

```text
🔐 Privacy & Security
```

```text
🗑️ Data Deletion
```

```text
🙋 Talk to a Human
```

```text
🌍 International Shipping
```

```text
🏬 Pickup Options
```

```text
📏 Size Guide
```

```text
🛑 Order Cancellation
```

```text
🏠 Change Delivery Address
```

```text
🔔 Out‑of‑Stock Alerts
```

```text
💰 Delivery Fee Estimate
```

### 11.6 Seller Flow

```text
🏪 Seller Menu
```

```text
📦 Add New Product
```

```text
🆘 Seller Support
```

```text
🏦 Update Payout Account
```

```text
📋 Your Orders
```

```text
📊 Sales Report
```

```text
✅ Quantity Updated
```

```text
  Invalid Option
```

### 11.7 Seller Orders and Sales

```text
📋 Your Orders
```

```text
📊 Sales Report
```

```text
Detailed
```

```text
Export
```

```text
Back
```

### 11.8 Checkout and Payment

```text
📦 Address: Name, Phone, Address, City, State, Postal Code
```

```text
✅ Confirm your order?
```

```text
💳 Complete your payment
```

```text
✅ Payment Verified!
```

```text
  Payment verification failed
```

```text
Payment issue
```

### 11.9 Withdrawals

```text
Withdrawal Request Received
```

```text
Withdrawal Approved and Paid
```

```text
Withdrawal Rejected
```

### 11.10 Onboarding

```text
🎉 Welcome to Taja!
```

```text
❓ Frequently Asked Questions (FAQs)
```

```text
🔗 Create Your Account
```

```text
  Signup form unavailable
```

```text
  Support form unavailable
```

```text
  Error
```

### 11.11 Notes on Exactness

- Static text above is copied from the live codebase or normalized to match the displayed copy.
- Dynamic values like order ID, amount, product name, and links are inserted at runtime.
- Some WhatsApp Flow launches send no text because the user sees a Meta form instead.

