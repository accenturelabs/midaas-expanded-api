# midaas-expanded-api

## Overview

Extension of the [middas-API](https://github.com/CommerceDataService/midaas-api) with education and industry data

## API Documentation

### [GET] /quantiles.php
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
"WV", "WI", "WY", "PR", "undefined"
```

#### `race`

```
"white",
"african american",
"hispanic",
"asian",
"other"
```

#### `sex`

```
"male",
"female"
```

#### `agegroup`

```
"18-24",
"25-34",
"35-44",
"45-54",
"55-64",
"65+",
"undefined"
```

#### `education`

ID | Description
---|------------
0 | Undefined
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
0 | Undefined
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

#### `occuptation`
ID | Description
---|------------
0 | Undefined
11-0000 | Management Occupations:
11-10XX | Chief executives and legislators
11-1011 | Chief executives
11-1031 | Legislators
11-1021 | General and operations managers
11-2011 | Advertising and promotions managers
11-2020 | Marketing and sales managers
11-2031 | Public relations and fundraising managers
11-3011 | Administrative services managers
11-3021 | Computer and information systems managers
11-3031 | Financial managers
11-3111 | Compensation and benefits managers
11-3121 | Human resources managers
11-3131 | Training and development managers
11-3051 | Industrial production managers
11-3061 | Purchasing managers
11-3071 | Transportation, storage, and distribution managers
11-9013 | Farmers, ranchers, and other agricultural managers
11-9021 | Construction managers
11-9030 | Education administrators
11-9041 | Architectural and engineering managers
11-9051 | Food service managers
11-9071 | Gaming managers
11-9081 | Lodging managers
11-9111 | Medical and health services managers
11-9121 | Natural sciences managers
11-9141 | Property, real estate, and community association managers
11-9151 | Social and community service managers
11-9161 | Emergency management directors
11-9XXX | Miscellaneous managers, including funeral service managers and postmasters and mail superintendents
11-9061 | Funeral service managers
11-9131 | Postmasters and mail superintendents
11-9199 | Managers, all other
13-0000 | Business and Financial Operations Occupations:
13-1011 | Agents and business managers of artists, performers, and athletes
13-1021 | Buyers and purchasing agents, farm products
13-1022 | Wholesale and retail buyers, except farm products
13-1023 | Purchasing agents, except wholesale, retail, and farm products
13-1030 | Claims adjusters, appraisers, examiners, and investigators
13-1041 | Compliance officers
13-1051 | Cost estimators
13-1070 | Human resources workers
13-1141 | Compensation, benefits, and job analysis specialists
13-1151 | Training and development specialists
13-1081 | Logisticians
13-1111 | Management analysts
13-1121 | Meeting, convention, and event planners
13-1131 | Fundraisers
13-1161 | Market research analysts and marketing specialists
13-1199 | Business operations specialists, all other
13-2011 | Accountants and auditors
13-2021 | Appraisers and assessors of real estate
13-2031 | Budget analysts
13-2041 | Credit analysts
13-2051 | Financial analysts
13-2052 | Personal financial advisors
13-2053 | Insurance underwriters
13-2061 | Financial examiners
13-2070 | Credit counselors and loan officers
13-2081 | Tax examiners and collectors, and revenue agents
13-2082 | Tax preparers
13-2099 | Financial specialists, all other
15-0000 | Computer and mathematical occupations:
15-1111 | Computer and information research scientists
15-1121 | Computer systems analysts
15-1122 | Information security analysts
15-1131 | Computer programmers
15-113X | Software developers, applications and systems software
15-1134 | Web developers
15-1150 | Computer support specialists
15-1141 | Database administrators
15-1142 | Network and computer systems administrators
15-1143 | Computer network architects 
15-1199 | Computer occupations, all other
15-2011 | Actuaries
15-2031 | Operations research analysts
15-20XX | Miscellaneous mathematical science occupations, including mathematicians and statisticians
15-2021 | Mathematicians
15-2041 | Statisticians
15-2090 | Miscellaneous mathematical science occupations
17-0000 | Architecture and Engineering Occupations:
17-1010 | Architects, except naval
17-1020 | Surveyors, cartographers, and photogrammetrists
17-2011 | Aerospace engineers
17-20XX | Biomedical and agricultural engineers
17-2021 | Agricultural engineers
17-2031 | Biomedical engineers
17-2041 | Chemical engineers
17-2051 | Civil engineers
17-2061 | Computer hardware engineers
17-2070 | Electrical and electronics engineers
17-2081 | Environmental engineers
17-2110 | Industrial engineers, including health and safety
17-2121 | Marine engineers and naval architects
17-2131 | Materials engineers
17-2141 | Mechanical engineers
17-21XX | Petroleum, mining and geological engineers, including mining safety engineers
17-2151 | Mining and geological engineers, including mining safety engineers
17-2171 | Petroleum engineers
17-21YY | Miscellaneous engineers, including nuclear engineers
17-2161 | Nuclear engineers
17-2199 | Engineers, all other
17-3010 | Drafters
17-3020 | Engineering technicians, except drafters
17-3031 | Surveying and mapping technicians
19-0000 | Life, Physical, and Social Science Occupations:
19-1010 | Agricultural and food scientists
19-1020 | Biological scientists
19-1030 | Conservation scientists and foresters
19-10XX | Medical scientists, and life scientists, all other
19-1040 | Medical scientists
19-1099 | Life scientists, all other
19-2010 | Astronomers and physicists
19-2021 | Atmospheric and space scientists
19-2030 | Chemists and materials scientists
19-2040 | Environmental scientists and geoscientists
19-2099 | Physical scientists, all other
19-3011 | Economists
19-3030 | Psychologists
19-3051 | Urban and regional planners
19-30XX | Miscellaneous social scientists, including survey researchers and sociologists
19-3022 | Survey researchers
19-3041 | Sociologists
19-3090 | Miscellaneous social scientists and related workers
19-4011 | Agricultural and food science technicians
19-4021 | Biological technicians
19-4031 | Chemical technicians
19-40XX | Geological and petroleum technicians, and nuclear technicians
19-4041 | Geological and petroleum technicians
19-4051 | Nuclear technicians
19-40YY | Miscellaneous life, physical, and social science technicians, including social science research assistants
19-4061 | Social science research assistants
19-4090 | Miscellaneous life, physical, and social science technicians
21-0000 | Community and Social Service Occupations:
21-1010 | Counselors
21-1020 | Social workers
21-1092 | Probation officers and correctional treatment specialists
21-1093 | Social and human service assistants
21-109X | Miscellaneous community and social service specialists, including health educators and community health workers
21-2011 | Clergy
21-2021 | Directors, religious activities and education
21-2099 | Religious workers, all other
23-0000 | Legal Occupations:
23-10XX | Lawyers, and judges, magistrates, and other judicial workers
23-1011 | Lawyers
23-1020 | Judges, magistrates, and other judicial workers
23-1012 | Judicial law clerks
23-2011 | Paralegals and legal assistants
23-2090 | Miscellaneous legal support workers
25-0000 | Education, Training, and Library Occupations:
25-1000 | Postsecondary teachers
25-2010 | Preschool and kindergarten teachers
25-2020 | Elementary and middle school teachers
25-2030 | Secondary school teachers
25-2050 | Special education teachers
25-3000 | Other teachers and instructors
25-4010 | Archivists, curators, and museum technicians
25-4021 | Librarians
25-4031 | Library technicians
25-9041 | Teacher assistants
25-90XX | Other education, training, and library workers
25-9011 | Audio-visual collections specialists
25-9021 | Farm and home management advisors
25-9031 | Instructional coordinators
25-9099 | Education, training, and library workers, all others
27-0000 | Arts, Design, Entertainment, Sports, and Media Occupations:
27-1010 | Artists and related workers
27-1020 | Designers
27-2011 | Actors
27-2012 | Producers and directors
27-2020 | Athletes, coaches, umpires, and related workers
27-2030 | Dancers and choreographers
27-2040 | Musicians, singers, and related workers
27-2099 | Entertainers and performers, sports and related workers, all other
27-3010 | Announcers
27-3020 | News analysts, reporters and correspondents
27-3031 | Public relations specialists
27-3041 | Editors
27-3042 | Technical writers
27-3043 | Writers and authors
27-3090 | Miscellaneous media and communication workers
27-40XX | Broadcast and sound engineering technicians and radio operators, and media and communication equipment workers, all other
27-4010 | Broadcast and sound engineering technicians and radio operators
27-4099 | Media and communication equipment workers, all other
27-4021 | Photographers
27-4030 | Television, video, and motion picture camera operators and editors
29-0000 | Healthcare Practitioners and Technical Occupations:
29-1011 | Chiropractors
29-1020 | Dentists
29-1031 | Dietitians and nutritionists
29-1041 | Optometrists
29-1051 | Pharmacists
29-1060 | Physicians and surgeons
29-1071 | Physician assistants
29-1081 | Podiatrists
29-1181 | Audiologists
29-1122 | Occupational therapists
29-1123 | Physical therapists
29-1124 | Radiation therapists
29-1125 | Recreational therapists
29-1126 | Respiratory therapists
29-1127 | Speech-language pathologists
29-112X | Other therapists, including exercise physiologists
29-1128 | Exercise physiologists
29-1129 | Therapists, all other
29-1131 | Veterinarians
29-1141 | Registered nurses
29-1151 | Nurse anesthetists
29-11XX | Nurse practitioners and nurse midwives
29-1161 | Nurse midwives
29-1171 | Nurse practitioners
29-1199 | Health diagnosing and treating practitioners, all other
29-2010 | Clinical laboratory technologists and technicians
29-2021 | Dental hygienists
29-2030 | Diagnostic related technologists and technicians
29-2041 | Emergency medical technicians and paramedics
29-2050 | Health practitioner support technologists and technicians
29-2061 | Licensed practical and licensed vocational nurses
29-2071 | Medical records and health information technicians
29-2081 | Opticians, dispensing
29-2090 | Miscellaneous health technologists and technicians
29-9000 | Other healthcare practitioners and technical occupations
31-0000 | Healthcare Support Occupations:
31-1010 | Nursing, psychiatric, and home health aides
31-2010 | Occupational therapy assistants and aides
31-2020 | Physical therapist assistants and aides
31-9011 | Massage therapists
31-9091 | Dental assistants
31-9092 | Medical assistants
31-9094 | Medical transcriptionists
31-9095 | Pharmacy aides
31-9096 | Veterinary assistants and laboratory animal caretakers
31-9097 | Phlebotomists
31-909X | Healthcare support workers, all other, including medical equipment preparers
31-9093 | Medical equipment preparers
31-9099 | Healthcare support workers, all other
33-0000 | Protective Service Occupations:
33-1011 | First-line supervisors of correctional officers
33-1012 | First-line supervisors of police and detectives
33-1021 | First-line supervisors of fire fighting and prevention workers
33-1099 | First-line supervisors of protective service workers, all other
33-2011 | Firefighters
33-2020 | Fire inspectors
33-3010 | Bailiffs, correctional officers, and jailers
33-3021 | Detectives and criminal investigators
33-30XX | Miscellaneous law enforcement workers
33-3031 | Fish and game wardens
33-3041 | Parking enforcement workers
33-3050 | Police officers
33-3051 | Police and sheriff's patrol officers
33-3052 | Transit and railroad police
33-9011 | Animal control workers
33-9021 | Private detectives and investigators
33-9030 | Security guards and gaming surveillance officers
33-9091 | Crossing guards
33-9093 | Transportation security screeners
33-909X | Lifeguards and other recreational, and all other protective service workers
33-9092 | Lifeguards, ski patrol, and other recreational protective service workers
33-9099 | Protective service workers, all other
35-0000 | Food Preparation and Serving Related Occupations:
35-1011 | Chefs and head cooks
35-1012 | First-line supervisors of food preparation and serving workers
35-2010 | Cooks
35-2021 | Food preparation workers
35-3011 | Bartenders
35-3021 | Combined food preparation and serving workers, including fast food
35-3022 | Counter attendants, cafeteria, food concession, and coffee shop
35-3031 | Waiters and waitresses
35-3041 | Food servers, nonrestaurant
35-90XX | Miscellaneous food preparation and serving related workers, including dining room and cafeteria attendants and bartender helpers
35-9011 | Dining room and cafeteria attendants and bartender helpers
35-9099 | Food preparation and serving related workers, all other
35-9021 | Dishwashers
35-9031 | Hosts and hostesses, restaurant, lounge, and coffee shop
37-0000 | Building and Grounds Cleaning and Maintenance Occupations:
37-1011 | First-line supervisors of housekeeping and janitorial workers
37-1012 | First-line supervisors of landscaping, lawn service, and groundskeeping workers
37-201X | Janitors and building cleaners
37-2011 | Janitors and cleaners, except maids and housekeeping cleaners
37-2019 | Building cleaning workers, all other
37-2012 | Maids and housekeeping cleaners
37-2021 | Pest control workers
37-3010 | Grounds maintenance workers
39-0000 | Personal Care and Service Occupations:
39-1010 | First-line supervisors of gaming workers
39-1021 | First-line supervisors of personal service workers
39-2011 | Animal trainers
39-2021 | Nonfarm animal caretakers
39-3010 | Gaming services workers
39-3021 | Motion picture projectionists
39-3031 | Ushers, lobby attendants, and ticket takers
39-3090 | Miscellaneous entertainment attendants and related workers
39-40XX | Embalmers and funeral attendants
39-4031 | Morticians, undertakers, and funeral directors
39-5011 | Barbers
39-5012 | Hairdressers, hairstylists, and cosmetologists
39-5090 | Miscellaneous personal appearance workers
39-6010 | Baggage porters, bellhops, and concierges
39-7010 | Tour and travel guides
39-9011 | Childcare workers
39-9021 | Personal care aides
39-9030 | Recreation and fitness workers
39-9041 | Residential advisors
39-9099 | Personal care and service workers, all other 
41-0000 | Sales and Related Occupations:
41-1011 | First-line supervisors of retail sales workers
41-1012 | First-line supervisors of non-retail sales workers
41-2010 | Cashiers
41-2021 | Counter and rental clerks
41-2022 | Parts salespersons
41-2031 | Retail salespersons
41-3011 | Advertising sales agents
41-3021 | Insurance sales agents
41-3031 | Securities, commodities, and financial services sales agents
41-3041 | Travel agents
41-3099 | Sales representatives, services, all other
41-4010 | Sales representatives, wholesale and manufacturing
41-9010 | Models, demonstrators, and product promoters
41-9020 | Real estate brokers and sales agents
41-9031 | Sales engineers
41-9041 | Telemarketers
41-9091 | Door-to-door sales workers, news and street vendors, and related workers
41-9099 | Sales and related workers, all other
43-0000 | Office and Administrative Support Occupations:
43-1011 | First-line supervisors of office and administrative support workers
43-2011 | Switchboard operators, including answering service
43-2021 | Telephone operators
43-2099 | Communications equipment operators, all other
43-3011 | Bill and account collectors
43-3021 | Billing and posting clerks 
43-3031 | Bookkeeping, accounting, and auditing clerks
43-3041 | Gaming cage workers
43-3051 | Payroll and timekeeping clerks
43-3061 | Procurement clerks
43-3071 | Tellers
43-3099 | Financial clerks, all other
43-4011 | Brokerage clerks
43-4031 | Court, municipal, and license clerks
43-4041 | Credit authorizers, checkers, and clerks
43-4051 | Customer service representatives
43-4061 | Eligibility interviewers, government programs
43-4071 | File clerks
43-4081 | Hotel, motel, and resort desk clerks
43-4111 | Interviewers, except eligibility and loan
43-4121 | Library assistants, clerical
43-4131 | Loan interviewers and clerks
43-4141 | New accounts clerks
43-4XXX | Correspondence clerks and order clerks
43-4021 | Correspondence clerks
43-4151 | Order clerks
43-4161 | Human resources assistants, except payroll and timekeeping
43-4171 | Receptionists and information clerks
43-4181 | Reservation and transportation ticket agents and travel clerks
43-4199 | Information and record clerks, all other
43-5011 | Cargo and freight agents
43-5021 | Couriers and messengers
43-5030 | Dispatchers
43-5041 | Meter readers, utilities
43-5051 | Postal service clerks
43-5052 | Postal service mail carriers
43-5053 | Postal service mail sorters, processors, and processing machine operators
43-5061 | Production, planning, and expediting clerks
43-5071 | Shipping, receiving, and traffic clerks
43-5081 | Stock clerks and order fillers
43-5111 | Weighers, measurers, checkers, and samplers, recordkeeping
43-6010 | Secretaries and administrative assistants
43-9011 | Computer operators
43-9021 | Data entry keyers
43-9022 | Word processors and typists
43-9041 | Insurance claims and policy processing clerks
43-9051 | Mail clerks and mail machine operators, except postal service
43-9061 | Office clerks, general
43-9071 | Office machine operators, except computer
43-9081 | Proofreaders and copy markers
43-9111 | Statistical assistants
43-9XXX | Miscellaneous office and administrative support workers, including desktop publishers
43-9031 | Desktop publishers
43-9199 | Office and administrative support workers, all other
45-0000 | Farming, Fishing, and Forestry Occupations:
45-1011 | First-line supervisors of farming, fishing, and forestry workers
45-2011 | Agricultural inspectors
45-2041 | Graders and sorters, agricultural products
45-20XX | Miscellaneous agricultural workers, including animal breeders
45-2021 | Animal breeders
45-2090 | Miscellaneous agricultural workers 
45-3000 | Fishing and hunting workers
45-3011 | Fishers and related fishing workers
45-3021 | Hunters and trappers
45-4011 | Forest and conservation workers
45-4020 | Logging workers
47-0000 | Construction and Extraction Occupations:
47-1011 | First-line supervisors of construction trades and extraction workers
47-2011 | Boilermakers
47-2020 | Brickmasons, blockmasons, and stonemasons
47-2031 | Carpenters
47-2040 | Carpet, floor, and tile installers and finishers
47-2050 | Cement masons, concrete finishers, and terrazzo workers
47-2061 | Construction laborers
47-2071 | Paving, surfacing, and tamping equipment operators
47-207X | Construction equipment operators except paving, surfacing, and tamping equipment operators
47-2072 | Pile-driver operators
47-2073 | Operating engineers and other construction equipment operators
47-2080 | Drywall installers, ceiling tile installers, and tapers
47-2111 | Electricians
47-2121 | Glaziers
47-2130 | Insulation workers
47-2141 | Painters, construction and maintenance
47-2142 | Paperhangers
47-2150 | Pipelayers, plumbers, pipefitters, and steamfitters
47-2161 | Plasterers and stucco masons
47-2171 | Reinforcing iron and rebar workers
47-2181 | Roofers
47-2211 | Sheet metal workers
47-2221 | Structural iron and steel workers
47-3010 | Helpers, construction trades
47-4011 | Construction and building inspectors
47-4021 | Elevator installers and repairers
47-4031 | Fence erectors
47-4041 | Hazardous materials removal workers
47-4051 | Highway maintenance workers
47-4061 | Rail-track laying and maintenance equipment operators
47-XXXX | Miscellaneous construction workers, including solar photovoltaic installers, septic tank servicers and sewer pipe cleaners
47-2231 | Solar photovoltaic installers
47-4071 | Septic tank servicers and sewer pipe cleaners
47-4090 | Miscellaneous construction and related workers
47-50YY | Derrick, rotary drill, and service unit operators, and roustabouts, oil, gas, and mining
47-5010 | Derrick, rotary drill, and service unit operators, oil, gas, and mining
47-5071 | Roustabouts, oil and gas
47-5021 | Earth drillers, except oil and gas
47-5031 | Explosives workers, ordnance handling experts, and blasters
47-5040 | Mining machine operators
47-50XX | Miscellaneous extraction workers, including roof bolters and helpers
47-5061 | Roof bolters, mining
47-5081 | Helpers--extraction workers
47-50XX | Other extraction workers
47-5051 | Rock splitters, quarry
47-5099 | Extraction workers, all others
49-0000 | Installation, Maintenance, and Repair Occupations:
49-1011 | First-line supervisors of mechanics, installers, and repairers
49-2011 | Computer, automated teller, and office machine repairers
49-2020 | Radio and telecommunications equipment installers and repairers
49-2091 | Avionics technicians
49-2092 | Electric motor, power tool, and related repairers
49-209X | Electrical and electronics repairers, transportation equipment, and industrial and utility
49-2093 | Electrical and electronics installers and repairers, transportation equipment
49-209X | Electrical and electronics repairers, industrial and utility
49-2094 | Electrical and electronics repairers, commercial and industrial equipment
49-2095 | Electrical and electronics repairers, powerhouse, substation, and relay
49-2096 | Electronic equipment installers and repairers, motor vehicles
49-2097 | Electronic home entertainment equipment installers and repairers
49-2098 | Security and fire alarm systems installers
49-3011 | Aircraft mechanics and service technicians
49-3021 | Automotive body and related repairers
49-3022 | Automotive glass installers and repairers
49-3023 | Automotive service technicians and mechanics
49-3031 | Bus and truck mechanics and diesel engine specialists
49-3040 | Heavy vehicle and mobile equipment service technicians and mechanics
49-3050 | Small engine mechanics
49-3090 | Miscellaneous vehicle and mobile equipment mechanics, installers, and repairers
49-9010 | Control and valve installers and repairers
49-9021 | Heating, air conditioning, and refrigeration mechanics and installers
49-9031 | Home appliance repairers
49-904X | Industrial and refractory machinery mechanics
49-9041 | Industrial machinery mechanics
49-9045 | Refractory materials repairers, except brickmasons
49-9071 | Maintenance and repair workers, general
49-9043 | Maintenance workers, machinery
49-9044 | Millwrights
49-9051 | Electrical power-line installers and repairers
49-9052 | Telecommunications line installers and repairers
49-9060 | Precision instrument and equipment repairers
49-9091 | Coin, vending, and amusement machine servicers and repairers
49-9094 | Locksmiths and safe repairers
49-9095 | Manufactured building and mobile home installers
49-9096 | Riggers
49-9098 | Helpers--installation, maintenance, and repair workers 
49-909X | Other installation, maintenance, and repair workers, including wind turbine service technicians, and commercial divers, and signal and track switch repairers
49-9081 | Wind turbine service technicians
49-9092 | Commercial divers
49-9097 | Signal and track switch repairers
49-909X | Other installation, maintenance, and repair workers
49-9093 | Fabric menders, except garment
49-9099 | Installation, maintenance, and repair workers, all other
51-0000 | Production Occupations:
51-1011 | First-line supervisors of production and operating workers
51-2011 | Aircraft structure, surfaces, rigging, and systems assemblers
51-2020 | Electrical, electronics, and electromechanical assemblers
51-2031 | Engine and other machine assemblers
51-2041 | Structural metal fabricators and fitters
51-2090 | Miscellaneous assemblers and fabricators
51-3011 | Bakers
51-3020 | Butchers and other meat, poultry, and fish processing workers
51-3091 | Food and tobacco roasting, baking, and drying machine operators and tenders
51-3092 | Food batchmakers
51-3093 | Food cooking machine operators and tenders
51-3099 | Food processing workers, all other
51-4010 | Computer control programmers and operators
51-4021 | Extruding and drawing machine setters, operators, and tenders, metal and plastic
51-4022 | Forging machine setters, operators, and tenders, metal and plastic
51-4023 | Rolling machine setters, operators, and tenders, metal and plastic
51-4031 | Cutting, punching, and press machine setters, operators, and tenders, metal and plastic
51-4032 | Drilling and boring machine tool setters, operators, and tenders, metal and plastic 
51-4033 | Grinding, lapping, polishing, and buffing machine tool setters, operators, and tenders, metal and plastic
51-4034 | Lathe and turning machine tool setters, operators, and tenders, metal and plastic
51-4041 | Machinists
51-4050 | Metal furnace operators, tenders, pourers, and casters
51-4060 | Model makers and patternmakers, metal and plastic
51-4070 | Molders and molding machine setters, operators, and tenders, metal and plastic
51-4111 | Tool and die makers
51-4120 | Welding, soldering, and brazing workers
51-4191 | Heat treating equipment setters, operators, and tenders, metal and plastic
51-4193 | Plating and coating machine setters, operators, and tenders, metal and plastic
51-4194 | Tool grinders, filers, and sharpeners
51-4XXX | Miscellaneous metal workers and plastic workers, including milling and planing machine setters, and multiple machine tool setters, and layout workers
51-4035 | Milling and planing machine setters, operators, and tenders, metal and plastic
51-4081 | Multiple machine tool setters, operators, and tenders, metal and plastic 
51-4192 | Layout workers, metal and plastic
51-4199 | Metal workers and plastic workers, all other
51-5111 | Prepress technicians and workers
51-5112 | Printing press operators
51-5113 | Print binding and finishing workers
51-6011 | Laundry and dry-cleaning workers
51-6021 | Pressers, textile, garment, and related materials
51-6031 | Sewing machine operators
51-6041 | Shoe and leather workers and repairers
51-6042 | Shoe machine operators and tenders
51-6050 | Tailors, dressmakers, and sewers
51-606X | Textile bleaching and dyeing, and cutting machine setters, operators, and tenders
51-6061 | Textile bleaching and dyeing machine operators and tenders
51-6062 | Textile cutting machine setters, operators, and tenders
51-6063 | Textile knitting and weaving machine setters, operators, and tenders
51-6064 | Textile winding, twisting, and drawing out machine setters, operators, and tenders
51-6093 | Upholsterers
51-609X | Miscellaneous textile, apparel, and furnishings workers except upholsterers
51-6091 | Extruding and forming machine setters, operators, and tenders, synthetic and glass fibers
51-6092 | Fabric and apparel patternmakers
51-6099 | Textile, apparel, and furnishings workers, all other
51-7011 | Cabinetmakers and bench carpenters
51-7021 | Furniture finishers
51-7041 | Sawing machine setters, operators, and tenders, wood
51-7042 | Woodworking machine setters, operators, and tenders, except sawing
51-70XX | Miscellaneous woodworkers, including model makers and patternmakers
51-7030 | Model makers and patternmakers, wood
51-7099 | Woodworkers, all other
51-8010 | Power plant operators, distributors, and dispatchers
51-8021 | Stationary engineers and boiler operators
51-8031 | Water and wastewater treatment plant and system operators
51-8090 | Miscellaneous plant and system operators
51-9010 | Chemical processing machine setters, operators, and tenders
51-9020 | Crushing, grinding, polishing, mixing, and blending workers
51-9030 | Cutting workers
51-9041 | Extruding, forming, pressing, and compacting machine setters, operators, and tenders
51-9051 | Furnace, kiln, oven, drier, and kettle operators and tenders
51-9061 | Inspectors, testers, sorters, samplers, and weighers
51-9071 | Jewelers and precious stone and metal workers
51-9080 | Medical, dental, and ophthalmic laboratory technicians
51-9111 | Packaging and filling machine operators and tenders
51-9120 | Painting workers
51-9151 | Photographic process workers and processing machine operators
51-9191 | Adhesive bonding machine operators and tenders
51-9192 | Cleaning, washing, and metal pickling equipment operators and tenders
51-9194 | Etchers and engravers
51-9195 | Molders, shapers, and casters, except metal and plastic
51-9196 | Paper goods machine setters, operators, and tenders
51-9197 | Tire builders
51-9198 | Helpers--production workers
51-91XX | Other production workers, including semiconductor processors and cooling and freezing equipment operators
51-9141 | Semiconductor processors
51-9193 | Cooling and freezing equipment operators and tenders
51-9199 | Production workers, all other
53-0000 | Transportation and Material Moving Occupations:
53-1000 | Supervisors of transportation and material moving workers
53-2010 | Aircraft pilots and flight engineers
53-2020 | Air traffic controllers and airfield operations specialists
53-2031 | Flight attendants
53-3011 | Ambulance drivers and attendants, except emergency medical technicians
53-3020 | Bus drivers
53-3030 | Driver/sales workers and truck drivers
53-3041 | Taxi drivers and chauffeurs
53-3099 | Motor vehicle operators, all other
53-4010 | Locomotive engineers and operators
53-4021 | Railroad brake, signal, and switch operators
53-4031 | Railroad conductors and yardmasters
53-40XX | Subway, streetcar, and other rail transportation workers
53-4041 | Subway and streetcar operators
53-4099 | Rail transportation workers, all other
53-50XX | Sailors and marine oilers, and ship engineers
53-5011 | Sailors and marine oilers
53-5031 | Ship engineers
53-5020 | Ship and boat captains and operators
53-6021 | Parking lot attendants
53-6031 | Automotive and watercraft service attendants  
53-6051 | Transportation inspectors
53-6061 | Transportation attendants, except flight attendants
53-60XX | Miscellaneous transportation workers, including bridge and lock tenders and traffic technicians
53-6011 | Bridge and lock tenders
53-60XX | Other transportation workers 
53-6041 | Traffic technicians
53-6099 | Transportation workers, all other
53-7021 | Crane and tower operators
53-7030 | Dredge, excavating, and loading machine operators
53-7000 | Material Moving Occupations:
53-70XX | Conveyor operators and tenders, and hoist and winch operators
53-7011 | Conveyor operators and tenders
53-7041 | Hoist and winch operators
53-7051 | Industrial truck and tractor operators
53-7061 | Cleaners of vehicles and equipment
53-7062 | Laborers and freight, stock, and material movers, hand
53-7063 | Machine feeders and offbearers
53-7064 | Packers and packagers, hand
53-7070 | Pumping station operators
53-7081 | Refuse and recyclable material collectors
53-71XX | Miscellaneous material moving workers, including mine shuttle car operators, and tank car, truck, and ship loaders
53-7111 | Mine shuttle car operators
53-7121 | Tank car, truck, and ship loaders
53-7199 | Material moving workers, all other
55-1010 | Military officer special and tactical operations leaders
55-2010 | First-line enlisted military supervisors
55-3010 | Military enlisted tactical operations and air/weapons specialists and crew members
559830 | Military, rank not specified
999920 | Unemployed, with no work experience in the last 5 years or earlier or never worked
