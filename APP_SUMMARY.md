# Recology King County - Service Proration Calculator
## Application Summary & Documentation

**Version:** 1.0
**Release Date:** October 2025
**Application Type:** Standalone HTML Web Application
**Platform:** Cross-browser, Offline-capable
**Department:** Billing & Customer Service

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Purpose & Business Value](#purpose--business-value)
3. [Key Features](#key-features)
4. [Technical Specifications](#technical-specifications)
5. [Billing Cycles & Calculations](#billing-cycles--calculations)
6. [User Interface Overview](#user-interface-overview)
7. [Data Management](#data-management)
8. [Security & Privacy](#security--privacy)
9. [System Requirements](#system-requirements)
10. [Deployment & Distribution](#deployment--distribution)
11. [Support & Maintenance](#support--maintenance)

---

## Executive Summary

The **Recology King County Service Proration Calculator** is a standalone web application designed to streamline and standardize the calculation of prorated service charges and credits when customers start or stop service mid-billing cycle.

### At a Glance

- **Purpose:** Calculate accurate prorated charges/credits for partial billing periods
- **Users:** Billing staff, customer service representatives
- **Environment:** Runs in any modern web browser, no installation required
- **Deployment:** Single HTML file (portable, shareable)
- **Cost:** Zero - no licenses, subscriptions, or hosting fees
- **Availability:** 24/7 offline access

### Problem Solved

Prior to this application, staff members calculated prorations manually using spreadsheets or calculators, leading to:
- Inconsistent calculation methods
- Human calculation errors
- Time-consuming manual processes
- Difficulty auditing past calculations
- No standardized documentation

### Solution Benefits

- ✅ **100% accuracy** - Automated calculations eliminate human error
- ✅ **Consistency** - All staff use the same calculation method
- ✅ **Speed** - Instant results vs. manual calculations
- ✅ **Transparency** - Shows step-by-step calculation breakdown
- ✅ **Audit trail** - Automatic history tracking
- ✅ **Easy to use** - Intuitive interface requires minimal training

---

## Purpose & Business Value

### Primary Purpose

Calculate prorated service charges and credits when:
1. **Service Starts Mid-Cycle** - Customer begins service after billing period started
2. **Service Stops Mid-Cycle** - Customer cancels/ends service before billing period ends

### Business Value

#### Financial Impact
- **Reduces errors** - Prevents over-billing and under-billing
- **Eliminates disputes** - Accurate calculations reduce customer complaints
- **Speeds up billing** - Faster processing of mid-cycle changes
- **Improves cash flow** - Correct charges issued on first attempt

#### Operational Impact
- **Saves time** - Reduces calculation time from 5-10 minutes to seconds
- **Standardizes process** - All staff use the same method
- **Reduces training** - New staff can calculate accurately immediately
- **Improves morale** - Staff spend less time on tedious calculations

#### Customer Service Impact
- **Faster resolution** - Immediate answers to customer questions
- **Increased trust** - Transparent calculation breakdown builds confidence
- **Better documentation** - Easy to explain charges/credits to customers
- **Consistent experience** - All customers receive same accurate treatment

### Use Cases

1. **New Service Activation**
   - Scenario: Customer starts service on September 15
   - Need: Calculate charge for September 15-30
   - Output: Prorated charge for partial month

2. **Service Cancellation**
   - Scenario: Customer cancels service on September 21
   - Need: Calculate credit for unused days (Sept 21-30 + October)
   - Output: Credit amount to issue

3. **Service Upgrades/Downgrades**
   - Scenario: Customer changes service level mid-cycle
   - Need: Calculate adjustment for partial period
   - Output: Additional charge or credit amount

4. **Temporary Service Holds**
   - Scenario: Customer pauses service for vacation
   - Need: Calculate credit for hold period
   - Output: Credit for unused service days

---

## Key Features

### Core Functionality

#### 1. **Proration Calculation Engine**

**What It Does:**
- Calculates exact cost per day for any billing period
- Applies per-day rate to active service days
- Accounts for varying month lengths (28-31 days)
- Handles leap years automatically
- Maintains full mathematical precision (no rounding until display)

**Calculation Method:**
```
Per Day Rate = Full Period Charge ÷ Total Days in Period
Prorated Amount = Per Day Rate × Active Service Days
```

**Accuracy:**
- Uses full decimal precision internally
- Rounds only for display ($XX.XX)
- Consistent with industry best practices

---

#### 2. **Multi-Cycle Support**

**Supported Billing Cycles:**

1. **Commercial (Monthly)**
   - Bills: 1st of each month
   - Period: First to last day of month
   - Example: October 1-31 (31 days)

2. **R1A2 JAJO (Residential Quarterly)**
   - Quarters: Jan-Mar, Apr-Jun, Jul-Sep, Oct-Dec
   - Bills: Last day of first month in quarter
   - Example: Jul 1 - Sep 30, billed July 31

3. **R1A2 FMAN (Residential Quarterly)**
   - Quarters: Feb-Apr, May-Jul, Aug-Oct, Nov-Jan
   - Bills: Last day of first month in quarter
   - Example: Nov 1 - Jan 31, billed November 30

4. **R1A2 MJSD (Residential Quarterly)**
   - Quarters: Mar-May, Jun-Aug, Sep-Nov, Dec-Feb
   - Bills: Last day of first month in quarter
   - Example: Dec 1 - Feb 28/29, billed December 31

**Smart Period Detection:**
- Automatically determines correct billing period from service date
- Handles cross-year periods (Nov-Jan, Dec-Feb)
- Accounts for leap years in February calculations

---

#### 3. **Billing Status Intelligence**

**Determines:**
- Whether invoice for the period has been sent
- Whether customer has already been billed
- What action is required (credit, charge, or none)

**Three Possible Outcomes:**

1. **"No Adjustment Needed"**
   - Invoice hasn't been generated yet
   - Next invoice will have correct amount
   - No immediate action required

2. **"$XX.XX (Credit)"**
   - Customer was already billed for full period
   - Service stopped early
   - Credit must be issued

3. **"$XX.XX (Charge)"**
   - Customer was already billed
   - Service started after billing
   - Additional charge must be collected

---

### Advanced Features

#### 4. **Visual Timeline**

**Purpose:** Graphical representation of service period

**Display:**
- Horizontal bar representing full billing period
- Green section: Active service days
- Red section: Unused service days
- Black marker: Service start/stop date
- Period start and end labels

**Benefits:**
- Visual confirmation of calculation
- Easy to explain to customers
- Quick verification of accuracy
- Professional appearance

---

#### 5. **Calculation Breakdown**

**Purpose:** Show step-by-step mathematical process

**Shows:**
- Period dates and total days
- Full period charge calculation
- Per-day rate formula and result
- Active days calculation
- Final prorated amount formula
- Credit calculation (if applicable)

**Example:**
```
Period: August 1, 2025 to October 31, 2025
Total Days: 92
Full Period Charge: $30.00

Per Day Rate = $30.00 ÷ 92 = $0.32608695652173914

Active Days: 51
Prorated Amount = $0.32608695652173914 × 51 = $16.63

Credit = $30.00 - $16.63 = $13.37
```

**Benefits:**
- Transparency builds trust
- Easy to verify accuracy
- Helpful for training
- Useful for customer explanations

---

#### 6. **Copy Functions**

**Three Copy Options:**

1. **Copy Amount**
   - Copies just the dollar figure
   - Format: `$13.37`
   - Use: Quick paste into billing systems

2. **Copy Summary**
   - Copies complete calculation report
   - Includes all details and formulas
   - Use: Documentation, emails, records

3. **Calculation Details**
   - Available via "Show Calculation Details" button
   - Full mathematical breakdown
   - Use: Verification, training, audits

---

#### 7. **Calculation History**

**Features:**
- Automatic saving of all calculations
- Chronological list (newest first)
- Search across all fields
- Filter by type (start/stop/credit/charge)
- Auto-cleanup after 3 business days

**Information Stored:**
- Timestamp
- Billing cycle
- Service type (start/stop)
- Service date
- Monthly rate
- Prorated amount
- Period details
- User notes

**Search Capabilities:**
- Real-time filtering as you type
- Searches: dates, cycle names, notes, service type
- Combination search + filter
- "No matching entries" feedback

---

#### 8. **Analytics Dashboard**

**Access:** Click "📊 Dashboard" button

**Displays:**

**Key Metrics:**
- Total calculations performed
- Total credits issued
- Total charges applied
- Count of "no adjustment" calculations

**Activity Breakdown:**
- Commercial vs. Residential split
- Data retention policy reminder

**Purpose:**
- Quick overview of activity
- Spot trends (many credits = possible billing issues)
- Management visibility
- Quality assurance

---

#### 9. **Input Validation**

**Prevents Errors:**

- ✅ Ensures billing cycle is selected
- ✅ Validates date format and logic
- ✅ Requires positive rate amount
- ✅ Enforces min/max rate limits ($0.01 - $10,000)
- ✅ Warns for dates >2 years old
- ✅ Warns for future dates
- ✅ Clear, specific error messages

**User-Friendly:**
- Real-time validation
- Helpful error messages
- Confirmation prompts for unusual inputs
- No cryptic technical errors

---

#### 10. **Contextual Help (Tooltips)**

**Location:** Small "?" icons next to field labels

**Provides:**
- Explanation of what each field means
- Clarification of billing cycles
- Reminder about stop date exclusion
- Guidance on monthly vs. quarterly rates

**Benefits:**
- Reduces training needs
- Prevents common mistakes
- Always available when needed
- Non-intrusive (hover to see)

---

#### 11. **Theme Toggle (Light/Dark Mode)**

**Features:**
- Automatic OS theme detection
- Manual toggle override
- Smooth transitions
- Preference saved automatically

**Benefits:**
- Reduces eye strain
- User comfort preference
- Professional appearance
- Accessibility enhancement

---

## Technical Specifications

### Architecture

**Type:** Single-page web application (SPA)
**File Structure:** Self-contained HTML file
**Size:** ~55KB (incredibly lightweight)
**Dependencies:** None (completely standalone)

### Technology Stack

**Frontend:**
- HTML5 (semantic markup)
- CSS3 (modern styling, animations)
- JavaScript ES6+ (vanilla, no frameworks)

**Storage:**
- Browser localStorage (5-10MB available)
- No database required
- No server-side processing

**Libraries/Frameworks:**
- None - uses only native browser APIs
- No jQuery, React, Angular, etc.
- No external CSS frameworks

### Browser Compatibility

**Fully Supported:**
- Google Chrome 90+
- Mozilla Firefox 88+
- Microsoft Edge 90+
- Safari 14+

**Minimum Requirements:**
- ES6 JavaScript support
- localStorage API
- CSS Grid and Flexbox
- Date input type

### Performance

**Load Time:** <100ms (instant)
**Calculation Speed:** <5ms (instantaneous)
**Memory Usage:** <5MB
**Storage Usage:** ~1KB per calculation entry

### Code Quality

**Standards:**
- Clean, readable code structure
- Comprehensive inline comments
- Consistent naming conventions
- DRY principles (Don't Repeat Yourself)
- Defensive programming (error handling)

**Testing:**
- Manual testing of all features
- Edge case validation
- Cross-browser testing
- Input validation testing

---

## Billing Cycles & Calculations

### How Proration Works

**Core Principle:** Customer pays only for days they have service

**Formula:**
```
Cost Per Day = Full Period Charge ÷ Total Days in Period
Prorated Charge = Cost Per Day × Days of Service
```

### Example Calculation

**Scenario:** Residential customer (R1A2 FMAN) stops service

- **Period:** August 1 - October 31, 2025 (92 days)
- **Monthly Rate:** $10.00
- **Full Period Charge:** $10.00 × 3 months = $30.00
- **Service Stop Date:** September 21, 2025
- **Days Used:** Aug 1-31 (31) + Sept 1-20 (20) = 51 days
- **Days Unused:** Sept 21-30 (10) + Oct 1-31 (31) = 41 days

**Calculation:**
```
Per Day Rate = $30.00 ÷ 92 = $0.326087 per day
Amount Used = $0.326087 × 51 = $16.63
Credit Due = $30.00 - $16.63 = $13.37
```

**Result:** Customer receives a credit of **$13.37**

### Important Notes

1. **Stop dates are EXCLUDED** - If service stops Sept 21, last service day is Sept 20
2. **Start dates are INCLUDED** - If service starts Sept 21, billing begins Sept 21
3. **Monthly rate always used** - Even for quarterly customers, enter monthly rate
4. **Leap years handled** - February automatically adjusts for leap years
5. **Inclusive counting** - Both start and end dates of period are counted

---

## User Interface Overview

### Layout Structure

**Header:**
- Application title
- Dashboard button
- Theme toggle button

**Main Form:**
- Invoice cycle selector
- Service type radio buttons
- Date picker
- Monthly rate input
- Notes text area
- Calculate button

**Results Area:**
- Adjustment amount (large display)
- Detailed statistics
- Visual timeline
- Billing status explanation
- Action buttons (Show Details, Copy)

**History Section:**
- Search box
- Filter dropdown
- Clear log button
- Chronological list of past calculations

### Design Philosophy

**Principles:**
- Clean, uncluttered interface
- Logical top-to-bottom flow
- Clear visual hierarchy
- Consistent styling
- Professional appearance

**Color Scheme:**
- **Light Mode:** White/light gray backgrounds, dark text
- **Dark Mode:** Dark blue/gray backgrounds, light text
- **Accents:** Blue (primary), green (success), red (alerts)

**Typography:**
- System fonts (fast loading, familiar)
- Clear hierarchy (headings, labels, body text)
- Appropriate sizing for readability

---

## Data Management

### What Data is Stored

**Calculation Records:**
- Timestamp of calculation
- Billing cycle selected
- Service type (start/stop)
- Service date
- Monthly rate entered
- Calculated amounts
- Period details
- User notes

**User Preferences:**
- Theme preference (light/dark)

### Where Data is Stored

**Location:** Browser localStorage (local to each computer)

**Characteristics:**
- Stored on user's computer only
- Not sent to any server
- Not shared across browsers
- Not shared across computers
- Remains until manually cleared or auto-deleted

### Data Retention

**Automatic Cleanup:**
- Entries older than 3 business days are automatically deleted
- Weekends excluded from business day count
- Runs on every page load
- Transparent to user

**Manual Deletion:**
- "Clear Log" button removes all history immediately
- Cannot be undone
- Confirms before deleting

**Storage Limits:**
- Maximum 100 entries stored (enforced by app)
- Prevents localStorage overflow
- Oldest entries deleted if limit reached

---

## Security & Privacy

### Data Privacy

**✅ Completely Private:**
- All data stays on user's computer
- No data transmitted to internet
- No tracking or analytics
- No cookies (except localStorage)
- No external connections

**✅ No Personal Information:**
- Doesn't store customer names
- Doesn't store account numbers
- Doesn't store personal data
- Only stores calculation parameters

### Access Control

**Current State:**
- Open access (no login required)
- Anyone with the file can use it
- Each user has separate history (per browser)

**Multi-User Considerations:**
- Users can't see each other's calculations
- Each browser instance is independent
- No central audit trail across users

### Data Security

**Strengths:**
- Offline = no network vulnerabilities
- No database to hack
- No server to compromise
- Data controlled by user

**Limitations:**
- No encryption (data in plain text in localStorage)
- No user authentication
- No access logging
- Suitable for low-sensitivity data only

---

## System Requirements

### Minimum Requirements

**Computer:**
- Any desktop or laptop
- Windows, macOS, or Linux
- 1GB RAM minimum
- 50MB free disk space

**Browser:**
- Google Chrome 90+
- Mozilla Firefox 88+
- Microsoft Edge 90+
- Safari 14+

**Internet:**
- NOT required for operation
- Optional for initial file download

### Recommended Setup

**Computer:**
- Modern desktop or laptop (2015 or newer)
- 4GB RAM or more
- Up-to-date operating system

**Browser:**
- Latest version of Chrome, Firefox, or Edge
- Browser storage enabled (not in "Private/Incognito" mode)

**Display:**
- Minimum 1024×768 resolution
- 1920×1080 or higher recommended

---

## Deployment & Distribution

### Installation

**Steps:**
1. Copy `proration_calculator.html` to desired location
2. Double-click to open in default browser
3. Bookmark for easy access (optional)

**No installation required** - it's just an HTML file!

### Recommended Deployment

**Option 1: Network Share**
- Place file on shared network drive
- All staff access from same location
- Easy to update (replace file)

**Option 2: Email Distribution**
- Email file to staff
- Staff saves to their computer
- Each user has own copy

**Option 3: Intranet**
- Host on company intranet
- Access via URL
- Centralized version control

### Updates & Versioning

**Current Approach:**
- Version number in file comments
- Manual distribution of updates
- Users replace old file with new file

**Best Practice:**
- Notify users of updates via email
- Provide changelog of new features
- Replace file on network share (if using)

---

## Support & Maintenance

### User Support

**Resources:**
- User Guide (USER_GUIDE.md)
- This summary document
- Tooltips within application
- Calculation breakdowns for verification

**Support Channels:**
- Supervisor for calculation questions
- IT department for technical issues
- Email copy of calculations for audit

### Maintenance Requirements

**Ongoing:**
- None - application is self-contained
- No database to maintain
- No server to update
- No subscriptions to renew

**Periodic:**
- Review for accuracy (annually)
- Update if billing cycles change
- Test with new browser versions

### Known Limitations

1. **No collaboration** - Users can't see each other's calculations
2. **No central audit** - No enterprise-wide calculation tracking
3. **Browser-dependent** - History tied to specific browser
4. **3-day retention** - History auto-deletes (by design)
5. **No backup** - Users must copy important calculations
6. **No reporting** - No aggregate reports across all users

### Future Enhancements (Potential)

**Could Add:**
- Export history to CSV
- Print calculation reports
- Shared database for collaboration
- User authentication
- Enterprise audit logging
- Integration with billing system

**Currently Not Planned:**
- These would require significant architecture changes
- Would add complexity and dependencies
- Current solution meets core business needs

---

## Summary of Benefits

### For Staff

✅ **Faster** - Seconds vs. minutes for calculations
✅ **Easier** - No manual math required
✅ **Accurate** - Eliminates human error
✅ **Transparent** - Shows all calculation steps
✅ **Helpful** - Built-in help and validation

### For Customers

✅ **Fair** - Consistent, accurate proration
✅ **Clear** - Easy-to-understand explanations
✅ **Fast** - Quick resolution of billing questions
✅ **Trustworthy** - Mathematical precision

### For Organization

✅ **Standardized** - One method for all staff
✅ **Auditable** - Calculation history tracked
✅ **Cost-effective** - Zero ongoing costs
✅ **Scalable** - Works for any number of users
✅ **Reliable** - No downtime or dependencies

---

## Conclusion

The Recology King County Service Proration Calculator represents a simple yet powerful solution to a common business problem. By automating and standardizing proration calculations, it:

- **Improves accuracy** and consistency
- **Saves time** for staff
- **Enhances customer service**
- **Reduces billing disputes**
- **Provides transparency** and auditability

The application's standalone architecture ensures:

- **Zero ongoing costs**
- **Maximum uptime** (offline capable)
- **Easy deployment** (single file)
- **Minimal support** requirements
- **Complete data privacy**

This tool demonstrates that effective business solutions don't always require complex infrastructure or expensive software – sometimes a well-designed, focused application is the perfect answer.

---

## Quick Facts

| Attribute | Value |
|-----------|-------|
| **File Size** | ~55KB |
| **Languages** | HTML, CSS, JavaScript |
| **Dependencies** | None |
| **Internet Required** | No |
| **Installation** | None (double-click to run) |
| **Cost** | $0 |
| **License Required** | No |
| **User Limit** | Unlimited |
| **Concurrent Users** | Unlimited |
| **Data Storage** | Local (localStorage) |
| **Backup Required** | No (auto-deletes in 3 days) |
| **Maintenance** | Minimal to none |
| **Training Time** | <30 minutes |

---

**Document Version:** 1.0
**Last Updated:** October 22, 2025
**Prepared For:** Recology King County
**Prepared By:** Development Team

*For questions or feedback, contact your IT department or supervisor.*
