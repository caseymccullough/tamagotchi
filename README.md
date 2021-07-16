![GA Logo](https://camo.githubusercontent.com/6ce15b81c1f06d716d753a61f5db22375fa684da/68747470733a2f2f67612d646173682e73332e616d617a6f6e6177732e636f6d2f70726f64756374696f6e2f6173736574732f6c6f676f2d39663838616536633963333837313639306533333238306663663535376633332e706e67)
# Front End Software Architecure Day 2 of 2

---
Title: Front End Software Architecture<br>
Type: Deep Dive<br>
Creator: Arthur Bernier Jr<br>
Competencies: DOM Manipulation, OOP, CSS

---

## Begin with the end in mind

![itsalive](https://media.git.generalassemb.ly/user/15881/files/9e180580-8a07-11ea-9e5a-f03084d192f1)

### Agenda
1. Review Robustness of an APP
1. Review Adaptability of An App
1. Explain The Concept of Reusability
1. Explain Modularity
1. Explain Encapsulation
1. Explain Abstraction
1. Divide of our programming into classes
1. Decide how the classes will interact with each other
1. Decide what data is stored in each class
1. Decide what actions will be performed by each method
1. Use JQuery to Visualize the changes to our App State in the DOM


## Robustness
1. When we speak to robustness, we are speaking to one of the foundations of a good programmer.  Programmers naturally want their programs to work.  Not only does this mean that they want their software to function for what its intended to but to also handle unseen circumstances.  For example, if we are to build a program that is a simple to do list, we are going to expect a variety of strings to be entered to represent the items on our list.  What if we receive integers?  We would want to make sure our program can handle this as well.
1. This principle is especially critical for life-critical applications.  These are applications where severe injury or loss of life can happen if there is a software error.  Think of an amusement park ride.  If it is not robust enough in its calculations, then the ride may miscalculate and injure people in the process of the ride.

## Adaptability
1. A second aspect of OOP is that we want the software to be adaptable.  This allows the software to live for many years.  We also want to balance portability which allows for software to run with minimal change on different hardware operating platforms.  A key example of this would be gaming software applications.  In order to hit the largest possible market, programs need to be built so that it can adapt to multiple platforms with minimal changes to the software.

## Reusability
1. Reusability is a goal that goes hand in hand with adaptability.  This allows certain parts of the code to be reused as a component of different systems in different applications.  This is a cost and time-saving measure since software development can be expensive and time-consuming.  However, care should be taken to monitor compatibility and to maintain robustness.  
 
# Principles of Object-Oriented Systems
The major elements of object-oriented programs include modularity, encapsulation, and abstraction. We will revisit these throughout the course.
## Modularity
1. Modularity is the degree to which components can be separated and recombined.  This allows our software to be more manageable over time. 
## Encapsulation
1. In object-oriented programming, encapsulation facilitates the bundling of data with the methods (or other functions) operating on that data.  
## Abstraction
1. Abstraction involves taking a holistic view of a problem.  Extraneous, or accidental, properties are abstracted out making solutions more achievable.
# The Software Design Process

### In the design process, you may be familiar with the three foundation phases: design, implementation, and testing/debugging.  
### There is the overarching idea of design but for object-oriented programming, we see a great reliance on the design process because this allows us to do the following:
	1.	Divide of our programming into classes
	2.	Decide how the classes will interact with each other
	3.	What data is stored in each class
	4.	What actions will be performed by each method
__________________________________
Class Variables vs Object Variables
Class Var = Variable that is given to all Instances
Object Var = Variable owned by the Object itself


# Using OOP To Build An Application

```
// Example Code lets pull it into a code pen and see what we are doing here
class Component {
    // Our contsructor creates our class
    constructor(boundElement, state, props){
        this.el = document.querySelector(boundElement)
        this.state = {...state}
        this.props = props
        Object.keys(this.props).forEach((prop)=> {
            this.el.setAttribute(prop, this.props[prop])
        })
    }
    // This function will be used to make our component dynamic
    setState(newState){
        this.state = {...this.state, ...newState}
        this.render()
    }
    // This will be what renders our component aka what ads it to the screen
    render(){
        return(
            this.el.innerHTML = `Hello <b>world</b> ${this.state.content? this.state.content : 'user'}!`
        )
    }
}
// This code below is code that we want to load after the dom is ready.
window.onload = () => {
    // First we construct our element
    const $example = new Component('#example', {content:'Arthur'}, {'class':'love'})
    // Next we build our 
    $example.render()
    const $button = document.querySelector('#trigger').addEventListener('click', ()=>{
        $example.setState({content: `Arthur made $${(Math.random() * 10).toFixed(4)} Million Today`})
    })
}
```



# Tomagotchi Code Along

<img src="https://cms.qz.com/wp-content/uploads/2017/08/vintage-tamagotchis.jpg?quality=75&strip=all&w=1200&h=900&crop=1">

### Description

Let's use our front-end web development skills to create a "living" pet! We'll use HTML, CSS, and JavaScript to interact with our pet.

#### Here is a [live example ](https://starter-code.madeline.vercel.app/) of what we are going to build


## Learning Objectives
Today's lesson will be focused on building out interactivity in the DOM. This will enable us to take the games we have been building and combine them with user interactivity. 

Along the way, we will be learning about some common UI and how to build them. These include:

- Building a [Modal](https://codepen.io/reidark/pen/FEueH)
- Building a [Carousel](https://codepen.io/arfeus/pen/BWOqZQ)


### Guidelines
:pencil: Style the page.

:pencil: Add a Modal to start the game.

:pencil: Add a Carousel of images for user to choose the background.

:pencil: Create a Class ( for your tomagotchi
* Instatiate your Tomagotchi
* Display a character of your choice on the screen to represent your pet
* Increase your pet's age every x minutes
* Increase your pet's Hunger, Sleepiness, and Bored metrics on an interval of your choosing.
* You pet should die if Hunger, Boredom, or Sleepiness hits 10.
* Morph your pet at certain ages.

:pencil: Display the following metrics for your pet: 
 * Hunger (1-10 scale)
 * Sleepiness (1-10 scale)
 * Boredom (1-10 scale)
 * Age
 * Name

:pencil: Add buttons to the screen to feed your pet, turn off the lights, and play with your pet.


* Animate your pet across the screen while it's alive.

### Extras
* Animate your pet across the screen while it's alive.
* Add anything you can think of... use your imagination!
