---
toc: True
comments: True
layout: post
title: Popcorn hacks
courses: {'compsci': {'week': 24}}
type: hacks
---

# CB popcorn hacks
4.as a popcorn hack (binary challenge), describe an overflow in 8 binary digits
- Add 1 to 11111111 (255) because this exceeds the maximum value so it causes overflow 

5.As a popcorn hack (coding challenge), create multiple new circuits and gates
- NAND: def NAND_gate(A, B):
    return not (A and B)

11.as a hack (binary challenge), make the rgb standard colors

import matplotlib.pyplot as plt
import matplotlib.patches as patches

# Function to convert binary to decimal
def binary_to_decimal(binary):
    return int(binary, 2)

def plot_colors(rgb_triplets):
    # Create a figure with one subplot per RGB triplet
    fig, axs = plt.subplots(1, len(rgb_triplets), figsize=(2 * len(rgb_triplets), 2))
    
    # Ensure axs is always a list
    axs = axs if len(rgb_triplets) > 1 else [axs]

    for ax, (red_binary, green_binary, blue_binary) in zip(axs, rgb_triplets):
        # Convert to binary strings to decimal
        red_decimal = binary_to_decimal(red_binary)
        green_decimal = binary_to_decimal(green_binary)
        blue_decimal = binary_to_decimal(blue_binary)

        # Normalize number to [0, 1] range, as it is expected by matplotlib 
        red, green, blue = red_decimal/255, green_decimal/255, blue_decimal/255

        # Define a rectangle patch with the binary RGB triplet color and a black border
        rect = patches.Rectangle((0, 0), 1, 1, facecolor=(red, green, blue), edgecolor='black', linewidth=2)
        
        # Add the rectangle to the plot which shows the color 
        ax.add_patch(rect)

        # Remove axis information, we just want to see the color
        ax.axis('off')

        # Print the binary and decimal values
        print("binary:", red_binary, green_binary, blue_binary)    
        print("decimal", red_decimal, green_decimal, blue_decimal)
        print("proportion", red, green, blue)

    # Show the colors
    plt.show()

50.as a popcorn hack (coding challenge), scale list of size by factor of 10 and measure the times