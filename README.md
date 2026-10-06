# Calculator_Menu_filter
# Menu Calculator: QA Testing Project

Manual QA project on the **Menu Calculator** web app ("Calculation of dinners in the Online Cafe"), completed as part of the SQA training program at the A1QA training center (QATC).

## Overview

Menu Calculator lets a user pick dishes from a daily menu, place an order, and track the account balance and order history. This repository documents the testing performed and the defects found in version **1.0**.

## Application Behavior

- Daily menus for Monday to Saturday, selected from a dropdown.
- Each dish has a price in RUB (for example Pilaf 150, Semolina Porridge 52.1, Pork Stew 250, Cabbage Soup 129.3).
- The user selects dishes and clicks **Place Order**. The total is deducted from the main account balance.
- Each placed order is added to the **Order History**.
- A **50 RUB daily compensation** applies to the first order of the day only.
- Placing an empty order should be rejected with a message.
- The **Menu Calculator** button should return to the home page only. The **Start** button is the only way to reset the page.

## Scope of Testing

| Type | Focus |
|------|-------|
| Functional | Item selection, price calculation, balance deduction, order history, compensation rules, empty orders, order limits |
| GUI | Spelling of item names, hover effects, navigation behavior |

## Test Environment

| Item | Details |
|------|---------|
| OS | Windows 11 (64-bit) |
| Browser | Google Chrome 150.0.7871.115 |
| Application version | 1.0 |
| Defect tracking | Jira (project: Training Center, component: Calculator Menu) |

## Defect Summary

**42 defects** were reported, all currently **Open**.

| Severity/Priority | Count |
|---|---|
| Major | 38 |
| Minor | 1 |
| Trivial | 3 |

| Error type | Count |
|---|---|
| Functional | 38 |
| GUI | 4 |

### Defect categories

| Category | Examples |
|----------|----------|
| Balance and price calculation | Wrong amount deducted; some items increase the balance instead of reducing it; some items not debited; floating-point totals such as `212.54000000000002` |
| Order history | Decimal values omitted; history amount does not match the deduction |
| Selection state | Items stay selected after ordering or when switching days; items from other days are added to the bill |
| Compensation and empty orders | 50 RUB applied to every order; repeated empty orders add money; unexpected notification on repeated empty orders |
| Balance validation | Balance goes negative; order accepted with insufficient funds |
| Order limits | No limit on repeated orders (button click or Space key) |
| Navigation and GUI | Menu Calculator button clears history; hover effect applied to the wrong element; misspelled item names |

## Defect Report Format

Each defect was logged in Jira with:

- Title and summary
- Steps to reproduce
- Actual result and expected result
- Environment (OS, browser)
- Priority, severity, and error type (Functional / GUI)
- Screenshots as attachments

## Skills Demonstrated

- Functional and GUI testing
- Boundary and negative testing (insufficient balance, empty orders, repeated actions)
- Clear, reproducible bug reporting
- Defect tracking and lifecycle management in Jira

## Author

**Arshad Md. Adel**: SQA trainee, CSE graduate of United International University (UIU).
