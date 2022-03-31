# JetBrains
This repository has information about JetBrains

https://www.jetbrains.com/help/dotcover/dotCover__Console_Runner_Commands.html#zip

Analyze code coverage without activating Resharper in Visaul Studio
Install command line tool
dotnet tool install JetBrains.dotCover.GlobalTool -g
Copy target files (so that dotnet will run)
    $source = "C:\Program Files\Microsoft Visual Studio\2022\Professional\Msbuild\Xamarin"
    $drain = "C:\Program Files\dotnet\sdk\6.0.200"

    cd $drain
    mkdir Xamarin
    cd Xamarin
    mkdir Android
    mkdir iOS

    copy-item $source/Android/Xamarin.Android.Aapt.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.Application.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.AvailableItems.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.Common.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.CSharp.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.D8.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.Designer.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.DesignTime.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.EmbeddedResource.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.Legacy.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.PCLSupport.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.SkipCases.projitems $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.Tooling.targets $drain/Xamarin/Android
    copy-item $source/Android/Xamarin.Android.Wear.targets $drain/Xamarin/Android

    copy-item $source/iOS/Xamarin.ImplicitFacade.targets $drain/Xamarin/iOS
    copy-item $source/iOS/Xamarin.iOS.Common.props $drain/Xamarin/iOS
    copy-item $source/iOS/Xamarin.iOS.Common.targets $drain/Xamarin/iOS
    copy-item $source/iOS/Xamarin.iOS.CSharp.targets $drain/Xamarin/iOS
    copy-item $source/iOS/Xamarin.Shared.props $drain/Xamarin/iOS
    copy-item $source/iOS/Xamarin.Shared.Stubs.targets $drain/Xamarin/iOS
    copy-item $source/iOS/Xamarin.Shared.targets $drain/Xamarin/iOS
Build solution with VS or cake

Invoke the analysis

dotnet dotcover test --no-build --dcReportType=HTML
View the analysis by opening dotCover.Output.html in a browser. This shous the percentage of covered code down to the method level. Also, when clicking on a method, you'll get the source code with coverage highlighting (green: line was covered in UT, red: it was not)
