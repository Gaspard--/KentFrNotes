# Choice of representation

Which one should i use?
-> often through experimenting, but the choice may impact results.

- Euclidean sensitive to noise

# Probabillity refresher

Random variable -> X
Instantiation of the radom variable -> x
Probabillity that x is observed -> P(x)
Noraisation condition -> sum for all possible x of P(x) = 1
If x is a continuous variable, then the normalisation condition becomes integration from min(x) to max(x) of P(x) * dx = 1

Markov chains:
Does not make sense to transition to oneself in continuous time (equivalent of waiting)
Transitions only depend on current state

# Conitnuous time vs descrete time

- Transitions in descrete are probabilties
- Transitions for CTMCs(ConTinuaous Markow Chaines) are rates
  - assumme at state s1 there are 3 possibilities k1, k2, k3
  - probability of first transition is k1 / (k1 + k2 + k3)
  - A rate (roughly) means the avergae amount of transitions that happen within a unit of time
  - the avergae waiting time for the first transition is 1 / k1
  - rates have a time element

Initial condition and steady state behaviour
- a Markov chain usualy in an initial state. s23 , Pt=0(S23) = 1
- At time T = infinity PT=infinity(si) for each state si
- under mild conditions, the probability of the end sates does not depend on the initial state.

# Pebbles, Metropolis, needles

Assumming a cercle in a square, and pebbles evenly distributed.

In that case:
pebbles in circle / pebbles in square
= Area of circle / area of square
= PI * a² / area of square
= PI * a² / 4 * a²
= PI / 4

Uses of the symbol PI: also used for steady state probabillity

PIx * p(x -> y) = PIy * p(y -> x)

## Metropolis alogrithm

We have a markow chain with states 1 .. N

1. start at state `a`
2. current state is `a` propose a new random state. Choice has to be symmetric. (This means that you have to think more about choice for the new state if symmetry is impossible)
3. accept this proposed move to new state `b` with the following acceptance `Paxx = min(1, PIb / PIa)`
4. goto 2

Probablity for a transition is Pacc * Pchoice

1. calculate the acceptance rate for each pair of states
2. calculate the chance chosing a given state (usually a fixed value)
3. multiply  these values. This will be the transition probability
4. if the transition probabilities to leave a state don't add to 1, then add a self-transition so that all probabilities add to 1.

## Finding steady state probabilities

1. Construct a Markow chain with states [1, N] 
2. Initialise a array of N to 0
3. Start in a random initial state
4. Do n times
   1. Do m times
      1. perform a TOWER SAMPLING to decide next state
      2. transition to new state
      3 Set i to the current state label
   2. count[i] += 1
5. Calculate estimated probability for PI(i) as
PI(i) = count[i] / n

'n' and 'm' must be very large numbers
The purpose of 'm' is to forget the initial state.

Nb: N ?= n

### TOWER SAMPLING

1. k = number of possible transitions from current state
2. We associate the transitions wut numbers in order of probability (not essential)
3. t[] array of size k + 1
   1. t[0] = 1
   2. t[k] = probabilitu of transition to k
4. r = rand between ° and 1
5. Find the index l such that:
   sum of t[i] for i in 0, l - 1 < r <= sum of t[i] for i between 0 and l


Detailed balance condition.

# Simulating a CTMC

1. choose a random initial state an set to T = 0
2. Assume current state is A, and there l state transitions from i.

P = sum of k(j) for j in [0, l[

3. r = random number between 0 and 1
4.

choose  deltaT = -1 / P * ln(r)
5. update T = T + deltaT
6. calculate transition probablities for all states and choose new state as in DTMC
7. goto 2
