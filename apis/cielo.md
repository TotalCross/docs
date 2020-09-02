---
name: PrinterManager
route: /api/printermanager
menu: API
---

# PrinterManager

## Overview

PrinterManager is the class responsible for enabling printing on Cielo machines and it uses the singleton pattern to guarantee a unique instance of PrinterManager.

## Atributes

The attributes will be inserted into the hashMap and will be used at the time of printing

#### Used in alignment - KEY_ALIGN

| Name             | Description     |
| :--------------- | :-------------- |
| VAL_ALIGN_CENTER | Align to center |
| VAL_ALIGN_LEFT   | Align to left   |
| VAL_ALIGN_RIGHT  | Align to right  |

#### Other features

| Name                     | Description                                                               |
| :----------------------- | :------------------------------------------------------------------------ |
| KEY_TEXT_SIZE            | Text size, must be an integer value                                       |
| KEY_TYPEFACE             | Text font, must be an integer between 0 and 8, where each value is a      |
| different font           |
| KEY_MARGIN_LEFT          | Left margin, must be an integer value                                     |
| KEY_MARGIN_RIGHT         | Right margin, must be an integer value                                    |
| KEY_MARGIN_TOP           | Top margin, must be an integer value                                      |
| KEY_MARGIN_BOTTOM        | Bottom margin, must be an integer value                                   |
| KEY_LINE_SPACE           | Spacing between consecutive lines, must be an integer value               |
| KEY_WEIGHT               | Used when printing multiple columns, to choose the weight of each column, |
| must be an integer value |

## Methods

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">getInstance()</td>
      <td style="text-align:left">Creates a new instance or returns the instance previously created.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>printText(String textToPrint, Map&lt;String, Integer&gt; printerAttributes)
          <br
          />
        </p>
        <p>printText(String textToPrint, Map&lt;String, Integer&gt; printerAttributes,
          <br
          />PrinterListener printerListener)</p>
      </td>
      <td style="text-align:left">
        <p>Prints the text received in the textToPrint parameter.</p>
        <p></p>
        <p>printerAttributes will have the attributes of the print.</p>
        <p></p>
        <p>printerListener will receive the PrinterListener interface methods</p>
      </td>
    </tr>
  </tbody>
</table>

## Usage

<!-- {% code title="Code Example" %} -->

```java
HashMap<String, Integer> printerAttributes = new HashMap<>();

printerAttributes.put(PrinterAttributes.KEY_ALIGN, PrinterAttributes.VAL_ALIGN_CENTER);
printerAttributes.put(PrinterAttributes.KEY_TYPEFACE, 1);
printerAttributes.put(PrinterAttributes.KEY_TEXT_SIZE, 20);

String textToPrint = "TEXT TO PRINT";
PrinterManager.getInstance()
               .printText(textToPrint, printerAttributes);
```

<!-- {% endcode %} -->
