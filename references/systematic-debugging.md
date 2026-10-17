# Systematic Debugging Reference

## The Iron Law of Debugging
```
NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST
```
Never guess or apply superficial symptom patches. Guessing creates compounding bugs and hidden regressions.

---

## The 4-Phase Debugging Process

### Phase 1: Root Cause Investigation
1. **Full Trace Dissection**:
   - Read the complete error message, error codes, and full stack trace.
   - Pinpoint the exact line number, file path, and runtime context.
2. **Reproduce Consistently**:
   - Establish the exact minimal steps or test case that triggers the failure 100% of the time.
3. **Trace the Data Flow**:
   - Check where valid state transforms into invalid state.
   - Verify inputs, variable bounds, nullability, and asynchronous timing.
4. **Hypothesis Verification**:
   - Formulate a falsifiable hypothesis explaining why the error occurs. Test the hypothesis before writing fix code.

### Phase 2: Targeted Solution Design
- Identify the single cleanest architectural point of correction.
- Ensure the fix addresses the root mechanism rather than masking symptoms with null checks or exception suppression.

### Phase 3: Minimal Implementation
- Implement the smallest clean diff that resolves the issue.
- Avoid incidental changes or unrelated refactoring in the fix commit.

### Phase 4: Regression Proofing
- Verify that previous passing test cases still pass.
- Write a new regression test specifically designed to prevent this issue from recurring.
