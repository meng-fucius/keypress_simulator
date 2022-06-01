# keypress_simulator

[![pub version][pub-image]][pub-url] [![][discord-image]][discord-url] ![][visits-count-image] 

[pub-image]: https://img.shields.io/pub/v/keypress_simulator.svg
[pub-url]: https://pub.dev/packages/keypress_simulator

[discord-image]: https://img.shields.io/discord/884679008049037342.svg
[discord-url]: https://discord.gg/zPa6EZ2jqb

[visits-count-image]: https://img.shields.io/badge/dynamic/json?label=Visits%20Count&query=value&url=https://api.countapi.xyz/hit/leanflutter.keypress_simulator/visits

This plugin allows Flutter desktop apps to simulate key presses.

---

English | [简体中文](./README-ZH.md)

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [keypress_simulator](#keypress_simulator)
  - [Platform Support](#platform-support)
  - [Quick Start](#quick-start)
    - [Installation](#installation)
    - [Usage](#usage)
  - [Who's using it?](#whos-using-it)
  - [License](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Platform Support

| Linux | macOS | Windows |
| :---: | :---: | :-----: |
|   ➖   |   ✔️   |    ✔️    |

## Quick Start

### Installation

Add this to your package's pubspec.yaml file:

```yaml
dependencies:
  keypress_simulator: ^0.1.0
```

Or

```yaml
dependencies:
  keypress_simulator:
    git:
      url: https://github.com/leanflutter/keypress_simulator.git
      ref: main
```

### Usage

```dart
import 'package:keypress_simulator/keypress_simulator.dart';

// 1. Simulate pressing ⌘ + C

// 1.1 Simulate key down
await keyPressSimulator.simulateKeyPress(
  key: LogicalKeyboardKey.keyC,
  modifiers: [ModifierKey.metaModifier],
);

// 1.2 Simulate key up
await keyPressSimulator.simulateKeyPress(
  key: LogicalKeyboardKey.keyC,
  modifiers: [ModifierKey.metaModifier],
  keyDown: false,
);

// 2. Simulate long pressing ⌘ + space

// 2.1. Simulate key down
await keyPressSimulator.simulateKeyPress(
  key: LogicalKeyboardKey.space,
  modifiers: [
    ModifierKey.metaModifier,
  ],
);

await Future.delayed(const Duration(seconds: 5));
                
// 2.2. Simulate key up
await keyPressSimulator.simulateKeyPress(
  key: LogicalKeyboardKey.space,
  modifiers: [
    ModifierKey.metaModifier,
  ],
  keyDown: false,
);
```

> Please see the example app of this plugin for a full example.

## Who's using it?

- [Biyi (比译)](https://biyidev.com/) - A convenient translation and dictionary app.

## License

[MIT](./LICENSE)
