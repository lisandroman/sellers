# FC Sellers - User Guide & Platform Documentation

**Version:** 1.0
**Last Updated:** November 2025

---

## Table of Contents

1. [Introduction](#introduction)
2. [Platform Overview](#platform-overview)
3. [User Roles](#user-roles)
4. [Getting Started](#getting-started)
5. [Feature Guide](#feature-guide)
   - [For Sellers](#for-sellers)
   - [For Administrators](#for-administrators)
6. [Account Management](#account-management)
7. [Payout System](#payout-system)
8. [FAQ](#faq)
9. [Support](#support)

---

## Introduction

Welcome to **FC Sellers**, a platform designed for managing FC26 coin sales. This platform enables sellers to manage their FC26 accounts, track coin transfers, and receive payments efficiently.

### Key Features

- **Real-time Account Management**: Monitor and manage your FC26 accounts in real-time
- **Automated Coin Tracking**: Track coin balances and transfers automatically
- **Flexible Payout Options**: Multiple payout methods with different processing times
- **Professional Dashboard**: Clean, intuitive interface for managing all operations
- **Admin Tools**: Comprehensive administrative features for platform management

---

## Platform Overview

The FC Sellers platform operates as a marketplace where:

1. **Sellers** provide FC26 accounts with coins that are sold through the FCS (FC26 Coin Service)
2. The platform tracks coin deliveries and calculates payments
3. **Administrators** manage global rates, process payouts, and oversee operations

---

## User Roles

### SELLER (Standard User)
- Manage personal FC26 accounts
- View coin inventory and sales
- Request payouts for completed orders
- Track payment history
- Update profile and payment information

### ADMIN (Only the platform creator can assign the ADMIN role)
- Full Dashboard access
- View all seller accounts
- Monitor platform statistics
- Configure global commission rates
- Process payout requests
- Configure payout options
- View payment request history
- Manage global settings and rates

---

## Getting Started

### 1. Registration & Login

**Accessing the Platform:**

1. Navigate to the login page
2. Enter your credentials (email and password)
3. Click "Sign In"

**First-Time Setup:**

- If you don't have an account, got o /auth/registration to create one
- Upon first login, you'll be redirected to your dashboard based on your role

### 2. Platform Navigation

The platform uses a **sidebar menu** with the following main sections:

#### For Sellers:
- **Accounts** (`/tables`) - Main account management page
- **Personal Info** (`/profile`) - Personal information and payout settings
- **Order History** (`/payments-history`) - Orders History

#### For Admins/SuperAdmins:
- **Dashboard** (`/dashboard`) - Rate management and statistics
- **Payouts Queue** (`/superadmin/payouts`) - Process payment requests
- **Payment History** (`/superadmin/history`) - View historical payments
- All seller features mentioned above

---

## Feature Guide

## For Sellers

### My Accounts Page (`/tables`)

This is your main workspace for managing FC26 accounts.

#### Key Metrics (Top Cards)

**1. Actual Rate x 100k**
- Shows current payment rate per 100,000 coins
- Separate rates for PC and Console platforms
- Updates automatically when administrators change rates

**2. Coins Stock**
- Total coins available in your accounts
- Breakdown by platform (PC vs Console)
- Number of active accounts per platform

**3. Pending Payout**
- Amount available to request for payout
- Only includes completed orders
- Includes an information tooltip explaining payout eligibility

#### Accounts Table

The main table displays all your FC26 accounts with the following columns:

| Column | Description |
|--------|-------------|
| **ID** | Unique account identifier |
| **Account** | Email address with platform icon (PC/Console) |
| **WebApp Coins** | Initial coin balance from FC26 Web App |
| **Status** | Current account status (see status legend below) |
| **Selling on FCS** | Coins currently listed for sale / Total ordered |
| **FCS Taken** | Coins already delivered to buyers |
| **Last Update** | Last status update timestamp |
| **Rate x 100k** | Applied rate (may show special rate in red) |
| **Amount** | Calculated payment amount in USD |
| **Note** | Payment notes or error messages |
| **Actions** | Available actions based on status |

#### Account Status Legend

| Status | Description | Visual |
|--------|-------------|--------|
| **READY** | Account is ready and available for orders | Green badge |
| **TRANSFERRING** | Actively transferring coins | Orange badge |
| **ORDER COMPLETED** | Transfer completed, ready for payout | Green badge |
| **PAID** | Payment processed | Light green badge |
| **LOGGING_IN** | System is logging into the account | Blue badge |
| **CANCELED_BY_SELLER** | Canceled before delivery started | Gray badge (muted) |
| **CONTACT_SUPPORT** | Manual intervention required | Yellow badge |
| **Error States** | Various login/technical errors | Red/yellow badges (muted) |

#### Actions You Can Take

**1. Add Account**
- Click "Add Account" button (top left)
- Fill in account details:
  - Email
  - Password
  - Platform (PC or Console)
  - Backup codes (if 2FA enabled)
- Submit to add account to the system

**2. Request Payout** (for completed accounts)
- Appears when status is "ORDER COMPLETED"
- Click "Request Payout" button
- Select payout option (Instant, Express, or Standard)
- Review commission and net amount
- Confirm request

**3. Cancel Order** (for READY accounts)
- Available only for accounts in READY status with no coins delivered
- Click "Cancel" button
- Confirm cancellation in popup
- Account status changes to "CANCELED_BY_SELLER"

**4. Search Accounts**
- Use the search box (top right)
- Search by Account ID or Email
- Results filter in real-time

#### Pagination
- Navigate through pages using controls at the bottom
- Shows 25 accounts per page
- Jump to first/last page or navigate by page numbers

---

### Profile Page (`/profile`)

Manage your personal information and payout preferences.

#### Contact Information Section

**Displays:**
- Your registered email address
- Twitter handle (if provided)

#### Payment Details Section

**Configure:**
- **Payment Method**: Choose between PayPal or USDT or USDC
- **Payment Details**:
  - For PayPal: Your PayPal email
  - For USDT: Your TRC20 wallet address
  - For USDC: Your Polygon(Matic) address

**Important:** You must configure payment information before requesting payouts.

**Edit Payment Information:**
1. Click the "Edit" button (pencil icon)
2. Update your payment method and details
3. Save changes

#### Payout Request Section

**Available Balance Display:**
- Shows total amount available to request
- Only includes completed orders not yet in a payment request

**Creating a Payout Request:**

1. **Check Your Balance**: Ensure you have available funds
2. **Select Payout Option**: Choose from available options:

   | Option | Commission | Processing Time | You Receive |
   |--------|-----------|-----------------|-------------|
   | **Instant** | Higher fee | ~6 hours | Amount - 7% (example) |
   | **Express** | Medium fee | 1 day | Amount - 5% (example) |
   | **Standard** | Lower fee | 3 days | Amount - 3% (example) |

   *Note: Actual commission rates are configured by administrators*

3. **Review Details**:
   - Total Amount: Your completed order value
   - Commission: Percentage deducted
   - Net Amount: What you'll receive

4. **Submit Request**: Click "Confirm Payout Request"

**Tracking Your Requests:**

Active requests display:
- Status badge (Pending/Paid/Error)
- Payout option selected
- Countdown timer until processing deadline
- List of included accounts
- Net amount to receive

**Payment Status:**
- **Pending**: Request is in the admin queue
- **Paid**: Payment completed (shows in table)
- **Payment Error**: Issue with payment details (requires action)

#### Handling Payment Errors

If a payment error occurs:

1. **Review Error Message**: Check the error reason in the alert
2. **Update Payment Information**: Click "Update Payment Info"
3. **Correct the Issue**: Fix the problem mentioned in the error
4. **Request Again**: Submit a new payout request

Common error reasons:
- Invalid wallet address
- Wrong PayPal email
- Network mismatch (wrong blockchain)
- Account issues

---

### FAQs Page (`/faqs`) ==> The FAQs need to be updated.

Access frequently asked questions and platform documentation.

**Typical Topics Covered:**
- How payouts work
- Account requirements
- Processing times
- Commission structure
- Technical issues
- Security guidelines

---

## For Administrators

### Dashboard Page (`/dashboard`)

*Available to: ADMIN and SUPERADMIN roles*

The Dashboard is the control center for platform-wide settings.

#### Current Rates Display

**Two Rate Cards:**
- **Console Rate** (PlayStation/Xbox)
- **PC Rate**

Each displays:
- Current rate per 100k coins
- Platform icons
- Real-time updates

#### Edit Global Rates (SUPERADMIN Only)

**Changing Rates:**

1. Locate the "Edit Global Rates" section
2. Select the platform to update (Console or PC)
3. Enter new rate in the input field
   - Format: Decimal number (e.g., 5.75)
   - Represents USD per 100,000 coins
4. Click "Save Console Rate" or "Save PC Rate"
5. Confirm the change

**Impact:**
- New accounts use the updated rate
- Existing matched accounts keep their original rate
- Change is logged in Rate Change History

#### Payout Options Management (SUPERADMIN Only)

**Viewing Options:**
- Table displays all configured payout options
- Shows: Key, Display Name, Description, Commission %, Days to Process, Status

**Adding a New Option:**

1. Click "Add New Option"
2. Fill in the form:
   - **Key**: Unique identifier (e.g., INSTANT, EXPRESS)
   - **Display Name**: User-friendly name
   - **Description**: What sellers see (e.g., "Payment within ~6 hours")
   - **Commission Rate**: Percentage (e.g., 7.00)
   - **Days to Process**: Number of days (0 = same day)
   - **Sort Order**: Display position
3. Click "Create"

**Editing an Option:**

1. Click the pencil icon next to an option
2. Modify desired fields
3. Click "Update"

**Activating/Deactivating:**
- Click the toggle icon to enable/disable an option
- Disabled options don't appear to sellers

**Deleting an Option:**
- Click the trash icon
- Confirm deletion
- Cannot delete if option is in use by pending requests

#### Rate Change History

**Table Columns:**
- **Date**: When the change occurred
- **Scope**: Type of change (e.g., GLOBAL)
- **Platform**: PC or Console
- **Currency**: Always USD
- **Old Rate**: Previous rate value
- **New Rate**: Updated rate value
- **Note**: Optional explanation

**Purpose:**
- Audit trail of all rate modifications
- Track who made changes and when
- Historical reference for rate trends

---

### Payouts Queue (`/superadmin/payouts`)

*Available to: ADMIN and SUPERADMIN roles*

Process seller payment requests efficiently.

#### Queue Statistics

**Three Metric Cards:**
1. **Sellers with Pending**: Count of sellers awaiting payment
2. **Total Pending Amount**: Sum of all pending payments
3. **Total Requests**: Number of payment requests in queue

#### Payment Queue Table

**Columns:**

| Column | Description |
|--------|-------------|
| **Seller** | Email and seller ID |
| **Payment Method** | PayPal or USDT (copyable) |
| **Payment Details** | Address/email (copyable) |
| **Requests** | Number of pending requests + account count |
| **Total Amount** | Sum before commission |
| **Net Amount** | Amount to pay seller |
| **Most Urgent** | Countdown to processing deadline |
| **Note/Status** | Any error messages or notes |
| **Actions** | Details and Mark Paid buttons |

#### Processing a Payment

**Method 1: Quick Pay from Table**

1. Click "Mark Paid" button in the row
2. Optionally add a payment note (TX ID, reference)
3. Click "Confirm Payment"
4. Request is marked as PAID

**Method 2: Detailed View**

1. Click "Details" button
2. Review complete seller information:
   - All pending requests
   - Account details for each request
   - Breakdown of amounts
3. Expand individual requests to see:
   - List of accounts included
   - Commission calculation
   - Degradation history (if applicable)
4. Click "Mark as Paid" for specific request
5. Add optional payment note
6. Confirm

#### Payment Errors

If there's an issue with payment details:

1. Click "Details" on the seller
2. Expand the problematic request
3. Click "Payment Error" button
4. **Enter Error Reason** (required):
   - Be specific (e.g., "Invalid USDT address - wrong network")
   - Seller will see this message
5. Click "Confirm Error"

**Result:**
- Request status → PAYMENT_ERROR
- Seller is notified
- Seller can update info and request again

#### Countdown System

**Color Coding:**
- **Red**: Less than 2 hours remaining or overdue
- **Yellow**: Less than 6 hours remaining
- **Blue**: More than 6 hours remaining

**Overdue Requests:**
- Show "⏰" icon
- Display "(overdue)" text
- Automatically degrade to next commission tier (if configured)

#### Fee Degradation (Automatic)

When a payout request isn't processed by the deadline:

1. System automatically downgrades to next-lower commission tier
2. Seller keeps more money (lower commission)
3. Request remains in queue
4. Degradation history is logged

**Example:**
- Original: INSTANT (7% commission)
- After 6 hours: Downgrades to EXPRESS (5% commission)
- After 24 hours: Downgrades to STANDARD (3% commission)

**Viewing Degradation:**
- Look for "Fee Reduced" badge
- Check degradation history in request details
- Shows original vs current commission

#### Search Functionality

- Search by seller email or ID
- Real-time filtering
- Works across all pending requests

---

### Payment History (`/superadmin/history`)

*Available to: ADMIN and SUPERADMIN roles*

Review all completed and processed payment requests.

**Typical Information:**
- Historical payment requests
- Completed payouts
- Payment dates
- Transaction references
- Seller information

---

## Account Management

### Account Statuses Explained

Understanding what each status means helps you know what to expect:

#### Active Statuses (Account is working)

**READY**
- Account logged in successfully
- Coins verified
- Waiting for buyer order
- Can be listed on FCS

**TRANSFERRING**
- Actively sending coins to buyer
- Transfer bot is working
- Progress tracked automatically

**LOGGING_IN**
- System is accessing the account
- Verifying credentials
- Checking 2FA if enabled

#### Completion Statuses

**ORDER COMPLETED**
- All coins delivered successfully
- Payment calculation complete
- Ready for payout request
- Account can be reused for new orders. The seller must upload it again with the new order.

**PAID**
- Payment processed to you
- Transaction complete
- Historical record

#### Actionable Statuses (May require your attention)

**CONTACT_SUPPORT**
- Manual review needed
- May indicate unusual situation
- Check with support team

**CANCELED_BY_SELLER**
- You canceled the order
- No coins were delivered
- Account can be relisted

#### Error Statuses (Automated handling, account is inactive)

These typically require the account to be fixed or replaced:

**Login Errors:**
- ERROR_LOGIN_USER_PASS: Wrong email or password
- BC_CODE_ERROR: Backup code issue
- CAPTCHA_ERROR: CAPTCHA challenge failed
- ENABLE_2_FACTOR: 2FA not properly configured

**Market Errors:**
- BANNED_MARKET: Account restricted from transfer market
- NO_MARKET_ACCESS: Cannot access market features

**Technical Errors:**
- ERROR_NO_COINS: Coin balance mismatch
- SOFT_BAN: Temporary EA restriction
- TRANSFER_LIST_FULL: Cannot add more items
- WATCHED_LIST_FULL: Watch list at capacity
- UNASSIGNED_PLAYERS_ERROR: Issue with unassigned items

### Account Lifecycle

```
1. ADD ACCOUNT
   ↓
2. LOGGING_IN (verification)
   ↓
3. READY (available for sale)
   ↓
4. TRANSFERRING (sending coins)
   ↓
5. ORDER COMPLETED (delivery done)
   ↓
6. Request Payout
   ↓
7. PAID (payment received)
```

## Payout System

### How Payouts Work

**Step-by-Step Process:**

1. **Complete Orders**
   - Sell coins through your accounts
   - Wait for status to become "ORDER COMPLETED"
   - System calculates your earnings

2. **Check Eligibility**
   - Go to Profile page
   - View "Available to Request" amount
   - Must have payment method configured

3. **Create Request**
   - Choose payout option (Instant/Express/Standard)
   - Review commission and net amount
   - Submit request

4. **Admin Processing**
   - Request enters admin queue
   - Processed within chosen timeframe
   - Payment sent to your configured method

5. **Receive Payment**
   - Status updates to "PAID"
   - Notification sent (if enabled)
   - Check your payment account

### Payout Options Comparison

| Feature | Instant | Express | Standard |
|---------|---------|---------|----------|
| **Processing Time** | ~6 hours | 1 business day | 3 business days |
| **Commission** | Highest (e.g., 7%) | Medium (e.g., 5%) | Lowest (e.g., 3%) |
| **Best For** | Urgent needs | Balanced option | Maximum earnings |
| **Countdown** | 6 hours | 24 hours | 72 hours |
| **Auto-Downgrade** | To Express if late | To Standard if late | No further downgrade |

*Note: Exact commission rates are set by administrators*

### Payment Methods

**PayPal:**
- Enter your PayPal email address
- Must match your PayPal account name
- Payments typically arrive instantly
- May have PayPal fees

**USDT (TRC20):**
- Provide your TRC20 wallet address
- **Must be TRC20 network** (not ERC20 or other networks)
- Typical confirmation time: 5-10 minutes
- Verify address carefully (transactions are irreversible)

**USDC Polygon (Matic):**
- Provide your USDC Polygon wallet address
- **Must be in the correct network** (not other networks)
- Typical confirmation time: 5-10 minutes
- Verify address carefully (transactions are irreversible)

### Payout Timeline

**Countdown Timer:**
- Each request has a deadline
- Timer shows: Days, Hours, Minutes, Seconds
- Visible in Profile and Admin Queue

**What Happens at Deadline:**
- Admin has until deadline to process
- If deadline passes:
  - Request automatically downgrades to next tier
  - You pay less commission
  - New deadline is set

**Example Timeline:**
```
Request Created: Monday 10:00 AM (INSTANT, 7% fee)
Deadline: Monday 4:00 PM (6 hours)

If not processed by 4:00 PM:
→ Downgrades to EXPRESS (5% fee)
New deadline: Tuesday 10:00 AM (24 hours)

If not processed by Tuesday 10:00 AM:
→ Downgrades to STANDARD (3% fee)
New deadline: Thursday 10:00 AM (72 hours)
```

### Common Payout Issues

**Issue: "Payment Method Required" Warning**
- **Solution**: Go to Profile → Click Edit → Add payment details

**Issue: Payment Error Status**
- **Cause**: Invalid payment information
- **Solution**:
  1. Read error message carefully
  2. Update payment information
  3. Request payout again

**Issue: Can't Request Payout**
- **Check**: Do you have completed orders?
- **Check**: Is payment method configured?
- **Check**: Is there already a pending request?

**Issue: Request Taking Long**
- **Normal**: Admins process within chosen timeframe
- **Check**: Look at countdown timer
- **Benefit**: If late, commission automatically reduces

---

## FAQ

### General Questions

**Q: How long does it take to get paid?**
A: Depends on your chosen option:
- Instant: ~6 hours
- Express: 1 business day
- Standard: 3 business days

If the deadline passes, your commission is automatically reduced, but payment may take longer.

**Q: Can I cancel a payout request?**
A: No, once submitted, requests cannot be canceled. They must be processed or marked as payment error by an administrator.

**Q: What happens to my accounts after ORDER COMPLETED?**
A: They can be reused for new orders. The payment is calculated and added to your available balance.

**Q: Can I add more accounts while I have pending payouts?**
A: Yes, you can continue adding accounts and making sales independently of your payout requests.

**Q: Do I need different accounts for PC and Console?**
A: Yes, FC26 accounts are platform-specific. You must have separate accounts for each platform.

### Payment Questions

**Q: Which payment method is better?**
A:
- **PayPal**: Faster, easier, but may have fees
- **USDT**: No intermediary fees, cryptocurrency-based, requires wallet

**Q: What if I enter wrong payment details?**
A: Admins will mark your request as "Payment Error" with a reason. Update your info and request again.

**Q: Do I lose money if my request downgrades?**
A: No! You actually save money. Downgrades reduce the commission, so you receive more.

**Q: Can I have multiple pending requests?**
A: Yes, you can create additional requests if you have more completed accounts. Each request is processed independently.

**Q: How is the amount calculated?**
A: `Amount = (Delivered Coins / 100,000) × Rate × (1 - Commission%)`

Example:
- 500,000 coins delivered
- Rate: $5.00 per 100k
- Commission: 7% (INSTANT)
- Calculation: (500,000 / 100,000) × $5.00 × 0.93 = $23.25

### Account Questions

**Q: Why is my account showing an error status?**
A: Common reasons include:
- Wrong email or password
- 2FA issues (backup codes needed)
- EA restrictions (soft ban, market ban)
- Technical FC26 issues

**Q: Can I edit an account after adding it?**
A: Contact administrators if you need to update account credentials.

**Q: What if EA bans my account?**
A: Accounts with market bans or soft bans will show error status and won't be used until resolved.

**Q: How many accounts can I add?**
A: There's no hard limit, but manage responsibly. Quality accounts are better than quantity.

### Technical Questions

**Q: Why is the site not updating?**
A: The platform uses real-time updates via WebSockets. Try:
1. Refreshing the page
2. Checking your internet connection
3. Clearing browser cache

**Q: I see old data in my tables**
A: Click the refresh icon or reload the page. Data caches for performance but auto-updates every few seconds.

**Q: Can I use the platform on mobile?**
A: Yes, the interface is responsive and works on tablets and smartphones.

**Q: Is my data secure?**
A: Yes, all connections are encrypted (HTTPS), and passwords are securely stored.

---

## Support


### Best Practices

**Account Security:**
- Use strong, unique passwords
- Enable 2FA on FC26 accounts when possible
- Don't share account credentials outside the platform

**Payment Information:**
- Double-check payment details before saving
- Test with a small payout first
- For USDT/USDC: Verify network type 

**Regular Monitoring:**
- Check your accounts daily
- Review transaction history regularly
- Monitor pending payouts

**Communication:**
- Respond promptly to administrator requests
- Keep contact information updated
- Report issues immediately

---

## Appendix

### Platform URLs Quick Reference

| Page | URL | Access Level |
|------|-----|--------------|
| Login | `/auth/login` | Public |
| My Accounts | `/tables` | Seller+ |
| Profile | `/profile` | Seller+ |
| Add Funds | `/add-funds` | Seller+ |
| FAQs | `/faqs` | Seller+ |
| Dashboard | `/dashboard` | Admin+ |
| Payouts Queue | `/superadmin/payouts` | Admin+ |
| Payment History | `/superadmin/history` | Admin+ |
| Terms | `/terms` | All |
| Logout | `/logout` | All |


### Glossary

- **Account**: A FC26 Ultimate Team account used for coin transfers
- **Coins**: In-game currency in FC26 Ultimate Team
- **Delivered Coins**: Amount of coins successfully transferred to buyers
- **FCS**: FC26 Coin Service - the marketplace platform
- **Rate**: Payment per 100,000 coins (USD/100k)
- **Special Rate**: Custom rate applied to specific accounts
- **Commission**: Platform fee deducted from payout
- **Net Amount**: Final payment after commission
- **Countdown**: Time remaining to process payout request
- **Degradation**: Automatic commission reduction if deadline passed
---

**Document End**

---

**Version History:**
- **v1.0** (November 2025) - Initial user guide creation

