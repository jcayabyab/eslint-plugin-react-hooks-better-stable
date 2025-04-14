# `eslint-plugin-react-hooks-better-stable`

This ESLint plugin adds two additional options to the original `eslint-plugin-react-hooks`:

1. `knownStableValues`: If commonly-used variables are known to be stable (e.g., `dispatch` from Redux), you can specify them as RegEx.
2. `markStableValuesAsUnnecessary`: Stable values such as `set` functions returned from `React.setState` don't do anything when included in the dependency array, this allows you to enforce that they are not included in the dependency array.
3. `checkReactiveFunctionOutputIsStable`: Checks if the output of a reactive function is stable.
4. `stableHooks`: Allows specifying known stable hooks and their dependencies.

See [motivation](./MOTIVATION.md) for insight.

See [rules/exhaustive-deps.md](./docs/rules/exhaustive-deps.md) for more details around the extra options.

## Installation

```sh
# npm
npm install eslint-plugin-react-hooks-better-stable --save-dev

# yarn
yarn add eslint-plugin-react-hooks-better-stable --dev
```

Then extend the recommended eslint config and turn off the original `eslint-plugin-react-hooks/exhaustive-deps` rule:

```js
{
  "extends": [
    // ...
    "plugin:react-hooks-exhaustive-deps-better-stable/recommended"
  ],
  "rules": {
    "react-hooks/exhaustive-deps": "off"
  }
}
```

## Development

### Testing

Run `npm test` to run all tests for rules.
