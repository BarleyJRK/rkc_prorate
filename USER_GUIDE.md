# Recology King County - Service Proration Calculator
## User Guide

**Version:** 1.0
**Last Updated:** October 2025
**For:** Staff Members

---

## Table of Contents
1. [Getting Started](#getting-started)
2. [Performing a Basic Calculation](#performing-a-basic-calculation)
3. [Understanding the Results](#understanding-the-results)
4. [Using Advanced Features](#using-advanced-features)
5. [Viewing Analytics Dashboard](#viewing-analytics-dashboard)
6. [Searching Calculation History](#searching-calculation-history)
7. [Troubleshooting](#troubleshooting)
8. [Tips & Best Practices](#tips--best-practices)

---

## Getting Started

### Opening the Calculator

1. **Locate the file:** `proration_calculator.html`
2. **Double-click** the file to open it in your default web browser
   - Works with: Chrome, Firefox, Edge, Safari
   - No internet connection required
3. The calculator will open immediately - no login or setup needed

### Understanding the Interface

When you first open the calculator, you'll see:

- **Header Area:**
  - Title: "Recology King County - Service Proration Calculator"
  - 📊 Dashboard button (top right)
  - 🌙/☀️ Theme toggle (for dark/light mode)

- **Calculator Form:** Main area with input fields
- **Calculation History:** Below the calculator showing past calculations

---

## Performing a Basic Calculation

### Step 1: Select Invoice Cycle

**Field:** "Invoice Cycle" (dropdown)

**Options:**
- **Commercial (Monthly)** - For commercial customers billed monthly
- **R1A2 JAJO** - Residential quarterly: Jan/Apr/Jul/Oct
- **R1A2 FMAN** - Residential quarterly: Feb/May/Aug/Nov
- **R1A2 MJSD** - Residential quarterly: Mar/Jun/Sep/Dec

**Action:** Click the dropdown and select the customer's billing cycle

💡 **Hover over the "?" icon** for help text explaining billing cycles

---

### Step 2: Choose Service Type

**Field:** "Service Type" (radio buttons)

**Options:**
- **Start of Service** - Customer is starting service (select this for new service)
- **End of Service** - Customer is stopping service (select this for cancellations)

**Action:** Click the appropriate radio button

💡 **Important:** For "End of Service," the stop date is **NOT included** in the billing period. If service stops on September 21, the customer's last day of service is September 20.

---

### Step 3: Enter Service Date

**Field:** "Service Date" (date picker)

**Action:**
- **Option A:** Click the calendar icon and select a date
- **Option B:** Type the date directly in MM/DD/YYYY format

**Validation Warnings:**
- Dates older than 2 years will prompt a confirmation
- Future dates will prompt a confirmation
- Invalid dates will show an error

💡 **Tip:** For service stops, enter the date the customer STOPPED service (not their last day of service)

---

### Step 4: Enter Monthly Service Rate

**Field:** "Monthly Service Rate ($)" (number input)

**Action:** Enter the customer's **monthly rate** as a dollar amount

**Examples:**
- For $45.50 per month → Enter: `45.50`
- For $120 per month → Enter: `120.00`

**Important Notes:**
- ✅ Always enter the MONTHLY rate (even for quarterly billing)
- ✅ For residential customers, enter the monthly rate, NOT the quarterly total
- ❌ Do NOT enter the quarterly amount

**Validation:**
- Minimum: $0.01
- Maximum: $10,000.00
- Must be a positive number

---

### Step 5: Add Notes (Optional)

**Field:** "Notes" (text area)

**Purpose:** Record any additional context about this calculation

**Examples:**
- "Customer upgraded service mid-cycle"
- "Service put on hold - vacation"
- "Account cancellation - moved out of service area"

**Action:** Type any relevant notes (optional but recommended for record-keeping)

---

### Step 6: Calculate

**Action:** Click the blue **"Calculate Proration"** button

**What Happens:**
1. Form inputs are validated
2. Calculation is performed instantly
3. Results appear below the form
4. Entry is added to Calculation History
5. Entry is saved in browser storage

---

## Understanding the Results

### Result Display

After clicking Calculate, you'll see a results box with:

#### 1. **Adjustment Amount** (Large, bold at top)

**Possible Displays:**

- **"No Adjustment Needed"**
  - Meaning: Invoice for this period hasn't been sent yet
  - Action: No immediate action needed; upcoming invoice will have correct amount

- **"$XX.XX (Credit)"**
  - Meaning: Customer was already billed; they are owed a credit
  - Action: Issue a credit note for this amount

- **"$XX.XX (Charge)"**
  - Meaning: Customer was already billed but service started after billing
  - Action: Charge customer this additional amount

---

#### 2. **Detailed Statistics**

The results show:

- **Period:** The billing period dates (e.g., "August 1, 2025 to October 31, 2025")
- **Cycle:** The billing cycle name
- **Monthly Rate:** The rate you entered
- **Full Period Charge:** Total charge for entire period (monthly rate × months)
- **Per Day Rate:** Cost per day with full precision (unrounded)
- **Total Days in Period:** Total days in the billing period
- **Active Service Days:** Days customer had service
- **# of Unused Service Days:** Days NOT used (for credits)

---

#### 3. **Visual Timeline**

A color-coded bar showing:

- **Green gradient:** Days of active service
- **Red gradient:** Unused days (if any)
- **Black marker:** Service start or stop date
- **Labels:** Period start and end dates

**How to Read It:**
- The bar represents the entire billing period
- Green shows what the customer used
- Red shows what they didn't use (for stops)
- The marker shows exactly when service changed

---

#### 4. **Billing Status Explanation**

A detailed message explaining:

- Whether the period has been billed already
- What action (if any) is needed
- The calculation context

**Example Messages:**

> "The invoice for this period was issued on October 31, 2025. The customer was billed for the full period ($30.00). Since service ended on September 21, 2025, **credit $13.37** for the unused portion of the service period."

> "The invoice for this period (scheduled for October 31, 2025) has not been generated yet. No separate adjustment needed – the next bill will include the prorated charge of $16.63."

---

## Using Advanced Features

### Show Calculation Details

**Purpose:** See the step-by-step math behind the calculation

**How to Use:**
1. After performing a calculation, look for the button: **"Show Calculation Details"**
2. Click the button
3. A breakdown appears showing:
   - Period information
   - Per day rate calculation formula
   - Active days calculation
   - Final prorated amount with all steps

**Example Breakdown:**
```
Calculation Breakdown:
Period: August 1, 2025 to October 31, 2025
Billing Cycle: R1A2 FMAN
Total Days in Period: 92 days
Full Period Charge: $30.00

Per Day Rate = Full Period Charge ÷ Total Days
Per Day Rate = $30.00 ÷ 92
Per Day Rate = $0.32608695652173914

Service Stopped: September 21, 2025
Active Days: 51 days
Unused Days: 41 days

Prorated Amount = Per Day Rate × Active Days
Prorated Amount = $0.32608695652173914 × 51
Prorated Amount = $16.63

Credit Amount = Full Period Charge - Prorated Amount
Credit Amount = $30.00 - $16.63
Credit Amount = $13.37
```

**To Hide:** Click **"Hide Calculation Details"**

---

### Copy Functions

Three copy buttons appear after each calculation:

#### 1. **Copy Amount**
- Copies just the dollar amount to your clipboard
- Format: `$13.37` or `No Adjustment Needed`
- Use: Quick paste into other systems

#### 2. **Copy Summary**
- Copies a full text summary of the calculation
- Includes: All statistics, dates, amounts, and adjustment needed
- Use: Email to colleagues, paste into tickets, documentation

**Example Copy Summary:**
```
Recology King County - Service Proration
===========================================
Date: 10/22/2025, 2:30:45 PM

Period: August 1, 2025 to October 31, 2025
Cycle: R1A2 FMAN
Service Stopped: September 21, 2025
Monthly Rate: $10.00
Full Period Charge: $30.00
Per Day Rate: $0.32608695652173914
Total Days: 92
Active Days: 51
Unused Days: 41
Prorated Amount: $16.63

ADJUSTMENT: Credit $13.37
```

---

### Theme Toggle

**Purpose:** Switch between light and dark mode for comfort

**How to Use:**
1. Click the 🌙 or ☀️ button in the top right
2. The app switches themes immediately
3. Your preference is saved automatically
4. Next time you open the app, your chosen theme loads

**Default Behavior:**
- App detects your operating system theme preference
- Automatically shows dark mode if your OS is in dark mode
- Manually selecting a theme overrides the automatic detection

---

## Viewing Analytics Dashboard

### Opening the Dashboard

**Action:** Click the **"📊 Dashboard"** button in the top right

### What You'll See

The dashboard displays:

#### 1. **Key Statistics (4 Cards)**

- **Total Calculations:** Number of calculations performed
- **Total Credits:** Sum of all credit amounts
- **Total Charges:** Sum of all charge amounts
- **No Adjustment:** Count of calculations requiring no action

#### 2. **Activity Breakdown**

- **Commercial Cycles:** Count of commercial calculations
- **Residential Cycles:** Count of residential calculations

#### 3. **Data Retention Notice**

> "Calculations are automatically deleted after 3 business days."

### Closing the Dashboard

**Two Ways:**
1. Click the **×** button in the top right of the dashboard
2. Click anywhere outside the dashboard box

---

## Searching Calculation History

### Using the Search Box

**Location:** Above the Calculation History section

**How to Use:**
1. Click in the **"🔍 Search logs..."** box
2. Type any keyword
3. Results filter in real-time as you type

**What You Can Search:**
- Date (e.g., "September", "9/21", "2025")
- Billing cycle (e.g., "FMAN", "Commercial")
- Service type (e.g., "start", "stop")
- Notes (e.g., "vacation", "moved")

**Example Searches:**
- Type `september` → Shows all September calculations
- Type `credit` → Shows entries requiring credits
- Type `commercial` → Shows commercial customer calculations

---

### Using the Filter Dropdown

**Location:** Next to the search box

**Filter Options:**
- **All Entries** - Shows everything (default)
- **Start Only** - Shows only service starts
- **Stop Only** - Shows only service stops
- **Credits Only** - Shows only calculations requiring credits
- **Charges Only** - Shows only calculations requiring charges

**How to Use:**
1. Click the dropdown
2. Select a filter option
3. History updates immediately

**Combining Search & Filter:**
- You can use search and filter together
- Example: Filter "Credits Only" + Search "September" = All September credits

---

### Clearing History

**Purpose:** Remove all calculation history

**How to Use:**
1. Click the **"Clear Log"** button
2. Confirm when prompted: "Are you sure you want to clear all calculation history? This cannot be undone."
3. All history is deleted immediately

**⚠️ Warning:** This action cannot be undone. All history is permanently deleted.

**Note:** History also auto-deletes after 3 business days (weekends excluded)

---

## Troubleshooting

### Problem: Error Message "Please enter a valid date"

**Cause:** Date is not in a recognized format or is invalid

**Solution:**
- Use the date picker (calendar icon) instead of typing
- If typing, use format: MM/DD/YYYY (e.g., 09/21/2025)
- Check for typos (e.g., month 13, day 32)

---

### Problem: "Monthly rate cannot exceed $10,000"

**Cause:** Entered amount is too high

**Solution:**
- Check if you accidentally added extra digits
- Verify the monthly rate with customer records
- If legitimate rate is over $10,000, contact IT for limit adjustment

---

### Problem: "Warning: Unable to save calculation history"

**Cause:** Browser storage is full or disabled

**Solution:**
1. Clear browser history/cache
2. Enable browser storage (check browser settings)
3. Close other tabs to free up memory
4. If problem persists, calculations still work but won't be saved

---

### Problem: Calculator won't open / shows blank page

**Cause:** Browser compatibility issue

**Solution:**
- Try a different browser (Chrome, Firefox, Edge recommended)
- Update your current browser to the latest version
- Check that JavaScript is enabled in browser settings
- Try refreshing the page (F5 or Ctrl+R)

---

### Problem: Calculation seems incorrect

**Cause:** Possible input error or misunderstanding

**Solution:**
1. Click **"Show Calculation Details"** to see the math
2. Verify:
   - Correct billing cycle selected
   - Correct service type (start vs stop)
   - Correct date entered
   - Monthly rate (not quarterly) entered
3. Remember: Stop dates are NOT included in service days
4. If still seems wrong, use the Copy Summary feature and contact your supervisor

---

### Problem: Can't find a past calculation

**Cause:** History auto-deletes after 3 business days OR search/filter is active

**Solution:**
1. Check the search box - clear it (delete any text)
2. Check the filter dropdown - set to "All Entries"
3. If calculation is older than 3 business days, it was auto-deleted
4. For records older than 3 days, check your email or ticketing system

---

## Tips & Best Practices

### ✅ DO:

1. **Always use "Show Calculation Details"** for complex calculations
   - Helps verify the math is correct
   - Useful for explaining to customers

2. **Add notes to every calculation**
   - Makes it easier to search history later
   - Helps other staff understand the context

3. **Use "Copy Summary"** for documentation
   - Paste into customer records
   - Include in email communications
   - Attach to billing adjustments

4. **Double-check the service type**
   - Start vs Stop makes a big difference
   - Verify with customer before calculating

5. **Verify the billing cycle**
   - Check customer account before selecting
   - Wrong cycle = wrong calculation

6. **Keep the calculator open** throughout your shift
   - History persists as long as the window is open
   - No need to reopen for each calculation

---

### ❌ DON'T:

1. **Don't enter quarterly amounts for residential customers**
   - Always use the monthly rate
   - The calculator will multiply by 3 automatically

2. **Don't forget stop dates are exclusive**
   - If service stops 9/21, last service day was 9/20
   - The calculator handles this automatically

3. **Don't rely solely on history beyond 3 days**
   - Copy important calculations immediately
   - Save summaries in your ticketing system

4. **Don't calculate manually**
   - Always use the calculator for accuracy
   - Manual calculations are error-prone

5. **Don't ignore warnings**
   - If prompted about old dates, verify the date is correct
   - If prompted about future dates, verify you meant to do this

---

### 🎯 Accuracy Checklist

Before clicking Calculate, verify:

- [ ] Correct customer billing cycle selected
- [ ] Service type is correct (Start vs Stop)
- [ ] Date is accurate
- [ ] Monthly rate (not quarterly) entered
- [ ] Notes added (optional but recommended)

After calculation, verify:

- [ ] Result makes sense (not negative, not unreasonably high)
- [ ] Period dates match customer's billing period
- [ ] Adjustment type is correct (Credit/Charge/No Adjustment)

---

### 📞 Getting Help

**For technical issues:**
- Contact IT Support with a screenshot of the error

**For calculation questions:**
- Use "Show Calculation Details" to review the math
- Use "Copy Summary" and share with your supervisor
- Refer to this user guide

**For billing policy questions:**
- Contact your supervisor or billing department

---

## Quick Reference Card

### Common Scenarios

| Scenario | Cycle | Type | Date | Rate |
|----------|-------|------|------|------|
| Commercial customer starts mid-month | Commercial (Monthly) | Start | Date service began | Monthly rate |
| Commercial customer cancels mid-month | Commercial (Monthly) | Stop | Date service ended | Monthly rate |
| Residential customer starts in October | R1A2 JAJO | Start | Date service began | Monthly rate |
| Residential customer cancels in September | R1A2 FMAN | Stop | Date service ended | Monthly rate |

### Keyboard Shortcuts

- **Tab** - Move to next field
- **Shift+Tab** - Move to previous field
- **Enter** - Submit form (when in any field)
- **Esc** - Close dashboard (when dashboard is open)

### Important Reminders

- 🚫 Stop dates are NOT included in billing
- 💵 Always enter MONTHLY rate (never quarterly)
- 📅 History auto-deletes after 3 business days
- 💾 Copy important calculations immediately
- ❓ Hover over "?" icons for help

---

**End of User Guide**

*For questions or feedback about this guide, contact your supervisor or IT department.*
