---
title: Basic Generator
metadata: hide
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
{% raw %}
```yaml

- btnReset:
    Control: Button
    Properties:
      OnSelect: |-
        =UpdateContext(
            {
                MyBPF: {
                    Title: "Ticket Resolution Process",
                    SubTitle: "Active for less than one minute",
                    ActiveStage: 1,
                    Finished:false,
                    Stages: Table({Title: "Identify"},{Title: "Process"},{Title: "Document"},{Title: "Complete"}                
                        )
                }
            }
        );
        Select(galStages,MyBPF.ActiveStage)
      Text: ="Reset"
      X: =1224
      Y: =132
- cntBPF:
    Control: GroupContainer
    Variant: horizontalAutoLayoutContainer
    Properties:
      Fill: =RGBA(214, 221, 224, 1)
      Height: =80
      LayoutMode: =LayoutMode.Auto
      Width: =1366
      X: =0
      Y: =0
    Children:
    - cntName:
        Control: GroupContainer
        Variant: verticalAutoLayoutContainer
        Properties:
          DropShadow: =DropShadow.None
          Fill: =RGBA(0, 113, 186, 1)
          FillPortions: =0
          LayoutDirection: =LayoutDirection.Vertical
          LayoutMinHeight: =50
          LayoutMode: =LayoutMode.Auto
          PaddingBottom: =5
          PaddingLeft: =20
          PaddingRight: =5
          PaddingTop: =5
          RadiusBottomLeft: =0
          RadiusBottomRight: =0
          RadiusTopLeft: =0
          RadiusTopRight: =0
          Width: =300
        Children:
        - lblName:
            Control: Text
            Properties:
              FontColor: =RGBA(255, 255, 255, 1)
              Size: =20
              Text: =MyBPF.Title
              Weight: ='TextCanvas.Weight'.Bold
              AlignInContainer: =AlignInContainer.Stretch
              FillPortions: =2
              LayoutMinHeight: =10
        - lblTime:
            Control: Text
            Properties:
              FontColor: =RGBA(255, 255, 255, 1)
              Text: =MyBPF.SubTitle
              AlignInContainer: =AlignInContainer.Stretch
              FillPortions: =1
              LayoutMinHeight: =10
    - icnBack:
        Control: Classic/Icon
        Variant: ChevronLeft
        Properties:
          OnSelect: |
            =If(galStages.Selected.Index>1,Select(galStages,galStages.Selected.Index-1));
          AlignInContainer: =AlignInContainer.Stretch
          Color: =RGBA(0, 0, 0, 1)
          Fill: =RGBA(255, 255, 255, 1)
          Icon: =Icon.ChevronLeft
          Width: =20
    - galStages:
        Control: Gallery
        Variant: BrowseLayout_Horizontal_TwoTextOneImageVariant_ver5.0
        Properties:
          Items: |-
            =// It automatically adds an index column to the stages collection
            ForAll(Sequence(CountRows(MyBPF.Stages)),{Title:Index(MyBPF.Stages,Value).Title,Index:Value, IsSelected:MyBPF.ActiveStage=Value})
          DelayItemLoading: =true
          LayoutMinHeight: =Parent.Height
          LayoutMinWidth: =100
          LoadingSpinner: =LoadingSpinner.Data
          TemplatePadding: =0
          TemplateSize: =If(Self.AllItemsCount>0,Self.Width/Self.AllItemsCount,50)
        Children:
        - cntStageItem:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              BorderStyle: =BorderStyle.None
              DropShadow: =DropShadow.None
              Height: =Parent.Height
              LayoutAlignItems: =LayoutAlignItems.Center
              LayoutDirection: =LayoutDirection.Vertical
              LayoutMode: =LayoutMode.Auto
              Width: =Parent.TemplateWidth
            Children:
            - cntCircles:
                Control: GroupContainer
                Variant: manualLayoutContainer
                Properties:
                  AlignInContainer: =AlignInContainer.Center
                  BorderStyle: =BorderStyle.None
                  DropShadow: =DropShadow.None
                  Height: =Parent.Height-lblStageName.Height
                  LayoutMinHeight: |
                    =cirOuter.Height/2+cirOuter.Y
                  RadiusBottomLeft: =0
                  RadiusBottomRight: =0
                  RadiusTopLeft: =0
                  RadiusTopRight: =0
                  Width: =Parent.Width
                Children:
                - cirOuter:
                    Control: Circle
                    Properties:
                      BorderColor: =If(ThisItem.IsSelected, App.Theme.Colors.Primary, App.Theme.Colors.Lighter80)
                      BorderThickness: =5
                      Fill: =App.Theme.Colors.PrimaryForeground
                      Height: =30
                      Width: =30
                      X: =Parent.Width/2-Self.Width/2
                      Y: =Parent.Height/2-Self.Height/2
                - cirInner:
                    Control: Circle
                    Properties:
                      Height: =10
                      Visible: =ThisItem.IsSelected And !MyBPF.Finished
                      Width: =10
                      X: =Parent.Width/2-Self.Width/2
                      Y: =Parent.Height/2-Self.Height/2
                - icnCompleted:
                    Control: Classic/Icon
                    Variant: CheckBadge
                    Properties:
                      Height: =30
                      Icon: =Icon.CheckBadge
                      Visible: =galStages.Selected.Index>ThisItem.Index Or MyBPF.Finished
                      Width: =30
                      X: =Parent.Width/2-Self.Width/2
                      Y: =Parent.Height/2-Self.Height/2
            - lblStageName:
                Control: Text
                Properties:
                  Align: ='TextCanvas.Align'.Center
                  Text: =ThisItem.Title
                  Weight: =If(ThisItem.IsSelected And !MyBPF.Finished, 'TextCanvas.Weight'.Bold, 'TextCanvas.Weight'.Regular )
                  Width: =Parent.Width
        - recLeftLine:
            Control: Rectangle
            Properties:
              Height: =4
              Visible: =ThisItem.Index>1
              Width: =Parent.TemplateWidth/2
              Y: =cirOuter.Height/2+cirOuter.Y
        - recRightLine:
            Control: Rectangle
            Properties:
              Height: =4
              Visible: =ThisItem.Index<galStages.AllItemsCount
              Width: =Parent.TemplateWidth/2
              X: =Parent.TemplateWidth/2
              Y: =cirOuter.Height/2+cirOuter.Y
    - icnNext:
        Control: Classic/Icon
        Variant: ChevronLeft
        Properties:
          OnSelect: |
            =If(galStages.Selected.Index<galStages.AllItemsCount,Select(galStages,galStages.Selected.Index+1),UpdateContext({MyBPF:Patch(MyBPF,{Finished:true})}));
          AlignInContainer: =AlignInContainer.Stretch
          Color: =RGBA(0, 0, 0, 1)
          Fill: =RGBA(255, 255, 255, 1)
          Icon: =Icon.ChevronRight
          Width: =20
```
{% endraw %}