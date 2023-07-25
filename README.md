# Travelpass Frontend Style Guide

## Types

1. When exporting `types` and `interfaces`, export them as `types`.

## Variable naming

1. Prefer descriptive names over short names.

   > **Example**: in a component called HomeHeroCard, `homeHeroCardCameraIconWrapperCss` would be better than `homeHeroCardCameraCss`.

2. In child components, variable names should include the full component name to differentiate it from its parent.

   > **Example**: HomeHeroCard is a child of HomeHero, so `homeHeroCardCameraIconWrapperCss` would be better than `cameraIconWrapperCss`.

## Pull request etiquette

1. Keep PRs under 100 lines when possible. Large PRs can be chunked into smaller ones by creating a new branch with the same name as the original with `-part-n` appended to the end.

2. When posting to `#eng-frontend-reviews` on Slack, the format should be:
   > `{URL} {Branch name} {Short description}`.

## Code and functions

1.  **Do not duplicate code whenever possible.**

2.  If inline logic (e.g. anonymous functions, ternaries) is longer than one line, extract it to a named function.

    > Example TBD

3.  Avoid nested ternaries. Use functions for complicated logic.

        Bad

        const isHidden = isInMiddle
        ? index < currentSlide - 2 || index > currentSlide + 2
        : currentSlide < 2
        ? index > 4
        : index < totalItems - 5

        Good

        const isHidden = isInMiddle
        ? index < currentSlide - 2 || index > currentSlide + 2
        : leftOrRight()
