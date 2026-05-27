# Open Source Contributions

Technical notes from open source contributions across multiple ecosystems.

This repository documents pull requests delivered to real open source projects. The goal is to make the work easy for technical recruiters and maintainers to scan: what problem was solved, why the change mattered, and which engineering judgment was involved.

## Structure

Each ecosystem has its own directory. Inside each ecosystem, notes are grouped by project.

```text
dotnet/
  mudblazor/
    pr-13244-rating-mobile-width.md
php/
  symfony/
    pr-64359-svg-dimension-validation.md
founder-led-projects/
  pr-maven-cli/
    README.md
```

## Note Format

Each note is intentionally concise:

- focus area and contribution type;
- links to the official pull request and related issue;
- short summary of the problem;
- technical value of the contribution;
- key implementation and learning points.

Mutable status fields such as review state or CI state are intentionally omitted. The official pull request remains the source of truth for current status, discussion, validation details, and merge history.

## Ecosystems

- [.NET](dotnet/README.md) - 3 contributions
- [Elixir](elixir/README.md) - 1 contribution
- [Go](go/README.md) - 4 contributions
- [iOS](ios/README.md) - 2 contributions
- [Java](java/README.md) - 13 contributions
- [JavaScript](javascript/README.md) - 10 contributions
- [Kotlin](kotlin/README.md) - 6 contributions
- [PHP](php/README.md) - 5 contributions
- [Python](python/README.md) - 18 contributions
- [Ruby](ruby/README.md) - 15 contributions
- [TypeScript](typescript/README.md) - 15 contributions

## Founder-Led Open Source Projects

These projects are documented separately from third-party OSS contributions because my role is founder or maintainer, not only external contributor.

- [PR Maven CLI](founder-led-projects/pr-maven-cli/README.md) - Founder-Led Project

## Additional Technical Explorations

A focused set of [technical explorations](technical-explorations/README.md) is kept separately from the main contribution notes. These records document useful OSS investigation and iteration while leaving the official pull request as the source of truth.
