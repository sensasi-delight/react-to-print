# CHANGELOG

## 2.3.1 (August 6th, 2019)

- FIX [154](https://github.com/gregnb/react-to-print/pull/154): TSLint was not working properly for the project. A configuration was added, and linting errors were fixed. While fixing linting errors, a bug was discovered whereby if a stylesheet was found that did not have tag type `STYLE` it was possible that `react-to-print` would not include all stylesheets from the page into the print window

- FIX: [154](https://github.com/gregnb/react-to-print/pull/154) (meant to be a different PR, was included by mistake in 154): When passing `removeAfterPrint` some users were getting the error `TypeError: Object doesn't support property or method 'remove'`. This was due to using an incorrect way to remove the iframe

## 2.3.0 (July 30th, 2019)

- FEATURE [152](https://github.com/gregnb/react-to-print/pull/152): Previously, this library used a window rather than an `iframe` to handle printing. That was changed some time ago, however, the `closeAfterPrint` prop was never removed from the documentation (though it was removed from the code). This release restores similar functionality, in a new `removeAfterPrint` prop. Passing this prop will ensure that `react-to-print` removes the `iframe` it uses to print from the DOM after printing (something that it currently does not do). NOTE: the `iframe` is removed after the call to `onAfterPrint` (if provided) has completed. We will likely make this the default functionality in version 3, but are keeping it like this for now to ensure anyone relying on the `iframe` does not face issues. Thanks [aviklai](https://github.com/aviklai)

## 2.2.1 (July 22nd, 2019)

- FIX [149](https://github.com/gregnb/react-to-print/pull/149): Print window would not open if `onBeforePrint` was not given. Thanks [aviklai](https://github.com/aviklai)

## 2.2.0 (July 19th, 2019)

- FEATURE [140](https://github.com/gregnb/react-to-print/issues/140): `onBeforePrint` can now optionally return a Promise. If a Promise is returned, `react-to-print` will wait for it to resolve before continuing with the print. NOTE: `react-to-print` does not handle if the Promise rejects, so this must be accounted for when using this option. Thanks [aviklai](https://github.com/aviklai)

## 2.1.3 (June 22nd, 2019)

- FIX [134](https://github.com/gregnb/react-to-print/pull/134): Solve print window issues in Safari (especially Mobile Safari), thanks [Ellenergic](https://github.com/Ellenergic)
- CHORE: Updated the README to contain a link to a fully updated demo

## 2.1.2 (May 3rd, 2019)

- FIX [118](https://github.com/gregnb/react-to-print/issues/118): Ensure fonts have time to load before printing, thanks [aviklai](https://github.com/aviklai)

## 2.1.1 (April 13th, 2019)

- FIX: Ensure we build the package as UMD instead of CommonJS ([#116](https://github.com/gregnb/react-to-print/pull/116), thanks [@aviklai](https://github.com/aviklai))
- CHORE: Added a CHANGELOG

## 2.1.0 (April 2nd, 2019)

- CHORE: Convert the package to TypeScript ([#111](https://github.com/gregnb/react-to-print/pull/111), thanks [@sergeyshmakov](https://github.com/sergeyshmakov))