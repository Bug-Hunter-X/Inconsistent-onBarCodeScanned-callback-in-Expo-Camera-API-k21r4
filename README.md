# Inconsistent onBarCodeScanned callback in Expo Camera API

This repository demonstrates a bug in the Expo Camera API where the `onBarCodeScanned` callback function is not always called when a barcode is scanned. The issue is likely due to the internal state management of the `Camera` component.  This example shows the problem and a potential solution using the `useRef` hook to ensure the callback is correctly referenced.

## Bug Reproduction

1. Clone this repository.
2. Run `npm install`.
3. Run `expo start`.
4. Point the camera at a barcode.  Observe that the `onBarCodeScanned` function may not always be triggered.

## Solution

The provided solution uses the `useRef` hook to maintain a persistent reference to the `onBarCodeScanned` function, ensuring the `Camera` component always has access to the latest version of the function. This effectively resolves the inconsistent callback issue. 

## Additional Information

This issue highlights the importance of correctly managing state when working with asynchronous events and component updates in React Native.