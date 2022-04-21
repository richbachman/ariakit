# ariakit

## 2.0.0-next.23

### Major Changes

- Dropped support for React 16. ([#1225](https://github.com/ariakit/ariakit/pull/1225))

  The package may still work with React 16.8, but we're not testing the codebase against this version anymore. Upgrade to React 17 or higher to guarantee that your app works with Ariakit.

- Dropped support for `auto`, `auto-start` and `auto-end` placements on `usePopoverState` and derived state hooks. ([#1229](https://github.com/ariakit/ariakit/pull/1229))
- Replaced `defaultAnchorRect`, `anchorRect` and `setAnchorRect` props on `usePopoverState` by a single `getAnchorRect` prop. ([#1252](https://github.com/ariakit/ariakit/pull/1252))

  Before:

  ```js
  const popover = usePopoverState();

  // inside an effect or event handler
  popover.setAnchorRect({ x: 10, y: 10 });
  ```

  After:

  ```js
  const popover = usePopoverState({ getAnchorRect: () => ({ x: 10, y: 10 }) });
  ```

- The `padding` prop has been renamed to `overflowPadding` on `usePopoverState` and derived state hooks. ([#1229](https://github.com/ariakit/ariakit/pull/1229))

  ```diff
    const popover = usePopoverState({
  -   padding: 4,
  +   overflowPadding: 4,
    });
  ```

- The `shift` and `gutter` props on `usePopoverState` and derived state hooks don't support string values anymore. Now only numbers are supported. ([#1229](https://github.com/ariakit/ariakit/pull/1229))
- The `preventOverflow` prop has been renamed to `slide` on `usePopoverState` and derived state hooks. ([#1229](https://github.com/ariakit/ariakit/pull/1229))

  ```diff
    const popover = usePopoverState({
  -   preventOverflow: false,
  +   slide: false,
    });
  ```

### Minor Changes

- The `setValueOnClick` prop from `ComboboxItem` now also supports a function that receives the click event and returns a boolean value.
- Added `setValueOnChange` prop to `Combobox`.
- Added `setValueOnClick` prop to `Combobox`.
- Added `fitViewport` prop to `usePopoverState` and derived state hooks. ([#1229](https://github.com/ariakit/ariakit/pull/1229))
- Added `overlap` prop to `usePopoverState` and derived state hooks. ([#1229](https://github.com/ariakit/ariakit/pull/1229))

### Patch Changes

- Fixed `Combobox` with `autoSelect` and `autoComplete="both"` props setting an incorrect value when there are no matches. ([#1219](https://github.com/ariakit/ariakit/pull/1219))
- Fixed `useDisclosureState` reading from a mutating ref on the render phase. ([#1224](https://github.com/ariakit/ariakit/pull/1224))
- Fixed extra re-renders on `FormField`, `FormInput`, `FormCheckbox` and `FormError` components when they have been touched.
- Fixed a bug where quickly hovering over nested `Hovercard` components right after they were mounted would cause the parent and the nested `Hovercard` to hide. ([#1229](https://github.com/ariakit/ariakit/pull/1229))
- Fixed how the "transit polygon" is shaped on `Hovercard` to make it easier to hover over adjacent elements. ([#1240](https://github.com/ariakit/ariakit/pull/1240))
- Fixed types for `@types/react` v18. ([#1222](https://github.com/ariakit/ariakit/pull/1222))
- Updated dependencies: `ariakit-utils@0.17.0-next.16`.

## 2.0.0-next.22

### Minor Changes

- Published packages with the `next` tag. ([#1213](https://github.com/ariakit/ariakit/pull/1213))

### Patch Changes

- Updated dependencies: `ariakit-utils@0.17.0-next.15`.