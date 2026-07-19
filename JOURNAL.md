## Week 7 — Issue selection

**Issue link:** [https://github.com/ascherj/pathreview/issues/71]

**Issue title:** [Implement a red-teaming test suite for the prompt injection defense]

**Tier:** [ ] Tier 1  [ ] Tier 2  [X] Tier 3

**Selection rationale:**
I selected this issue because it is a critical security vulnerability that needs to be addressed. I work as a security engineer and am interested in how AI/ML can be used to improve security processes. Prompt injection is also a major concern for most companies. I worked through the checklist and meet most of the criteria for Tier 3. I understand the issue, can explain it, and understand what "done" looks like. I have contributed to large codebases before and am comfortable working with unfamiliar codebases. I'm confident I can understand the relevant files and make changes without breaking functionality. The cohort ledger claims look fine (I was first to claim this issue) and the scope is realistic for 1-2 weeks.

**Problem summary:**
[In 3–5 sentences, in your own words: what the issue is (not a copy-paste of
the title), what is currently broken or missing, and what a successful fix
would accomplish. Naming the part of the codebase it affects is helpful context.]

The application currently lacks automated verification to ensure prompt injection defenses (safety/prompt_defense.py) remain effective against malicious inputs. To address this missing test coverage, we need to implement a dedicated red-teaming test suite that attempts automated prompt injection attacks against the safety layer.

A successful fix will introduce these automated tests and integrate them into the CI pipeline, guaranteeing they will always run on every pull request that touches safety/.

This implementation will add a new automated prompt injection script to tests/security/test_prompt_injection.py and utilize curated prompt injection attack payloads from tests/fixtures/injection_attempts/.

There are related issues that are not in scope for this change to add the integration tests to the safety layer (Issue #75 - tests/integration/test_safety_middleware.py) and to sanitize user provided newline characters (Issue #64 - safety/prompt_defense.py).

**Branch name:** [https://github.com/daianx/pathreview/tree/feat/71-implement-prompt-injection-test-suite]

**Setup confirmation:** [X] App runs locally at localhost:5173

**Cohort ledger:** [X] Issue added to cohort ledger
