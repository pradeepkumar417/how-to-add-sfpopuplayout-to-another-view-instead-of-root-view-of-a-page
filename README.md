# how-to-add-sfpopuplayout-to-another-view-instead-of-root-view-of-a-page

## About the sample

This repository contains sample that demonstrates how to add SfPopupLayout inside a Grid Layout

```c#

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms"
             mc:Ignorable="d"
             x:Class="Popup.MainPage">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="50"/>
        </Grid.RowDefinitions>
        
        <sfPopup:SfPopupLayout x:Name="popUpLayout" Grid.Row="0">
            
            <sfPopup:SfPopupLayout.PopupView>
                
                <sfPopup:PopupView HeightRequest="230"
                           HeaderTitle="Popup view"
                           ShowFooter="False">
                    <sfPopup:PopupView.ContentTemplate>
                        <DataTemplate>
                            <StackLayout Padding="10">
                            <Label Text="SfPopupLayout is loaded inside xamarin forms Grid"
                           WidthRequest="260"
                           BackgroundColor="White"
                           HorizontalOptions="FillAndExpand" />
                            </StackLayout>
                        </DataTemplate>
                    </sfPopup:PopupView.ContentTemplate>
                </sfPopup:PopupView>
                
            </sfPopup:SfPopupLayout.PopupView>
            
            <sfPopup:SfPopupLayout.Content>
                <StackLayout x:Name="mainLayout">
                    <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" 
                            VerticalOptions="Start" 
                            HorizontalOptions="FillAndExpand" 
                            Clicked="Button_Clicked" />
                </StackLayout>
            </sfPopup:SfPopupLayout.Content>
            
        </sfPopup:SfPopupLayout>
    </Grid>
</ContentPage>

```

```c#

        private void Button_Clicked(object sender, EventArgs e)
        {
            popUpLayout.Show();
        }

```

Screenshot

![Xamarin-forms-popup-in-Grid](Screenshot/Xamarin-forms-popup-in-Grid.png)

