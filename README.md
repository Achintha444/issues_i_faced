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

4. When need to show `double` in the given number of decimal places. We can use `toStringAsFixed`

```dart
  1.toStringAsFixed(3);  // 1.000
  (4321.12345678).toStringAsFixed(3);  // 4321.123
  (4321.12345678).toStringAsFixed(5);  // 4321.12346
  123456789012345.toStringAsFixed(3);  // 123456789012345.000
  10000000000000000.toStringAsFixed(4); // 10000000000000000.0000
  5.25.toStringAsFixed(0); // 5
```

5. `popUntil()` equivalent in GoRouter. For this we can use `go` or `goNamed`

```dart
  GoRouter.of(context).go(
   Routes.user,
   extra: "1234",
  );
```

6. How do I add a bullet or create a bulleted list in flutter ?

```dart
Text('\u2022 Bullet Text')
```

If you want to convert a list of strings to a bulleted list.

```dart
...data.details.benefits.map(
  (benefit) => Text('\u2022 ${benefit}'),
  ),
),
```

7. How to align `WidgetSpan` to the `TextSpan` according to the letters ?
```dart
    TextSpan(
        text: sprintf(
          AppLocalizations.of(context)!.switchAuthTypesText1,
          [currentAuthType.value],
        ),
        style: AppTextStylePrimary.body1r.textPrimary,
        children: [
          WidgetSpan(
            alignment: PlaceholderAlignment.baseline,
            baseline: TextBaseline.alphabetic,
            child: InkWell(
              onTap: () => {
                context.read<SendConfirmationVerifyOtpBloc>().add(
                      SendConfirmationVerifyOtpSwitchAuthType(
                        authType: nextAuthType,
                      ),
                    ),
              },
              child: Text(
                nextAuthType.value,
                style: AppTextStylePrimary.link1r.textLink,
              ).paddingOnly(top: 2),
            ),
          ),
          TextSpan(
            text: AppLocalizations.of(context)!.switchAuthTypesText2,
          ),
        ],
      ),
```
using `PlaceholderAlignment.baseline` and `TextBaseline.alphabetic`.

## Tailwind

1. Tailwind CSS responsive breakpoint overrides not working ?

Every time you design something with Tailwind, start from mobile.

```
<div class="text-center sm:text-left">
  Lorem ipsum dolor sit amet.
</div>
```
  So basically on this example. Instead of saying:

    Text should be centered only on smaller devices.

  Do this:

    Text should be always centered, and aligned left for bigger devices

2. Tailwind breakpoints

```
sm	40rem (640px)	@media (width >= 40rem) { ... }
md	48rem (768px)	@media (width >= 48rem) { ... }
lg	64rem (1024px)	@media (width >= 64rem) { ... }
xl	80rem (1280px)	@media (width >= 80rem) { ... }
2xl	96rem (1536px)	@media (width >= 96rem) { ... }
```
