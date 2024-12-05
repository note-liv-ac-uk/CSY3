# Recover 2
<font size="4">Hongye Qian</font> 


1. **Q: Why does the input pattern in the training set not include the value of $a_0$? What is the value of $a_0$? Explain your answer.**
The special input $a_0$ has a fixed value, which is equal to 1. **The input pattern in the training data set only contains has the input value from the index 1.** By letting the weight $w_0$ of the $a_0$ connection be renamed as $-\theta$, we have 
$$S = w_0 a_0 + \sum_{i=1}^n w_i a_i = -\theta + \sum_{i=1}^n w_i a_i$$ （题目中n=3)
Thus, we do no need to set the threhold manually. Instead, we can train the threhold as weight.
<br></br>
2. **Question:** **Does the weight $w_0$ of the connection between $a_0$ and the output $X_1$ change during the training? If so, how does it change during the training? If not, explain why the weight does not change.**
The weight $w_0$ of the $a_0$ connection change during the training. It changes in the same way as the weights of other connections. 
$$ w_0 = w_0 + \Delta w_0$$
$$\Delta w_0 = C e_1 a_0 = C (t_1 - X_1) a_0 = C (t_1 - X_1)$$
where $C$ is the learning rate.
<br></br>
3. **Will the perceptron learning rule converge if there is only one input pattern in the training set?**
Yes. There is only one input pattern in the training data set. Thus, the training set is linearly separable. The perceptron learning algorithm converges for the training data set that is linearly separable. When the algorithm terminates, the perceptron will produce the same output as the label for each input in the training data set.
<br></br>
4. **What is the limitation of the perceptron?**
A perceptron cannot be used to learn a non-absolutely linearly separable function. For example: XOR function.
<br></br>
5. **What is the advantage of a multilayer perceptron against a perceptron?**
   A perceptron can only learn linearly separable functions, while a multilayer perceptron can learn non-linearly separable functions.
<br></br>
6. **Why is the learning rule for multilayer perceptrons called backpropagation?**
It is called backpropagation because the weights of the multilayer perceptron are updated backwards, from the output layer to the input layer.
<br></br>
7. **Definition: Genetic Algorithm's**
- **Chromosome**: Genetic Algorithm's Chromosome is a string of characters, **coding a candidate solution for a particular problem.**
- **gene**: In GA, a gene is a character of a chromosome.
- **Allele**: Possible settings for a gene.
- **Population**: Population of chromosomes is a set of chromosomes, and it is the evolving unit.
<br></br>
- **Selection**: The selection operator chooses those chromosomes in the population that will be allowed to reproduce, and on average the fitter chromosomes produce more offspring than the less fit ones.
- **Mutation**: Mutation is to flip a random bit of a gen from its orginal state.
- **Crossover**: Crossover recombines parts of two parent chromosomes to make two "children".
- **Inversion**: Inversion  is a mutation where part of a chromosome is cut out, rotates by $180^\circ$ and then fitted back into the same position.
<br></br>
8. **What is a chromosome schema?**
A schema in the Schema theorem is a similarity template that describes a subset of strings with similarities at certain string positions.
<br></br>
9. **What characters are used to describe schemas of a binary chromosome?**
0, 1, and *.
<br></br>
10. **How many schemas are there in an N-bit chromosome?**
Following that for a schema to fit a chromosome, the schema must be of the same length as the chromosome at every locus have either the same character as there is in the chromosome or the "do not care symbol" *. Thus, there are $2^N$ schemas in an N-bit chromosome.
11. Formulate the schema theorem. What does it say on the role of highly fit, short defining length, low order schemas in the evolution of a population of chromosomes?
Highly fit, short defining length, low order schemas propagate from generation to generation and give an exponential increase of samples to the observed best.
<br></br>
11. **What problems can be solved by genetic algorithms?**
If the solution of a problem can be coded as binary strings, one could use genetic algorithms to obtain high quality (but not necessary optimal), heuristic solutions to this problem, in particular the optimization problems with non-differentiable fitiness functions.











