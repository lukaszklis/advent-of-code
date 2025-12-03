# Advent of Code

My solutions for Advent of Code, written in TypeScript.

## Setup

This project uses `pnpm` for dependency management.

```bash
pnpm install
```

## Project Structure

```text
.
├── src/
│   ├── day01/
│   │   ├── solution.ts
│   │   ├── solution.test.ts
│   │   ├── README.md
│   │   ├── input1.txt (not tracked in git)
│   │   ├── input2.txt (not tracked in git)
│   │   ├── expectation1.txt (not tracked in git)
│   │   └── expectation2.txt (not tracked in git)
│   ├── day02/
│   │   ├── solution.ts
│   │   ├── solution.test.ts
│   │   ├── README.md
│   │   ├── input1.txt (not tracked in git)
│   │   ├── input2.txt (not tracked in git)
│   │   ├── expectation1.txt (not tracked in git)
│   │   └── expectation2.txt (not tracked in git)
│   └── ...
└── ...
```

## Adding New Days

To add a new day, use the `generate-day` script:

```bash
pnpm generate-day <dayNumber>
```

For example, to generate day 2:

```bash
pnpm generate-day 2
```

This will create a new folder `src/day02/` with:

- `solution.ts` - Template for your solution functions (`part1` and `part2`)
- `solution.test.ts` - Test file template
- `README.md` - Empty file where you can paste the problem descriptions for part 1 and part 2
- `input1.txt` - Empty file for part 1 input (not tracked in git)
- `input2.txt` - Empty file for part 2 input (not tracked in git)
- `expectation1.txt` - Empty file for part 1 expectation (not tracked in git)
- `expectation2.txt` - Empty file for part 2 expectation (not tracked in git)

After generating a day, you can:

1. Paste the problem descriptions into `README.md`.
1. Add your input data to `input1.txt` and `input2.txt`.
1. Implement your solution in `solution.ts`.
1. Update the expected values in `expectation1.txt` and `expectation2.txt`.
1. Run the tests with `pnpm test` to see if your solution is correct.

## Scripts

- `pnpm generate-day <dayNumber>` - Generate a new day folder with template files (e.g., `pnpm generate-day 2`)
- `pnpm test` - Run tests with Vitest
- `pnpm test:watch` - Run tests in watch mode
- `pnpm lint` - Lint code with Oxlint
- `pnpm format` - Format code with Prettier
- `pnpm format:check` - Check code formatting

## GitHub Actions

This repository includes a GitHub Actions workflow (`.github/workflows/check.yaml`) that automatically runs on pull requests and pushes to the `main` branch. The workflow:

- Runs the linter (`pnpm lint`)
- Checks code formatting (`pnpm format:check`)
- Validates that test files have not been changed to contain hardcoded answers

### Enabling Required Status Checks

To enforce that all checks pass before merging pull requests:

1. Go to your repository **Settings**
1. Navigate to **Rules** → **Rulesets**
1. Click **New ruleset** → **New branch ruleset**
1. Configure the ruleset name and target branches (e.g., `main`)
1. Enable **Require status checks to pass**
1. Click **Show additional settings**
1. Under **Status checks that are required**, click **Add checks**
1. Type `check` and select the **check** action
1. Click **Save changes**

## Excluded Files

- Input files (`input*.txt`)
- Expectation files (`expectation*.txt`)

> Why do we exclude these files from git?

AoC is all about the mystery about problems, inputs, and the final answers. Since I don't want to give away the answers,
I want to keep the mystery alive.
