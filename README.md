# Issues I faced

## Using VS Code

1. How do you format code in Visual Studio Code (VSCode)?
  -  On Windows Shift + Alt + F
  - On Mac Shift + Option + F
  - On Linux Ctrl + Shift + I

## Flutter

1. How to capitalize text in Flutter ?
  - `.toUpperCase()`

2. In Flutter `shared_preferences` pacakge, when using the `SharedPreferencesAsync` if we try to access a parameter that is not set it will return `null` without throwing an error.

3. How to execute somethnig `finally` in Javascript/Flutter swich-case statement?

```dart
    switch (request.type) {
      case Blockchain.ethereum:
        await ethereumWithdraw();
        break;
      case Blockchain.tron:
        await tronWithdraw();
        break;
      default:
        withdrawSuccess = false;
    }

    // On successful withdraw, clear the used tokens
    if (withdrawSuccess) {
      await clearUsedTokens();
    } else {
      throw Exception('Failed to withdraw crypto');
    }
```
