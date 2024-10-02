---
title: Theme Builder
metadate: hide
categories:
  - canvasapp
  - generators
image: /assets/images/theme-builder/image.png
authors:
  - cfernandez
---

###### Overview

This generator will help you creating a theme for your Canvas App.

###### How to use it

1. Copy the code below into an empty Power Apps Canvas App screen.
2. Then click on the Reset button.
3. Configure your style.
4. Copy the generated code into the Formulas section of your app.

<a id="copyCode" class="btn btn-sm btn-primary mt-2" href="#">Copy Code</a>

###### Code
{% raw %}
```md
- cntThemeBuilderMain:
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
    - LeftContainer1:
        Control: GroupContainer
        Variant: verticalAutoLayoutContainer
        Properties:
          Fill: =RGBA(255, 255, 255, 1)
          LayoutDirection: =LayoutDirection.Vertical
          LayoutMode: =LayoutMode.Auto
          RadiusBottomLeft: =8
          RadiusBottomRight: =8
          RadiusTopLeft: =8
          RadiusTopRight: =8
        Children:
        - tabStyles:
            Control: TabList
            Variant: pcfdataset
            Properties:
              Items: =["Colors", "Fonts", "Icons"]
              AlignInContainer: =AlignInContainer.Stretch
        - cntTabsStyles_Colors:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              LayoutDirection: =LayoutDirection.Vertical
              LayoutMode: =LayoutMode.Auto
              Visible: =tabStyles.Selected.Value="Colors"
            Children:
            - cntColorsHelp:
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
                - linkCoolors:
                    Control: Link
                    Properties:
                      Align: ='LinkCanvas.Align'.Center
                      Text: ="https://coolors.co/"
                      URL: ="https://coolors.co/"
                      FillPortions: =1
                      LayoutMinWidth: =50
                      Width: =200
                - linkColorHunt:
                    Control: Link
                    Properties:
                      Align: ='LinkCanvas.Align'.Center
                      Text: ="https://colorhunt.co/"
                      URL: ="https://colorhunt.co/"
                      FillPortions: =1
                      LayoutMinWidth: =50
                      Width: =200
            - cntPrimaryColors:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  DropShadow: =DropShadow.None
                  FillPortions: =0
                  Height: =170
                  LayoutAlignItems: =LayoutAlignItems.Stretch
                  LayoutJustifyContent: =LayoutJustifyContent.SpaceBetween
                  LayoutMinWidth: =100
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
                - cntPrimary1:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblPrimary1:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Primary 1"
                          FillPortions: =1
                          Height: =30
                    - txtPrimary1:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#30475E"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectPrimary1:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtPrimary1.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntPrimary2:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblPrimary2:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Primary 2"
                          FillPortions: =1
                          Height: =30
                    - txtPrimary2:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#F05454"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectPrimary2:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtPrimary2.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntPrimary3:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblPrimary3:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Primary 3"
                          FillPortions: =1
                          Height: =30
                    - txtPrimary3:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#222831"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectPrimary3:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtPrimary3.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntPrimary4:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblPrimary4:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Primary 4"
                          FillPortions: =1
                          Height: =30
                    - txtPrimary4:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#DDDDDD"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectPrimary4:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtPrimary4.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
            - cntAccentColors:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  DropShadow: =DropShadow.None
                  FillPortions: =0
                  Height: =170
                  LayoutAlignItems: =LayoutAlignItems.Stretch
                  LayoutJustifyContent: =LayoutJustifyContent.SpaceBetween
                  LayoutMinWidth: =100
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
                - cntAccentColor1:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblAccentColor1:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Accent Color 1"
                          FillPortions: =1
                          Height: =30
                    - txtAccentColor1:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#000000"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectAccentColor1:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtAccentColor1.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntAccentColor2:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblAccentColor2:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Accent Color 2"
                          FillPortions: =1
                          Height: =30
                    - txtAccentColor2:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#17A2B8"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectAccentColor2:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtAccentColor2.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntAccentColor3:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblAccentColor3:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Accent Color 3"
                          FillPortions: =1
                          Height: =30
                    - txtAccentColor3:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#28A745"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectAccentColor3:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtAccentColor3.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntAccentColor4:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblAccentColor4:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Accent Color 4"
                          FillPortions: =1
                          Height: =30
                    - txtAccentColor4:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#FD7E14"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectAccentColor4:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtAccentColor4.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
            - cntNeutralColors:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  DropShadow: =DropShadow.None
                  FillPortions: =0
                  Height: =170
                  LayoutAlignItems: =LayoutAlignItems.Stretch
                  LayoutJustifyContent: =LayoutJustifyContent.SpaceBetween
                  LayoutMinWidth: =100
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
                - cntNeutralColor1:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblNeutralColor1:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Neutral Color 1"
                          FillPortions: =1
                          Height: =30
                    - txtNeutralColor1:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#484644"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectNeutralColor1:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtNeutralColor1.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntNeutralColor2:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblNeutralColor2:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Neutral Color 2"
                          FillPortions: =1
                          Height: =30
                    - txtNeutralColor2:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#8A8886"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectNeutralColor2:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtNeutralColor2.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntNeutralColor4:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblNeutralColor4:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Neutral Color 4"
                          FillPortions: =1
                          Height: =30
                    - txtNeutralColor4:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#B3b0AD"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectNeutralColor4:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtNeutralColor4.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
                - cntNeutralColor3:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      DropShadow: =DropShadow.None
                      Fill: =RGBA(255, 255, 255, 1)
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinHeight: =50
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblNeutralColor3:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          AutoHeight: =true
                          Text: ="Neutral Color 3"
                          FillPortions: =1
                          Height: =30
                    - txtNeutralColor3:
                        Control: TextInput
                        Properties:
                          Align: ='TextInputCanvas.Align'.Center
                          Appearance: ='TextInputCanvas.Appearance'.FilledDarker
                          Value: ="#D2D0CE"
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - rectNeutralColor3:
                        Control: Rectangle
                        Properties:
                          BorderStyle: =BorderStyle.None
                          Fill: =ColorValue( txtNeutralColor3.Value)
                          FillPortions: =2
                          Height: =50
                          LayoutMinHeight: =32
                          X: =40
        - cntTabsStyles_Fonts:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              LayoutDirection: =LayoutDirection.Vertical
              LayoutMode: =LayoutMode.Auto
              Visible: =tabStyles.Selected.Value="Fonts"
            Children:
            - cntFontssHelp:
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
                - linkTypio:
                    Control: Link
                    Properties:
                      Align: ='LinkCanvas.Align'.Center
                      Text: ="https://typ.io/"
                      URL: ="https://typ.io/"
                      FillPortions: =1
                      LayoutMinWidth: =50
                      Width: =200
            - cntFontHeading:
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
                - lblHeadingFont:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Heading"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - drpHeadingFont:
                    Control: Classic/DropDown
                    Properties:
                      Default: ="Arial"
                      Items: |-
                        =[
                            "Arial",
                            "Arial Black",
                            "Avant Garde",
                            "Bookman",
                            "Comic Sans MS",
                            "Courier",
                            "Garamond",
                            "Georgia",
                            "Helvetica",
                            "Impact",
                            "Lucida Console",
                            "Lucida Sans Unicode",
                            "Palatino",
                            "Tahoma",
                            "Times New Roman"
                        ]
                      AlignInContainer: =AlignInContainer.Center
                      FillPortions: =1
                      LayoutMinWidth: =50
            - cntFontBody:
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
                - lblBodyFont:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Body"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - drpBodyFont:
                    Control: Classic/DropDown
                    Properties:
                      Default: ="Roboto"
                      Items: |-
                        =[
                            "Arial",
                            "Arial Black",
                            "Avant Garde",
                            "Bookman",
                            "Comic Sans MS",
                            "Courier",
                            "Garamond",
                            "Georgia",
                            "Helvetica",
                            "Impact",
                            "Lucida Console",
                            "Lucida Sans Unicode",
                            "Palatino",
                            "Tahoma",
                            "Times New Roman"
                        ]
                      AlignInContainer: =AlignInContainer.Center
                      FillPortions: =1
                      LayoutMinWidth: =50
            - cntSizes:
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
                - lblSizes:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Sizes"
                      Weight: ='TextCanvas.Weight'.Bold
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
            - cntSizeTiny:
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
                - lblSizeTiny:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Tiny"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - cntSizeTinyCtrls:
                    Control: GroupContainer
                    Variant: horizontalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Center
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutGap: =20
                      LayoutMinHeight: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - sldSizeTiny:
                        Control: Slider
                        Properties:
                          Max: =50
                          Min: =5
                          Value: =10
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - numSizeTiny:
                        Control: NumberInput
                        Properties:
                          Value: =sldSizeTiny.Value
                          AlignInContainer: =AlignInContainer.Center
                          LayoutMinWidth: =50
                          Width: =60
            - cntSizeRegular:
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
                - lblSizeRegular:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Regular"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - cntSizeRegularCtrls:
                    Control: GroupContainer
                    Variant: horizontalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Center
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutGap: =20
                      LayoutMinHeight: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - sldSizeRegular:
                        Control: Slider
                        Properties:
                          Max: =50
                          Min: =5
                          Value: =12
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - numSizeRegular:
                        Control: NumberInput
                        Properties:
                          Value: =sldSizeRegular.Value
                          AlignInContainer: =AlignInContainer.Center
                          LayoutMinWidth: =50
                          Width: =60
            - cntSizeSubtitle:
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
                - lblSizeSubtitle:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Subtitle"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - cntSizeSubtitleCtrls:
                    Control: GroupContainer
                    Variant: horizontalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Center
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutGap: =20
                      LayoutMinHeight: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - sldSizeSubtitle:
                        Control: Slider
                        Properties:
                          Max: =50
                          Min: =5
                          Value: =14
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - numSizeSubtitle:
                        Control: NumberInput
                        Properties:
                          Value: =sldSizeSubtitle.Value
                          AlignInContainer: =AlignInContainer.Center
                          LayoutMinWidth: =50
                          Width: =60
            - cntSizeTitle:
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
                - lblSizeTitle:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Title"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - cntSizeTitleCtrls:
                    Control: GroupContainer
                    Variant: horizontalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Center
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutGap: =20
                      LayoutMinHeight: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - sldSizeTitle:
                        Control: Slider
                        Properties:
                          Max: =50
                          Min: =5
                          Value: =20
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - numSizeTitle:
                        Control: NumberInput
                        Properties:
                          Value: =sldSizeTitle.Value
                          AlignInContainer: =AlignInContainer.Center
                          LayoutMinWidth: =50
                          Width: =60
            - cntSizeHuge:
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
                - lblSizeHuge:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Huge"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - cntSizeHugeCtrls:
                    Control: GroupContainer
                    Variant: horizontalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Center
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Stretch
                      LayoutGap: =20
                      LayoutMinHeight: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - sldSizeHuge:
                        Control: Slider
                        Properties:
                          Max: =50
                          Min: =5
                          Value: =28
                          FillPortions: =1
                          LayoutMinWidth: =50
                    - numSizeHuge:
                        Control: NumberInput
                        Properties:
                          Value: =sldSizeHuge.Value
                          AlignInContainer: =AlignInContainer.Center
                          LayoutMinWidth: =50
                          Width: =60
        - cntTabsStyles_Icons:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              LayoutDirection: =LayoutDirection.Vertical
              LayoutMode: =LayoutMode.Auto
              Visible: =tabStyles.Selected.Value="Icons"
            Children:
            - cntIconsHelp:
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
                - linkFontAwesome:
                    Control: Link
                    Properties:
                      Align: ='LinkCanvas.Align'.Center
                      Text: ="Font Awesome"
                      URL: ="https://fontawesome.com/v6/icons"
                      FillPortions: =1
                      LayoutMinWidth: =50
                      Width: =200
                - linkMDevaney:
                    Control: Link
                    Properties:
                      Align: ='LinkCanvas.Align'.Center
                      Text: ="Matthew Devaney"
                      URL: ="https://www.matthewdevaney.com/2000-free-power-apps-icons/"
                      FillPortions: =1
                      LayoutMinWidth: =50
                      Width: =200
                - linkMaterial:
                    Control: Link
                    Properties:
                      Align: ='LinkCanvas.Align'.Center
                      Text: ="Material"
                      URL: ="https://fonts.google.com/icons"
                      FillPortions: =1
                      LayoutMinWidth: =50
                      Width: =200
                - linkBootstrap:
                    Control: Link
                    Properties:
                      Align: ='LinkCanvas.Align'.Center
                      Text: ="Bootstrap"
                      URL: ="https://icons.getbootstrap.com/"
                      FillPortions: =1
                      LayoutMinWidth: =50
                      Width: =200
            - cntNewIcon:
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
                - lblNewIcon:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="New Icon"
                      Weight: ='TextCanvas.Weight'.Bold
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
            - cntNewIconName:
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
                - lblNewIconName:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Name"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - txtNewIconName:
                    Control: TextInput
            - cntNewIconSvg:
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
                - lblNewIconSvg:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Svg"
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
                - txtNewIconSvg:
                    Control: TextInput
            - cntNewIconAdd:
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
                - btnNewIconAdd:
                    Control: Button
                    Properties:
                      OnSelect: |-
                        =If(
                            !IsBlank(txtNewIconName.Value) And !IsBlank(txtNewIconSvg.Value),
                            Collect(
                                colIcons,
                                {
                                    Name: txtNewIconName.Value,
                                    Svg: Concatenate("data:image/svg+xml;utf8, ", EncodeUrl(txtNewIconSvg.Value))
                                }
                            );
                            Reset(txtNewIconName);
                            Reset(txtNewIconSvg);
                            Select(galIcons,galIcons.AllItemsCount)
                        )
                      Font: =drpBodyFont.SelectedText.Value
                      FontSize: =numSizeRegular.Value
                      Icon: ="Add"
                      Text: ="Add"
                      Width: =150
                      X: =148
                      Y: =8
                - btnIconsReset:
                    Control: Button
                    Properties:
                      OnSelect: |-
                        =ClearCollect(
                            colIcons,
                            {
                                Name: "Checklist",
                                Svg: "data:image/svg+xml;utf8, %3Csvg%20%20viewBox%3D%270%200%202048%202048%27%20xmlns%3D%27http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%27%3E%3Cpath%20d%3D%27M256%200h1536v2048H256V0zm1408%201920V128H384v1792h1280zM1536%20512v128h-512V512h512zm0%20512v128h-512v-128h512zm0%20512v128h-512v-128h512zM941%20429L704%20666%20531%20493l90-90%2083%2083%20147-147%2090%2090zm0%20512l-237%20237-173-173%2090-90%2083%2083%20147-147%2090%2090zm0%20512l-237%20237-173-173%2090-90%2083%2083%20147-147%2090%2090z%27%20fill%3D%27%230078d4%27%3E%3C%2Fpath%3E%3C%2Fsvg%3E"
                            },
                            {
                                Name: "Checkmark",
                                Svg: "data:image/svg+xml;utf8, %3Csvg%20%20viewBox%3D%270%200%202048%202048%27%20xmlns%3D%27http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%27%3E%3Cpath%20d%3D%27M1024%200q141%200%20272%2036t244%20104%20207%20160%20161%20207%20103%20245%2037%20272q0%20141-36%20272t-104%20244-160%20207-207%20161-245%20103-272%2037q-141%200-272-36t-244-104-207-160-161-207-103-245-37-272q0-141%2036-272t104-244%20160-207%20207-161T752%2037t272-37zm603%20685l-136-136-659%20659-275-275-136%20136%20411%20411%20795-795z%27%20fill%3D%27%2300ad56%27%3E%3C%2Fpath%3E%3C%2Fsvg%3E"
                            },
                            {
                                Name: "Pylon",
                                Svg: "data:image/svg+xml;utf8, %3Csvg%20%20viewBox%3D%270%200%202048%202048%27%20xmlns%3D%27http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%27%3E%3Cpath%20d%3D%27M1920%201920v128H128v-128h270l96-384h802l-32-128H526l64-256h610l-32-128H622l224-896h356l448%201792h270z%27%20fill%3D%27%23ca5010%27%3E%3C%2Fpath%3E%3C%2Fsvg%3E"
                            },
                            {
                                Name: "Flashlight",
                                Svg: "data:image/svg+xml;utf8, %3Csvg%20%20viewBox%3D%270%200%202048%202048%27%20xmlns%3D%27http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%27%3E%3Cpath%20d%3D%27M2048%20384v1152h-475l-256-256H0V640h1317l256-256h475zM128%201152h1152V768H128v384zm1499%20256h37V512h-37l-219%20219v458l219%20219zm293-896h-128v896h128V512zm-832%20384q26%200%2045%2019t19%2045q0%2026-19%2045t-45%2019q-26%200-45-19t-19-45q0-26%2019-45t45-19z%27%20fill%3D%27%2369797e%27%3E%3C%2Fpath%3E%3C%2Fsvg%3E"
                            }
                        );
                        Reset(txtNewIconName);
                        Reset(txtNewIconSvg);
                        Reset(galIcons);
                      Font: =drpBodyFont.SelectedText.Value
                      FontSize: =numSizeRegular.Value
                      Icon: ="ArrowClockwise"
                      Text: ="Reset"
                      Width: =150
                      X: =148
                      Y: =8
            - cntIcons:
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
                - lblIcons:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Start
                      AutoHeight: =true
                      Text: ="Icons"
                      Weight: ='TextCanvas.Weight'.Bold
                      FillPortions: =1
                      Height: =30
                      LayoutMinWidth: =50
            - cntIconsList:
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
                - galIcons:
                    Control: Gallery
                    Variant: galleryVertical
                    Properties:
                      Items: =colIcons
                      DelayItemLoading: =true
                      Layout: =Layout.Vertical
                      LoadingSpinner: =LoadingSpinner.Data
                      TemplateFill: =If(ThisItem.IsSelected, Color.LightGray, RGBA(0, 0, 0, 0))
                      TemplateSize: =100
                    Children:
                    - imgIcon:
                        Control: Image
                        Properties:
                          OnSelect: =Select(Parent)
                          Image: =ThisItem.Svg
                          Height: =80
                          Width: =80
                          X: =48
                          Y: =10
                    - lblIconName:
                        Control: Text
                        Properties:
                          Text: =ThisItem.Name
                          X: =151
                          Y: =34
    - RightContainer1:
        Control: GroupContainer
        Variant: verticalAutoLayoutContainer
        Properties:
          Fill: =RGBA(255, 255, 255, 1)
          LayoutDirection: =LayoutDirection.Vertical
          LayoutMode: =LayoutMode.Auto
          RadiusBottomLeft: =8
          RadiusBottomRight: =8
          RadiusTopLeft: =8
          RadiusTopRight: =8
        Children:
        - tabOutput:
            Control: TabList
            Variant: pcfdataset
            Properties:
              Items: =["Preview", "Code"]
              AlignInContainer: =AlignInContainer.Stretch
        - cntTabOutputPreview:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              LayoutDirection: =LayoutDirection.Vertical
              LayoutMode: =LayoutMode.Auto
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
              Visible: =tabOutput.Selected.Value="Preview"
            Children:
            - cntHeading:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  DropShadow: =DropShadow.None
                  FillPortions: =0
                  Height: =90
                  LayoutMinWidth: =50
                  LayoutMode: =LayoutMode.Auto
                  PaddingBottom: =20
                  PaddingLeft: =20
                  PaddingRight: =20
                  PaddingTop: =20
                  RadiusBottomLeft: =0
                  RadiusBottomRight: =0
                  RadiusTopLeft: =0
                  RadiusTopRight: =0
                Children:
                - cntHeadingLeft:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Start
                      DropShadow: =DropShadow.None
                      FillPortions: =8
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Center
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblHeadingPreview:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          Font: =drpHeadingFont.SelectedText.Value
                          Size: =sldSizeTitle.Value
                          Text: ="Heading"
                          Height: =Parent.Height
                          Width: =Parent.Width
                - cntHeadingRight:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Start
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Center
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - btnCopyDefaultHeading:
                        Control: Button
                        Properties:
                          Icon: ="Copy"
                          Text: =
                          LayoutMinWidth: =50
                          Width: =50
            - cntBodyPreview:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  DropShadow: =DropShadow.None
                  FillPortions: =0
                  Height: =90
                  LayoutMinWidth: =50
                  LayoutMode: =LayoutMode.Auto
                  PaddingBottom: =20
                  PaddingLeft: =20
                  PaddingRight: =20
                  PaddingTop: =20
                  RadiusBottomLeft: =0
                  RadiusBottomRight: =0
                  RadiusTopLeft: =0
                  RadiusTopRight: =0
                Children:
                - cntBodyLeft:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Start
                      DropShadow: =DropShadow.None
                      FillPortions: =8
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Center
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - lblBodyPreview:
                        Control: Text
                        Properties:
                          Align: ='TextCanvas.Align'.Center
                          Font: =drpBodyFont.SelectedText.Value
                          Size: =sldSizeRegular.Value
                          Text: ="Body Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam."
                          Height: =Parent.Height
                          Width: =Parent.Width
                - cntBodyRight:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Start
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Center
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - btnCopyDefaultBody:
                        Control: Button
                        Properties:
                          Icon: ="Copy"
                          Text: =
                          LayoutMinWidth: =50
                          Width: =50
            - cntButtonPrimary:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  DropShadow: =DropShadow.None
                  FillPortions: =0
                  Height: =90
                  LayoutMinWidth: =50
                  LayoutMode: =LayoutMode.Auto
                  PaddingBottom: =20
                  PaddingLeft: =20
                  PaddingRight: =20
                  PaddingTop: =20
                  RadiusBottomLeft: =0
                  RadiusBottomRight: =0
                  RadiusTopLeft: =0
                  RadiusTopRight: =0
                Children:
                - cntButtonPrimaryLeft:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Start
                      DropShadow: =DropShadow.None
                      FillPortions: =8
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Center
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - btnButtonPrimaryPreview:
                        Control: Button
                        Properties:
                          BasePaletteColor: =ColorValue(txtPrimary1.Value)
                          Font: =drpBodyFont.SelectedText.Value
                          FontSize: =numSizeRegular.Value
                          Text: ="Primary Button"
                          Width: =250
                          X: =148
                          Y: =8
                - cntButtonPrimaryRight:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Start
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Center
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - btnCopyDefaultButtonPrimary:
                        Control: Button
                        Properties:
                          OnSelect: |-
                            =Copy($"
                            - btnButton1:
                                Control: Button
                                Properties:
                                  BasePaletteColor: =MyTheme.Colors.Primary1
                                  Font: =MyTheme.Fonts.Body
                                  FontSize: =MyTheme.Fonts.Size.Regular
                                  Text: =""Button""
                                  X: =148
                                  Y: =8
                            ")
                          Icon: ="Copy"
                          Text: =
                          LayoutMinWidth: =50
                          Width: =50
            - cntButtonSecondary:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  DropShadow: =DropShadow.None
                  FillPortions: =0
                  Height: =90
                  LayoutMinWidth: =50
                  LayoutMode: =LayoutMode.Auto
                  PaddingBottom: =20
                  PaddingLeft: =20
                  PaddingRight: =20
                  PaddingTop: =20
                  RadiusBottomLeft: =0
                  RadiusBottomRight: =0
                  RadiusTopLeft: =0
                  RadiusTopRight: =0
                Children:
                - cntButtonSecondaryLeft:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Start
                      DropShadow: =DropShadow.None
                      FillPortions: =8
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Center
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - btnButtonSecondaryPreview:
                        Control: Button
                        Properties:
                          Appearance: ='ButtonCanvas.Appearance'.Secondary
                          BasePaletteColor: =ColorValue(txtPrimary1.Value)
                          Font: =drpBodyFont.SelectedText.Value
                          FontSize: =numSizeRegular.Value
                          IconStyle: ='ButtonCanvas.IconStyle'.Outline
                          Text: ="Secondary Button"
                          Width: =250
                          X: =148
                          Y: =8
                - cntButtonSecondaryRight:
                    Control: GroupContainer
                    Variant: verticalAutoLayoutContainer
                    Properties:
                      AlignInContainer: =AlignInContainer.Start
                      DropShadow: =DropShadow.None
                      Height: =50
                      LayoutAlignItems: =LayoutAlignItems.Center
                      LayoutDirection: =LayoutDirection.Vertical
                      LayoutJustifyContent: =LayoutJustifyContent.Center
                      LayoutMinWidth: =50
                      LayoutMode: =LayoutMode.Auto
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                    Children:
                    - btnCopyDefaultButtonSecondary:
                        Control: Button
                        Properties:
                          Icon: ="Copy"
                          Text: =
                          LayoutMinWidth: =50
                          Width: =50
        - cntTabOutputCode:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              LayoutAlignItems: =LayoutAlignItems.Stretch
              LayoutDirection: =LayoutDirection.Vertical
              LayoutGap: =20
              LayoutJustifyContent: =LayoutJustifyContent.SpaceBetween
              LayoutMinHeight: =50
              LayoutMode: =LayoutMode.Auto
              PaddingBottom: =20
              PaddingLeft: =20
              PaddingRight: =20
              PaddingTop: =20
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
              Visible: =tabOutput.Selected.Value="Code"
            Children:
            - lblCode:
                Control: Text
                Properties:
                  Text: |-
                    =$"
                    MyTheme = {{
                        Colors: {{

                            // Primary Colors
                            Primary1: ColorValue(""{txtPrimary1.Value}""),
                            Primary2: ColorValue(""{txtPrimary2.Value}""),
                            Primary3: ColorValue(""{txtPrimary3.Value}""),
                            Primary4: ColorValue(""{txtPrimary4.Value}""),

                            // Accent Colors
                            Accent1: ColorValue(""{txtAccentColor1.Value}""),
                            Accent2: ColorValue(""{txtAccentColor2.Value}""),
                            Accent3: ColorValue(""{txtAccentColor3.Value}""),
                            Accent4: ColorValue(""{txtAccentColor4.Value}""),

                            // Neutral Colors
                            Neutral1: ColorValue(""{txtNeutralColor1.Value}""),
                            Neutral2: ColorValue(""{txtNeutralColor2.Value}""),
                            Neutral3: ColorValue(""{txtNeutralColor3.Value}""),
                            Neutral4: ColorValue(""{txtNeutralColor4.Value}"")
                        }},
                        Fonts: {{
                            Heading: ""{drpHeadingFont.SelectedText.Value}"",
                            Body: ""{drpBodyFont.SelectedText.Value}"",
                            Size: {{
                                Tiny: {numSizeTiny.Value},
                                Regular: {numSizeRegular.Value},
                                Subtitle: {numSizeSubtitle.Value},
                                Title: {numSizeTitle.Value},
                                Huge: {numSizeHuge.Value}
                            }}
                        }},
                        Icons:
                        {{
                            {Concat(colIcons,$"{Name}:""{Svg}""",",")}
                        }}    
                    }};
                    "
                  Wrap: =false
                  Height: =Parent.Height-btnCopyThemeCode.Height-Parent.PaddingTop-Parent.PaddingBottom-Parent.LayoutGap
            - btnCopyThemeCode:
                Control: Button
                Properties:
                  OnSelect: =Copy(lblCode.Text)
                  Icon: ="Copy"
                  Text: ="Copy"

```
{% endraw %}