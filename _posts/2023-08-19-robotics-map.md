---
layout: post
title: Robotics Engineer, A Recipe (and how to prepare for interviews)
date: 2023-08-19 10:14:00-0400
description: Some thoughts and observations from working and interviewing for robotics engineering teams.
categories: industry
giscus_comments: true
related_posts: false
---

I feel extremely fortunate to have had the chance to work with multiple robotics engineering teams in the past few years. Throughout the process of applying and interviewing for these positions, and of course developing and implementing algorithms in the real world, I have gotten extensive advice from my mentors and colleagues. After some time I have begun to see trends in these pieces of advice, and I thought it could be useful to to write them down and share them with, well, with you.

### If you do not want to read this, but you do want to do robotics engineering, then
Then just choose a robotics project, and go make it. You'll learn a ton and hopefully have some fun too. I feel like if you have the time and motivation then there is no better way to get a deep understanding of robotics systems other than creating them.

### If you do, though

Then let's get into more details. I have divided this post into two parts.

The first part is the **what**. This is the _stuff_  that would hopefully give you a sufficiently broad view of a robotic system. Besides needing this kind of perspective, in my opinion, to build robust systems, interviewers will also probably want you to demonstrate that you have it in a basic level. The list below could be overwhelming -- remember tht each role would require knowledge of a different subset of topics, so pick and choose what you think is relevant for you :).

The second part is the **how**. This will be a collection of tips and tricks that I have found useful in the past when I was being interviewed.

None of the lists to follow are comprehensive. Hopefully they could point you in the right direction, though!

## The What: Algorithms and Concepts

I like seeing the different topics that comprise the field of robotics as a hierarchy. Going from the least "abstract" to the most, I tend to put topics in the following high-level buckets:

- **Controls**: what voltage should motors receive in order for a robot to track some predefined trajectory. What are common methods for using sensory feedback and reacting to it?
- **Planning**: how can we find a sequence of actions that will take a robot from point A to point B. How can we do this in a way that is dynamically-sound, and robust to uncertainty and to the presence of other agents and obstacles?
- **Localization and Mapping**: how can we build a map of the environment and localize a robot within it. With this information, we could plan paths from a start location on a map to a goal location on the map and control the robot to follow it.
- **Learning, Perception, and Higher Level Scene Understanding**: robots can be seen as data-collection machines. Can robots learn to improve themselves from the data they collect? Yes, they can. And learning algorithms can be applied to improve perception, planning, and control algorithms (and more!).

Each of these topics is extremely broad. Here are some subtopics and algorithms you could familiarize yourself with to get a grasp of each of these topics. Their order is somewhat arbitrary, I see this as a bit of a cookbook recipe and encourage you to tweak it as you need!


- **Controls**
    * PID
    * Pure Pursuit
    - State space and state space models
    - Model predictive control
    - Trajectory optimization

- **Planning** 
    * Graph based methods:
        * Dijkstra's Algorithm
        * A*
        * BFS
        * DFS
        * ARA\*, MHA*, and many others

    * Sampling based methods:
        * RRT (Rapidly exploring Random Trees)
        * Bidirectional RRT
        * RRT*
        * RRG (Rapidly exploring Random Graphs)
        * PRM (probabilistic roadmaps)
        * PRM*
    * And if you are cool, multi agent planning algorithms (the following are graph-based)
        * Conflict Based Search (CBS)
        * ECBS (Enhanced CBS)
        * MAPF-LNS (Multi-agent path finding with large neighborhood search)

- **Localization (and state estimation)** 
    * Different map representations
        * grid occupancy maps, voxel grids, graphs of convex sets, meshes, etc.
    * Scan matching (2D and 3D pointclouds, often using ICP with laser scans)
    * ICP (Iterative Closest Point)
    * Ray tracing
    * Particle filter
    * **Kalman Filters** (and the extended Kalman filter for extra credit)
    * Fundamentals of odometry

- **Mapping**
    * SLAM (includes localization, of course). Knowledge of the two components of general SLAM systems: motion model and sensor model. 
    * Online SLAM (Full-SLAM) and offline slam.
    * Extra: pose-graph optimization, KF-based SLAM vs Smoothing based SLAM. Know of semantic SLAM, visual slam, and more traditional SLAM. Hector-SLAM, and Cartographer. 
    * Octomapping/gmapping.

- **Learning, Perception, and Higher Level Scene Understanding** 
    * Neural Networks
        * Convolutional neural networks
        * Activation layers
        * Loss functions
        * Backpropagation
        * Gradient descent
        * Reinforcement learning, supervised learning, semi-supervised learning, unsupervised learning
        * And to be trendy, large language models and transformers.
    * Perception and learning
        * 3D geometry
            * Shape estimation
            * Place recognition 
            * Manipulation example: grasp computation
        * Computer vision
            * Segmentation
            * Detection
            * Visual odometry
            * Optical flow,
            * Tracking)
            * Camera calibration (intrinsics, extrinsics)
            - Epipolar geometry (essential matrix, fundamental matrix.)

We must also remember our fundamentals:

* A tad ot **physics**:
    - Kinematics
    - Free-fall mechanics (accelerations)
    - $$F = ma$$ (sounds silly but this is important for going between talking in terms of velocity derivatives and energy).
    - Forward and inverse kinematics (mostly for manipulation).

* A bit of **math**:

    - Reference frames and rigid transformations
    - Pseudo-inverse
    - SVD
    - Eigenvalues and eigenvectors
    * Optimization

If you know all of that, you'll be a... good theoretical researcher. Undoubtedly, you'll be able to talk to many folks in the field and be up to speed with their work. However, to transform yourself to a great _engineer_, you'll also need some hands-on experience with the common tools teams use to apply all of these theoretical concepts in real-world systems.


## The What: Software Tools

Let's face it. Most robotics engineers are specialized software engineers. We (they) spend much of our (their) time coding in a collaborative environment. Besides common software engineering tools, there are a few tools that are specific to robotics that you may benefit from being familiar with. Here are some of them (alongside the common tools):

* Robot Operation System (ROS)
    * Topics, services, rosbags and analysis (shoutout to plotjuggler)
* Embedded systems, micro-controllers, and generally small computers (e.g. Raspberry Pis and Nvidia Jetsons)
    * When we deploy algorithms, we don't often get to run them on our personal computers but rather on some other, usually weaker and smaller, computer on board the robot.
    * SSH, and working headless.
* It may often come in handy to be able to design hardware parts in CAD. After all, we work on physical systems here that may need modifications or additions.
* Git and GitHub
* Python, especially if you are working in machine learning. In this case, PyTorch or Tensorflow are a must. Pytorch3D if you work on, well, 3D. In this case also Open3D (Python and C++) and PCL(C++) could be nice.
* C++ for real-time systems.


## The How: Interviewing Rules of Thumb

Before you get to the stage of being interviewed at all, I would try to figure out what kinds of topics you'll be interacting with in your role or field of study. Once you know that, brush up on relevant knowledge and **implement the algorithms** that are related to it. I find **learning by doing** to be extremely effective (and fun!). Some interviewers like asking for coding-challenges. Either on a board or via some online resource like LeetCode or HackerRank. Make sure to practice those challenges too if you think there is a chance that you'll be asked to complete one. Finally, practice the "expected" question. "Tell me about yourself," "tell me about a project you have worked on and your part in it," "tell me about a challenging time in your professional life," etc., are all questions you should be able to answer in your sleep (or right after waking up -- that would be a bit less creepy). Be concise and confident. I like treating interviews as friendly conversations where the interviewer is genuinely curious to know more about you. So if they are so interested in you, how could you not tell them? :)

In a technical interview, I follow a few simple rules of thumb:

* When asked to come up with a solution to a problem,
    * Communicate your thoughts! Communicat your assumptions!
    * Communicating your assumption about the problem shows that you are communicating well and would also help you to understand the problem better. Literally restating the problem back to the interviewer is good. If you are unsure about something, ask for clarification. [This was introduced to me by some Google employees.]
    * As you formulate your solution, always start with the simplest solution you can find. Once you get there, ask if the interviewer would like you to improve on the naive solution.  [This was also introduced to me by some Google employees.]
    * I find it better to speak out my thoughts instead of thinking silently. I feel like it keeps the interviewer engaged and shows that you have a clear line of thoughts.

* When asked to describe a project,
    * Know the tools you have used before. Whether it is YOLO, Octomapping, GTSAM, some other deep learning models or algorithms, make sure you know how they work. You don't have to be familiar with all the details, but definitely understand the bigger picture. If asked why you chose those tools instead of others, be able to justify your choices. 
    * If you worked on a team, be able to describe your part in detail. 


And that's all for today! These are my quick thoughts on the **what** and **how** of robotics interviews and engineering. This post is a bit of a thought-dump -- I hope it would at the very least direct you towards some helpful keywords :robot:.