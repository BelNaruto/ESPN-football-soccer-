# ESPN Football (Soccer) API Documentation
This is the unofficial ESPN Football (Soccer) Unofficial API.
This API is listed on RapidAPI - [https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/espn-football-soccer](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/espn-football-soccer)
## Endpoint: Retrieve Available Leagues

### GET `/leagues`

This endpoint retrieves a list of available football (soccer) leagues with their names and IDs.

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON array containing the available leagues, including their names and IDs.

  ```json
  [
    {
      "leagueName": "All",
      "leagueId": "all"
    },
    {
      "leagueName": "UEFA Super Cup",
      "leagueId": "UEFA.SUPER_CUP"
    }
    // More leagues...
  ]

## Endpoint: Retrieve Match Summary Data

### GET `/match-summary/:gameId`

This endpoint retrieves the summary data for a specific football (soccer) match.

### Parameters

- **Path Parameters:**
  - `gameId` (string): The unique identifier for the match. Example: `677769`

- **Query Parameters:**
  - `leagueId` (string, optional): The identifier for the league. If not provided, it defaults to `'eng.1'` (Premier League). Example: `eng.1`, `esp.1` (La Liga).

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the match summary data.

  ```json
  {
    // Match summary data as returned by the API
  }

## Endpoint: Retrieve Picks Data

### GET `/picks/:gameId`

This endpoint retrieves picks data for a specific football (soccer) match. Picks data typically includes predictions, betting odds, or expert recommendations related to the match.

### Parameters

- **Path Parameters:**
  - `gameId` (string): The unique identifier for the match. Example: `677769`

- **Query Parameters:**
  - `leagueId` (string, optional): The identifier for the league. If not provided, it defaults to `'eng.1'` (Premier League). Example: `eng.1`, `esp.1` (Check the endpoint /leagues for more options).

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the picks data.

  ```json
  {
    // Picks data as returned by the API
  }

## Endpoint: Retrieve Schedule Data

### GET `/schedule`

This endpoint retrieves the football (soccer) match schedule for a specific date or range within a league. You can specify a particular year, month, and day to get the schedule for that day, or just the year and month to get a broader schedule.

### Query Parameters

- **year** (string, required): The year for which to retrieve the schedule. Example: `2021`
- **month** (string, optional): The month for which to retrieve the schedule. If not provided, data for all months in the specified year will be returned. Example: `02` (February)
- **day** (string, optional): The day for which to retrieve the schedule. If not provided, data for the entire month and year will be returned. Example: `15`
- **leagueId** (string, optional): The identifier for the league. Defaults to `'eng.1'` (Premier League) if not provided. Example: `eng.1`, `esp.1`  (Check the endpoint /leagues for more options)

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the schedule data.

  ```json
  {
    // Schedule data as returned by the API
  }

## Endpoint: Retrieve Scoreboard Data

### GET `/scoreboard`

This endpoint retrieves the scoreboard data for football (soccer) matches. You can specify a particular year, month, and day to get the scores for that date, or just the year and month for a broader range. You can also limit the number of results returned.

### Query Parameters

- **year** (string, required): The year for which to retrieve the scoreboard data. Example: `2024`
- **month** (string, optional): The month for which to retrieve the scoreboard data. If not provided, data for all months in the specified year will be returned. Example: `08` (August)
- **day** (string, optional): The day for which to retrieve the scoreboard data. If not provided, data for the entire month and year will be returned. Example: `26`
- **limit** (integer, optional): The maximum number of results to return. Defaults to `200` if not provided. Example: `100`
- **leagueId** (string, optional): The identifier for the league. Defaults to `'uefa.europa'` (UEFA Europa League) if not provided. Example: `uefa.europa`, `eng.1` (Use the endpoint /leagues for more options)

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the scoreboard data.

  ```json
  {
    // Scoreboard data as returned by the API
  }

## Endpoint: Retrieve Team Scoreboard Data

### GET `/scoreboard-team/:teamId`

This endpoint retrieves the scoreboard data for a specific football (soccer) team. You can specify a particular year, month, and day to get the scores for that date, or just the year and month for a broader range. You can also limit the number of results returned.

### Path Parameters

- **teamId** (string): The unique identifier for the team. Default is `691532`. Example: `691532` (team identifier)

### Query Parameters

- **year** (string, required): The year for which to retrieve the scoreboard data. Example: `2024`
- **month** (string, optional): The month for which to retrieve the scoreboard data. If not provided, data for all months in the specified year will be returned. Example: `08` (August)
- **day** (string, optional): The day for which to retrieve the scoreboard data. If not provided, data for the entire month and year will be returned. Example: `26`
- **limit** (integer, optional): The maximum number of results to return. Defaults to `200` if not provided. Example: `100`
- **leagueId** (string, optional): The identifier for the league. Defaults to `'uefa.europa'` (UEFA Europa League) if not provided. Example: `uefa.europa`, `eng.1` (For more options use the endpoint /leagues)

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the scoreboard data for the specified team.

  ```json
  {
    // Team scoreboard data as returned by the API
  }

## Endpoint: Retrieve Transfers Data

### GET `/transfers`

This endpoint retrieves transfer data for football (soccer) players. You can specify the league, the number of results to return, the page number for pagination, and the year for which to retrieve the data.

### Query Parameters

- **leagueId** (string, optional): The identifier for the league. Defaults to `"all"` if not provided. Example: `uefa.europa`, `eng.1` (For more options use the endpoint /leagues)
- **limit** (string, optional): The maximum number of results to return per page. Defaults to `"20"`. Example: `"10"`, `"50"`
- **page** (string, optional): The page number for pagination. Defaults to `"1"`. Example: `"1"`, `"2"`
- **year** (string, optional): The year for which to retrieve the transfer data. Defaults to `'2023'`. Example: `"2024"`

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the transfer data.

  ```json
  {
    // Transfers data as returned by the API
  }

## Endpoint: Retrieve Team List Data

### GET `/team-list`

This endpoint retrieves a list of football (soccer) teams for a specified season and league. You can specify the number of results to return and the league for which to retrieve the team data.

### Query Parameters

- **limit** (integer, optional): The maximum number of teams to return. Defaults to `50`. Example: `20`, `100`
- **season** (string, optional): The season for which to retrieve the team list. Defaults to `'2024'`. Example: `'2024'`, `'2023'`
- **leagueId** (string, optional): The identifier for the league. Defaults to `'eng.1'` (Premier League). Example: `'eng.1'`, `'esp.1'` (For more options use the endpoint /leagues)

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the team list data.

  ```json
  {
    // Team list data as returned by the API
  }

## Endpoint: Retrieve Team Information

### GET `/team-info`

This endpoint retrieves detailed information about a specific football (soccer) team. You can specify the season, league, and team ID to get detailed data about the team.

### Query Parameters

- **season** (string, optional): The season for which to retrieve the team information. Defaults to `'2024'`. Example: `'2024'`, `'2023'`
- **leagueId** (string, optional): The identifier for the league. Defaults to `'eng.1'` (Premier League). Example: `'eng.1'`, `'esp.1'` (For more options use the endpoint /leagues)
- **teamId** (string, required): The unique identifier for the team. Example: `'1'`, `'2'`

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing detailed information about the specified team.

  ```json
  {
    // Team information data as returned by the API
  }


## Endpoint: Retrieve News Data

### GET `/news`

This endpoint retrieves the latest news related to football (soccer) for a specified league. You can specify the league and the number of news articles to return.

### Query Parameters

- **leagueId** (string, optional): The identifier for the league for which to retrieve news. Defaults to `'eng.1'` (Premier League). Example: `'eng.1'`, `'esp.1'` (For more options please check the endpoint /leagues)
- **limit** (string, optional): The maximum number of news articles to return. Defaults to `'20'`. Example: `'10'`, `'50'`

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the news data.

  ```json
  {
    // News data as returned by the API
  }

## Endpoint: Retrieve League Stats Data

### GET `/league-stats`

This endpoint retrieves statistical data for a specified football (soccer) league. You can specify the league to get comprehensive stats related to that league.

### Query Parameters

- **leagueId** (string, optional): The identifier for the league for which to retrieve statistics. Defaults to `'eng.1'` (Premier League). Example: `'eng.1'`, `'esp.1'` (For more options please check the endpoint /leagues)

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the league statistics data.

  ```json
  {
    // League stats data as returned by the API
  }

## Endpoint: Retrieve Player Description Data

### GET `/player-description`

This endpoint retrieves detailed statistical information and description for a specific football (soccer) player within a specified league. 

### Query Parameters

- **leagueId** (string, optional): The identifier for the league in which the player competes. Defaults to `'uefa.champions'` (UEFA Champions League). Example: `'uefa.champions'`, `'eng.1'`  (For more options please check the endpoint /leagues)
- **playerId** (string, optional): The unique identifier for the player. Defaults to `'291281'`. Example: `'291281'`, `'123456'`

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing detailed information about the specified player.

  ```json
  {
    // Player description data as returned by the API
  }

## Endpoint: Retrieve Player Stats Data

### GET `/player-stats/:playerId`

This endpoint retrieves statistical data for a specific football (soccer) player for a specified season. 

### URL Parameters

- **playerId** (string, optional): The unique identifier for the player. Defaults to `'291281'`. Example: `'52'`, `'123456'`

### Query Parameters

- **season** (string, optional): The season for which to retrieve the player's statistics. Defaults to `'2023'`. Example: `'2023'`, `'2024'`

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the player's statistical data for the specified season.

  ```json
  {
    // Player stats data as returned by the API
  }


## Endpoint: Retrieve Team Statistics Data

### GET `/team-statistic/:teamId`

This endpoint retrieves statistical data for a specific football (soccer) team for a specified season and league.

### URL Parameters

- **teamId** (string, required): The unique identifier for the team. Example: `'364'`

### Query Parameters

- **season** (string, optional): The season for which to retrieve the team statistics. Defaults to `'2023'`. Example: `'2023'`, `'2024'`
- **leagueId** (string, optional): The identifier for the league in which the team competes. Defaults to `'eng.1'` (Premier League). Example: `'eng.1'`, `'esp.1'` (For more options please check the endpoint /leagues)

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the team's statistical data for the specified season and league.

  ```json
  {
    // Team statistics data as returned by the API
  }


## Endpoint: Retrieve Injuries Data

### GET `/injuries`

This endpoint retrieves information about player injuries for the current season within a specified league.

### Query Parameters

- **leagueId** (string, optional): The identifier for the league for which to retrieve injury data. Defaults to `'uefa.champions'` (UEFA Champions League). Example: `'uefa.champions'`, `'eng.1'`  (For more options please check the endpoint /leagues)

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the injury data for the specified league.

  ```json
  {
    // Injuries data as returned by the API
  }

## Endpoint: Retrieve Team Roster Data

### GET `/team-roster`

This endpoint retrieves the roster of players for a specified football (soccer) team for a given season and league.

### Query Parameters

- **teamId** (string, required): The unique identifier for the team. Example: `'364'`, `'123'`
- **leagueId** (string, optional): The identifier for the league in which the team competes. Defaults to `'eng.1'` (Premier League). Example: `'eng.1'` (For more options please check the endpoint /leagues)
- **season** (string, optional): The season for which to retrieve the team roster. Defaults to `'2023'`. Example: `'2023'`, `'2024'`

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the roster data for the specified team.

  ```json
  {
    // Team roster data as returned by the API
  }


## Endpoint: Retrieve Soccer Schedules by Team

### GET `/schedule-team`

This endpoint retrieves the schedule of matches for a specified football (soccer) team for a given season and league.

### Query Parameters

- **teamId** (string, required): The unique identifier for the team. Example: `'364'`, `'123'`
- **season** (string, optional): The season for which to retrieve the team's schedule. Defaults to `'2023'`. Example: `'2023'`, `'2024'`
- **leagueId** (string, optional): The identifier for the league in which the team competes. Defaults to `'eng.1'` (Premier League). Example: `'eng.1'`, `'esp.1'` (For more options please check the endpoint /leagues)

### Response

- **200 OK**: If the request is successful, the endpoint will return a JSON object containing the schedule data for the specified team.

  ```json
  {
    // Team schedule data as returned by the API
  }
