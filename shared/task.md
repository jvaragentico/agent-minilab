# Shared Task — Day 1

## Mission
Research one useful AI feature a small local business could deploy, then produce a simple implementation proposal.

## Workflow
1. Planner reads this mission and creates the execution plan.
2. Builder receives the plan and produces the implementation proposal.
3. Reviewer receives the original mission, Planner output, and Builder output.
4. Reviewer returns PASS or FAIL.
5. If FAIL, only the Reviewer feedback is sent back to Builder for correction, then the result is reviewed again.

## Day 1 success condition
Complete at least one full Planner → Builder → Reviewer cycle while keeping the three responsibilities separate.

## Experiment
After the normal cycle works, deliberately introduce one false factual claim into the Builder output and test whether the Reviewer detects it. Do not tell the Reviewer which statement is false.
