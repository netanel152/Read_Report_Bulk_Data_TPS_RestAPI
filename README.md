# Read_Bulks_TPS_RestAPI

A .NET Web API designed to simulate and retrieve bulk purchase data. This project demonstrates a layered architecture pattern (Controller -> Manager -> Repository) for handling bulk data retrieval requests via a RESTful endpoint.

## Features

- **Bulk Data Retrieval**: specific bulk retrieval of purchase records based on a starting date and amount.
- **Layered Architecture**: Separation of concerns using Managers and Repositories.
- **Swagger UI**: Integrated Swagger for easy API testing and documentation.

## Prerequisites

- [.NET SDK](https://dotnet.microsoft.com/download) (Compatible with the version specified in the project files, likely .NET 6, 7, or 8).
- An IDE like Visual Studio or VS Code.

## Getting Started

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Read_Report_Bulk_Data_TPS_RestAPI
   ```

2. **Build the project**
   ```bash
   dotnet build
   ```

3. **Run the application**
   ```bash
   dotnet run --project Read_Bulks_TPS_RestAPI
   ```

   The application will likely start on `http://localhost:5207` (check your console output or `launchSettings.json`).

## API Documentation

### Get Bulk Purchases

Retrieves a specific amount of purchase records starting from a given date.

- **URL**: `/api/Purchase/getBulkPurchases`
- **Method**: `POST`
- **Content-Type**: `application/json`

#### Request Body

| Field | Type | Description |
| :--- | :--- | :--- |
| `startFrom` | `DateTimeOffset` | The starting date and time for the bulk retrieval. |
| `bulkAmount` | `int` | The number of records to retrieve. |

**Example Request:**

```json
{
  "startFrom": "2023-01-10T09:00:00+02:00",
  "bulkAmount": 5
}
```

#### Response

Returns a list of purchase objects matching the criteria.

## Project Structure

- **Controllers**: Handles incoming HTTP requests (`PurchaseController`).
- **Manager**: Business logic layer (`PurchaseManager`).
- **Repositories**: Data access layer (`PurchaseRepository`).
- **Models**: Data transfer objects and entity definitions (`Purchase`, `RequestBulkPurchase`).

## Swagger

If running in the **Development** environment, you can access the interactive API documentation at:

```
https://localhost:<port>/swagger
```