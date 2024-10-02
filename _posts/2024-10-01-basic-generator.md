---
title: Basic Generator
metadate: hide
categories:
  - canvasapp
  - generators
image: /assets/images/basic-generator/image.png
authors:
  - cfernandez
---

###### Overview

A simple generator that generates HTML code for a greeting page.

###### How to use it

Copy the code below into an empty Power Apps Canvas App screen.

<a id="copyCode" class="btn btn-sm btn-primary mt-2" href="#">Copy Code</a>

###### Code
```md
- HtmlText1_1:
    Control: HtmlViewer
    Properties:
      HtmlText: =txtHTML_1.Text
      BorderStyle: =BorderStyle.Solid
      Font: =Font.'Open Sans'
      Height: =651
      Width: =403
      X: =886
      Y: =40
- txtHTML_1:
    Control: Text
    Properties:
      BorderColor: =RGBA(0, 0, 0, 1)
      BorderStyle: =BorderStyle.Solid
      BorderThickness: =0
      Text: |-
        =$"<!DOCTYPE html>
        <html lang='en'>
        <head>
            <meta charset='UTF-8'>
            <meta name='viewport' content='width=device-width, initial-scale=1.0'>
            <title>Greeting Page</title>
        </head>
        <body style='display: flex; flex-direction: column; align-items: center; justify-content: center; height: 100vh; margin: 0; font-family: Arial, sans-serif;'>
            <h1 style='text-align: center;'>Hello {txtName_1.Value}</h1>
            <div style='background-color: {drpColor_1.Selected.Value}; color: white; padding: 20px; margin-top: 20px; border-radius: 5px;'>
                Your favorite color is {drpColor_1.Selected.Value}
            </div>
        </body>
        </html>
        "
      Height: =651
      Width: =410
      X: =434
      Y: =40
- drpColor_1:
    Control: DropDown
    Variant: pcfdataset
    Properties:
      BorderColor: =RGBA(0, 0, 0, 1)
      BorderStyle: =BorderStyle.Solid
      BorderThickness: =0
      Items: =["red", "green", "blue"]
      X: =40
      Y: =270
- lblFavoriteColor_1:
    Control: Text
    Properties:
      BorderColor: =RGBA(0, 0, 0, 1)
      BorderStyle: =BorderStyle.Solid
      BorderThickness: =0
      Text: ="What's your favorite colour?"
      Height: =52
      Width: =353
      X: =40
      Y: =218
- txtName_1:
    Control: TextInput
    Properties:
      BorderColor: =RGBA(0, 0, 0, 1)
      BorderStyle: =BorderStyle.Solid
      BorderThickness: =0
      X: =40
      Y: =157
- lblName_1:
    Control: Text
    Properties:
      BorderColor: =RGBA(0, 0, 0, 1)
      BorderStyle: =BorderStyle.Solid
      BorderThickness: =0
      Text: ="What's your name?"
      Height: =52
      Width: =353
      X: =40
      Y: =105
```