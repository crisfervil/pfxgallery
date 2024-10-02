---
title: Form Generator
metadate: hide
categories:
  - canvasapp
  - generators
image: /assets/images/form-generator/image.png
authors:
  - cfernandez
---

###### Overview

This generator will make your life easier when it comes to generating forms for your Canvas Apps.

###### How to use it

Copy the code below into an empty Power Apps Canvas App screen. Then click on the Reset button.

<a id="copyCode" class="btn btn-sm btn-primary mt-2" href="#">Copy Code</a>

###### Code
{% raw %}
```md

- cntFormGeneratorMain:
    Control: GroupContainer
    Variant: horizontalAutoLayoutContainer
    Properties:
      Fill: =RGBA(245, 245, 245, 1)
      Height: =Parent.Height
      LayoutAlignItems: =LayoutAlignItems.Stretch
      LayoutGap: =16
      LayoutMode: =LayoutMode.Auto
      LayoutWrap: =true
      PaddingBottom: =16
      PaddingLeft: =16
      PaddingRight: =16
      PaddingTop: =16
      Width: =Parent.Width
    Children:
    - LeftContainer2:
        Control: GroupContainer
        Variant: verticalAutoLayoutContainer
        Properties:
          Fill: =RGBA(255, 255, 255, 1)
          LayoutAlignItems: =LayoutAlignItems.Stretch
          LayoutDirection: =LayoutDirection.Vertical
          LayoutMode: =LayoutMode.Auto
          RadiusBottomLeft: =8
          RadiusBottomRight: =8
          RadiusTopLeft: =8
          RadiusTopRight: =8
        Children:
        - cntFieldName:
            Control: GroupContainer
            Variant: horizontalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              FillPortions: =0
              Height: =50
              LayoutAlignItems: =LayoutAlignItems.Stretch
              LayoutMode: =LayoutMode.Auto
              PaddingBottom: =10
              PaddingLeft: =10
              PaddingRight: =10
              PaddingTop: =10
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
            Children:
            - lblFiedName:
                Control: Text
                Properties:
                  Align: ='TextCanvas.Align'.Start
                  AutoHeight: =true
                  Text: ="Field Name"
                  FillPortions: =1
                  Height: =30
                  LayoutMinWidth: =50
            - txtFieldName:
                Control: TextInput
        - cntFieldType:
            Control: GroupContainer
            Variant: horizontalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              FillPortions: =0
              Height: =50
              LayoutAlignItems: =LayoutAlignItems.Stretch
              LayoutMode: =LayoutMode.Auto
              PaddingBottom: =10
              PaddingLeft: =10
              PaddingRight: =10
              PaddingTop: =10
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
            Children:
            - lblFiedType:
                Control: Text
                Properties:
                  Align: ='TextCanvas.Align'.Start
                  AutoHeight: =true
                  Text: ="Field Type"
                  FillPortions: =1
                  Height: =30
                  LayoutMinWidth: =50
            - drpFieldType:
                Control: DropDown
                Variant: pcfdataset
                Properties:
                  Items: =["Text", "Number", "Date"]
        - cntFieldMandatory:
            Control: GroupContainer
            Variant: horizontalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              FillPortions: =0
              Height: =50
              LayoutAlignItems: =LayoutAlignItems.Stretch
              LayoutMode: =LayoutMode.Auto
              PaddingBottom: =10
              PaddingLeft: =10
              PaddingRight: =10
              PaddingTop: =10
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
            Children:
            - lblFiedMandatory:
                Control: Text
                Properties:
                  Align: ='TextCanvas.Align'.Start
                  AutoHeight: =true
                  Text: ="Mandatory"
                  FillPortions: =1
                  Height: =30
                  LayoutMinWidth: =50
            - chkFieldMandatory:
                Control: CheckBox
                Properties:
                  Label: =
                  FillPortions: =1
        - cntNewFieldAdd:
            Control: GroupContainer
            Variant: horizontalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              FillPortions: =0
              Height: =50
              LayoutAlignItems: =LayoutAlignItems.Stretch
              LayoutGap: =10
              LayoutJustifyContent: =LayoutJustifyContent.Center
              LayoutMode: =LayoutMode.Auto
              PaddingBottom: =10
              PaddingLeft: =10
              PaddingRight: =10
              PaddingTop: =10
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
            Children:
            - btnFieldsReset:
                Control: Button
                Properties:
                  OnSelect: |-
                    =ClearCollect(
                        colFields,
                        {
                            Name: "Name",
                            Type: "Text",
                            Mandatory: true
                        }
                    )
                  Icon: ="ArrowClockwise"
                  Text: ="Reset"
                  Width: =150
                  X: =148
                  Y: =8
            - btnNewFieldAdd:
                Control: Button
                Properties:
                  OnSelect: |
                    =If(
                        !IsBlank(txtFieldName.Value) And !IsBlank(drpFieldType.Selected.Value),
                        Collect(
                            colFields,
                            {
                                Name: txtFieldName.Value,
                                Type: drpFieldType.Selected.Value,
                                Mandatory: chkFieldMandatory.Checked
                            }
                        );
                        Reset(txtFieldName);
                        Reset(drpFieldType);
                        Reset(chkFieldMandatory)
                    );
                  Icon: ="Add"
                  Text: ="Add"
                  Width: =150
                  X: =148
                  Y: =8
        - cntFieldsList:
            Control: GroupContainer
            Variant: horizontalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              Height: =50
              LayoutAlignItems: =LayoutAlignItems.Stretch
              LayoutMode: =LayoutMode.Auto
              PaddingBottom: =10
              PaddingLeft: =10
              PaddingRight: =10
              PaddingTop: =10
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
            Children:
            - galFields:
                Control: Gallery
                Variant: galleryVertical
                Properties:
                  Items: =colFields
                  DelayItemLoading: =true
                  Layout: =Layout.Vertical
                  LoadingSpinner: =LoadingSpinner.Data
                  TemplateFill: =If(ThisItem.IsSelected, Color.LightGray, RGBA(0, 0, 0, 0))
                  TemplateSize: =100
                Children:
                - lblFieldName:
                    Control: Text
                    Properties:
                      Text: =ThisItem.Name
                      Height: =33
                      Width: =591
                      X: =16
                      Y: =8
                - lblFieldType:
                    Control: Text
                    Properties:
                      Text: =ThisItem.Type
                      Height: =33
                      Width: =229
                      X: =16
                      Y: =41
                - lblMandatory:
                    Control: Text
                    Properties:
                      Text: |-
                        =$"Mandatory: {If(ThisItem.Mandatory,"yes","no")}"
                      Height: =33
                      Width: =229
                      X: =299
                      Y: =41
    - RightContainer2:
        Control: GroupContainer
        Variant: verticalAutoLayoutContainer
        Properties:
          Fill: =RGBA(255, 255, 255, 1)
          LayoutAlignItems: =LayoutAlignItems.Stretch
          LayoutDirection: =LayoutDirection.Vertical
          LayoutMode: =LayoutMode.Auto
          RadiusBottomLeft: =8
          RadiusBottomRight: =8
          RadiusTopLeft: =8
          RadiusTopRight: =8
        Children:
        - lblFormCode:
            Control: Text
            Properties:
              VerticalAlign: ='TextCanvas.VerticalAlign'.Top
              FillPortions: =1

```
{% endraw %}