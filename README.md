# Smart Safety Map

Smart Safety Map is a map-based web service that allows users to intuitively view public safety information around a building by selecting topics of interest.

## Service Overview

A web service that displays safety-related information around a building on a map.

## Core Mechanism

When a user selects a button, only the information related to that topic is displayed on the map.

## Main Categories

Mobility-vulnerable users, Flooding, Risk zones, Reports, Air quality, CCTV and emergency bells, Shelters and hospitals

## Air Quality Display

Good, Moderate, Bad, Very Bad

## User Flow

Check map → Select button → View information

## Service Features

Focused on building surroundings  
Topic-based map structure  
Intuitive visualization  
Expandable through public APIs

## Detailed Plan

### Service Goal

Smart Safety Map is a map-based web service designed to provide various safety-related information around a building on a single screen.  
Users can select the topics they need and view only the relevant information, allowing them to quickly understand surrounding conditions through intuitive visual data rather than complex datasets.

### Core Idea

Each topic is provided as a button, and when a user selects a button, only the related category is displayed on the map.

Examples  
Mobility-vulnerable users button → shows accessibility-related information  
Flooding button → shows flood-related risk information  
Risk zones button → shows caution areas and risk-related information  
Reports button → shows user-submitted report locations  
Air quality button → shows air quality status

### Main Functions

#### Mobility-vulnerable users
Displays accessibility-related information such as facilities for people with disabilities, accessible routes, elevators, accessible restrooms, ramps, and accessible entrances.

#### Flooding
Displays flood history areas and flood risk zones around the building.

#### Risk zones
Displays caution areas based on accumulated reports or public data.  
At the early stage, it is more practical to narrow the scope into categories such as flood-prone areas or frequently reported areas rather than defining all risk zones broadly.

#### Reports
A built-in reporting feature that allows users to select a location on the map and submit a report with text and photos.  
Both general users and administrators can directly submit reports.

#### Air Quality
Displays the air quality around the building in simple levels: Good, Moderate, Bad, Very Bad.

#### CCTV and emergency bells
Displays the locations of CCTV cameras and emergency bells around the building.

#### Shelters and hospitals
Displays nearby shelters, hospitals, and emergency response locations.

### Reporting Flow

1. User selects a location on the map
2. User enters a description of the hazard
3. User uploads a photo
4. The report is submitted
5. The location is displayed on the map
6. Accumulated reports can later be used to identify caution areas

### Nationwide Map Strategy

A nationwide map is possible, but it may be difficult to provide every category with equal coverage across all regions.  
Therefore, the map can be offered nationwide while clearly marking unsupported regions as unavailable or coming soon.

Example messages  
Data not available for this region  
This area is currently unsupported  
This category is only available in selected regions  
Coverage varies by region

## Technical Implementation Difficulty

| Level | Item | Reason |
|---|---|---|
| Easy | Air quality | Public APIs are relatively well organized and simple level-based display is easy to implement |
| Easy | Mobility-vulnerable users | Facility-based location data is suitable for map display |
| Easy | Shelters and hospitals | Mainly location-based information, so the structure is simple |
| Easy | Built-in reports | Can be implemented with location selection, text input, and photo upload |
| Medium | Flooding | Data exists, but interpretation differs depending on whether it is history, risk zones, or warning information |
| Medium | CCTV and emergency bells | The function is simple, but data formats and coverage vary by region |
| Medium | Nationwide map operation | Requires design for unsupported regions and varying local coverage |
| Hard | Risk zones | Requires defining criteria for what should be considered risky, which introduces decision logic |

## Recommended First Phase

Air quality, Mobility-vulnerable users, Built-in reports, Shelters and hospitals

## Recommended Second Phase

Flooding, CCTV and emergency bells, Regional support handling for nationwide maps

## Consider Later

Risk zones

## Short Presentation Phrase

A map service for selecting and viewing safety information around a building

## Service Name

Smart Safety Map
