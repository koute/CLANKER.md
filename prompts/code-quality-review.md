I want you to do a thorough holistic review of the current project.
If you see a correctness issue or a missing feature which should be implemented then feel free to report it, but that is not the focus of this review.
What we want to focus on is code quality.

Examples of some things to look out for:
  - Are there any places in the code where the same information is maintained in multiple places, and could be unified? (i.e. prefer to have a single source of truth)
  - Are there any places in the code where the same/similar code is maintained in multiple places, and could be unified? (i.e. a check for X in multiple places should be unified so that the check is done only in a single place)
  - Are there any places in the code where invalid states are representable? (for example, we have an enum `Entry::CreateNode` which contains `kind: NodeKind::{File, Directory}, bytes: &[u8]`, so `bytes` is nonsense when kind is a directory)
  - Are there any places in the code where a layering violation happens? (i.e. high level business logic *directly* checks low-level detais which should have been abstracte away with a method call)
  - Are there any fields or parameters which use raw, primitive types, but could be better served by a newtype, either to validate correctness, or for readability?
  - Are there any objects/structs which devolved into a "ball of mud" with many fields/methods, which could be split?
  - Are there any parts of the code which could benefit from refactoring it in a layered fashion? That is: instead of growing an existing single object, split it by layering/composing multiple objects on top?
  - Are there any pairs of modules which are closely entangled with each other's internals and could use a refactoring to use a proper interface between them?
  - Are there any modules which accrued functionality over time, became a "ball of mud", and which should be split into multiple modules?
  - Are there any parts of the codebase which could benefit from being split into multiple crates?
  - Are there any parts of the code which could be rewritten without any loss of functionality while becoming simpler?
  - Are there any opportunities to reduce code bloat? Less code the better.
