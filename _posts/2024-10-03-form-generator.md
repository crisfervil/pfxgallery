---
title: Form Generator
metadata: hide
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
```yaml
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
    - cntFormGeneratorMainLeft:
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
            - lblFieldName:
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
            - lblFieldType:
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
                  Items: =["Text", "Number", "Date", "Dropdown", "ComboBox", "CheckBox", "Rating", "Slider", "Toggle", "Attachments"]
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
                  OnSelect: "=ClearCollect(\n    colFields,\n    {\n        Name: \"Full Name\",\n        Type: \"Text\",\n        Mandatory: true\n    },\n    {\n        Name: \"Phone Number\",\n        Type: \"Text\",\n        Mandatory: true\n    },\n    {\n        Name: \"Email\",\n        Type: \"Text\",\n        Mandatory: true\n    },\n    {\n        Name: \"Date of Birth\",\n        Type: \"Date\",\n        Mandatory: true\n    },\n    {\n        Name: \"Number of Cars\",\n        Type: \"Number\",\n        Mandatory: true\n    }\n\n    \n)"
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
                - btnRemoveField:
                    Control: Button
                    Properties:
                      OnSelect: =Remove(colFields,ThisItem)
                      Icon: ="Delete"
                      Text: =
                      Width: =43
                      X: =568
                      Y: =24
                - lbl_gal_FieldName:
                    Control: Text
                    Properties:
                      Text: |-
                        =$"Field Name: {ThisItem.Name}"
                      Height: =33
                      Width: =559
                      X: =20
                      Y: =8
                - lbl_gal_FieldType:
                    Control: Text
                    Properties:
                      Text: |-
                        =$"Field Type: {ThisItem.Type}"
                      Height: =33
                      Width: =154
                      X: =20
                      Y: =41
                - lblMandatory:
                    Control: Text
                    Properties:
                      Text: |-
                        =$"Mandatory: {If(ThisItem.Mandatory,"yes","no")}"
                      Height: =33
                      Width: =229
                      X: =185
                      Y: =41
    - cntFormGeneratorMainRight:
        Control: GroupContainer
        Variant: verticalAutoLayoutContainer
        Properties:
          Fill: =RGBA(255, 255, 255, 1)
          LayoutAlignItems: =LayoutAlignItems.Stretch
          LayoutDirection: =LayoutDirection.Vertical
          LayoutGap: =30
          LayoutMode: =LayoutMode.Auto
          PaddingBottom: =20
          PaddingLeft: =20
          PaddingRight: =20
          PaddingTop: =20
          RadiusBottomLeft: =8
          RadiusBottomRight: =8
          RadiusTopLeft: =8
          RadiusTopRight: =8
        Children:
        - lblFormCode:
            Control: Text
            Properties:
              BorderColor: =RGBA(214, 221, 224, 1)
              BorderStyle: =BorderStyle.Solid
              BorderThickness: =1
              Text: |-
                =
                $"
                - cntForm:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =8
                      RadiusBottomRight: =8
                      RadiusTopLeft: =8
                      RadiusTopRight: =8
                    Children:{Concat(colFields,$"
                    - cnt{Substitute(Name," ","")}:
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
                        - lbl{Substitute(Name," ","")}:
                            Control: Text
                            Properties:
                              Align: ='TextCanvas.Align'.Start
                              AutoHeight: =true
                              Text: =""{Name}""
                              FillPortions: =1
                              Height: =30
                              LayoutMinWidth: =50{
                            If(Type="Text",$"
                        - txt{Substitute(Name," ","")}:
                            Control: TextInput",
                            Type="Number",$"
                        - ni{Substitute(Name," ","")}:
                            Control: NumberInput",
                            Type="Date",$"
                        - dp{Substitute(Name," ","")}:
                            Control: DatePicker",
                            Type="Dropdown",$"
                        - dd{Substitute(Name," ","")}:
                            Control: Dropdown",
                            Type="ComboBox",$"
                        - cbx{Substitute(Name," ","")}:
                            Control: ComboBox",
                            Type="Checkbox",$"
                        - cb{Substitute(Name," ","")}:
                            Control: Checkbox",
                            Type="Rating",$"
                        - rat{Substitute(Name," ","")}:
                            Control: Rating",
                            Type="Slider",$"
                        - sl{Substitute(Name," ","")}:
                            Control: Slider",
                            Type="Toggle",$"
                        - tg{Substitute(Name," ","")}:
                            Control: Toggle",
                            Type="Attachments",$"
                        - atch{Substitute(Name," ","")}:
                            Control: Attachments")}")}
                "
              VerticalAlign: ='TextCanvas.VerticalAlign'.Top
              FillPortions: =1
        - btnCopyFormCode:
            Control: Button
            Properties:
              OnSelect: =Copy(lblFormCode.Text)
              Icon: ="Copy"
              Text: ="Copy"

```
{% endraw %}