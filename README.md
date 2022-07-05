# My_teams

## A CLI server written in C to communicate with differents clients.

The purpose of this project was to learn network programming, handling multi-clients, implementing a communication protocol.
You can create teams, in those teams, you can create channels, in those channels, you can create threads and you can reply to thoses threads.

## Build

``` zsh
make
```

## Usage

- This will run the server on the specified port.

``` zsh
./my_teams_server <PORT>
```

- This will run the clients, you must specify the server IP address and port.

``` zsh
./my_teams_cli <IP> <PORT>
```

I made this project with 1 teammate:
- [Victor Harri-Chal](https://github.com/VictorHarri-Chal "VictorHarri-Chal").

## Features

- `/help`: show help
- `/login[“user_name”]`: set the user_name used by client
- `/logout`: disconnect the client from the server
- `/users`: get the list of all users that exist on the domain
- `/user[“user_uuid”]`: get information about a user
- `/send[“user_uuid”][“message_body”]`: send a message to a user
- `/messages[“user_uuid”]`:list all messages exchange with an user
- `/subscribe [“team_uuid”]`: subscribe to the event of a team and its sub directories (enable reception
of all events from a team)
- `/subscribed?[“team_uuid”]`: list all subscribed teams or list all users subscribed to a team
- `/unsubscribe[“team_uuid”]`: unsubscribe from a team
- `/use?[“team_uuid”]?[“channel_uuid”]?[“thread_uuid”]`: use specify a context team/channel/thread
- `/create`: based on what is being used create the sub resource (see below)
- `/list`: based on what is being used list all the sub resources (see below)
- `/info`: based on what is being used list the current (see below)

## Create

When the context is not defined (`/use`):
- `/create[“team_name”][“team_description”]`: create a new team

When team_uuid is defined (`/use “team_uuid”`):
- `/create[“channel_name”][“channel_description”]`: create a new channel

When team_uuid and channel_uuid are defined (`/use “team_uuid” “channel_uuid”`):
- `/create[“thread_title”][“thread_message”]`: create a new thread

When team_uuid, channel_uuid and thread_uuid are defined (`/use “team_uuid” “channel_uuid” “thread_uuid”`):
- `/create[“comment_body”]`: create a new reply
___
Check my [portfolio](http://simonlefourn.com) for more informations on this project.
