# GitHub CodeQL Overview

## Where CodeQL Fits

CodeQL is a semantic code analysis tool that can identify security issues by analysing source code as structured data. It fits naturally into GitHub-based development workflows and can run on pull requests, branches, and scheduled scans.

CodeQL is most useful when teams want SAST integrated close to code review.

## Practical Use Cases

- identify injection and unsafe data flow patterns
- review pull requests for security-relevant changes
- run scheduled scans across repositories
- support custom security queries for repeated patterns
- provide developers with findings in the GitHub workflow

## Engineering Considerations

CodeQL can be powerful because it reasons about code structure and data flow, but findings still need human review. Security engineers should validate whether the affected path is reachable, exposed, and relevant to sensitive data or privileged operations.

## Practical Summary

CodeQL is GitHub-native SAST that helps teams detect risky source code patterns during development. It is valuable for pull request review and scalable code analysis, especially when findings are triaged with business and architectural context.
