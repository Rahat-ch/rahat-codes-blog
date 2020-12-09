---
title: JavaScript Closures and Pokemon
description: Closures are a hard concept to get down. Let's explore closures and understand them better by catching pokemon.
date: 2020-12-06
layout: layouts/post.njk
image: /../img/pokeball.jpg
alt: a person holding a pokeball
---

One of the most difficult things for me to learn in JavaScript was closures. After speaking to several other JavaScript Developers I've come to the conclusion that I'm not the only one. I've read a ton of different explanations about it but here is my take on what a closure is and an example of how you can use it in your code.

A closure in JavaScript happens when a child function accesses its parents scope. What? Functions can have kids? What this means is I can write a function that has another function inside of it. The outer function is the parent and the inner one is the child. When I run the outer function as long as I return the inner function I can do some cool stuff inside the scope of the Parent function(also known as lexical environment). 

Let's take a look at the example below: 

I'm going to start with a super boilerplate HTML file. Feel free to copy this into your favorite editor and run it. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
  <script>
   console.log("Hello World")
  </script>
</body>
</html>
```
If you save and open this file in a browser and check the console you should get a nice little Hello world message! Now lets move on to the good stuff. Say we're creating an online Pokemon Battle Simulator and we want to give all of our Players random teams of Pokemon to play with. Let's build some logic that can generate some teams for us. The following code can all replace everything inside the script tags! 

```javascript

const wildPokemon = ["Pikachu", "Eevee", "Ditto", "Charmander", "Reshiram", "Necrozma", "Dugtrio", "Mewtwo", "Honedge", "Scyther", "Mew", "Cyndaquil", "Sneasel", "Natu", "MagiKarp", "Squirtle", "Bulbasaur", "Treeko", "Jigglypuff", "Machop", "Bellsprout", "Caterpie", "Pidgeot", "Mankey", "Mr. Mime", "Gastly", "Riolu", "Arcanine", "Gyarados", "Wailord", "Skitty", "Onix", "Cloyster", "Magmar", "Muk", "Butterfree", "Exodia", "Agumon", "Goku"];

```

So I've defined this array that's full of strings of Pokemon that can be assigned to trainers. So here is what I want to be able to do: 

- Create a function that takes a trainer name as an argument.
- Define an array in the function that represents the trainers team. 
- Choose a random pokemon from the wild pokemon array and log it. 

Ok so the steps above don't have anything to do with closures just yet but I'm just setting the stage here. Below is one way of getting the above steps translated to code:

(Note: I added these lines below my initial array)

```javascript

function trainerTeam(trainerName) {
    const myTeam = []

    function getPokemon() {
      const newPokemon = wildPokemon[Math.floor(Math.random() * wildPokemon.length)]
      return newPokemon
    }
    return getPokemon
  }

  const RahatTeam = trainerTeam("Rahat")

```

So with the way I wrote this we kind of already have a closure but lets dive a little deeper. If you head to your console and call the function RahatTeam() then you should get a new Pokemon returned every time. This is because in the function trainerTeam I'm returning the inner function. How does JavaScript actually interpret this?

- The JavaScript Engine will go through your code line by line. 
- If it sees a function it will not immediately read the lines inside of it. It needs to be told to read those lines. 
- Eventually, we get to the declaration of RahatTeam which is where the trainerTeam function is called with "Rahat" as an argument.   
- When I call the RahatTeam function, JavaScript then sees that the trainerTeam function is called and starts reading the lines in there. 
- It finds that a function is declared and skips over it first.
- Once it hits that return statement (return getPokemon) that's when it knows to check out the getPokemon function and then execute and return it. 
- Executing getPokemon for now just returns a random Pokemon from the wildPokemon array.

So this isn't too useful so far. I'm getting random Pokemon but I need to make sure I actually have a bunch of Pokemon to actually play with. Let's do some more stuff with our code:

- Take the random Pokemon from getPokemon and add it to the myTeam array. 
- Return the myTeam Array instead of the new Pokemon. 
- Define an additional trainer team. 

Here is what the updated function looks like:

```javascript

  function trainerTeam(trainerName) {
    const myTeam = []

    function getPokemon() {
      const newPokemon = wildPokemon[Math.floor(Math.random() * wildPokemon.length)]
      myTeam.push(newPokemon)
      return myTeam
    }
    return getPokemon
  }

  const RahatTeam = trainerTeam("Rahat")
  const AshTeam = trainerTeam("Ash")

```

Now go ahead and run RahatTeam() and AshTeam() a couple of times in your console! Now instead of returning a random Pokemon every time, we get an array of Pokemon we can use on our team. Ash gets the same as well but I'll probably win that Pokemon battle. 

Now, believe it or not, we just implemented a closure in our code while making a nice reusable function for creating Pokemon teams for any number of trainers we want! 

- Every time we execute our child function getPokemon it has access to its parents scope. 
- The parent scope includes the myTeam array which we are adjusting as well as the wildPokemon array which is in the global scope.  
- getPokemon itself cannot be accessed from outside of the function (try running getPokemon outside of the trainerTeam function and see!)
- Since it cannot be run outside of the function it can safely just update the trainer we assign it to instead of every trainer that exists.

Let's do a little bit of adjustment. If you've played Pokemon before you might recall that a trainers team may only have 6 Pokemon on it. Here is my last adjustment to the code:

```javascript

  function trainerTeam(trainerName) {
    const myTeam = [];
    function getPokemon() {
      if (myTeam.length < 6) {
        const newPokemon = wildPokemon[Math.floor(Math.random() * wildPokemon.length)]
        myTeam.push(newPokemon)
        return `${trainerName}'s team is ${myTeam.toString()}`
      }
      return `${trainerName}'s team is ${myTeam.toString()}`
    }
    return getPokemon
  }

  const RahatTeam = trainerTeam("Rahat")
  const AshTeam = trainerTeam("Ash")

``` 

I just updated to make sure we aren't adding more than 6 Pokemon to the myTeam array and returning a nice little string that tells us the name of the trainer and the Team. 

That's all for today's lesson on closures! 

If you're a new dev looking for their first job check out the ebook I am working on:

[Build a Product become a Developer](https://www.buildaproduct.dev)

I'm adding some great methodologies and cool tech you can learn to stand out for your job search. Feel free to follow me on [Twitter](https://twitter.com/rahatcodes) or connect on [LinkedIn](https://www.linkedin.com/in/rahatc/) as well!