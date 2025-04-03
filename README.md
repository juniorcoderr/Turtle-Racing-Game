# 🐢 **Turtle Racing Game** 🎮  

This is a **fun Turtle Racing Game** built using **Python’s Turtle module**.  
Users can **place a bet on a turtle color** and watch the race to see if they win!  

---

## 🚀 **How the Game Works**  
1. The game **asks the user to place a bet** on which turtle will win the race.  
2. Six turtles of different colors start from the **left side of the screen**.  
3. The turtles **move randomly** towards the right side of the screen.  
4. The first turtle to **reach the finish line (right edge)** wins.  
5. If the user’s chosen turtle wins, they **win the bet**, otherwise, they lose.  

---

## 🖥 **How to Play**  
1. Run the script in Python.  
2. A **popup appears** asking you to **choose a turtle color** (red, orange, yellow, green, blue, or purple).  
3. Watch the **turtles race across the screen**.  
4. The game prints the **winning turtle color** and whether you **won or lost** the bet.  

---

## 📜 **Code Explanation (Step-by-Step)**  

### 📌 **1. Importing Required Modules**  
```python
from turtle import Turtle, Screen
import random
```
- **Turtle module** → Used to create the racing turtles and display them.  
- **Screen module** → Controls the game screen setup and user interactions.  
- **Random module** → Allows turtles to move randomly, making the race unpredictable.  

---

### 🖥 **2. Setting Up the Game Window**  
```python
screen = Screen()
screen.setup(width=500, height=400)
```
- **Creates the game window** with a width of `500px` and height of `400px`.  
- The race takes place inside this window.  

---

### 🎲 **3. Asking User for a Bet**  
```python
user_bet = screen.textinput(title="Make your bet", prompt="Which turtle will win the race? Enter a color: ")
```
- **`textinput()`** → Opens a popup box asking the user to enter a turtle color.  
- The user types the color they think will win the race.  

---

### 🐢 **4. Creating and Positioning the Turtles**  
```python
colors = ["red", "orange", "yellow", "green", "blue", "purple"]
y_positions = [-70, -40, -10, 20, 50, 80]
all_turtles = []
```
- `colors` → Defines **six turtle colors** for the race.  
- `y_positions` → Sets **starting Y-positions** so turtles are placed in different lanes.  
- `all_turtles` → Stores **all turtle objects** in a list for easy access.  

---

### 🎨 **5. Creating Turtle Objects**  
```python
for turtle_index in range(0, 6):
    new_turtle = Turtle(shape="turtle")  # Creates a turtle
    new_turtle.color(colors[turtle_index])  # Assigns a unique color
    new_turtle.penup()  # Lifts the pen to prevent drawing
    new_turtle.goto(x=-235, y=y_positions[turtle_index])  # Moves turtle to start position
    all_turtles.append(new_turtle)  # Adds turtle to the list
```
- A loop creates **six turtles**, each with:  
  ✅ A unique color  
  ✅ A **starting position** on the left (`x = -235`)  
  ✅ A **different lane** using `y_positions`  

---

### 🏁 **6. Starting the Race**  
```python
if user_bet:
    is_race_on = True
```
- The race **starts only if the user has placed a bet**.  

---

### 🚀 **7. Moving the Turtles Randomly**  
```python
while is_race_on:
    for turtle in all_turtles:
        if turtle.xcor() > 230:  # If a turtle reaches the finish line
            is_race_on = False  # Stop the race
            winning_color = turtle.pencolor()  # Get the winning turtle's color
            if winning_color == user_bet:
                print(f"You've won! The {winning_color} turtle is the winner!")
            else:
                print(f"You've lost! The {winning_color} turtle is the winner!")
        
        random_distance = random.randint(0, 10)  # Move randomly between 0-10 pixels
        turtle.forward(random_distance)
```
- **Each turtle moves forward by a random distance (0-10 pixels)**.  
- The race continues **until a turtle reaches the finish line (`x > 230`)**.  
- When a turtle **crosses the finish line**, the race **stops**, and the winning color is checked.  

---

### ❌ **8. Closing the Game Window**  
```python
screen.exitonclick()
```
- Waits for **a mouse click before closing the game window**.  

---

## 📚 **Python Concepts Used in This Code**  

✅ **Turtle Graphics** → Used to create and control the turtle movement.  
✅ **For Loops (`for turtle_index in range(0, 6)`)** → Used to create multiple turtles dynamically.  
✅ **Lists & Indexing (`colors[turtle_index]`)** → Assign colors and positions efficiently.  
✅ **Randomization (`random.randint(0, 10)`)** → Makes the race **unpredictable** and fun!  
✅ **Conditional Statements (`if...else`)** → Determines the winner and prints results.  
✅ **Functions & Methods (`.goto()`, `.penup()`, `.pencolor()`)** → Controls turtle movement and properties.  

---

## 🎯 **Conclusion**  
This **Turtle Racing Game** is a great way to practice:  
✔ **Python’s Turtle module**  
✔ **Event handling with user input**  
✔ **Loops, lists, and randomization**  

✨ **Try modifying the game!**  
- **Change the number of turtles**  
- **Adjust movement speed**  
- **Customize colors and track size**  

👉 **Fork the repo, experiment, and have fun racing!** 🚀
