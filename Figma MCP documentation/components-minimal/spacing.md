# Spacing

## Overview
The Nova spacing system is based on an 8px grid, providing a consistent scale for margins, padding, and gaps. This ensures visual rhythm and hierarchy across the design system.

## Spacing Scale
The scale ranges from `2px` to `64px`, with each value available as a design token.

| Token                  | Value | Multiplier | Purpose                       |
| ---------------------- | ----- | ---------- | ----------------------------- |
| `nova/spacing/slight`  | 2px   | 0.25×      | Minimal gaps (e.g., between icons) |
| `nova/spacing/next`    | 4px   | 0.5×       | Small gaps, internal spacing  |
| `nova/spacing/tight`   | 8px   | 1×         | Base unit, standard component gaps |
| `nova/spacing/close`   | 12px  | 1.5×       | Close proximity spacing       |
| `nova/spacing/near`    | 16px  | 2×         | Default margins and padding   |
| `nova/spacing/related` | 24px  | 3×         | Spacing for related sections  |
| `nova/spacing/breathe` | 32px  | 4×         | Clear visual separation       |
| `nova/spacing/separate`| 48px  | 6×         | Strong separation for different items |
| `nova/spacing/distant` | 64px  | 8×         | Maximum separation for unrelated sections |

## Usage Guidelines

### Best Practices
-   **Use Tokens:** Always use the provided spacing tokens instead of hardcoding values.
-   **Hierarchy:** Use closer spacing for more related elements and larger spacing for less related ones.
-   **Consistency:** Apply the same spacing for similar components and layouts to maintain a consistent visual rhythm.
-   **Semantic Naming:** The token names (e.g., `near`, `distant`) are intended to communicate the relationship between elements.

### Common Applications
-   **Internal Component Spacing:** `tight` (8px) to `close` (12px).
-   **Related Elements (e.g., form fields):** `near` (16px) to `related` (24px).
-   **Section Separation:** `breathe` (32px) to `separate` (48px).
-   **Major Page Divisions:** `distant` (64px).

## Accessibility
Consistent and adequate spacing improves readability and helps users with cognitive or visual disabilities to better parse and navigate content. Use spacing to create clear visual groups and a logical reading flow.