import matplotlib.pyplot as plt
import numpy as np

def braking_distance(initial_velocity, deceleration):
    braking_distance = (initial_velocity ** 2) / (2 * deceleration)
    return braking_distance

def calculate_deceleration(mu, theta):
    g = 9.8  # Acceleration due to gravity (m/s^2)
    deceleration = g * (mu * np.cos(np.radians(theta)) - np.sin(np.radians(theta)))
    return deceleration

def velocity_time_graph(initial_velocity, deceleration, time_interval):
    time_points = np.arange(0, time_interval + 0.1, 0.1)
    velocities = initial_velocity - deceleration * time_points
    return time_points, velocities

def distance_time_graph(initial_velocity, deceleration, time_interval):
    time_points = np.arange(0, time_interval + 0.1, 0.1)
    distances = initial_velocity * time_points - 0.5 * deceleration * time_points**2
    return time_points, distances

# User input for surface and inclination
mu_surface = float(input("Enter the coefficient of friction for the surface: "))
theta_inclination = float(input("Enter the inclination angle in degrees (0 for horizontal): "))

# Example parameters
initial_velocity = float(input("Enter the initial velocity of the vehicle (m/s): "))
deceleration = calculate_deceleration(mu_surface, theta_inclination)
time_interval = 10.0  # seconds

# Calculate braking distance
distance = braking_distance(initial_velocity, deceleration)
print(f"The braking distance is: {distance} meters")

# Velocity-time graph
time_points, velocities = velocity_time_graph(initial_velocity, deceleration, time_interval)
plt.subplot(2, 1, 1)
plt.plot(time_points, velocities, label='Velocity')
plt.title('Velocity-Time Graph')
plt.xlabel('Time (s)')
plt.ylabel('Velocity (m/s)')
plt.legend()

# Distance-time graph
time_points, distances = distance_time_graph(initial_velocity, deceleration, time_interval)
plt.subplot(2, 1, 2)
plt.plot(time_points, distances, label='Distance')
plt.title('Distance-Time Graph')
plt.xlabel('Time (s)')
plt.ylabel('Distance (m)')
plt.legend()

plt.tight_layout()
plt.show()
