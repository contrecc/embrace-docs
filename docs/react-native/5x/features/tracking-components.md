---
title: Tracking Components
description: Track the mounting and unmounting of React Components for your React Native application using the Embrace SDK
sidebar_position: 2
---

# Tracking Components

By default, Embrace will track native views.
If you'd like to track when a React component is mounted and unmounted, you can do so with the `startView` and `endView` functions.

These methods are flexible, so it's up to you as a developer to define when a view "starts" and "ends".
Perhaps it's when a component is mounted and unmounted, or maybe it's when a style is applied that makes the component visible or not visible to the user.

```javascript
import {startView, endView} from '@embrace-io/react-native';

startView('MyView');

endView('MyView');
```  

There's also a `logScreen` function available, which will log a breadcrumb with the name of the component.
This could be helpful as a lightweight option to breadcrumb which components were visible if you don't care about the duration the component was visible for.
In most cases it's recommended to use `startView` and `endView`.

```javascript
import {logScreen} from '@embrace-io/react-native';

// This will add a breadcrumb to the session with the following format: "Opening screen [MyView]".
logScreen('MyComponent'); 
```
