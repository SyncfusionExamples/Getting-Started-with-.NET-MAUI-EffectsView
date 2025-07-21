# Getting Started with .NET MAUI EffectsView (SfEffectsView)

This section provides a quick overview for working with the SfEffectsView for .NET MAUI. Walk through the entire process of creating a real world of this control.

## Creating an application using the .NET MAUI Effects View
 1. Create a new .NET MAUI application in Visual Studio.
 2. Syncfusion .NET MAUI components are available on [nuget.org](https://www.nuget.org/). To add SfBadgeView to your project, open the NuGet package manager in Visual Studio, search for Syncfusion.Maui.Core and then install it.

## Register the handler

To use this control inside an application, you must register the handler for Syncfusion® core.

```C#

using Microsoft.Extensions.Logging;
using Syncfusion.Maui.Core.Hosting;

namespace BadgeViewGettingStarted
{
    public static class MauiProgram
    {
        public static MauiApp CreateMauiApp()
        {
            var builder = MauiApp.CreateBuilder();
            builder
                .UseMauiApp<App>()
                .ConfigureSyncfusionCore()
                .ConfigureFonts(fonts =>
                {
                    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                    fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
                });

#if DEBUG
    		builder.Logging.AddDebug();
#endif

            return builder.Build();
        }
    }
}

```

## Add a basic Effects View
1. Import the control namespace `Syncfusion.Maui.Core` in XAML or C# code.
2. Initialize the [SfEffectsView](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Core.SfEffectsView.html) control.

```xml
<ContentPage   
    . . .
    xmlns:badgeView="clr-namespace:Syncfusion.Maui.Core;assembly=Syncfusion.Maui.Core">

   <effectsView:SfEffectsView /> 
</ContentPage>
```

```C#
using Syncfusion.Maui.Core;
. . .

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        effectsView = new SfEffectsView(); 
        this.Content = effectsView;  
    }
}
```

## Adding a content in .NET MAUI Effects View

```
    <Border HorizontalOptions="Center" VerticalOptions="Center">
        <Border.StrokeShape>
            <RoundRectangle CornerRadius="18" />
        </Border.StrokeShape>
        <Border.Background>
            <LinearGradientBrush EndPoint="1,0">
                <GradientStop Color="#4E54C8" Offset="0.0" />
                <GradientStop Color="#8F94FB" Offset="1.0" />
            </LinearGradientBrush>
        </Border.Background>
        <effectsView:SfEffectsView>
            <Grid>
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="90" />
                    <ColumnDefinition Width="*"/>
                </Grid.ColumnDefinitions>

                <Image Source="laura.png" Margin="7" VerticalOptions="Center"
                               WidthRequest="72" HeightRequest="72" />
                <StackLayout Grid.Column="1" VerticalOptions="Center">
                    <Label Text="Laura Steffi" Margin="10,0,10,0" FontSize="18" />
                    <Label Text="Data Science Analyst" Margin="10,0,10,0" FontSize="12"/>
                </StackLayout>
            </Grid>
        </effectsView:SfEffectsView>
    </Border>

```

Run the application to render the following output:

![Getting started with .NET MAUI Effects View](RippleEffect.gif)
