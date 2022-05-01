# Front-end League Of Legends
1. Frontend that consumes the API developed in this repository https://github.com/dev-lmoreno/lol-backend (Developed based on consumption of official riot games APIs)
2. Basically on the front we have a form to fill in the name of the invoker and make the submite to receive the data in the API return. This data is then displayed in a card component.

# Technology
1. Vue 3 (https://vuejs.org/)
2. Vite (https://vitejs.dev/)

# How to use:
1. clone the project
2. use npm install to install the dependencies
3. npm run dev to start the application
4. enter your summoner name or a friend's name to list some ranked queue information

# Official API Riot Games:
1. to get the credentials to use the official riot api go to: https://developer.riotgames.com/ and create your account

# Dependencies used in the application
1. axios: make requests to API's

# API return example (backend)
```
{
    "summonerLevel": 493,
    "tier": "PLATINUM",
    "rank": "IV",
    "wins": 40,
    "losses": 39,
    "queueType": "RANKED_SOLO_5x5",
    "iconUrl": "https://ddragon.leagueoflegends.com/cdn/12.8.1/img/profileicon/582.png",
    "winRate": "50.63"
}
```

# Next steps
1. add docker