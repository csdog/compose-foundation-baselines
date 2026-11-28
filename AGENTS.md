# AGENTS.md — Compose Foundation baselines

This repository holds the approved platform screenshots and pins the upstream shadcn visual references through the `shadcn/` Git submodule used by [Compose Foundation](https://github.com/csdog/compose-foundation). Start with [the screenshot index](Index.md).

## shadcn visual references

Initialize the reference checkout with `git submodule update --init -- shadcn`. Capture changes in [the shadcn-baselines repository](https://github.com/csdog/shadcn-baselines).

- Work through one component at a time. Inspect the pinned upstream Base UI examples for variants and states. Include the applicable states, such as expanded menus, disabled items, selected tabs, and filtered or empty lists. Record gaps in the component index.
- Capture a light and dark pair. Save the PNGs in `shadcn/<component>/` using `<component>-<variant>-<state>-<theme>.png`. Keep the example URL, source revision, example style, and any interaction steps with the images. Record the source index revision separately if the hosted deployment does not expose its revision.
- Update the component and root indexes in the reference repository. Group screenshot changes by component and open a PR there. After it merges, fetch and check out the approved commit in `shadcn/` and submit the updated submodule pointer in a PR here.

## Platform screenshot baselines

- Run **Component parity** with `update=review` in the Compose Foundation source repository. Review the platform candidates alongside matching shadcn references in `component-parity-shadcn-review-*` and check the index patch when one is available.
- After the source PR is approved and merged, the maintainer runs `update=publish` from the source repository's `main` for the same component scope. That workflow recaptures the approved cases and brings the validated PNGs and updated platform indexes into this repository. Follow [the source workflow](https://github.com/csdog/compose-foundation/blob/main/.github/workflows/component-parity.yml) for the current artifact and publication steps.
- Platform pixel regression compares each new capture with the approved screenshot for that same platform. The shadcn reference guides visual review across platforms. Preserve existing provenance when updating either set of screenshots.
