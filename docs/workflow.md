# Sales / Closing Workflow

## Scenario

**Make Scenario:** Sales / Closing

The scenario connects ClickUp and Gmail to automate prospect sales and closing actions.

## Module Flow

```text
ClickUp — List Filtered Tasks
              ↓
           Router
          ↙     ↘
       Route 1  Route 2
         ↓        ↓
      Gmail    ClickUp
         ↓        ↓
      ClickUp
```

## Module 1 — ClickUp: List Filtered Tasks

The first module retrieves prospect tasks from ClickUp.

The prospect information comes from the ClickUp **New Prospects** list.

Relevant information includes:

* Prospect name
* Email
* Phone
* Status
* Visa Interest
* Other ClickUp task information

## Module 2 — Router

The Router separates prospects into different paths based on their information.

This allows different actions to be performed depending on the prospect's current situation.

## Route 1 — Sales / Closing Communication

The first route uses a filter based on the prospect's ClickUp status and date-related information.

The current test condition includes:

* Status = `appointment`
* Current date/time condition is being tested

When the conditions are met, the prospect continues to the Gmail module.

### Gmail

The Gmail module sends the appropriate automated email to the prospect.

After the email action, the workflow continues to a ClickUp task update.

### ClickUp

The ClickUp module updates the prospect's task after the communication step.

## Route 2 — Visa Interest

The second route uses the ClickUp custom field **Visa Interest**.

The important distinction is that the automation uses the **actual task-level custom-field value**, rather than the original custom-field configuration.

### Current Test Condition

The ClickUp dropdown contains:

* `Yes`
* `No`

The current ClickUp configuration shows:

```text
No = 1
```

Therefore, the filter uses:

```text
Visa Interest → Value
Equal to
1
```

This allows the automation to correctly identify prospects whose Visa Interest selection is **No**.

## Testing

The workflow is currently being tested with test prospects.

Testing is being performed before the automation is used with live prospects.

The tests verify:

1. ClickUp retrieves the correct prospects.
2. The Router receives the correct bundles.
3. Each filter evaluates the correct task-level data.
4. Gmail is triggered only when the correct route conditions are met.
5. ClickUp is updated after the appropriate action.

## Important Implementation Detail

When working with ClickUp custom fields in Make, the workflow should use the task's actual **Custom Fields** data.

The **Custom Fields (original)** structure contains custom-field configuration information and should not be used as the task's selected value for routing decisions.

For the Visa Interest filter, the correct data source is:

```text
Custom Fields → Visa Interest
```

with the corresponding task value.

## Status

**Current stage:** Testing

The automation will be considered ready for live use after the routing, Gmail actions, and ClickUp updates have been successfully tested with multiple test prospects.
