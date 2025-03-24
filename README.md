# What's New in .NET 10

## Table of Contents
- [ .NET Runtime Enhancements](#net-runtime-enhancements)
- [ .NET Libraries Improvements](#net-libraries-improvements)
- [ .NET SDK Updates](#net-sdk-updates)
- [ ASP.NET Core Enhancements](#aspnet-core-enhancements)
  - [ Blazor Improvements](#blazor-improvements)
  - [ OpenAPI Improvements](#openapi-improvements)
  - [ Minimal APIs](#minimal-apis)
  - [ Authentication and Authorization](#authentication-and-authorization)

## .NET Runtime Enhancements
- **Array Interface Method Devirtualization:** The JIT can now devirtualize and inline array interface methods, improving performance for array enumerations.
- **Array Enumeration De-Abstraction:** Reduces abstraction overhead for array iteration via enumerators, enabling better inlining and stack allocation.
- **Inlining of Late Devirtualized Methods:** The JIT can now inline methods that become eligible for devirtualization due to previous inlining.
- **Devirtualization Based on Inlining Observations:** Utilizes precise type information from inlining to devirtualize subsequent calls.
- **Stack Allocation of Arrays of Value Types:** Small, fixed-sized arrays of value types without garbage collector pointers can now be stack-allocated.
- **AVX10.2 Support:** Introduces support for Advanced Vector Extensions (AVX) 10.2 for x64-based processors, though currently disabled by default.

## .NET Libraries Improvements
- **Certificate Thumbprint Flexibility:** A new method allows finding certificates using hash algorithms like SHA-256, beyond SHA-1.
- **PEM Encoding Enhancements:** PEM encoding APIs now support reading directly from ASCII/UTF-8 data.
- **ISOWeek Support for DateOnly:** New overloads in the ISOWeek class support the DateOnly type.
- **String Normalization for Spans:** New APIs allow Unicode string normalization to work with spans of characters, reducing allocations.
- **Numeric Ordering for String Comparison:** A new `CompareOptions.NumericOrdering` option enables numerical string comparisons.
- **TimeSpan.FromMilliseconds Overload:** A single-parameter overload resolves issues with LINQ expressions.
- **ZipArchive Performance:** Optimizations reduce memory usage and improve performance for ZipArchive in Update mode and parallel extraction.
- **OrderedDictionary Enhancements:** New TryAdd and TryGetValue overloads return an index for fast access.
- **JSON Serialization Updates:** Source generators now allow specifying ReferenceHandler in JsonSourceGenerationOptionsAttribute.
- **Left-Handed Matrix Transformations:** New APIs for creating left-handed transformation matrices.
- **PKCS#12 Export Enhancements:** New methods allow specifying encryption and digest algorithms for PKCS#12/PFX export.

## .NET SDK Updates
- **Pruning of Framework-Provided Package References:** Automatically removes unused framework-provided package references, reducing build times and disk usage.
- **Consistent Command Order:** New noun-first aliases for `dotnet` CLI commands improve readability and consistency.

## ASP.NET Core Enhancements
### Blazor Improvements
- Added the `ReconnectModal` component to the Blazor Web App project template for improved reconnection UI control.
- The `NavigateTo` method no longer scrolls to the top for same-page navigation.
- The `NavLink` component now ignores query strings and fragments when using `NavLinkMatch.All`.
- Added the `RowClass` parameter to `QuickGrid` for applying styles to rows based on their data.
- Added the `CloseColumnOptionsAsync` method to `QuickGrid` for programmatically closing column options.
- Blazor framework script is now served as a static web asset with precompression and fingerprinting enabled.

### OpenAPI Improvements
- Added support for generating OpenAPI version 3.1 documents.
- Added support for serving OpenAPI documents in YAML format.
- Populated XML doc comments into OpenAPI documents.

### Minimal APIs
- Improved integration testing for apps using top-level statements.
- Empty strings in form posts are now treated as null for nullable value types.

### Authentication and Authorization
- Added new metrics for authentication and authorization events.
