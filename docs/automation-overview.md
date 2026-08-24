
# Sales & Closing Automation

## Overview

This project automates prospect follow-up and sales-closing workflows using Make, ClickUp, and Gmail.

The automation reads prospect information from ClickUp, evaluates the prospect's current status and visa interest, and routes the prospect to the appropriate sales or follow-up action.

## Tools Used

* **ClickUp** — Prospect management and task/status tracking
* **Make** — Automation and routing
* **Gmail** — Automated email communication
* **GitHub** — Documentation and version control

## Current Automation

The current Make scenario is called **Sales / Closing**.

### Main Flow

1. Make retrieves filtered prospect tasks from ClickUp.
2. A Router evaluates the prospect's information.
3. Prospects are routed based on their current status and other qualifying information.
4. The appropriate Gmail or ClickUp action is executed.
5. ClickUp is updated so the prospect's progress remains organized.

## Visa Interest

The ClickUp list contains a custom field called **Visa Interest**.

The field is a dropdown with values such as:

* Yes
* No

The automation uses the actual task-level **Visa Interest value**, rather than the original custom-field configuration.

For the current test data:

* `No` corresponds to value `1`.

## Testing

The automation is currently being tested using test prospects.

Test prospects are intentionally used while the routing, email, and ClickUp update logic are being validated.

## Goal

The goal is to create a reliable automated sales-closing workflow that:

* Identifies the correct prospect stage
* Sends the appropriate communication
* Updates ClickUp automatically
* Reduces manual follow-up work
* Provides a clear and maintainable automation structure
