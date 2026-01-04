# Settings

## Database file

The settings is configured the database file table `bewxx_Settings`. The following fields are applicable

|Attribute Group|Attribute|Value|Description|
|-|-|-|-|
|Base|HomeCountry|**Country**|Use this to remove your own country from the trip unique countries field. Use same spelling as in your notes and in the table `bewx_ContinentCountries`.|
|Base|LanguageFile|**Filename**|Filename to the translation file located in the **personal** folder, e.g. `swedish.json`.|
|Base|SqliteFile|**Relative path**|Path to the SQLite file relative to index.html (e.g. `personal/bewegung.db`).|
|Base|DatasetEditorUrl|**URL**|An URL to the webbased editor you use for the SQLite file. Could be used in conjunction with [libsql (Turso)](https://github.com/tursodatabase/libsql).|
|Base|Immich|**Disabled** or **Enabled**|Enable if you want filter links from all event dates to Immich.|
|Feature|ImmichUrl|**URL**|Online URL to the Immich installation (e.g. `https://immich.example.com/`).|

## Path to database

Change the relative path to the database file in `server_db_path.txt` if you want your own database to load automatically when self-hosting.




