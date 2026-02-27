# Admin Use Case Diagram (Markdown Preview)

## AI-Enhanced Quiz Management System

```mermaid
flowchart LR
	%% Actors
	PU["Primary User"]
	A["Admin"]

	%% System Boundary
	subgraph SYS["AI-Enhanced Quiz Management System"]
		L(["Login / Authenticate"])
		T(["Two-Factor Authentication"])
		R(["Reset Password"])
		P(["Manage Profile"])

		U(["Manage User Accounts"])
		C(["Manage Courses / Categories"])
		S(["Monitor System Security"])
		V(["View Audit Logs"])
		G(["Generate Global Analytics"])
	end

	%% Generalization (Actor inheritance)
	PU -. generalization .-> A

	%% Actor Associations
	A --> L
	A --> P
	A --> U
	A --> C
	A --> S
	A --> G

	%% UML-style Relationships
	T -. "extend" .-> L
	R -. "extend" .-> L
	S -. "include" .-> V
```

### Legend
- `include`: Mandatory sub-use-case.
- `extend`: Optional/conditional behavior.
- `generalization`: Admin inherits common behavior from Primary User.