<!-- OXFORD: You may submit either a research proposal comprising a detailed outline of your intended research or, if you are not yet ready to submit a full proposal, you should submit a statement of research interests, in English, describing the general area of research in which you are interested. You should summarize the research in this area that you are aware of, referring to existing papers where appropriate. You could also describe a research problem and your initial ideas on research work towards solving this or open problems. -->
<!-- MIT: what you would like to study -->
# Statement of Purpose

I am interested in the _context_ in which tasks are performed. When I drive a car, how does my mind access previously learned driving skills and what internal signal cues this process? How do I retrieve memories relevant to the activity, like the meaning of traffic signs or the dynamics of moving vehicles? How does the mind orchestrate component tasks like steering, navigation, and observation? These are the questions that distinguish an autonomous driving algorithm from a thinking human behind the wheel.

Despite the seemingly unstoppable march of its conquests, machine learning is mostly confined to domains in which task context is static. Here, _context_ refers to the information that transcends specific tasks, but organizes and governs the programs for executing them. Mechanisms for establishing and mutating context include memory, planning, and abstract thought. Tasks that depend heavily on context tend to be more difficult, including one-shot learning, multi-task learning, planning, variable binding, etc.

<!-- Drawing an analogy between the mind and a computer, most machine learning focuses on the CPU, while the programs that populate computer memory and establish the state of the system before the computation is even performed remain a mystery. I would like to understand those programs: how they are stored -->

I would like to design machines that emulate the mind's ability to create and modify context: how it cues task-specific programs, how it accesses relevant knowledge from the morass of memory accumulated over a lifetime, and how it orchestrates these processes to accomplish large, complex tasks. The specific problem that I am interested in for my doctoral research <!-- at X University --> is how to combine constituent tasks to perform larger complex ones.

Several recent works have deeply influenced my thinking on these subjects. In "Neural Program Interpreters," De Freitas et al. train a model to store task-specific programs in memory, and to dynamically switch between these programs in order to perform complex tasks like addition of large numbers. This paper concretely demonstrates the capability to encode entire programs in compact hidden state vectors. It also demonstrates that a deep recurrent neural network can learn to choose among these programs in the performance of larger tasks, much like the human driver who integrates subtasks, like pedaling and steering into the larger task of driving.

In “Control of Memory, Active Perception, and Action in Minecraft,” Singh et al. train a model to perform complex, sequence-based tasks in 3D maze environments by combining deep Q-learning with an external memory architecture similar to the one that Sukhbaatar et al. present in "End-To-End Memory Networks." With the aid of this memory architecture, the model is able to perform tasks with long temporal dependencies that thwart ordinary deep Q-networks.

Finally, in "Hierarchical Deep Reinforcement Learning: Integrating Temporal Abstraction and Intrinsic Motivation," Tenenbaum et al. train a model, _h-DQN_, to master a relatively complex video game (Montezuma's Revenge) by learning to decompose the game into simpler subgoals. This paper demonstrates that a model can accomplish more complex tasks with a division of labor between parts responsible for choosing goals and parts responsible for executing the associated tasks. This paper demonstrates that with an encoding that effectively constrains the space of possible goals, a model can learn to choose subgoals for the sake of larger directives.

I am interested in extending these works to perform tasks

- that are too complex to be discovered by purely random exploration.
- without any domain-specific constraints on the goal/subtask space.
- ideally with reinforcement learning, not supervised learning.

<!-- I propose a model that includes a controller and a meta-controller, like Tenenbaum's _h-DQN_, with the meta-controller responsible for specifying goals or tasks and the controller responsible for executing them. -->

I would also like to borrow several ideas from an earlier work, "Intrinsically Motivated Reinforcement Learning." In this work, Singh et al. train a model to learn complex tasks in a toy environment with discrete states. The model receives rewards for discovering "salient" states and these rewards are proportional to the unexpectedness of the state. Inspired by this approach, I would like to use artificial curiosity as a heuristic to encourage broader exploration. In Dr. Singh's paper, salient states are hard-coded. I would like to explore more dynamic criteria.
<!-- For example we might train an additional network to predict state transitions and use this to assess unexpectedness---if the network predicted a low probability for a transition, this would indicate that something unexpected and therefore salient had occurred. -->
<!-- Lyle: is this pedantic? -->

Another important feature of the model proposed in this paper is that it learns higher-order actions with increasing levels of abstraction. For example, to turn on a light, the model must perform a three-step sequence of actions. However, after discovering this salient event, the "turn on light" action becomes atomic, and the model can cue the associated subroutine as a single action. I would like to develop a model that learns to perform a similar kind of abstraction over complex tasks. The three works that I originally mentioned all demonstrate methods for encoding and therefore compressing complex actions, which could be applied to this purpose.

<!-- Finally, I am interested in exploring one more novel direction of research: deeper hierarchy in the system of learners. Like a deep network with many layers, the system might benefit from multiple layers of controllers: higher level controllers training lower level controllers and pushing increased responsibility to them over time, with more complex goals and sparser feedback. -->

The goal of this research is a learner capable of autonomously navigating a complex environment, learning new skills without a human specifying them and with minimal supervision or feedback. I consider this an exciting and attainable next step in artificial intelligence research.
