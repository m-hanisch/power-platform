---
title: Abs, Exp, Ln, Power, Log, and Sqrt functions in Power Apps
description: Reference information including syntax and examples for the Abs, Exp, Ln, Power, and Sqrt functions in Power Apps.
author: gregli-msft

ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/14/2021
ms.subservice: canvas-maker
ms.author: gregli
search.audienceType: 
  - maker
search.app: 
  - PowerApps
contributors:
  - gregli-msft
  - tapanm-msft
---
# Abs, Exp, Ln, Power, Log, and Sqrt functions in Power Apps
Calculates absolute values, logarithms, square roots, and the results of raising *e* or any number to specified powers.

## Description
The **Abs** function returns the non-negative value of its argument. If a number is negative, **Abs** returns the positive equivalent.

The **Exp** function returns *e* raised to the power of its argument.  The transcendental number *e* begins 2.7182818...

The **Ln** function returns the natural logarithm (base *e*) of its argument.

The **Power** function returns a number raised to a power.  It is equivalent to using the [**^** operator](operators.md).

The **Log** function returns the logarithm of its first argument in the base specified by its second argument (or 10 if not specified).

The **Sqrt** function returns the number that, when multiplied by itself, equals its argument.

If you pass a single number, the return value is a single result based on the function called.  If you pass a single-column [table](/power-apps/maker/canvas-apps/working-with-tables) that contains numbers, the return value is a single-column table of results, one result for each record in the argument's table. If you have a multi-column table, you can shape it into a single-column table, as [working with tables](/power-apps/maker/canvas-apps/working-with-tables) describes.  

If an argument would result in an undefined valued, the result is *blank*.  This can happen, for example, with square roots and logarithms of negative numbers.

## Syntax
**Abs**( *Number* )<br>**Exp**( *Number* )<br>**Ln**( *Number* )<br>**Sqrt**( *Number* )

* *Number* - Required. Number to operate on.

**Power**( *Base*, *Exponent* )

* *Base* - Required. Base number to raise.
* *Exponent* - Required. The exponent to which the base number is raised.

**Log**( *Number*, *Base* )

* *Number* - Required. Number to calculate the logarithm.
* *Base* - Optional. The base of the logarithm to calculate. By default, 10 (when not specified).

**Abs**( *SingleColumnTable* )<br>**Exp**( *SingleColumnTable* )<br>**Ln**( *SingleColumnTable* )<br>**Sqrt**( *SingleColumnTable* )

* *SingleColumnTable* - Required. A single-column table of numbers to operate on.

## Examples
### Single number

| Formula | Description | Result |
| --- | --- | --- |
| **Abs( -55 )** |Returns the number without the negative sign. |55 |
| **Exp( 2 )** |Returns *e* raised to the power of 2, or *e* \* *e*. |7.389056... |
| **Ln( 100 )** |Returns the natural logarithm (base *e*) of the number 100. |4.605170... |
| **Log( 100 )** |Returns the logarithm in base 10 of the number 100. |2 |
| **Log( 64, 2 )** |Returns the logarithm in base 2 of the number 64. |6 |
| **Power( 5, 3 )** |Returns 5 raised to the power of 3, or 5 \* 5 \* 5. |125 |
| **Sqrt( 9 )** |Returns the number that, when multiplied by itself, results in 9. |3 |

### Single-column table
The examples in this section use a [data source](/power-apps/maker/canvas-apps/working-with-data-sources) that's named **ValueTable** and that contains this data:

![Table example.](media/function-numericals/values.png)

| Formula | Description | Result |
| --- | --- | --- |
| **Abs(&nbsp;ValueTable&nbsp;)** |Returns the absolute value of each number in the table. | ![Abs.](media/function-numericals/values-abs.png) |
| **Exp(&nbsp;ValueTable&nbsp;)** |Returns *e* raised to the power of each number in the table. | ![Exp.](media/function-numericals/values-exp.png) |
| **Ln(&nbsp;ValueTable&nbsp;)** |Returns the natural logarithm of each number in the table. | ![Ln.](media/function-numericals/values-ln.png) |
| **Sqrt(&nbsp;ValueTable&nbsp;)** |Returns the square root of each number in the table |![Sqrt.](media/function-numericals/values-sqrt.png) |

### Step-by-step example
1. Add a **[Text input](/power-apps/maker/canvas-apps/controls/control-text-input)** control, and name it **Source**.
2. Add a **Label** control, and set its **[Text](/power-apps/maker/canvas-apps/controls/properties-core)** property to this formula:
   <br>
   **Sqrt( Value( Source.Text ) )**
3. Type a number into **Source**, and confirm that the **Label** control shows the square root of the number that you typed.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]