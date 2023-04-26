# DefaultDialogs

- [1 Introduction](#1-introduction)
- [2 API](#2-api)
  - [2.1 GeneralButtonBasedDialog (Window)](#21-generalbuttonbaseddialog-window)
  - [2.2 GeneralButtonBasedDialogStyle (class)](#22-generalbuttonbaseddialogstyle-class)
  - [2.3 SuccessMode (enum)](#23-successmode-enum)

## 1 Introduction

The `DefaultDialogs` offer a configurable dialog template that can contain custom buttons with configurable captions. Each button can either house an action to perform on click or set the result of the dialog to a given value.

## 2 API

### 2.1 GeneralButtonBasedDialog (Window)

> A dialog with a header and text that can contain several buttons to select an action or result.
>
> The dialog is created via the given configuration methods and can either be configured to trigger an `Action` or the set a `Result` whenever a specific button is clicked.
> For the latter, use the `ShowForResult` method with the according building methods for the buttons.

Accessible Interface:

```c#
public object Result
public GeneralButtonBasedDialog(GeneralButtonBasedDialogStyle style)

public GeneralButtonBasedDialog WithTitle(string title)
public GeneralButtonBasedDialog WithText(string text)

public GeneralButtonBasedDialog WithDefaultButton(string text, Action action)
public GeneralButtonBasedDialog WithNeutralButton(string text, Action action, bool isDefault = false, bool isCancel = false)
public GeneralButtonBasedDialog WithCancelButton(string text, Action action)

public GeneralButtonBasedDialog WithDefaultButton(string text, object result = null)
public GeneralButtonBasedDialog WithNeutralButton(string text, object result = null, bool isDefault = false, bool isCancel = false)
public GeneralButtonBasedDialog WithCancelButton(string text, object result = null)

public GeneralButtonBasedDialog WithBorder(SuccessMode mode)

public object ShowForResult()
```

### 2.2 GeneralButtonBasedDialogStyle (class)

> Configurable style information for a `GeneralButtonBasedDialog`

Accessible Interface:

```c#
public SolidColorBrush HeaderBackground
public SolidColorBrush Background
public FontFamily HeaderFontFamily
public FontFamily FontFamily
public int HeaderFontSize
public int FontSize
public SolidColorBrush HeaderBorderColor
public int HeaderBorderThickness
public Color NegativeColor
public Color NeutralColor
public Color PositiveColor
public Color CancelButtonBackground
public Thickness ButtonMargin
```

### 2.3 SuccessMode (enum)

> Whether an action was successful

Accessible Interface:

```c#
Error = -1
Neutral = 0
Success = 1
```
