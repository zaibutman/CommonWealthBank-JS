# Task 3: Backend-Frontend Integration

## Objective

Connect the frontend icon selection to the backend PUT request for persistence.

## Integration Points

### 1. API Client (types.ts)
The Goal interface with icon support is shared between frontend and backend:

```typescript
export interface Goal {
  id: string
  name: string
  targetAmount: number
  balance: number
  targetDate: Date
  created: Date
  accountId: string
  transactionIds: string[]
  tagIds: string[]
  icon?: string  // New field added in Task 2
}
```

### 2. Goal Manager Component (GoalManager.tsx)
Handles the complete flow when icon is selected:

```typescript
// Icon selection triggers three actions:
const onEmojiSelect = (emoji: BaseEmoji, event: React.MouseEvent) => {
  event.stopPropagation()
  const selectedIcon = emoji.native

  // 1. Update local state
  setIcon(selectedIcon)
  setIsEmojiPickerOpen(false)

  // 2. Update Redux state
  const updatedGoal: Goal = {
    ...props.goal,
    icon: selectedIcon,
  }
  dispatch(updateGoalRedux(updatedGoal))

  // 3. Persist to backend API (key integration point!)
  updateGoalApi(props.goal.id, updatedGoal)
}
```

### 3. Other Update Handlers
All field changes also include icon in the update payload:

```typescript
// Name change
const updateNameOnChange = (event) => {
  const updatedGoal: Goal = {
    ...props.goal,
    name: nextName,
    icon: icon ?? props.goal.icon,  // Icon is now part of updates
  }
  dispatch(updateGoalRedux(updatedGoal))
  updateGoalApi(props.goal.id, updatedGoal)  // PUT request!
}
```

## What Makes This Integration

1. **Real-time Sync**: Icon changes persist immediately
2. **State Consistency**: Redux and API stay in sync
3. **Error Handling**: Updates flow through established patterns
4. **Type Safety**: TypeScript ensures correct data structure

## Files Included (from Task 2)

The integration is implemented within the existing frontend components:
- `../../Task-2-Frontend/types.ts` - Shared interface definition
- `../../Task-2-Frontend/GoalManager.tsx` - Update handlers with API calls
- `../../Task-2-Frontend/GoalCard.tsx` - Displays persisted icon

## How It Works

```
User selects emoji
    ↓
onEmojiSelect() called
    ↓
Icon set in local state
    ↓
Dispatch Redux action (update UI)
    ↓
Call updateGoalApi() with new goal
    ↓
Backend PUT /api/goals/{id}
    ↓
MongoDB updated with new Icon field
    ↓
Icon persists through refresh
```

## Testing the Integration

To verify the integration works:

1. **Frontend Test:**
   - Navigate to a goal
   - Click the icon area to open emoji picker
   - Select an emoji
   - Icon should update immediately

2. **Backend Verification:**
   - Check MongoDB that the goal now has an `Icon` field
   - Make another change (name, amount, etc.)
   - Verify icon still present in the update

3. **Refresh Test:**
   - Refresh browser
   - Icon should still display (was persisted to DB)

## Common Issues

**Issue:** Icon doesn't change
**Fix:** Check that updateGoalApi is being called with correct params

**Issue:** Icon disappears after save
**Fix:** Ensure icon field is included in the update payload

**Issue:** API call fails
**Fix:** Check that Goal.id and Goal.UserId are both populated

## Key Files for Investigation

- `src/api/lib.ts` - API client implementation
- `src/store/goalsSlice.ts` - Redux slice for goals
- `CommBank-Server/Services/GoalService.cs` - Backend service
- `CommBank-Server/Repositories/GoalRepository.cs` - Data access

## Status

✅ Integration complete and working
✅ Ready for submission
✅ Task 3 objectives met