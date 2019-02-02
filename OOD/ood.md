## Object Oriented Design
Object-oriented design (OOD) is the process of using an object-oriented methodology to design a computing system or application.

Object-oriented system design involves defining the context of a system followed by designing the architecture of the system.

Object-oriented system design involves: 
- Definition of the context of the system
- Designing system architecture
- Identification of the objects in the system
- Construction of design models
- Specification of object interfaces

various diagrams can be drawn in each step:
sample system: [amity_space_allocation](https://github.com/kjagoo/Amity_Space_Allocation)
```
Problem Description
model a room allocation system for one of Andela’s facilities called Amity.

Constraints
Amity has rooms which can be offices or living spaces. An office can accommodate a maximum of 6 people. A living space can accommodate a maximum of 4 people.

A person to be allocated could be a fellow or staff. Staff cannot be allocated living spaces. Fellows have a choice to choose a living space or not.

This system will be used to automatically allocate spaces to people at random.


```

- context diagram:
<img width="646" alt="screenshot 2019-02-02 at 14 56 06" src="https://user-images.githubusercontent.com/8224798/52164466-d0eb2500-2702-11e9-9202-aec39ea33de0.png">

uml class diagram of a System
<img width="845" alt="uml diagram" src="https://user-images.githubusercontent.com/8224798/52164549-41467600-2704-11e9-9c9e-386bc417264d.png">

object diagram:
```
{ Amity:
    {rooms: 
        [
          {name: "room1", capacity: 5, type:"office", people:[],..}, 
          {},
        ]
      },
    {people: 
        [
            {name: "joshua", type: "fellow"...},{name:"kelvin", type:staff,..}, {}, 
         ]
     }
  }
  ```

Object design:
<img width="832" alt="screenshot 2019-02-02 at 15 45 34" src="https://user-images.githubusercontent.com/8224798/52164471-e95b3f80-2702-11e9-93a4-6c2ce6292335.png">



