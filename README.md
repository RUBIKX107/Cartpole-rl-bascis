# Cartpole-rl-bascis 

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
