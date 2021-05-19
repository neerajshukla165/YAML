# YAML

Hello, and welcome to this topic.

In this topic, we take a look at what YAML files are. All Ansible playbooks are written in YAML.

If you have worked with other data structure formats like XML or JSON, you should be able to easily pick it up.

Don't worry. If you haven't worked on any of these, you should still be able to easily pick it up.

Going through the coding exercises that accompany this page.

## Introduction

A YAML file is used to represent data, in this case, configuration data.

Here is a quick comparison of a sample data in three different formats.

The one on the left is XML where we display a list of servers and their information.

The same data is represented in JSON format in the middle, and finally, in YAML format to the right.

Take a minute to compare the three formats.

```
XML                                       JSON                              YAML
<Servers>                              {                                 Servers:
  <Server>                                Servers: [                        -  name: Server1  
    <Name>Server1</name>                    {                                  owner: John
    <owner>John</owner>                     name: Server1,                     created: 12232012
    <created>12232012</created>             owner:John,                        status: active
    <Status>active</active>                 created: 12232012,
  </Server>                                 status: active,
</Servers>                                  }
                                          ]
                                        }  
  
 ```
 
Let's take a close look at YAML.

If you take the data in its simplest form, such as key-value pair, this is how you would define it in YAML; 

key, and value separated by a colon.

The keys are fruit, vegetable, liquid, and meat, the values are apple, carrot, water, and chicken.

Remember, you must have a space followed by a colon differentiating the key and the value.

Let's take a look at how an array is represented.

We would like to list some fruits and vegetables.

We would say fruits followed by a colon

on the next line, enter each item with a dash in the front.

That dash indicates that it's an element of an array.


```
    Key- Value Pair                         Arrays/Lists                       Dictionary/Map

Fruit: Apple                           Fruits:                             Banana:
Vegetable: Carrot                      - Orange                                 Calories: 105
Liquid: Water                          - Apple                                  Fat: 0.4 g
Meat: Chicken                          - Banana                                 Carbs: 27g
                                       Vegetable:                          Grapes:
                                       - Carrot                                 Calories: 62 
                                       - Cauliflower                            Fat: 0.3 g
                                       - Tomato                                 Carbs: 16 g
                                       
```

How about a dictionary?

A dictionary is a set of properties grouped together under an item.

Here, we try to represent nutrition information of two fruits.

The calories, fat, and carbs are different for each fruit.

Notice the blank space before each item, you must have equal number of blank spaces before the properties of 

a single item so they are all aligned together.

Let's take a closer look at spaces in YAML.

Here we have a dictionary representing the nutrition information of banana.

The total amount of calories, fat, and carbs are shown.

Notice the number of spaces before each property that indicates these key-value pairs fall within banana.

What if we had extra spaces for fat and carbs?

Then they will fall under calories thus become properties of calories, which doesn't make any sense.

This will result in a syntax error which will tell you that mapping values are not allowed here because calories already have a value set, which is 105.

You can either set a direct value or a HashMap.

You cannot have both.

The number of spaces before each property is key in YAML,

you must ensure they're in the right form to represent your data correctly.


## Example

First of all, it is important to understand that all of what we've discussed so far such as XML, JSON, or YAML are used to represent data.

It could be data about an organization and all of its employees and their personal details, or it could be data about a school and all of its students and their grades, or it 

could be data about an automobile manufacturing company and all of its cars and its details.

It could be anything.

Let's take an example of a car.

A car is a single object, it has properties such as color, model, transition, and price.

To store different information or properties of a single object, we use a dictionary.

In this simple dictionary, I have properties of the car defined in a key-value format.

```
       Dictionary
   Color: Blue
   Model: Corvette
   Transmission: Manual
   Price: Rs.2000000
```
This need not be as simple as this.

For example, in case we need to split the model further into model name and make year, you could then represent this as a dictionary within another dictionary.

In this case, the single value of model is now replaced by a small dictionary with two properties; name and year.

This is a dictionary within another dictionary.

```
       Dictionary
   Color: Blue
   Model:
      Name: Corvette
      Year: 1995
   Transmission: Manual
   Price: Rs.2000000
```

Let's say we would like to store the name of three cars.

The names are formed by the color and the model of the car.

To store this, we would use a list or an array as it is multiple items of the same type of object.

Since we are only storing the names, we have a symbol list of strings.

What if we would like to store all information about each car, everything that we listed before, such as the color model, transition, and price?

We will then modify the array from a list of strings to a list of dictionaries.

We expand each item in the array and replace the name with the dictionary we built earlier.

This way, we are able to represent all information about multiple cars in a single YAML file using a list of dictionaries.

That's the difference between dictionary list and list of dictionaries.

I hope you understood the difference between the three and when to use each of these.

```
     List                                 List of Dictionaries
- Blue Corvette                        - Color: Blue
- Grey Corvette                          Model:  
- Red Corvette                              Name: Corvette
                                            Year: 1995
                                         Transmission: Manual
                                         Price: Rs.2000000
                                       - Color: Grey
                                         Model:
                                            Name: Corvette
                                            Year: 1995
                                         Transmission: Automatic
                                         Price: Rs.3000000
                                       - Color: Red
                                         Model:
                                            Name: Corvette
                                            Year: 1995
                                         Transmission: Manual
                                         Price: Rs.1500000
```
