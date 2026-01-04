# Create the dataset

## Database Structure

|Table|Type|Description|
|-|-|-|
|**bewa_Overview**|Table|The table that defines your trips. One trip per row.|
|**bewb_Events**|Table|The table containg detailed notes from your trips. One row per day (date).|
|**bewx_ParticipantGroups**|Table|Your travel groups. Feel free to edit.|
|**bewx_TripDomains**|Table|Trip types.|
|**bewxx_Settings**|Table|App settings storage (used when you bind the file to browser via File API).|

For more detailed instructions, follow the [Trip Syntax](trip-syntax.html).

> [!TIP]
> Download a pre-filled [SQLite template file](https://github.com/plans-coding/immer-in-bewegung/raw/refs/heads/main/personal/bewegung.db) and edit the tables within.

> [!NOTE]
> To obtain coordinates for a given position, you can use the [Coordinate Tool](https://online.bewegung.app/coordinate-tool.html) and easily copy and paste the coordinates into the SQLite file.
