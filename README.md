# midaas-expanded-api

## Overview

Extension of the [middas-API](https://github.com/CommerceDataService/midaas-api) with education and industry data

## API Documentation

### [GET] /quantiles
**query params**:  `state, race, sex, agegroup, education, industry` _(see below for options)_<br>
**response format**:  `{'<quantile>':  <income>}`<br>
**example**:
```
curl http://54.226.19.203/quantiles.php?state=MD
{
  "5%": 480,
  "10%": 3000,
  "20%": 10000,
  "30%": 15000,
  "40%": 20200,
  "50%": 27000,
  "60%": 35000,
  "70%": 43500,
  "80%": 55000,
  "90%": 79000,
  "95%": 102000,
  "99%": 311000
}
```

### Query Parameter Options

The query parameters **`state, race, sex, agegroup`** match the [middas-API](https://github.com/CommerceDataService/midaas-api) definitions.
Both **`education, industry`** are new query options and their values are defined below.

#### `state`

The two letter postal abbreviation...

```
"AL", "AK", "AR", "AZ", "CA", "CO", "CT", "DE",
"DC", "FL", "GA", "HI", "ID", "IL", "IN", "IA",
"KS", "KY", "LA", "ME", "MD", "MA", "MI", "MN",
"MS", "MO", "MT", "NE", "NV", "NH", "NJ", "NM",
"NY", "NC", "ND", "OH", "OK", "OR", "PA", "RI",
"SC", "SD", "TN", "TX", "UT", "VT", "VA", "WA",
"WV", "WI", "WY"
```

#### `race`

```
"white",
"african american",
"hispanic",
"asian"
```

#### `sex`

```
"male",
"female"
```

#### `agegroup`

```
"0-15",
"16-25",
"26-35",
"36-45",
"46-55",
"55-65",
"65+"
```

#### `education`

ID | Description
---|------------
1 | No High School
2 | High School
3 | GED
4 | Some College
5 | Associates Degree
6 | Bachelors Degree
7 | Masters Degree
8 | Professionals Degree
9 | Doctorate Degree

#### `industry`

ID | Description
---|------------
11 | Management
13 | Business and Financial Operations
15 | Computer and Mathematical
17 | Architecture and Engineering
19 | Life, Physical, and Social Science
21 | Community and Social Service
23 | Legal
25 | Education, Training, and Library
27 | Arts, Design, Entertainment, Sports, and Media
29 | Healthcare Practitioners and Technical
31 | Healthcare Support
33 | Protective Service
35 | Food Preparation and Serving Related
37 | Building and Grounds Cleaning and Maintenance
39 | Personal Care and Service
41 | Sales and Related
43 | Office and Administrative Support
45 | Farming, Fishing, and Forestry
47 | Construction and Extraction
49 | Installation, Maintenance, and Repair
51 | Production
53 | Transportation and Material Moving
55 | Military Specific
99 | Unemployed with no work experience in last 5 years or never worked

