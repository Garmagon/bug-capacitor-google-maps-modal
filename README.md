# Bug example of capacitor-google-maps and ionic modal on iOS

## Bug description

After a modal is opened while having an inicialized map, the map will not work anymore, the map area becomes scrollable and the only way to fix is app restart.

## Prerequisites

You will need an API key to be able to run the app on iOS.

Go to `/src/components/BaseMap.vue` and insert the api key into the `<GOOGLE_MAPS_API_KEY>` area of `createMap` function.

For more information on setup check out [the docs](https://capacitorjs.com/docs/apis/google-maps#api-keys).

## App setup

The app is installed with `ionic start` with locally installed ionic version `7.2.0`. The following options was chosen:

1. Framework: Vue
2. Starter template: sidemenu

Then added capacitor google maps following the [docs](https://capacitorjs.com/docs/apis/google-maps)

## Installation

After cloning run:

```bash
npm install
```

then go to `/ios/App` run:

```bash
pod install
```

then run build, sync and open xcode:

```bash
npm run build && ionic cap sync && ionic cap open ios
```

## Reproduction

(The app should open by default on `/` route, but if not navigate to `/` route)

1. In XCode, select signing, and run the app (I was running it on iPhone 15 with iOS version 17.4)

2. Click on the button `Open map`, the map will appear.

3. Then click on button `Modal`, the modal will open.

4. After closing the modal, the map is unusable.
