# base-city-celebration-yields

The difference celebrating makes to the squares a city works, as a library for a ruleset's city yield rules:

- `lib/celebrationYields`: `celebrationYields(city, government, YieldTypes, stepProviders, steps, afterSteps)`, the
  yields to add to a celebrating city. A square's own yields are worked out for a city that isn't celebrating, so for
  each of `YieldTypes` this takes what each worked square yields before the government's steps (less the yields from
  `stepProviders`), runs it through `steps(YieldType, value, government, true)` and then `afterSteps(tile)` (called
  once per square, after `tile.yields(...)`), and returns the difference, provided by `<tile id>: celebration`, or
  nothing where there is none.

The ruleset says which yield types, which providers are its steps, how its steps combine and what follows them, and
when a city counts as celebrating. A library: it registers no rules. See `civ1-city-happiness` for Civilization's.
