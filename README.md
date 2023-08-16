# SystemTextJsonHelper

`SystemTextJsonHelper` is a C# helper class lib that simplifies the process of serializing and deserializing objects using the `System.Text.Json` namespace. It provides a flexible and convenient way to handle JSON serialization and deserialization with customizable options.

## Features

- Serialize objects to JSON strings with customizable options.
- Deserialize JSON strings back into objects with customizable options.
- Easily set global serialization options for consistent behavior across the application.



## Usage

To use the `SystemTextJsonHelper` in your project, follow these steps:

1. Install the package from [NuGet](https://www.nuget.org/packages/nightmaregaurav.systemtextjsonhelper).
2. import the `SystemTextJsonHelper` namespace.
3. Configure global options using `SetGlobalJsonSerializerOptions` method of `JsonHelper` class.
4. You can get current options using `GetJsonSerializerOptions` or `GetJsonSerializerOptions` to get default options.
5. Access static methods `Serialize` or `Deserialize` from the `JsonHelper` class for serialization and deserialization.

### Serialization

```csharp
var myObject = new MyCustomObject();
string json = JsonHelper.Serialize(myObject);

// With custom options:
string customJson = JsonHelper.Serialize(myObject, options => {
    // Customize the JsonSerializerOptions here
    options.IncludeFields = true;
    return options;
});
```

### Deserialization

```csharp
string jsonString = "{\"propertyName\": \"propertyValue\"}";
MyCustomObject deserializedObject = JsonHelper.Deserialize<MyCustomObject>(jsonString);

// With custom options:
MyCustomObject customDeserializedObject = JsonHelper.Deserialize<MyCustomObject>(jsonString, options => {
    // Customize the JsonSerializerOptions here
    options.PropertyNameCaseInsensitive = true;
    return options;
});
```

## License

`SystemTextJsonHelper` is released under the MIT License. You can find the full license details in the [LICENSE](LICENSE) file.

Made with ❤️ by [NightmareGaurav](https://github.com/nightmaregaurav).

---
Open For Contribution
---

We welcome contributions from the community. If you have suggestions, bug reports, or feature requests, please feel free to open issues or pull requests on [GitHub](https://github.com/nightmaregaurav/SystemTextJsonHelper).
