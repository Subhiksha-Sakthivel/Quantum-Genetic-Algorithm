# Quantum-Genetic-Algorithm
An implementation of quantum genetic algorithm in Google Colab

Funtion Used: Rastrigin Function

Number of Variables: 5

Number of solutions: 6

Range in which the solutions exist: -5 to +5

First step is generating the quantum population:
  10 quantum genes are generated randomly in the above range as a uniform distribution with its pdf being 1. Every 2 quantum genes interfere to generate pdfs and their cdfs are generated. Each cdf represents a varaible. Hence there are 5 cdfs generated. 

Second step is converting the Quantum population to Classical population:
  Random 6 y values in the range of 0 to 1 are chosen and their corresponding x values from each cdf are derived. These represent the values of one variable in every solution(chromosome). Since, each solution(chromosome) has 5 variales(genes) every x value derived from the cdf corresponds to the value of the variable in every solution. Thus all the 6 solutions obtained are considered as Classical population.

Third step is to apply Classical Genetic Algorithm on the Classical population and deriving 2 Classical Best solutions:
  Genetic algorithms are commonly used to generate high-quality solutions to optimization on the given Rastrigin function by relying on biologically inspired operators such as mutation, crossover and selection. If the children generated are not better than the parents then the children are generated again.Then 2 best solutions are extracted to form Classical population.
  
Fourth step is converting the 2 Classical best solutions to Quantum population and repeat from step 2:
  Each variable's value is extracted from the solutions and converted to quantum gene by considering the value as center to the uniform distribution with pdf value of 1. Thus these 10 quantum genes are generated and two of the same varaible's values interfere to generate a pdf and their cdfs are generated. Thus 5 cdfs are generated and then passed on to the Second step. 
  
Stopping Criteria considered here is: 
  1)Maximum number of Iterations as 50 (or)
  2)If all the children are better than the parents
