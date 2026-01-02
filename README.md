
  # 📋 QR Code Generator Pro API - Documentation

 This API generates high-quality, customizable QR codes with options for colors, shapes, and embedded logos. It returns a **PNG image** directly.

  ## **Endpoints URL**

  ```
  # On Rapidapi
  POST https://qr-code-generator-pro7.p.rapidapi.com/generate 
  
  # On Zylalabs
  POST https://zylalabs.com/api/11611/qr+code+pro+generator+api/21914/generate+qr+code
  
  # On your own host or my server please contact me via https://wroclawprogramowanie.pl/ contact form
  ```

  ## **Request Body (JSON)**

  The body must be a valid JSON object containing the data to encode and configuration options.

  ```json
  {
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#square",
    "config": {
      "body": "square",
      "eye": "frame0",
      "eyeBall": "ball0",
      "bodyColor": "#000000",
      "bgColor": "#FFFFFF",
      "eye1Color": "#000000",
      "eye2Color": "#000000",
      "eye3Color": "#000000",
      "eyeBall1Color": "#000000",
      "eyeBall2Color": "#000000",
      "eyeBall3Color": "#000000",
      "logo": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNk+A8AAQUBAScY42YAAAAASUVORK5CYII=",
      "logoMode": "clean"
    }
  }
  ```

  ## **Parameters Table**

  | Parameter          | Type   | Required | Description                                                  |
  | :----------------- | :----- | :------- | :----------------------------------------------------------- |
  | **`data`**         | String | **Yes**  | The text or URL to be encoded in the QR code.                |
  | **`config`**       | Object | No       | Configuration object for styling. Defaults to standard B&W QR. |
  | `config.body`      | String | No       | Dot style. See accepted values below.                        |
  | `config.eye`       | String | No       | Outer eye frame style. See accepted values below.            |
  | `config.eyeBall`   | String | No       | Inner eye ball style. See accepted values below.             |
  | `config.bodyColor` | Hex    | No       | Color of the main data dots (e.g. `#FF0000`).                |
  | `config.bgColor`   | Hex    | No       | Background color (e.g. `#FFFFFF` or `transparent`).          |
  | `config.logo`      | Base64 | No       | Base64 encoded image string to place in the center.          |
  | `config.logoMode`  | String | No       | Controls the logo's background. Can be `clean` for transparency, a hex color (e.g., `#FF0000`), or empty for a default white background. |

  ### Accepted values

  #### `config.body`

  | Accepted Value | Aliases                    | Description                  |
  | :------------- | :------------------------- | :--------------------------- |
  | `circle`       | `round`                    | Circular body shape.         |
  | `clover`       | `shamrock`, `lucky`        | Clover-like body shape.      |
  | `diamond`      |                            | Diamond body shape.          |
  | `dot`          | `small-dot`                | Small dot body shape.        |
  | `drop`         | `water`, `tear`, `liquid`  | Drop-like body shape.        |
  | `flower`       | `blossom`, `daisy`         | Flower-like body shape.      |
  | `seed`         | `grain`, `wheat`           | Grain-like body shape.       |
  | `hex`          | `honeycomb`, `sześciokąt`  | Hexagonal body shape.        |
  | `leaf`         | `organic`, `eco`, `nature` | Leaf-like body shape.        |
  | `pointed`      |                            | Pointed body shape.          |
  | `square`       | `box`, `rect`              | Square body shape (default). |
  | `star`         | `stellar`                  | Star-like body shape.        |

  #### `config.eye`

  | Accepted Value | Aliases                             | Description                      |
  | :------------- | :---------------------------------- | :------------------------------- |
  | `frame0`       | `square`, `box`                     | Square eye frame (default).      |
  | `frame12`      | `ring`, `circle`                    | Ring-shaped eye frame.           |
  | `frame13`      | `rounded`, `smooth`                 | Rounded eye frame.               |
  | `frame14`      | `leaf`, `organic-box`, `asymmetric` | Asymmetrical, organic eye frame. |
  | `frameHex`     | `hexagon-frame`                     | Hexagonal eye frame.             |

  #### `config.eyeBall`

  | Accepted Value | Aliases                                 | Description                |
  | :------------- | :-------------------------------------- | :------------------------- |
  | `ball0`        | `square`, `box`                         | Square eye ball (default). |
  | `ball14`       | `disc`, `solid-circle`, `filled-circle` | Disc-shaped eye ball.      |
  | `ball15`       | `rounded`, `smooth`                     | Rounded eye ball.          |
  | `cat-eye`      | `cat`, `reptile`, `dragon-eye`          | Cat-eye shaped eye ball.   |
  | `clover`       | `shamrock`, `lucky`, `heart-clover`     | Clover-shaped eye ball.    |
  | `diamond`      | `gem`, `brilliant`                      | Diamond-shaped eye ball.   |
  | `drop`         | `ball_liquid`, `teardrop`, `water`      | Drop-shaped eye ball.      |
  | `hex`          | `ball_hex`, `hive`                      | Hexagonal eye ball.        |
  | `leaf`         | `organic`, `simple-leaf`                | Leaf-shaped eye ball.      |


  ## **Style Options Reference**

  - **Body Styles:** `square`, `circle`, `diamond`, `dot`, `drop`, `flower`, `grain`, `hex`, `leaf`, `pointed`, `star`
  - **Frame Styles:** `frame0`, `frame12`, `frame13`, `frame14`, `frameHex`
  - **Ball Styles:** `ball0`, `ball14`, `ball15`, `cat-eye`, `clover`, `diamond`, `drop`, `hex`, `leaf`

  ## **Response**

  - **Success (200 OK):** Returns binary `image/png` data.
  - **Error (400 Bad Request):** Returns JSON with error details (e.g. invalid Base64 logo).

---

  ## Examples

  ### Green Square Style

  This example generates a QR code with a classic square look but in shades of green.

  ```bash
  # Example 1: square - Green style
  echo "Generating: example-01-green-square.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#green-square",
    "config": {
      "body": "square",
      "eye": "frame0",
      "eyeBall": "ball0",
      "bodyColor": "#5C8B29",
      "bgColor": "#FFFFFF",
      "eye1Color": "#3F6B2B",
      "eye2Color": "#3F6B2B",
      "eye3Color": "#3F6B2B",
      "eyeBall1Color": "#60A541",
      "eyeBall2Color": "#60A541",
      "eyeBall3Color": "#60A541",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-01-green-square.png
  ```

  ![Green Square Style](images/example-01-green-square.png)

  ### Red Circle Style

  This example uses circular elements and a vibrant red color scheme.

  ```bash
  # Example 2: circle - Red style
  echo "Generating: example-02-red-circle.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#red-circle",
    "config": {
      "body": "circle",
      "eye": "frame13",
      "eyeBall": "ball15",
      "bodyColor": "#8b2929",
      "bgColor": "#FFFFFF",
      "eye1Color": "#a30812",
      "eye2Color": "#e10aa8",
      "eye3Color": "#9d052b",
      "eyeBall1Color": "#6f150d",
      "eyeBall2Color": "#fa1468",
      "eyeBall3Color": "#a00909",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-02-red-circle.png
  ```

  ![Red Circle Style](images/example-02-red-circle.png)

  ### Blue Diamond Style

  ```bash
  # Example 3: diamond - Blue style
  echo "Generating: example-03-blue-diamond.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#blue-diamond",
    "config": {
      "body": "diamond",
      "eye": "frame13",
      "eyeBall": "ball15",
      "bodyColor": "#000080",
      "bgColor": "#FFFFFF",
      "eye1Color": "#000060",
      "eye2Color": "#002299",
      "eye3Color": "#0A3D8F",
      "eyeBall1Color": "#000040",
      "eyeBall2Color": "#001166",
      "eyeBall3Color": "#052963",
      "logo": "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"
    }
  }' --output example-03-blue-diamond.png
  ```

  ![Blue Diamond Style](images/example-03-blue-diamond.png)

  ### Cosmic Gold Star Style

  A dark-themed QR code with golden star-shaped dots for a cosmic feel. The logo has a transparent background.

  ```bash
  # Example 4: star - Cosmic Gold style
  echo "Generating: example-04-cosmic-star.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#star",
    "config": {
      "body": "star",
      "eye": "frame13",
      "eyeBall": "ball15",
      "bodyColor": "#F4D03F",
      "bgColor": "#1A1A2E",
      "eye1Color": "#FFD700",
      "eye2Color": "#FFD700",
      "eye3Color": "#FFD700",
      "eyeBall1Color": "#FFFFFF",
      "eyeBall2Color": "#FFFFFF",
      "eyeBall3Color": "#FFFFFF",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-04-cosmic-star.png
  ```

  ![Cosmic Gold Star Style](images/example-04-cosmic-star.png)

  ### Modern Minimalist Dot Style

  ```bash
  # Example 5: dot - Modern Minimalist style
  echo "Generating: example-05-modern-dot.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#dot",
    "config": {
      "body": "dot",
      "eye": "frame0",
      "eyeBall": "ball0",
      "bodyColor": "#2C3E50",
      "bgColor": "#ECF0F1",
      "eye1Color": "#E74C3C",
      "eye2Color": "#E74C3C",
      "eye3Color": "#E74C3C",
      "eyeBall1Color": "#2C3E50",
      "eyeBall2Color": "#2C3E50",
      "eyeBall3Color": "#2C3E50",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-05-modern-dot.png
  ```

  ![Modern Minimalist Dot Style](images/example-05-modern-dot.png)

  ### Spring Pointed Style

  ```bash
  # Example 6: pointed - Spring style
  echo "Generating: example-06-spring-pointed.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#pointed",
    "config": {
      "body": "pointed",
      "eye": "frame12",
      "eyeBall": "ball14",
      "bodyColor": "#E91E63",
      "bgColor": "#FFF0F5",
      "eye1Color": "#880E4F",
      "eye2Color": "#880E4F",
      "eye3Color": "#880E4F",
      "eyeBall1Color": "#C2185B",
      "eyeBall2Color": "#C2185B",
      "eyeBall3Color": "#C2185B",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-06-spring-pointed.png
  ```

  ![Spring Pointed Style](images/example-06-spring-pointed.png)

  ### Spring Blossom Flower Style

  ```bash
  # Example 7: flower - Spring Blossom style
  echo "Generating: example-07-spring-flower.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#flower",
    "config": {
      "body": "flower",
      "eye": "frame12",
      "eyeBall": "ball14",
      "bodyColor": "#E91E63",
      "bgColor": "#FFF0F5",
      "eye1Color": "#880E4F",
      "eye2Color": "#880E4F",
      "eye3Color": "#880E4F",
      "eyeBall1Color": "#C2185B",
      "eyeBall2Color": "#C2185B",
      "eyeBall3Color": "#C2185B",
      "logo": "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",
      "logoMode": "#FFF0F5"
    }
  }' --output example-07-spring-flower.png
  ```

  ![Spring Blossom Flower Style](images/example-07-spring-flower.png)

  ### Eco Nature Leaf Style

  ```bash
  # Example 8: leaf - Eco Nature style
  echo "Generating: example-08-eco-leaf.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#leaf",
    "config": {
      "body": "leaf",
      "eye": "frame12",
      "eyeBall": "ball15",
      "bodyColor": "#1B5E20",
      "bgColor": "#FFFFFF",
      "eye1Color": "#2E7D32",
      "eye2Color": "#2E7D32",
      "eye3Color": "#2E7D32",
      "eyeBall1Color": "#1B5E20",
      "eyeBall2Color": "#1B5E20",
      "eyeBall3Color": "#1B5E20",
      "logo": "iVBORw0KGgoAAAANSUhEUgAAAEAAAABACAYAAACqaXHeAAAAAXNSR0IB2cksfwAAAARnQU1BAACxjwv8YQUAAAAgY0hSTQAAeiYAAICEAAD6AAAAgOgAAHUwAADqYAAAOpgAABdwnLpRPAAACcBJREFUeNrtmmmQVNUVx3/nve7pYRlkcIhGIK8HcaA0ECsVYsqA0cRSQXGpgJYmpqIftDQaTVgMGkBLA+KWRMqKW8gimkWiYkosl8RIRSwrkkTLlCOL9IsiKsuwz0x3v3fyoW+Hpue+193M4gf7VPWH7vv6vnv2/zn3QJ3qVKc61alOdapTnT6dJIf1J0+HKawGAmBeQng9n5FgIA/uptUNlJOB2w0jZ6svu/r9xQ2t6uDpjXiax1PF0914ugxPRw8E4yMnqODpaDz9OZ7uM2cI8PSmhlZ1+t8CPP0y8DxwRMmvCmwEpuDLx/0qAU8/C/wdaC07fwdwBr68Xst2To2mPxi4q4z5oiB9EfYMgM/uAjZblNcM3CWeDu0XATSMVUfhWuBky/IOYK5mpKu/BaC+dALXATsty1MUrq7FFap+MBswEZgNuGVLAXBPyuXNgQqAKZe3gTvMuw+JjcAN2ZCJfRoDxNNGhSeBsyzLawSmqy/7a4jgCYWEKkkgBewXIXCEIL+5umwing7RQiyyWeTzAheoLwd6LYCh41T25bgSWAYkypb3AGfhy6uV9km0qpsP8YAZwFRgPHA0MNi4UAZYD7wIvJBy6eh+V8IKAfErwLPA8LKVPDCn0eXerndFe2cBnh4P/BU4ymL6NycdFuc2Rx+0aZzK3hxpYB5wMdBUwfXywFbgIYFlcbk92apOLmQhsMCy5zbgFHxpP2wBSFpTqjwBTLcsvyZwpvqyO+aAbi7kXOBeYFSNaTcE/gNcn3L5W5Q1iKfNWrCCkyzLz4gwMy44R2piyLEqqnwHOMOyvB+YV4F5JxdyOfAbYPRhYA4HmAis7A44p3GsSkRW6DBZYa9l+UxVvjvoWJWaBbA/zzjgFovfh8ADrvBK1H9HtKnkQqYB9xiT7w01A8u7Ar4eGV8cXgfuM2c7ZAlY1JmnrSYXkLQ2qPIY8E3L8hvAN/BlR0zc8ICXDFrrK9oIfA1fPohwhSMUXgAmW5afFOFizUh3RQtoGqeiysXAuZaNDgCz45hPtqoL/ABIV+nneQOlK9GxwFyzv80VdgM3Avssy+eocmnTuJ6uIBbtpYE1wJjydwD3usKcICP5GO1/DlgHtMQws9ekrzUmBY4Cppn02BDzv53AifjyXhS+CJQ7ge9blLsVmIovmyIF4KS1IVQeAWZZhNNuTLBHsdMyXmVHF0MVTgW+DcyMiS/rgCtc4c1SQTppTYXK6cD9JmhGWczV+PJAjAKOouAKEy0KfNwRLg0zku3hAiPaVELlfOB8C/OdwBwb825aE9u7mKnwKvAn4MIY5tuBmfjyz3IrCjPSPXIQqw1W2BMTtKe6absbAODLR8B8oMti7ReEyqzmtoOu8P+D7uxmDLDEYoIK/NoVnu9xmrQ2Bspi4LfACUCyAsBZiC+ZqAe2tYsmHdYCD8fEhUmhMiQZU/C4wnPAryx7JIFFHd2MOsQFnLQmQ+WXxnzLtb8eOBVftlr87XaTgxNVBLEPBSbEYYcSMz7FmHFDhCD/BbwG/N4VXrPGJE9HGlg9yaZQR7gyzEjOAQiV6cZ0y5nvAuaXMw8QKGcD11TJPMAGETqrfHaTpdIrze2TzbtfCJRl1h6AL9tMVui2uMIloTKj4AKeHgPcaaqyckk96gh/tlViBiSl4kp306VZY2LDrU1Jcn1cGQ8CrlC420lrD2txCm77qMUVUsDteHqM4Ol9wFUW7W82aWOLxbymA0/F+HzWRPM7HeFjgTA2ddpTabthsBrKAZfjywrLXqONElotClruRPg9wKoGl602jG9AUhTzAXCbI8zBl/fDjGRrYv6gALWG55PAVZLWHhY5OMGWCCsQYKYD/MKCoQEuygY90VygJIDPxxzmHwJ3hxk5bHN3hA5TCdZCX1DlyB7QNc8Y4FsWJYfAw47x/39bNjwaWOqUSVULqfPIGL9fPayh6mBnRzsFzH494NdgCS7wmXJgByyOgOVvCCxO4MsOPJ0DrCqr3AQ4L1QubG7TFR3rC50VAdWeIKPU/Dfu3iDa6/Dmy1o8PQ24xFicGtdIGmYbjBaLeGCTwDvFFze3qXR0c1FEdjsA3KC+7EwAJIQ1eeUhI3WnzLdu6ejmzeC/JVqOQ2otfRbjfdk8/DhdvDeHC6hI4e1qiVmuEGZLOlMdBWB3iyVWKfCQK7wUHCIZT1sM+DjR8ofHHOGyMCO5xrEqXQGLgIURwfNpR5jZmxjQW6oA7N4yNc3OQ8thX7YDP47B0Oe1jFcxTcb7TX1uozND5Yzhx6l8EsyPnKASFkCazfT3A3OLzPfoB8Rg6MHA0u1dhSqtZRDFgsPWCk8BD+7KMs1Ja3KgBbCtk6OApRHA7hFXeDG2HyCejlBYa9rW5Rs86ArXBBnJu2lNBsr9wGURrtANPGfw+AFjWZ0lEdsxQU3Mp8l87zRrYcm+WnZmNc/kgbUG9hbrk58C34so50811WKFrrCnM4A/Ao2WsngWvjxjnhsDvFyh9RWWMKBVdKhrySCbga8WBYCnpwNPWxBkN3ARvqyqqinqCs8Cyy2HGQQsEU+bTdx4D/iR0Vxc49U1n0TMp5pnSj8KLBnWwPai5RpMM8hiub9zhNVVd4UNdF0SEehOUJidML05R3gKWFmj5npLCjzlCI/u2SCaaFVXCzFpkuXZDLAwKitFNhVaGtkC3GQpJx3gunzIKQa1ZU322DKAAvgAmF9sbeVDTjIFnWOpKRYMT/F+zfcC298RNdp93LI8FLhDPB0O0JQkA8yJyAp9TVlgwdAk7xbHdYC7gSEWK1npCI/vWh+NTJ0KmDxn7t1sXdgvKlzbMFadvRtFEw4rjRb8mGZGb6nTVJor9m0UTbaqo4WO1OQIK1lQ2gA9rMvRYeNU9uS4FHjQklt3U7gkWVdyEXokcB6Fq/QJBkOoSYMJI/RimiveC6SM0LImECbNdzWYv8N0k1e4wqtBcSDL08kmzQ6z9AeuGpJg+f5Nvb0dPtgu/4PpGJfTKwLT1Je91hkAk7clIkqW/h6VBwXUFXKlt9Di6VBzKTrFsu0T5iYoS58NSXnaZjortmvyBSmXpRXv8+m7SbVsyA3ArZaJlY8N4Hm7T0dkmpJsAG42Jlteh1/fHXD8QKWAbMgkE3RdS8f4tsEJ2umPMbkKozJ/EZhhhpj6jSStjaqsBk6zLD8nwgWaqf4MTo0TWl3AD6GAvspSzijtOT7X9whIGQ54llCxA5hXC/M1CwCg0aUd+ElJqtsN/IzCOMqH/S2AESk+Mtq/h4NDEQGwJOXy1kDNCg/RQrHkAgsTDuuqne7qKzITKF8ygTAQmFXLpFqd6lSnOtWpTnWq06ee/gc+I6onCRS/6AAAAABJRU5ErkJggg==",
      "logoMode": "clean"
    }
  }' --output example-08-eco-leaf.png
  ```

  ![Eco Nature Leaf Style](images/example-08-eco-leaf.png)

  ### Harvest Grain Style

  ```bash
  # Example 9: grain - Harvest style
  echo "Generating: example-09-harvest-grain.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#grain",
    "config": {
      "body": "seed",
      "eye": "frame12",
      "eyeBall": "ball15",
      "bodyColor": "#000000",
      "bgColor": "#FFFFFF",
      "eye1Color": "#8B4513",
      "eye2Color": "#8B4513",
      "eye3Color": "#8B4513",
      "eyeBall1Color": "#A0522D",
      "eyeBall2Color": "#A0522D",
      "eyeBall3Color": "#A0522D",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-09-harvest-grain.png
  ```

  ![Harvest Grain Style](images/example-09-harvest-grain.png)

  ### Realistic Nature Leaf Style

  ```bash
  # Example 10: leaf - Realistic Nature style
  echo "Generating: example-10-realistic-leaf.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#nature",
    "config": {
      "body": "leaf",
      "eye": "frame12",
      "eyeBall": "ball15",
      "bodyColor": "#228B22",
      "bgColor": "#F5FFFA",
      "eye1Color": "#006400",
      "eye2Color": "#006400",
      "eye3Color": "#006400",
      "eyeBall1Color": "#2E8B57",
      "eyeBall2Color": "#2E8B57",
      "eyeBall3Color": "#2E8B57",
      "logo": "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"
    }
  }' --output example-10-realistic-leaf.png
  ```

  ![Realistic Nature Leaf Style](images/example-10-realistic-leaf.png)

  ### Lucky Shamrock Clover Style

  ```bash
  # Example 11: clover - Lucky Shamrock style
  echo "Generating: example-11-lucky-clover.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#luck",
    "config": {
      "body": "clover",
      "eye": "frame13",
      "eyeBall": "lucky",
      "bodyColor": "#009A49",
      "bgColor": "#FFFFFF",
      "eye1Color": "#FFD700",
      "eye2Color": "#FFD700",
      "eye3Color": "#FFD700",
      "eyeBall1Color": "#009A49",
      "eyeBall2Color": "#009A49",
      "eyeBall3Color": "#009A49",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-11-lucky-clover.png
  ```

  ![Lucky Shamrock Clover Style](images/example-11-lucky-clover.png)

  ### Organic Love Frame14 Style

  ```bash
  # Example 12: frame14 - Organic Love style
  echo "Generating: example-12-organic-love.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#organic",
    "config": {
      "body": "flower",
      "eye": "frame14",
      "eyeBall": "ball_clover",
      "bodyColor": "#880E4F",
      "bgColor": "#FFF0F5",
      "eye1Color": "#C2185B",
      "eye2Color": "#C2185B",
      "eye3Color": "#C2185B",
      "eyeBall1Color": "#D81B60",
      "eyeBall2Color": "#D81B60",
      "eyeBall3Color": "#D81B60",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-12-organic-love.png
  ```

  ![Organic Love Frame14 Style](images/example-12-organic-love.png)

  ### Forest Whisper Leaf Style

  ```bash
  # Example 13: leaf - Forest Whisper style
  echo "Generating: example-13-forest-whisper.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#forest",
    "config": {
      "body": "leaf",
      "eye": "leaf",
      "eyeBall": "leaf",
      "bodyColor": "#2E7D32",
      "bgColor": "#F1F8E9",
      "eye1Color": "#1B5E20",
      "eye2Color": "#1B5E20",
      "eye3Color": "#1B5E20",
      "eyeBall1Color": "#388E3C",
      "eyeBall2Color": "#388E3C",
      "eyeBall3Color": "#388E3C",
      "logo": "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"
    }
  }' --output example-13-forest-whisper.png
  ```

  ![Forest Whisper Leaf Style](images/example-13-forest-whisper.png)

  ### Predator Cat-Eye Style

  The logo background is set to a dark grey to match the QR code's background.

  ```bash
  # Example 14: cat-eye - Predator style
  echo "Generating: example-14-predator-cateye.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#predator",
    "config": {
      "body": "dot",
      "eye": "leaf",
      "eyeBall": "cat-eye",
      "bodyColor": "#FF8F00",
      "bgColor": "#263238",
      "eye1Color": "#FF6F00",
      "eye2Color": "#FF6F00",
      "eye3Color": "#FF6F00",
      "eyeBall1Color": "#FFD54F",
      "eyeBall2Color": "#FFD54F",
      "eyeBall3Color": "#FFD54F",
      "logo": "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",
      "logoMode": "#263238"
    }
  }' --output example-14-predator-cateye.png
  
  ```

  ![Predator Cat-Eye Style](images/example-14-predator-cateye.png)

  ### Cyber Bee Hex Style

  ```bash
  # Example 15: hex - Cyber Bee style
  echo "Generating: example-15-cyber-bee.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#hex",
    "config": {
      "body": "hex",
      "eye": "hex",
      "eyeBall": "hex",
      "bodyColor": "#FBC02D",
      "bgColor": "#212121",
      "eye1Color": "#FFEB3B",
      "eye2Color": "#FFEB3B",
      "eye3Color": "#FFEB3B",
      "eyeBall1Color": "#FFF176",
      "eyeBall2Color": "#FFF176",
      "eyeBall3Color": "#FFF176",
      "logo": "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",
      "logoMode": "#212121"
    }
  }' --output example-15-cyber-bee.png
  ```

  ![Cyber Bee Hex Style](images/example-15-cyber-bee.png)

  ### Aqua Fresh Drop Style

  This example features a logo with a transparent background.

  ```bash
  # Example 16: drop - Aqua Fresh style
  echo "Generating: example-16-aqua-fresh.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#aqua",
    "config": {
      "body": "drop",
      "eye": "frame12",
      "eyeBall": "drop",
      "bodyColor": "#039BE5",
      "bgColor": "#E1F5FE",
      "eye1Color": "#0277BD",
      "eye2Color": "#0277BD",
      "eye3Color": "#0277BD",
      "eyeBall1Color": "#0288D1",
      "eyeBall2Color": "#0288D1",
      "eyeBall3Color": "#0288D1",
      "logo": "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",
      "logoMode": "clean"
    }
  }' --output example-16-aqua-fresh.png
  ```

  ![Aqua Fresh Drop Style](images/example-16-aqua-fresh.png)

  ### Luxury Sharp Diamond Style

  ```bash
  # Example 17: diamond - Luxury Sharp style
  echo "Generating: example-17-luxury-diamond.png"
  curl -X 'POST' \
    'https://qrapi.wroclawprogramowanie.pl/generate' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json' \
    -d '{
    "data": "https://wroclawprogramowanie.pl/qr-code-pro-generator-api/#luxury",
    "config": {
      "body": "diamond",
      "eye": "frame0",
      "eyeBall": "diamond",
      "bodyColor": "#455A64",
      "bgColor": "#FFFFFF",
      "eye1Color": "#263238",
      "eye2Color": "#263238",
      "eye3Color": "#263238",
      "eyeBall1Color": "#000000",
      "eyeBall2Color": "#000000",
      "eyeBall3Color": "#000000",
      "logo": "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"
    }
  }' --output example-17-luxury-diamond.png
  ```

  ![Luxury Sharp Diamond Style](images/example-17-luxury-diamond.png)
