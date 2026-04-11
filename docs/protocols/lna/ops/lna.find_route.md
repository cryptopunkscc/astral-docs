# lna.find_route

Get a route from source to destination that can deliver an amount of money.

## Arguments

* source (identity) – The identity of the source node for the route.
* destination (identity) – The identity of the destination node for the route.
* amount (amount) – The amount of money to be delivered at the destination.

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* A `lna.route` object with the route details.

## Examples

```shellsession
$ astral-query target:lna.find_route -source void0 -destination 
03c2abfa93eacec04721c019644584424aab2ba4dff3ac9bdab4e9c97007491dda -amount 10000000 -out json | jq
{
  "Type": "lna.route",
  "Object": {
    "Route": [
      {
        "Cost": 12,
        "Delay": 442,
        "Destination": "026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2",
        "ShortChannelID": "942564x704x0"
      },
      {
        "Cost": 11,
        "Delay": 408,
        "Destination": "0281d6f21551b0e2f733948bcd0ee5fcd258f949d0ab8d2c1418737d55dce2b88a",
        "ShortChannelID": "873413x3291x1"
      },
      {
        "Cost": 11,
        "Delay": 328,
        "Destination": "0272bafa59999de0536104984c8ee970ecc4b1a57e584555f3181a3ce6b8fae7cd",
        "ShortChannelID": "937203x1989x8"
      },
      {
        "Cost": 261,
        "Delay": 184,
        "Destination": "0267586e510d80fab314fbfa091f383b775646e7a87bc9ed8cd59bcded50405d6a",
        "ShortChannelID": "936042x2525x4"
      },
      {
        "Cost": 1011,
        "Delay": 40,
        "Destination": "03c2abfa93eacec04721c019644584424aab2ba4dff3ac9bdab4e9c97007491dda",
        "ShortChannelID": "586083x1800x0"
      }
    ]
  }
}

```