# React Native Dimensions API Undefined Issue

This repository demonstrates a common issue in React Native applications where using the `Dimensions` API to retrieve screen dimensions results in `undefined` values during the initial render.

The `DimensionsBug.js` file showcases the problem. The `DimensionsBugSolution.js` file demonstrates the solution, which involves using the `useEffect` hook with an empty dependency array to ensure the dimensions are fetched once the component is mounted and the native modules have initialized.

## Setup

1. Clone this repository.
2. Navigate to the project directory: `cd react-native-dimensions-undefined`
3. Run `npm install` or `yarn install` to install dependencies.
4. Run `npx react-native run-android` or `npx react-native run-ios` to start the app.

## Problem and Solution Explained

The root cause is that the `Dimensions` API requires the native modules to be ready before accurate dimensions can be obtained. Using the `useEffect` hook with an empty dependency array ensures that the `Dimensions.get` function is only executed once after the initial render and when dimensions are available.