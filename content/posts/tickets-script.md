---
title: "Tickets Script"
date: 2021-10-11T18:59:09-05:00
draft: false
---
Here is the tickets menu script from class today. There are a number of ways to improve this script. Have the menu repeat the prompt in case you wanted to purchase more than one, have the bands and the ticket prices be imported from a csv could be another improvement. 

```sh
#!/bin/sh
# Flaming Lips      $30
# Red Dirt Hogs     $10
# Chainsaw Kittens  $20

# Book Tickets for, how many tickets, total cost

TICKET_PRICE=0
NUM_TICKETS=0

echo "Who would you like tickets for?"
echo "[1] Flaming Lips     (\$30/ticket)"
echo "[2] Red Dirt Hogs    (\$10/ticket)"
echo "[3] Chainsaw Kittens (\$20/ticket)"

read -p "Enter choice [1-3]: " CHOICE

case $CHOICE in 
    "1")
        TICKET_PRICE=30
        ;;
    "2")
        TICKET_PRICE=10
        ;;
    "3")
        TICKET_PRICE=20
        ;;
    *)
        echo "Not a valid selection"
        exit 1
        ;;
esac

read -p "How many tickets? " NUM_TICKETS

# Check to ensure only positive numbers greater than 0 entered.
if ! [ "$NUM_TICKETS" -ge 0 ] 2>/dev/null ; then
    echo "Not a valid number of tickets"
    exit 1
fi

TOTAL_MONEY=$(echo "$NUM_TICKETS * $TICKET_PRICE" | bc)

echo "You owe \$$TOTAL_MONEY for your tickets." 
```
