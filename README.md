# CryptoHelper
:key: Cryptography helper methods for hashing passwords using a PBKDF2 implementation.

<hr>

| Windows | Linux | OS X |
| --- | --- | --- |
| [![Build status](https://ci.appveyor.com/api/projects/status/hai0kndijmx6xb9d?svg=true)](https://ci.appveyor.com/project/henkmollema/cryptohelper) | [![Build Status](https://travis-ci.org/henkmollema/CryptoHelper.svg)](https://travis-ci.org/henkmollema/CryptoHelper) | [![Build Status](https://travis-ci.org/henkmollema/CryptoHelper.svg)](https://travis-ci.org/henkmollema/CryptoHelper) |

--

This utility ports the password hashing functionality from the  [`System.Web.Helpers.Crypto`](http://aspnetwebstack.codeplex.com/SourceControl/latest#src/System.Web.Helpers/Crypto.cs) class to DNX. On DNX the new ASP.NET 5 Data Protection stack is used. Where as classic .NET 4.0 and 4.5 applications  will use `Rfc2898DeriveBytes` 

<hr>

## Installation

#### Add the [CryptoHelper NuGet package](https://www.nuget.org/packages/CryptoHelper) to your project
Add this to your `project.json`:
```json
"dependencies": {
    "CryptoHelper": "1.0.0-rc1-*"
}
```

--

#### Download using the NuGet Package Manager Console
```
Install-Package CryptoHelper
```

<hr>

## Usage
```csharp
using CryptoHelper;

// ...

public string HashPassword(string password)
{
    return Crypto.HashPassword(password);
}

public bool VerifyPassword(string hash, string password)
{
    return Crypto.VerifyHashedPassword(hash, password);
}
```
