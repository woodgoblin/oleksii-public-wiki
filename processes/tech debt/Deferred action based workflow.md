# Deferred action based workflow
This is here mostly for indexing, the most up to date version is linked below:

https://www.notion.so/Deferred-action-based-workflow-214c9b00b45080948076d9accb952be9



So, let’s say we didn’t proceed with the non-PO required (technical) change because it was ‘in the ideal world’ or ‘it is deprioritized, let’s fix it next sprint’

# Deferred actions detection

Usually whenever you think about a ‘tech debt ticket’ do the following

First, let’s define is it a deferred action or is it a housekeeping item.

IMPACT IMPACT IMPACT

## Impact based assessment

What is the impact?

1. If there is a functional impact (there is no ‘non-functional’ requirements) — it IS a deferred change
2. If there is an impact on maintainability or ease of change — it IS a deferred change.
3. If there is known multipliability of bad practice (e.g. bad naming without any impact) — it IS a deferred change.
4. If it is none of the above AND THE TEAM IS OKAY it is a housekeeping item.
5. If the Team strongly things that this is a housekeeping item and it doesn’t have high housekeeping turned deferred rate — it is a housekeeping item regardless of points 1-4.

### Checklist

- [ ]  Functional Impact Assessment
    - Impact on performance, security, or scalability? (yes/no)
    - Impact severity (1-10)
- [ ]  Maintainability Impact Assessment
    - Impact on code maintainability? (yes/no)
    - Impact severity (1-10)
- [ ]  Multiplication Risk Assessment
    - Risk of bad practice/degradation multiplication (1-10)
- [ ]  Housekeeping Classification
    - Can this be classified as housekeeping? (yes/no)
    - If yes, provide justification

## Reason

If classified as a deferred action, we MUST provide ‘reason of not doing it NOW’ with a more priority work item link.

We leave housekeeping items alone for the ‘lull in combat’ phases. Those clog the backlog and are filtered out. Maybe higher impact ones, if impact is assigned, are visible, others are invisible paper trail. We accept it. 

However, we try to pair them with code using TODOs when possible.

# Deferred actions active phase

## Post-detection estimation

We provide (in units of our choosing) the estimate it would have taken to fix this IF IT WAS DONE RIGHT NOW. It would be not done now but it is essential.

## Optional criticality

If the Team feels so, the arbitrary criticality could be assigned to deferred action meaning its IMPACT if not done.

## Optional classification (useful for accepting impact later)

### Type

Considering two things

- Were we knowing the info needed to make the right choice
- Did we make the knowing trade-off or an inadvertent mistake

Is it an

1. **Oversight**, i.e. mistake done with knowing the information but not paying attention.
2. **Shortcut**, i.e. mistake done with knowing the information, paying attention but accepting the wrong decision that needs to be fixed for the sake of short term benefit
3. **Adaptation**, i.e. right choice given that we didn’t know the information we know now.

### Binary multipliability (is it going to multiply)

yes/no

## Setting expiration

If quarterly planning is considered (bad):

- MUST be done in the next quarter
- MUST be first priority in the next quarter if not done in this quarter
- MUST be CRITICAL priority in the quarter after next (needs to be done yesterday)
- Barring the above, accept the impact and don’t plan for the action to be done at all.

If we can plan with sprints (good)

- MUST be done in the next 2-4 sprints (team agreement)
- MUST be first priority in the 3rd-5th sprint
- MUST be CRITICAL priority in the 4th - 6th spting
- Barring the above, accept the impact and don’t plan for the action to be done at all.

## Acceptance or impact in case of expiration

Impact is accepted means we don’t automatically plan on the deferred action to be done — not as housekeeping item, not as anything. It is an accepted bug (oversight), non-adaptability (adaptation) or shortcut (shortcut) — or if the classification is not done, just an accepted inaction.

### Optional ‘won’t do’ versus ‘not needed’

If the Team feels the need to do so, the check could be made of ‘not needed’ (this turned out to be not a mistake/overcome by events) versus ‘won’t do’ (we won’t do a valid deferred action because of its expiration)

## Doing a deferred action

In the unlikely event that the action is not expired, we approach it as the usual sprint item. We estimate it as a task or bug (depends on team preference) and fix it as if it were any other work item.

However there are few additional steps

### Estimate comparison

When created, a deferred action was estimated as if it would be done immediately.

Answer the following

- What is the difference?
    - If actual fix took more, why?
        - Is it because of multipliability
        - If not, what is the reason
    - If actual fix took less, why?
- Optional: was it beneficial to defer?

# Deferred actions reporting

In the automated report over a period (sprint/quarter/arbitrary), the following should be noted

## High level

1. In case of criticality assigned
    1. What are the most critical 10 impacts accepted?
    2. What are the most critical 10 impacts in progress?
    3. What is the action that spawned the most critical deferred action?
2. How many multipliable problems was accepted?
3. What is the action that spawned the most deferred actions?
4. How many actions out of all spawned deferred actions?
5. What is the total difference in current ↔ initial estimation in the deferred actions that are done?
6. What is the estimation value of the actions in progress?
7. If there’s won’t do/not needed
    1. What is the estimation value of the actions ‘won’t do’
    2. What is the estimation value of the actions ‘not needed’ → positive metric because it’s changes not needed that might have been taken

## Low-level

1. What impacts are currently in progress as deferred (not closed and not accepted)?
2. What impacts are currently accepted forever during this period? (accepted as won’t do if there’s this optional)