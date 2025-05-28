# Cartpole-rl-bascis 

Description

This project is a simple introduction to reinforcement learning using the classic CartPole-v1 environment from OpenAI Gym. It demonstrates how an agent interacts with an environment, takes random actions, and receives feedback in the form of rewards.

The project is useful for beginners exploring:

The structure of episodic tasks

Action-reward-feedback loops

Exploration vs exploitation concepts

Prepping for advanced RL algorithms (Q-Learning, SARSA, DQN)

Concepts Covered

Environment setup with gym.make()

Resetting and stepping through episodes

Handling episode termination via terminated and truncated

Understanding rewards and agent behavior in episodic tasks

The code

import gym
import numpy as np

# Create the environment
env = gym.make("CartPole-v1", render_mode="rgb_array")

# Run episodes
for episode in range(3):
    obs, _ = env.reset()
    done = False
    total_reward = 0
    
    while not done:
        action = env.action_space.sample()
        obs, reward, terminated, truncated, _ = env.step(action)
        done = terminated or truncated
        total_reward += reward

    print(f"Episode {episode + 1}: Total Reward = {total_reward}")

env.close()


Results

Each episode returns the total reward collected by the agent using random actions. It’s a good starting point before implementing smarter policies.

Example output:

Episode 1: Total Reward = 22.0
Episode 2: Total Reward = 16.0
Episode 3: Total Reward = 19.0
