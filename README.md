# 🤖✨ Simulating Robot Swarms with the Beta Algorithm

Hey there, future roboticist! 👋 Welcome to the repository for my third-year project at the University of Manchester, where we dive into the fascinating world of **Swarm Robotics**!

Ever wondered how flocks of birds or schools of fish move so gracefully together without bumping into each other? That's kind of what we're exploring here, but with robots! This project simulates a swarm of cool little bots and investigates how they can stick together and act as one coordinated unit – a concept called **coherence**.

## 🤔 What's the Big Idea?

Making individual robots is cool, but making *lots* of simple robots work together opens up amazing possibilities – from search and rescue missions to automated warehouses and even dazzling drone light shows!

But getting them to cooperate isn't easy. They need to stay connected and organized, especially when things get tricky. This project focuses on one specific method to achieve this: the **Beta (β) Algorithm**.

## 🔬 What's Inside This Project?

* **The Beta (β) Algorithm:** This is the star of the show! It's a clever way for robots to maintain connections with their neighbors using local communication. If a robot loses connection, it checks how many *shared* neighbors can still see the lost buddy. If that number drops below a threshold (β), it does a U-turn to try and reconnect! Pretty neat, huh?
* **Simulation Setup:** We used the **Webots** simulator – a fantastic tool for modeling and testing robots. Why Webots? It has a great physics engine (ODE), pre-built robot models, and let us focus on the algorithm itself.
* **Our Little Hero - The 'epuck' Robot:** We used the 'epuck' robot model. It's a popular choice in swarm research, equipped with infrared sensors for detecting obstacles (and buddies!) and wheels to zip around.
* **The Brains (Controller):** The robot's behavior is programmed in C. It handles:
    * **Obstacle Avoidance:** Using a Braitenberg-inspired approach, the robot uses its sensors to steer away from walls. We even added special logic to handle tricky corners!
    * **Communication:** Robots broadcast "heartbeat" messages with their ID and who they can see.
    * **β-Algorithm Logic:** Implementing the core rules for checking connections and deciding when to turn back.
* **Experiments:** We played around with different values for the β threshold to see how it affected the swarm's "spread" and coherence. We measured the distance between robot pairs to see how tightly knit the swarm stayed. Spoiler: β=2 seemed to be the sweet spot in our setup!

## 🎢 The Journey & Challenges

It wasn't all smooth sailing!
* **Simulator Battles:** Choosing the right simulator took time. Gazebo didn't play nice with Windows, and others seemed too complex. Webots was great but had its own quirks.
* **Collision Course:** Getting robots to avoid walls was one thing, but stopping them from bumping into *each other* needed extra tweaking.
* **Corner Conundrums:** Robots kept getting stuck in the corners of the square arena! We had to implement specific logic to help them escape.
* **Data Drama:** Webots didn't make tracking swarm data super easy, so we had to build custom ways to log results. My laptop also struggled with simulating *lots* of robots.

## 🚀 Future Directions

This is just the beginning! Future work could involve:
* Making the β-Algorithm even better at keeping the swarm tightly packed.
* Exploring ideas from "situated communication" to help the swarm adapt better.
* Experimenting with different swarm shapes for different tasks.
* Testing these ideas on **real physical robots**!

## 🙏 Acknowledgements

A massive thank you to my supervisor, **Prof. Clare Dixon**, for the invaluable guidance and support throughout this project!

---

Thanks for checking out the project! Feel free to explore the code and the full report (`Swarm-Robot-Simulation-Report.pdf`) for all the nitty-gritty details. Happy Swarming! 🎉
