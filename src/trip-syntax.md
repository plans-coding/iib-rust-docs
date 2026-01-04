# Trip Syntax

## Table: Overview

The first table in your SQLite file is named `bewa_Overview` with fields according to following.

> [!NOTE]
> Regarding validation: Some fields are checked for syntax and must comply to that.

|Column|Description|
|-|-|
|InnerId|The InnerId is used to connect each row to date notes in table `bewb_Events`. It consists of a letter and a number **without any dashes** or other characters. The letter specifies the Trip Domain, e.g. **domestic** (I), **abroad** (U), or **attachment** (D) (see separate definition). The number is a chronological number, where the first trip in each letter category is marked as **1**. E.g. **U23** for abroad trip number 23.  *Use **X** if you want to exclude the row from the web app.*<br /><br />**Syntax:** `<one letter trip domain abbreviation><a serial number>`
|ParticipantGroup|Could e.g. be **Family**, **Private**, or **Work**.<br /><br />**Syntax:** `<string that must exist in table bewx_ParticipantGroups>`
|OuterId|The OuterID is exposed to end-user of the web app. It uses a letter and a index number **separated by dash**, where the letter is a abbreviation of the Trip Domain and a chronological index number. E.g. **F-3** (family trip 3), **P-12** (private trip 12), or **W-4** (work trip 4).<br /><br />**Syntax:** `<letters and dashes and serial numbers of your choice>`
|OverallDestination|Type in you trip primary destination. E.g. **Finland**, or **Italia, Spain etc.**<br /><br />**Syntax:** `<string>`
|DepartureDate|Your departure date in ISO format.<br /><br />**Syntax:** `YYYY-MM-DD`
|ReturnDate|Your return date in ISO format.<br /><br />**Syntax:** `YYYY-MM-DD`
|MapPins|The main stops of your trip that you want to plot on the map.<br /><br />**Syntax (multi-line accepted):** `{ NAME_OF_MAP_PIN  \| LATITUDE, LONGITUDE }`
|TripDescription|A short description that explain the aim of the trip. E.g. **My fantastic summer trip to France**.<br /><br />**Syntax:** `<string>`
|PhotoStarttime|*For use with Immich.* If you leave your home at let say 8 pm and don't want to include photos from earlier on **departure day**, then you can set a time here. If left empty, all photos from departure day will be included.<br /><br />**Syntax:** `HH:MM`
|PhotoEndtime|*For use with Immich.* Same as above, but for **return day**.<br /><br />**Syntax:** `HH:MM`

## Table: Events
The second table in your SQLite file is named `bewb_Events` with fields according to following.

> [!NOTE]
> Regarding validation: Some fields are checked for syntax and must comply to that.

|Column Name|Description|
|-|-|
|InnerId|Reference to corresponding InnerId in table `bewa_Overview`.<br /><br />**Syntax:** `<one letter trip domain abbreviation><a serial number>`
|Date|Your date in ISO format.<br /><br />**Syntax:** `YYYY-MM-DD`
|Events|This is your fully description of what you did this day.<br /><br />**Syntax (multi-line accepted):** `<string>`
|Accommodation|The name and the address of your accommodation.<br /><br />**Syntax:** `<string>`
|AccommodationCountry|The name of the country you stayed in during the night.<br /><br />**Syntax:** `<string>`
|AccommodationCoordinateAccuracy|Possibility to mark the accuracy of the coordinates.<br /><br />**Syntax:** `<string>`
|AccommodationCoordinates|The gps coordinates of your accommodation, e.g. **59.329444, 18.068611**.<br /><br />**Syntax:** `lat_decimal,lng_decimal`
|TravelParticipants|The name of your travel buddies, separated by comma. **N.B.** *Not exposured in web app.*<br /><br />**Syntax:** `<string>`
|AdditionalNotes|**N.B.** *Additional notes not exposured in web app.*<br /><br />**Syntax (multi-line accepted):** `<string>`
|CountriesDuringDay|This field is for enhanced statistics. Enter all countries in cronologial order during that day, separated by comma. The country names need to conform to the country names defined in `settings.yaml`. In front of the country name prefix `*`, `**`, and `+` is allowed. Read more under [Appendix](./appendix).<br /><br />**Syntax (prefix allowed):** `<country name without space>, <country name without space>, <country name without space> [...]`

## Table: Continent Countries

The third table in your SQLite file is named `bewx_ContinentCountries` with fields according to following.

|Column Name|Description|
|-|-|
|Continent|The name of the continent the country belongs too.<br /><br />**Syntax:** `<continent name>`
|Country|Add the name of countries you want to define. This must be in same language as the field `CountriesDuringDay` in `bewb_Events`.<br /><br />**Syntax:** `<country name without space, use dash instead>`

### Make other country definitions (or translate country names)

If you want to change the pre-defined country settings you can do it by changing in the country definitions. Only countries defined in the table `bewx_ContinentCountries`  can be used in your trip notes and only with the very exact spelling.

> [!TIP]
> Other language: If you have the countries in `bewb_Events` (**CountriesDuringDay**)  written in another languange than English, then you can change the app behaviour by translating the countries in the table `bewx_ContinentCountries` to your own language.

```Pre-defined countries"
Europe
      - Albania
      - Andorra
      - Austria
      - Belarus
      - Belgium
      - Bosnia and Herzegovina
      - Bulgaria
      - Croatia
      - Cyprus
      - Czech Republic
      - Denmark
      - Estonia
      - Finland
      - Finland-Åland
      - France
      - Georgia
      - Germany
      - Greece
      - Hungary
      - Iceland
      - Ireland
      - Italy
      - Kosovo
      - Latvia
      - Liechtenstein
      - Lithuania
      - Luxembourg
      - Malta
      - Moldova
      - Moldova-Transnistria
      - Monaco
      - Montenegro
      - Netherlands
      - North Macedonia
      - Norway
      - Poland
      - Portugal
      - Romania
      - Russia
      - San Marino
      - Serbia
      - Slovakia
      - Slovenia
      - Spain
      - Sweden
      - Switzerland
      - Ukraine
      - United Kingdom
      - United Kingdom-Akrotiri and Dhekelia
      - United Kingdom-Gibraltar
      - United Kingdom-Jersey
      - Vatican City

Asia
      - Afghanistan
      - Armenia
      - Azerbaijan
      - Bahrain
      - Bangladesh
      - Bhutan
      - Brunei
      - Cambodia
      - China
      - Cyprus
      - Georgia
      - India
      - Indonesia
      - Iran
      - Iraq
      - Israel
      - Japan
      - Jordan
      - Kazakhstan
      - Kuwait
      - Kyrgyzstan
      - Laos
      - Lebanon
      - Malaysia
      - Maldives
      - Mongolia
      - Myanmar
      - Nepal
      - North Korea
      - Oman
      - Pakistan
      - Philippines
      - Qatar
      - Russia
      - Saudi Arabia
      - Singapore
      - South Korea
      - Sri Lanka
      - Syria
      - Taiwan
      - Tajikistan
      - Thailand
      - Timor-Leste
      - Turkey
      - Turkmenistan
      - United Arab Emirates
      - Uzbekistan
      - Vietnam
      - Yemen

North America
      - Antigua and Barbuda
      - Bahamas
      - Barbados
      - Belize
      - Canada
      - Costa Rica
      - Cuba
      - Dominica
      - Dominican Republic
      - El Salvador
      - Grenada
      - Guatemala
      - Haiti
      - Honduras
      - Jamaica
      - Mexico
      - Nicaragua
      - Panama
      - Saint Kitts and Nevis
      - Saint Lucia
      - Saint Vincent and the Grenadines
      - Trinidad and Tobago
      - United States

South America
      - Argentina
      - Bolivia
      - Brazil
      - Chile
      - Colombia
      - Ecuador
      - Guyana
      - Paraguay
      - Peru
      - Suriname
      - Uruguay
      - Venezuela

Africa
      - Algeria
      - Angola
      - Benin
      - Botswana
      - Burkina Faso
      - Burundi
      - Cabo Verde
      - Cameroon
      - Central African Republic
      - Chad
      - Comoros
      - Democratic Republic of the Congo
      - Djibouti
      - Egypt
      - Equatorial Guinea
      - Eritrea
      - Eswatini
      - Ethiopia
      - Gabon
      - Gambia
      - Ghana
      - Guinea
      - Guinea-Bissau
      - Ivory Coast
      - Kenya
      - Lesotho
      - Liberia
      - Libya
      - Madagascar
      - Malawi
      - Mali
      - Mauritania
      - Mauritius
      - Morocco
      - Mozambique
      - Namibia
      - Niger
      - Nigeria
      - Republic of the Congo
      - Rwanda
      - Sao Tome and Principe
      - Senegal
      - Seychelles
      - Sierra Leone
      - Somalia
      - South Africa
      - South Sudan
      - Sudan
      - Tanzania
      - Togo
      - Tunisia
      - Uganda
      - Zambia
      - Zimbabwe

Oceania
      - Australia
      - Fiji
      - Kiribati
      - Marshall Islands
      - Micronesia
      - Nauru
      - New Zealand
      - Palau
      - Papua New Guinea
      - Samoa
      - Solomon Islands
      - Tonga
      - Tuvalu
      - Vanuatu
```
## Table: Participant Groups

The forth table in your SQLite file is named `bewx_ParticipantGroups` with one field according to following.

|Column Name|Description|
|-|-|
|ParticipantGroup|Add the names of your different travel groups. The field `ParticipantGroup` in `bewa_Overview` is validated against groups in this table.<br /><br />**Syntax:** `<string without space>`

## Table: Trip Domains
The fifth table in your SQLite file is named `bewx_TripDomains` with fields according to following.

|Column Name|Description|
|-|-|
|DomainAbbreviation|A one letter abbreviation for the trip domain.<br /><br />**Syntax:** `<one capital letter>`
|DomainDescription|The description of the trip domain. E.g. abroad, domestic.<br /><br />**Syntax:** `<string without space>`
|Color|A hexadecimal number specifying the color of the trip domain. Eg. #123456.<br /><br />**Syntax:** `<haxadecimal color code>`

### About Trip Domains
There are three pre-defined trip domains
* Domestic trip
* Trip abroad
* Attachment trip

An attachment trip is defined as a visit to a country where you have a deeper connection. For example, if you study abroad, you might want to document that time but distinguish it from the ordinary abroad or domestic category.

## Appendix

### Special syntax used for Countries During Day (Events)

|Prefix|Function
|-|-|
|*|Shorter visit of significant importance
|**|Very short visit of without significant importance
|+|Restore, counts only if * and ** count

> [!NOTE]
> Countries During Day: When a prefix is used in front of a country name in field **CountriesDuringDay** in table `bewb_Events` it affect the **Statistics** page.



