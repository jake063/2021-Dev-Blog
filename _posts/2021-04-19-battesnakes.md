---
title: The Week of Snakes
date: 2021-04-19
---

Battlesnakes! A fight to the death! one snake left slithering! See how we created the one snake to rule them all...
...Sort of..

## The Idea

This last week me and a partner have been slaving away at getting a Battlesnake ready to fight in a double emimination tournament.

# How did our understanding of the problem evolve over the two weeks?

We had a good understanding of what we wanted our snake to do at first, we wanted our snake to avoid the walls and avoid its head.
The snake would scan each Y cord and if there was food on it then the snake would go to the X cord of the food.
If we had time we would have made a system to detect other snakes and avoid them as well.

# What role did I play in my team and how did I contribute?
 
I did not do much in our group, my partner did a lot of the headway in making our snek avoid the walls.
While my partner was being productive I was struggling to figure out where to even start for a few days.
Once I eventualy did get started I worked on the snakes food locating systems, but the code did not work and we had no time to fix it.

Once It was time to run the challenges and get ranked I took out the code we worked on and put the starter code in because it was honestly better than ours.

![Alternate title for the image](https://exporter.battlesnake.com/games/c8c3c42f-7fe2-47df-bb0f-5a2ce7675281/gif.gif)

````javascript
const bodyParser = require('body-parser')
const express = require('express')

const PORT = process.env.PORT || 3000

const app = express()
app.use(bodyParser.json())

app.get('/', handleIndex)
app.post('/start', handleStart)
app.post('/move', handleMove)
app.post('/end', handleEnd)

app.listen(PORT, () => console.log(`Battlesnake Server listening at http://127.0.0.1:${PORT}`))


function handleIndex(request, response) {
  var battlesnakeInfo = {
    apiversion: '1',
    author: '',
    color: '#888888',
    head: 'default',
    tail: 'default'
  }
  response.status(200).json(battlesnakeInfo)
}

function handleStart(request, response) {
  var gameData = request.body

  console.log('START')
  response.status(200).send('ok')
}

function handleMove(request, response) {
  var gameData = request.body

  var possibleMoves = ['up', 'down', 'left', 'right']
  var move = possibleMoves[Math.floor(Math.random() * possibleMoves.length)]

  console.log('MOVE: ' + move)
  response.status(200).send({
    move: move
  })
}

function handleEnd(request, response) {
  var gameData = request.body

  console.log('END')
  response.status(200).send('ok')
}
````

## The Process

# What does it mean to think algorithmically?

To me, thinking algorithmically would mean thinking like a computer, taking tasks and breaking them down into simple steps and carrying them out.

# What did I learn about problem solving and how did I break the problem down?

I am not good at problem solving which is why it took me a long time to get started.
The way I broke the problem down is I asked myself what exactly I want to do and I would slowly get started based on tiny tasks.

## Key takeaways

# What did I learn?

* how not to make a battlesnake
* some problem solving skills

## Next Steps

# With one more week, what could we do?

If we just had one more week I feel like my partner could lock down the snake not rinning into itself and the walls and I could get the snakes food sensors up and running, maybe we would even have time to detect other snakes.
