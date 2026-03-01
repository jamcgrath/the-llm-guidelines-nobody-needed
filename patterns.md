# Clean Code Pattern Guidelines

Every piece of code you write must align with the following principles: Clean Code, Separation of Concerns and Critical Path Management. You will also need to pay specific attention to naming. 

## Core Principles

### Clean Code

- Write self-documenting code

- Keep functions small and focused on single tasks

- Single Responsibility: Functions and classes should do one thing well. 
  - Split complex functions into smaller, focused units.

- Clear Naming: Use descriptive names for variables, functions, and classes that reveal their purpose without external context.

- DRY (Don't Repeat Yourself): Abstract common functionality into reusable modules.

- Consistent formatting

- Avoid Magic Values: Replace hardcoded values with named constants.

- Avoid private (#) fields, functions, variables, methods, and static class members. 
  - Use standard properties and module exports for encapsulation.

- Avoid tight coupling - components should work independently. 
  - Use props/events and state management for communication.


### Separation of Concerns

- Isolate business logic from UI
- Split complex components
- Use stores for shared state
- Separate styling from logic
- Extract reusable utilities

### Critical Path in code problem solving and troubleshooting 

Component Dependencies:

- Frontend: Parent-child relationships, global state/Svelte stores, third-party libraries
- Backend: API dependencies, microservice interactions, shared utilities

Critical Path Analysis:

1. System Level:
   - Maps interaction chains (Button → Store → API → UI)
   - Identify bottlenecks and failures
   - Document dependencies before changes
2. User Journey:
   - Tracks user interactions to key actions
   - Considers UI flow and system responses

Optimization Strategies:

1. Frontend:
   - Svelte 5 reactivity runes (`$state`, `$derived`) for memoization
   - Component splitting with dynamic imports
   - Svelte stores for state management
   - Keyed `{#each}` blocks for list rendering
   - Lightweight Svelte actions over heavy libraries
2. Backend:
   - Caching layers
   - Circuit breakers
   - Async communication
   - Batched database queries

Key Focus:

- Map dependency chains
- Analyze interaction steps
- Leverage Svelte's reactivity model

- Determine and understand component dependencies
- Identify blocking dependencies
- Mock APIs for parallel work
- Use feature flags
- Address blocking tech debt
- Maintain abstractions


## Naming Guidelines

### Variables and Properties

- Include domain context in names
- Avoid generic terms (type, status, value) without context
- Balance brevity with clarity, prioritizing clarity

Good:
```javascript
const articleType = "news"
const userAge = 42
const articleStatus = $state("draft")
const isPending = $derived(status === "pending")
```

Poor:
```javascript
const type = "news"
const value = 42
const status = $state("draft")  
const pending = $derived(s === "pending")
```

Exception: 

```JS
// Math variables, iterators
for(let i = 0; i < len; i++) { }
```

### Data Structures

Include parent entity in field names:

Good:
```javascript
{
  articleId: "123",
  articleType: "feature",
  articleStatus: "published"
}
```

Poor:
```javascript
{
  id: "123",
  type: "feature",
  status: "published"
}
```

### Component Structure
```Svelte
<script>
  // 1. Imports
  import { formatDate } from '../utils';
  
  // 2. Props
  const { articleId, authorId } = $props();
  
  // 3. State
  const isEditing = $state(false);
  
  // 4. Derived values
  // Clear, intention-revealing name
  const formattedPublishDate = $derived(() => formatDate(publishDate));
  
  // 5. Functions
  function handleFormSubmit() {
    // Single responsibility
    // "handleFormSubmit" clarifies the intent of this function
  }
</script>

<article class="article-card">
  <!-- Using a descriptive class name that matches its purpose -->
</article>

<style>
  /* Scoped styles */
  .article-card {
    /* ... */
  }
</style>
```
### Exceptions

- Simple loop iterators (i, j)
- Mathematical variables (x, y, z)
- Destructured properties with clear context: `const { id } = user`

## Implementation

- Apply guidelines to new code and during refactoring
- Review AI-generated code for naming clarity
- When uncertain, choose explicit naming over brevity