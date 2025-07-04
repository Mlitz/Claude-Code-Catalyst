# Prompt #6 V2.0: TDD Enforcement Template

**Version**: 2.0
**Last Updated**: January 2025
**Purpose**: Bulletproof TDD template ensuring test-first development with comprehensive validation

**Usage**: Use for EVERY feature implementation. Copy this template and replace [TASK_DESCRIPTION].

```
## 🎯 Development Task: [TASK_DESCRIPTION]

**STOP! TDD CHECKPOINT** 
Before proceeding, confirm:
- [ ] I will write tests FIRST
- [ ] I will NOT write implementation until tests fail
- [ ] I will verify test failures before implementing
- [ ] I understand violating TDD = task failure

Confirmed? Type "TDD CONFIRMED" to proceed.

---

## Phase 1: ANALYSIS & PLANNING (30 min)

### 1.1 Task Decomposition
Break down [TASK_DESCRIPTION] into testable components:

**Core Functionality**:
- Component 1: [What it does]
- Component 2: [What it does]
- Component 3: [What it does]

**Edge Cases**:
- Edge case 1: [Description]
- Edge case 2: [Description]

**Error Scenarios**:
- Error 1: [What could go wrong]
- Error 2: [What could go wrong]

### 1.2 Research Phase
Use MCP servers for preparation:

**Context7 Research**:
```
use context7 to find best practices for [technology/pattern]
use context7 for [library] testing examples
```

**Serena Analysis** (if modifying existing code):
```
Analyze [existing module] with Serena to understand current structure
Find dependencies with Serena in [component]
```

### 1.3 Test Strategy
Define comprehensive test plan:

**Unit Tests Required**:
- [ ] [Function/Component]: [What to test]
- [ ] [Function/Component]: [What to test]

**Integration Tests Required**:
- [ ] [API/Service]: [What to test]
- [ ] [Database/External]: [What to test]

**Test Data Requirements**:
- Mock data needed: [Description]
- Fixtures required: [Description]

---

## Phase 2: RED - WRITE FAILING TESTS (45 min)

### 2.1 Create Test File Structure
```typescript
// [component].test.ts
import { describe, it, expect, beforeEach, afterEach } from '@jest/globals';
// Import what will be tested (even if it doesn't exist yet)
import { [ComponentName] } from './[component]';

describe('[ComponentName]', () => {
  // Setup and teardown
  beforeEach(() => {
    // Test setup
  });

  afterEach(() => {
    // Cleanup
  });

  // Test suites organized by functionality
  describe('[Functionality Group]', () => {
    it('should [expected behavior]', () => {
      // Arrange
      // Act
      // Assert
    });
  });
});
```

### 2.2 Write Comprehensive Tests

**Happy Path Tests**:
```typescript
describe('Happy Path', () => {
  it('should handle normal input correctly', () => {
    // Test normal, expected usage
  });

  it('should return expected output for valid data', () => {
    // Test successful scenarios
  });
});
```

**Edge Case Tests**:
```typescript
describe('Edge Cases', () => {
  it('should handle empty input', () => {
    // Test boundary conditions
  });

  it('should handle maximum values', () => {
    // Test limits
  });
});
```

**Error Handling Tests**:
```typescript
describe('Error Handling', () => {
  it('should throw error for invalid input', () => {
    expect(() => component.method(invalid)).toThrow(ExpectedError);
  });

  it('should handle async errors gracefully', async () => {
    await expect(asyncMethod()).rejects.toThrow();
  });
});
```

### 2.3 Verify Test Failure
**CRITICAL STEP - Run tests and confirm ALL fail**:
```bash
npm test -- [test-file]
```

**Expected output**: 
- ❌ All tests should fail
- 🚫 "Cannot find module" or "undefined is not a function" errors
- ⚠️ If any test passes without implementation, the test is wrong!

**CHECKPOINT**: Type "TESTS FAILING ✅" before proceeding to implementation.

---

## Phase 3: GREEN - MINIMAL IMPLEMENTATION (45 min)

### 3.1 Create Implementation File
Write ONLY enough code to make tests pass:

```typescript
// [component].ts
// Minimal implementation - no extras!

export class [ComponentName] {
  // Only methods/properties needed for tests
}

export function [functionName]() {
  // Simplest possible implementation
}
```

### 3.2 Incremental Implementation
Make one test pass at a time:

1. Run single test: `npm test -- [test-file] -t "[test-name]"`
2. Write minimal code to pass
3. Verify ONLY that test passes
4. Commit: `git commit -m "test: add test for [feature]"`
5. Repeat for next test

### 3.3 Verify All Tests Pass
```bash
npm test -- [test-file]
```

**Required output**:
- ✅ All tests passing
- 📊 Coverage report shows high coverage
- 🎯 No implementation beyond test requirements

---

## Phase 4: REFACTOR - IMPROVE CODE (30 min)

### 4.1 Code Quality Improvements
With tests as safety net, improve code:

**Structure**:
- [ ] Extract common patterns
- [ ] Reduce duplication
- [ ] Improve naming
- [ ] Add type safety

**Performance** (if needed):
- [ ] Optimize algorithms
- [ ] Reduce memory usage
- [ ] Improve query efficiency

**Maintainability**:
- [ ] Add helpful comments
- [ ] Improve error messages
- [ ] Enhance logging

### 4.2 Continuous Verification
After EACH change:
```bash
npm test -- [test-file]  # Must still pass!
```

### 4.3 Final Quality Check
```bash
# All tests
npm test

# Linting
npm run lint

# Type checking
npm run type-check

# Coverage
npm run test:coverage
```

---

## Phase 5: INTEGRATION - CONNECT TO SYSTEM (30 min)

### 5.1 Integration Points
Connect new code to existing system:

- [ ] Wire up to routes/controllers
- [ ] Add to dependency injection
- [ ] Update configuration
- [ ] Modify database schema (if needed)

### 5.2 Integration Tests
```typescript
// [feature].integration.test.ts
describe('[Feature] Integration', () => {
  it('should work with real dependencies', async () => {
    // Test with actual services
  });

  it('should handle system errors', async () => {
    // Test failure scenarios
  });
});
```

### 5.3 Manual Testing
- [ ] Start application: `npm run dev`
- [ ] Test via UI/API client
- [ ] Verify logs are correct
- [ ] Check error handling

---

## Phase 6: DOCUMENTATION & COMMIT (15 min)

### 6.1 Code Documentation
Add comprehensive documentation:

```typescript
/**
 * [Brief description]
 * 
 * @param {Type} param - Parameter description
 * @returns {Type} Return value description
 * @throws {ErrorType} When this error occurs
 * 
 * @example
 * ```typescript
 * const result = myFunction(input);
 * ```
 */
```

### 6.2 Update Project Documentation
- [ ] Update API documentation
- [ ] Add to changelog
- [ ] Update README if needed
- [ ] Document in work-journal.md

### 6.3 Git Commit
Create atomic, meaningful commits:

```bash
# Stage changes
git add -p  # Review each change

# Commit with descriptive message
git commit -m "feat([scope]): implement [feature] with TDD

- Write comprehensive test suite first
- Implement minimal code to pass tests  
- Refactor for clarity and performance
- Add integration with [system]

Test coverage: XX%
All tests passing"
```

---

## Phase 7: COMPLETION CHECKLIST

### Technical Validation
- [ ] All tests written FIRST and initially failed
- [ ] 100% of new code is tested
- [ ] Full test suite passes
- [ ] Code coverage maintained/improved
- [ ] No linting errors
- [ ] Type checking passes
- [ ] Integration tests pass

### Process Validation  
- [ ] TDD process followed strictly
- [ ] Code follows project conventions
- [ ] Documentation updated
- [ ] Changes committed atomically
- [ ] Work journal updated
- [ ] Todo.md updated

### MCP Server Usage
- [ ] Context7 used for research
- [ ] Serena used for analysis (if applicable)
- [ ] Filesystem used for all file operations
- [ ] GitHub for version control
- [ ] Memory updated with insights

### Final Confirmation
Type: "✅ TDD TASK COMPLETE - All validations passed"

---

## 🚨 FAILURE RECOVERY

If TDD process breaks down:

### Test Failures After Implementation
1. STOP immediately
2. Delete implementation code
3. Fix tests
4. Start implementation again

### Coverage Decrease
1. Write missing tests
2. Verify new tests fail without code
3. Update implementation

### Integration Failures
1. Write integration test that captures failure
2. Fix implementation
3. Verify all tests pass

---

## 📋 Session Notes

**Challenges Encountered**:
[Document any difficulties]

**Decisions Made**:
[Document architectural choices]

**Lessons Learned**:
[What worked well or poorly]

**Future Considerations**:
[Related work needed]

---

Remember: The goal isn't just working code - it's well-tested, maintainable, documented code that the team can confidently modify in the future.
```