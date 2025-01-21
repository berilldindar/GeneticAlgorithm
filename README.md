# GeneticAlgorithm
![194086716-2deaab61-af0b-403f-8984-eab34bf0688c](https://github.com/user-attachments/assets/574f856f-11bc-4f1e-842f-e24aee664923)

Genetic Algorithm for Image Approximation

Introduction

This project demonstrates the use of a genetic algorithm (GA) to approximate an image by evolving a population of candidate solutions (organisms) over generations. The algorithm iteratively improves a collection of colored circles until the rendered result closely resembles a target image.

Genetic algorithms are inspired by the process of natural selection. They use techniques such as mutation, crossover, and selection to evolve a population toward a better solution. In this project, genes represent individual circles, and organisms are collections of these circles.

How It Works

Main Concepts

Gene:

Represents a single circle in the image.

Has properties such as position, diameter, and color.

Can mutate by changing one of its properties.

Organism:

Represents an individual solution (image composed of circles).

Contains multiple genes.

Can mutate by altering genes, adding new genes, or removing existing ones.

Fitness Function:

Compares the organism's rendered image to the target image.

Measures the difference between pixel values to calculate fitness.

Lower fitness scores are better (closer resemblance to the target image).

Workflow

Initialization:

The program starts with a random population of organisms. Each organism contains a number of randomly initialized genes.

Rendering:

Each organism is converted into an image by drawing its genes (circles).

Fitness Evaluation:

The fitness function calculates the difference between the organism's image and the target image.

Mutation and Selection:

The organism population undergoes mutation, where genes may change, be added, or removed.

A subset of organisms with the best fitness scores is selected to form the next generation.

Iteration:

Steps 2-4 are repeated for multiple generations.

Periodically, the best organism's image is saved to the Outputs directory to visualize progress.

Parallelization:

To improve performance, the mutation and fitness evaluation steps are distributed across multiple CPU cores using Python's multiprocessing module.

Code Overview

Key Components

Classes:

Point: Represents 2D coordinates for circle positions.

Color: Stores RGB values for circle colors and handles adjustments.

Gene: Encodes a circle's properties (position, color, size) and handles mutation.

Organism: Represents a collection of genes, manages mutations, and renders the image.

Functions:

fitness(im1, im2): Computes the pixel-wise difference between two images.

mutateAndTest(o): Creates a mutated copy of an organism and evaluates its fitness.

groupMutate(o, number, p): Distributes the mutation and testing of organisms across multiple processes.

run(cores): Orchestrates the genetic algorithm, iteratively improving the population over generations.

Parameters

POP_PER_GENERATION: Number of organisms per generation.

MUTATION: Probability of mutating a gene.

ADD_GENE: Probability of adding a new gene to an organism.

REM_GENE: Probability of removing a gene from an organism.

INITIAL_GENES: Number of genes in the initial population.

GENETAIONS_PER_IMAGE: Number of generations after which the current best organism's image is saved.

File Input

The target image (OdevSoru.png) is loaded at the beginning of the program. Ensure this file is present in the working directory.

Output

Evolved images are saved periodically to the Outputs directory, allowing you to track the progress of the algorithm.

Example Outputs

Over generations, the algorithm starts with a random collection of circles and gradually refines them to resemble the target image. Early generations are chaotic, but subsequent generations show increasing resemblance as the algorithm converges.

Applications

Image approximation and artistic rendering.

Optimization problems in other domains such as engineering, logistics, and machine learning.

Conclusion

This project is a creative demonstration of genetic algorithms in solving a visual approximation task. By combining simple biological principles with computational power, it showcases the potential of evolutionary techniques in optimization and creativity.

