---
title: BPF Generator
metadate: hide
categories:
  - canvasapp
  - generators
image: /assets/images/bpf-generator/image.png
authors:
  - cfernandez
---

###### Overview

This generator creates a Canvas App yaml code for a Business Process Flow bar.

###### How to use it

Copy the code below into an empty Power Apps Canvas App screen. Then click on the reset button.

<a id="copyCode" class="btn btn-sm btn-primary mt-2" href="#">Copy Code</a>

###### Code
{% raw %}
```yaml
- cntMainBPF:
    Control: GroupContainer
    Variant: verticalAutoLayoutContainer
    Properties:
      DropShadow: =DropShadow.None
      Height: =Parent.Height
      LayoutDirection: =LayoutDirection.Vertical
      LayoutMode: =LayoutMode.Auto
      RadiusBottomLeft: =0
      RadiusBottomRight: =0
      RadiusTopLeft: =0
      RadiusTopRight: =0
      Width: =Parent.Width
    Children:
    - cntBPF:
        Control: GroupContainer
        Variant: horizontalAutoLayoutContainer
        Properties:
          BorderStyle: =BorderStyle.None
          DropShadow: =DropShadow.None
          Fill: =RGBA(214, 221, 224, 1)
          FillPortions: =0
          Height: =80
          LayoutMode: =LayoutMode.Auto
          RadiusBottomLeft: =0
          RadiusBottomRight: =0
          RadiusTopLeft: =0
          RadiusTopRight: =0
          Width: =1366
        Children:
        - cntName:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              Fill: =RGBA(0, 113, 186, 1)
              FillPortions: =0
              LayoutAlignItems: =LayoutAlignItems.Stretch
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
            - lblName_2:
                Control: Text
                Properties:
                  FontColor: =RGBA(255, 255, 255, 1)
                  Size: =20
                  Text: =txtTitle.Value
                  Weight: ='TextCanvas.Weight'.Bold
            - lblTime_1:
                Control: Text
                Properties:
                  FontColor: =RGBA(255, 255, 255, 1)
                  Text: =txtSubTitle.Value
        - icnBack:
            Control: Classic/Icon
            Variant: ChevronLeft
            Properties:
              OnSelect: |+
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
                ForAll(Sequence(CountRows(Stages)),{Title:Index(Stages,Value).Title,Index:Value, IsSelected:ActiveStage=Value})
              DelayItemLoading: =true
              LayoutMinHeight: =50
              LoadingSpinner: =LoadingSpinner.Data
              TemplatePadding: =0
              TemplateSize: =If(Self.AllItemsCount>0,Self.Width/Self.AllItemsCount,50)
            Children:
            - cntStageItem_1:
                Control: GroupContainer
                Variant: verticalAutoLayoutContainer
                Properties:
                  BorderStyle: =BorderStyle.None
                  DropShadow: =DropShadow.None
                  Height: =Parent.Height
                  LayoutAlignItems: =LayoutAlignItems.Center
                  LayoutDirection: =LayoutDirection.Vertical
                  LayoutMode: =LayoutMode.Auto
                  RadiusBottomLeft: =0
                  RadiusBottomRight: =0
                  RadiusTopLeft: =0
                  RadiusTopRight: =0
                  Width: =Parent.TemplateWidth
                Children:
                - cntCircles_1:
                    Control: GroupContainer
                    Variant: manualLayoutContainer
                    Properties:
                      BorderStyle: =BorderStyle.None
                      DropShadow: =DropShadow.None
                      Height: =Parent.Height-lblStageName_1.Height
                      LayoutMinHeight: =50
                      RadiusBottomLeft: =0
                      RadiusBottomRight: =0
                      RadiusTopLeft: =0
                      RadiusTopRight: =0
                      Width: =Parent.Width
                    Children:
                    - cirOuter_1:
                        Control: Circle
                        Properties:
                          BorderColor: =If(ThisItem.IsSelected, App.Theme.Colors.Primary, App.Theme.Colors.Lighter80)
                          BorderThickness: =5
                          Fill: =App.Theme.Colors.PrimaryForeground
                          Height: =30
                          Width: =30
                          X: =Parent.Width/2-Self.Width/2
                          Y: =Parent.Height/2-Self.Height/2
                    - icnCompleted_1:
                        Control: Classic/Icon
                        Variant: CheckBadge
                        Properties:
                          Height: =30
                          Icon: =Icon.CheckBadge
                          Visible: =galStages.Selected.Index>ThisItem.Index Or Finished
                          Width: =30
                          X: =Parent.Width/2-Self.Width/2
                          Y: =Parent.Height/2-Self.Height/2
                    - cirInner_1:
                        Control: Circle
                        Properties:
                          Height: =10
                          Visible: =ThisItem.IsSelected And !Finished
                          Width: =10
                          X: =Parent.Width/2-Self.Width/2
                          Y: =Parent.Height/2-Self.Height/2
                - lblStageName_1:
                    Control: Text
                    Properties:
                      Align: ='TextCanvas.Align'.Center
                      Text: =ThisItem.Title
                      Weight: =If(ThisItem.IsSelected And !Finished, 'TextCanvas.Weight'.Bold, 'TextCanvas.Weight'.Regular )
                      Width: =Parent.Width
            - recRightLine_1:
                Control: Rectangle
                Properties:
                  Height: =4
                  Visible: =ThisItem.Index<galStages.AllItemsCount
                  Width: =Parent.TemplateWidth/2
                  X: =Parent.TemplateWidth/2
                  Y: =cirOuter_1.Height/2+cirOuter_1.Y
            - recLeftLine_1:
                Control: Rectangle
                Properties:
                  Height: =4
                  Visible: =ThisItem.Index>1
                  Width: =Parent.TemplateWidth/2
                  Y: =cirOuter_1.Height/2+cirOuter_1.Y
        - icnNext:
            Control: Classic/Icon
            Variant: ChevronLeft
            Properties:
              OnSelect: |+
                =If(galStages.Selected.Index<galStages.AllItemsCount,Select(galStages,galStages.Selected.Index+1),UpdateContext({Finished:true}));
              AlignInContainer: =AlignInContainer.Stretch
              Color: =RGBA(0, 0, 0, 1)
              Fill: =RGBA(255, 255, 255, 1)
              Icon: =Icon.ChevronRight
              Width: =20
    - cntBody:
        Control: GroupContainer
        Variant: horizontalAutoLayoutContainer
        Properties:
          DropShadow: =DropShadow.None
          LayoutMode: =LayoutMode.Auto
          RadiusBottomLeft: =0
          RadiusBottomRight: =0
          RadiusTopLeft: =0
          RadiusTopRight: =0
        Children:
        - cntLeftPanel:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              DropShadow: =DropShadow.None
              LayoutDirection: =LayoutDirection.Vertical
              LayoutMode: =LayoutMode.Auto
              PaddingLeft: =20
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
            Children:
            - cntTitle:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  BorderStyle: =BorderStyle.None
                  DropShadow: =DropShadow.None
                  Height: =50
                  LayoutGap: =10
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
                - lblTitle:
                    Control: Text
                    Properties:
                      Text: ="Title"
                      X: =33
                      Y: =192
                - txtTitle:
                    Control: TextInput
                    Properties:
                      Value: =Title
                      X: =176
                      Y: =192
            - cntSubTitle:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  BorderStyle: =BorderStyle.None
                  DropShadow: =DropShadow.None
                  Height: =50
                  LayoutGap: =10
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
                - lblSubTitle:
                    Control: Text
                    Properties:
                      Text: ="Sub Title"
                      X: =33
                      Y: =238
                - txtSubTitle:
                    Control: TextInput
                    Properties:
                      Value: =SubTitle
                      X: =143
                      Y: =46
            - cntNewStage:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  BorderStyle: =BorderStyle.None
                  DropShadow: =DropShadow.None
                  Height: =50
                  LayoutGap: =10
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
                - lblNewStage:
                    Control: Text
                    Properties:
                      Text: ="New Stage"
                      X: =33
                      Y: =294
                - txtNewStage:
                    Control: TextInput
                    Properties:
                      Value: =NewStage
                      Width: =202
                      X: =143
                      Y: =294
                - btnAdd:
                    Control: Button
                    Properties:
                      OnSelect: |+
                        =If(
                            // Check the new stage name is not empty and it doesn't exist already
                            !IsBlank(txtNewStage.Value) And CountRows(
                                Filter(
                                    Stages,
                                    Lower(Title) = Lower(txtNewStage.Value)
                                )
                            ) = 0,
                            // Add the new stage to the table
                            UpdateContext(
                                {
                                    NewStage: "",
                                    Stages: Collect(
                                        Stages,
                                        {Title: txtNewStage.Value}
                                    )
                                }
                            );
                            Reset(txtNewStage);
                        );

                      Icon: ="Add"
                      Text: ="Add"
                      X: =367
                      Y: =294
            - lblStages:
                Control: Text
                Properties:
                  Text: ="Stages"
                  Weight: ='TextCanvas.Weight'.Bold
                  AlignInContainer: =AlignInContainer.Stretch
                  X: =33
                  Y: =396
            - galStagesConfig:
                Control: Gallery
                Variant: galleryVertical
                Properties:
                  Items: =Stages
                  DelayItemLoading: =true
                  Height: =272
                  Layout: =Layout.Vertical
                  LoadingSpinner: =LoadingSpinner.Data
                  TemplateSize: =44
                  Width: =171
                  X: =33
                  Y: =32
                Children:
                - icnDelete:
                    Control: Classic/Icon
                    Variant: Trash
                    Properties:
                      OnSelect: =UpdateContext({Stages:Filter(Stages,Title<>ThisItem.Title)})
                      Height: =25
                      Icon: =Icon.Trash
                      Width: =41
                      X: =425
                      Y: =7
                - txtStageNameItem:
                    Control: Text
                    Properties:
                      Text: =ThisItem.Title
                      Height: =28
                      Width: =406
                      Y: =4
            - btnResetAll:
                Control: Button
                Properties:
                  OnSelect: |-
                    =UpdateContext(
                        {
                            Title: "Ticket Resolution Process",
                            SubTitle: "Active for less than one minute",
                            ActiveStage: 1,
                            Finished: false,
                            NewStage: "",
                            Stages: Table(
                                {Title: "Identify"},
                                {Title: "Process"},
                                {Title: "Document"},
                                {Title: "Complete"}
                            )
                        }
                    );
                    Reset(galStages);
                  Icon: ="ArrowSync"
                  Text: ="Reset"
                  AlignInContainer: =AlignInContainer.Center
                  Width: =150
                  X: =33
                  Y: =120
            - btnCopyCode:
                Control: Button
                Properties:
                  OnSelect: =Copy(lblGeneratedCode.Text)
                  Icon: ="Copy"
                  Text: ="Copy"
                  AlignInContainer: =AlignInContainer.Center
                  Width: =150
                  X: =33
                  Y: =120
        - lblGeneratedCode:
            Control: Text
            Properties:
              Text: |-
                =$"
                - btnReset:
                    Control: Button
                    Properties:
                      OnSelect: |-
                        =UpdateContext(
                            {{
                                MyBPF: {{
                                    Title: ""{Title}"",
                                    SubTitle: ""{SubTitle}"",
                                    ActiveStage: 1,
                                    Finished:false,
                                    Stages: Table({Concat(Stages,$"{{Title: ""{Title}""}}",",")}                
                                        )
                                }}
                            }}
                        );
                        Select(galStages,MyBPF.ActiveStage)
                      Text: =""Reset""
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
                            ForAll(Sequence(CountRows(MyBPF.Stages)),{{Title:Index(MyBPF.Stages,Value).Title,Index:Value, IsSelected:MyBPF.ActiveStage=Value}})
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
                            =If(galStages.Selected.Index<galStages.AllItemsCount,Select(galStages,galStages.Selected.Index+1),UpdateContext({{MyBPF:Patch(MyBPF,{{Finished:true}})}}));
                          AlignInContainer: =AlignInContainer.Stretch
                          Color: =RGBA(0, 0, 0, 1)
                          Fill: =RGBA(255, 255, 255, 1)
                          Icon: =Icon.ChevronRight
                          Width: =20
                "
              AlignInContainer: =AlignInContainer.Stretch
              FillPortions: =1

```
{% endraw %}