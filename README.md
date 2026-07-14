# EXPX Authentication Native AOT

Small WinForms example project for the EXPX authentication SDK with Native AOT enabled.

This sample includes:

- a simple login/register desktop UI
- SDK initialization on startup
- signed response validation through the embedded public key
- Native AOT-friendly JSON source generation in the SDK layer

## Project layout

- `EXPX_Authentication_NativeAot.sln` - solution file
- `EXPX_Authentication_NativeAot/Form1.cs` - example UI logic
- `EXPX_Authentication_NativeAot/Form1.Designer.cs` - form layout
- `EXPX_Authentication_NativeAot/txa_native.cs` - SDK implementation

## Setup

Open `EXPX_Authentication_NativeAot/Form1.cs` and update the app credentials:

```csharp
private static readonly EXPX Auth = new EXPX(
    name: "test",
    secret: "EXPX-ZKOM4LP9DA",
    version: "1.0"
);
```

Replace those values with your own application name, secret, and version.

## Run

From the solution folder:

```powershell
dotnet build
dotnet run --project .\EXPX_Authentication_NativeAot\EXPX_Authentication_NativeAot.csproj
```

Or open the solution in Visual Studio and run it normally.

## Publish Native AOT

```powershell
dotnet publish .\EXPX_Authentication_NativeAot\EXPX_Authentication_NativeAot.csproj -c Release
```

## Notes

- The form initializes the SDK when the window is shown.
- Login and register buttons are already wired to the SDK.
- If you change the backend signing key, update the embedded public key in `expx_native.cs` and rebuild.
