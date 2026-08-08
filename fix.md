---
description: Fix issues properly - no patches, no shortcuts, no regressions
---

## Context

```text
$ARGUMENTS
```

## Fixing Philosophy

**No half measures.** Every fix must be complete and correct.

### Principles

1. **Understand before fixing** - Read the code, trace the flow, identify root cause
2. **Fix the cause, not the symptom** - No band-aids, no workarounds, no "good enough"
3. **Rewrite if necessary** - Bad code deserves replacement, not patching
4. **TDD when appropriate** - Write failing test first, then fix, then verify green
5. **Zero regressions** - Run existing tests, don't break what works
6. **Clean as you go** - If you touch it, leave it better than you found it

### Anti-patterns to Avoid

- Adding flags to bypass broken logic
- Wrapping bad code in try-catch
- Commenting out problematic code
- Adding TODO for "later"
- Special-casing edge cases without fixing core issue
- Copy-pasting fixes across similar code

### Process

1. **Reproduce** - Confirm the issue exists
2. **Diagnose** - Find root cause (not just where it crashes)
3. **Test first** - Write test that captures the bug (if testable)
4. **Fix properly** - Address root cause, rewrite if needed
5. **Verify** - Run tests, check no regressions
6. **Clean up** - Remove dead code, update comments if needed

### When to Rewrite vs Patch

**Rewrite when:**
- The existing code is fundamentally flawed
- Patching would add complexity
- The fix requires understanding fragile logic
- Similar bugs have occurred in this code before

**Patch only when:**
- The code is sound but has a small oversight
- The fix is isolated and obvious
- Rewriting would introduce unnecessary risk
