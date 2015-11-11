# SoapDish
C# Generic SOAP client.


### Using SoapDish

```csharp
var client = SoapClient.Create("http://www.webservicex.net/globalweather.asmx");
var response = client.GetWeather(
    req =>  
    { 
        req.CountryName = "Spain",
        req.CityName = "Barcelona"
    }
);
```
**Async Example**

Using C# `await`:

```csharp
var client = SoapClient.Create("http://www.webservicex.net/globalweather.asmx");
var response = await client.GetWeatherAsync(
        req =>  
        { 
            req.CountryName = "Spain",
            req.CityName = "Barcelona"
        }
    );
```

Using Tasks:

```csharp
client.GetWeatherAsync(
    req =>  
    { 
        req.CountryName = "Spain",
        req.CityName = "Barcelona"
    })
  .Success(res => res.Print())
  .Failure(ex => { throw ex; } );
```
