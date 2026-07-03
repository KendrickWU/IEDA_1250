# IEDA 1250 Tutorial Script

**Tutorial:** Introduction to Queuing Theory  
**Based on:** `Tutorial/Jul03_QueuingTheory_Tutor.pdf`  
**TA:** Wu Hongfan  
**Course:** IEDA 1250, The Hong Kong University of Science and Technology  

This script is written to be read aloud. You can slow down at the practice slides and skip some repeated wording if time is short.

## Slide 1: Title

Good afternoon everyone. Today we will go through a tutorial on queuing theory.

In this course, queuing theory is used to analyze waiting systems. These systems appear in many familiar settings: customers waiting at a bank, jobs waiting for a server, cars waiting at a toll booth, or students waiting for help during office hours.

The key idea is that a queueing system is not only about how many customers arrive. It is also about how fast the service is, how long customers wait, how many customers are in the system, and whether the system is stable.

Today I will focus on four parts: basic queuing parameters, Little's Law, M/M/1 performance metrics, and birth-and-death processes.

## Slide 2: Outline

This slide shows the structure of today's tutorial.

First, we introduce queuing theory and define the core parameters, such as arrival rate and service rate.

Second, we discuss Little's Law. This is one of the most useful formulas in queuing theory because it connects the number of jobs, the arrival rate, and the time spent in the system.

Third, we summarize the standard formulas for an M/M/1 queue.

Finally, we introduce birth-and-death processes, which provide a more general way to derive steady-state probabilities.

## Slide 3: Core Parameters: Rates and Times

Let us start with arrivals and service.

For arrivals, we often assume a Poisson process. The average arrival rate is denoted by lambda, written as lambda. For example, if lambda equals 3 jobs per second, then on average 3 jobs arrive every second.

The mean interarrival time is 1 over lambda. This is the average time between two consecutive arrivals. If lambda is 3 jobs per second, then the mean interarrival time is one third of a second.

For service, we often assume exponential service time. The average service rate is denoted by mu. For example, if mu equals 4 jobs per second, the server can complete 4 jobs per second on average.

The mean service time is E of S, and it equals 1 over mu. If mu is 4 jobs per second, then the mean service time is one fourth of a second.

Please pay attention to the units. If lambda is customers per hour, then 1 over lambda is hours per customer. If mu is jobs per second, then 1 over mu is seconds per job.

## Slide 4: Performance Metrics

Now we define the main performance metrics.

T means response time, or time in system. It includes both waiting time and service time.

TQ means waiting time in the queue. This is only the time before service begins.

S means service time. Therefore, the relationship is:

E of T equals E of TQ plus E of S.

Next, N means the number of jobs in the system. The system includes both the queue and the jobs being served.

NQ means the number of jobs in the queue only.

Throughput is the rate at which jobs are completed. If C jobs are completed over a time period tau, then throughput is C divided by tau.

Utilization, denoted by rho, is the fraction of time the server is busy. If the server is busy for B units of time during a total observation time tau, then utilization is B divided by tau.

## Slide 5: Remarks on the Metrics

This slide makes two important points.

First, for a single-server queue, the stability rule is lambda less than mu.

Intuitively, customers must arrive more slowly than the server can process them. If lambda is greater than or equal to mu, then the server cannot keep up in the long run, and the queue tends to grow without bound.

Second, there is a throughput paradox.

The question is: if we make the server faster, does throughput increase?

The answer is: not necessarily. If the system is stable and every arriving job eventually gets served, then long-run throughput is limited by the arrival rate. In that case, throughput X equals lambda.

A faster server reduces waiting time and queue length, but it does not create more arrivals. So throughput is bottlenecked by arrivals, not by service speed, as long as the system is stable.

## Slide 6: Section Transition to Little's Law

Now we move to Little's Law.

This is probably the most important relationship in this tutorial. It is simple, but very powerful.

The main reason it is powerful is that it applies to many stable systems, not only M/M/1 queues.

## Slide 7: Little's Law

Little's Law states that:

E of N equals lambda times E of T.

Here E of N is the long-run average number of jobs in the system. Lambda is the average arrival rate. E of T is the average time a job spends in the system.

Let us use the coffee shop example.

Suppose 10 customers enter the shop per hour, so lambda equals 10 customers per hour. Also suppose each customer spends 0.5 hours in the shop on average.

Then by Little's Law:

E of N equals 10 times 0.5, which equals 5 customers.

So on average, there are 5 customers in the coffee shop.

The units also make sense: customers per hour times hours equals customers.

## Slide 8: Applying Little's Law

The most important idea on this slide is that we can define the system in different ways.

If the system is the entire facility, including the waiting line and the servers, then Little's Law gives:

E of N equals lambda times E of T.

Here N is the number of jobs in the entire system, and T is the total time in the system.

If the system is only the waiting line, then Little's Law gives:

E of NQ equals lambda times E of TQ.

Here NQ is the number of jobs waiting in line, and TQ is the waiting time before service starts.

So Little's Law is flexible. We just have to be consistent about what we call the system.

## Slide 9: Applying Little's Law: Deriving Utilization

Now we use Little's Law to derive utilization.

This time, define the system as only the server itself, excluding the waiting line.

The average time a job spends in this system is the average service time, E of S.

The expected number of jobs inside the server is either 1 or 0. If the server is busy, there is 1 job in service. If the server is idle, there are 0 jobs in service.

Therefore, the expected number in the server equals the probability that the server is busy. This is exactly utilization, rho.

Applying Little's Law to the server only:

rho equals lambda times E of S.

Since E of S equals 1 over mu, we get:

rho equals lambda over mu.

This is the utilization law for a single server.

## Slide 10: Practice: Little's Law

Now let us work through the bank example.

Midtown Bank has two tellers. Customers arrive at a mean rate of 40 per hour. Each teller requires an average of 2 minutes to serve a customer. Customers wait in a single line for an average of 1 minute before service begins.

First, compute the mean time in system.

Waiting time is 1 minute. Service time is 2 minutes. Therefore:

E of T equals E of TQ plus E of S, which equals 1 plus 2, so E of T equals 3 minutes.

Next, compute the mean number in queue.

The arrival rate is 40 per hour. To use minutes, convert it to customers per minute:

40 per hour equals 40 divided by 60, which is 2 over 3 customers per minute.

Then:

E of NQ equals lambda times E of TQ, which equals 2 over 3 times 1, so E of NQ equals 2 over 3 customers.

Finally, compute the mean number in system:

E of N equals lambda times E of T, which equals 2 over 3 times 3, so E of N equals 2 customers.

Notice that the number in the system includes both waiting customers and customers being served.

## Slide 11: Section Transition to M/M/1 Performance Metrics

Now we move to M/M/1 queues.

The notation M/M/1 means three things.

The first M means Markovian arrivals, usually a Poisson arrival process.

The second M means Markovian service times, usually exponential service times.

The 1 means there is one server.

For M/M/1 queues, we have closed-form formulas for the main performance metrics.

## Slide 12: Summary of M/M/1 Performance Metrics

This slide summarizes the standard M/M/1 formulas.

First, define utilization:

rho equals lambda divided by mu.

For stability, we need rho less than 1, which is equivalent to lambda less than mu.

The expected number of jobs in the system is:

E of N equals rho over 1 minus rho.

The expected number of jobs in the queue is:

E of NQ equals rho squared over 1 minus rho.

The difference between E of N and E of NQ is rho, because rho is the expected number of jobs in service.

For time metrics, the expected time in the system is:

E of T equals 1 over mu minus lambda.

The expected waiting time in queue is:

E of TQ equals rho over mu times 1 minus rho.

The expected service time is:

E of S equals 1 over mu.

And again:

E of T equals E of TQ plus E of S.

These formulas are also consistent with Little's Law:

E of N equals lambda times E of T, and E of NQ equals lambda times E of TQ.

## Slide 13: Section Transition to Birth and Death Processes

Next, we move to birth-and-death processes.

This part may look more theoretical, but the idea is simple. We track the number of jobs in the system as a state, and the state changes by plus one or minus one.

An arrival increases the state by one. A service completion decreases the state by one.

## Slide 14: Birth and Death Processes

A birth-and-death process is a continuous-time Markov chain with states 0, 1, 2, and so on.

The key restriction is that transitions can only go to adjacent states. From state i, the process can move to i plus 1 or i minus 1.

In a queueing system, the state usually represents the number of jobs in the system.

A birth means the state increases by one. In a queueing system, this is usually an arrival. The birth rate from state i is lambda sub i.

A death means the state decreases by one. In a queueing system, this is usually a service completion. The death rate from state i is mu sub i.

When there are i jobs in the system, the time until the next birth is exponentially distributed with rate lambda sub i, and the time until the next death is exponentially distributed with rate mu sub i.

The independence assumption helps us write balance equations and solve steady-state probabilities.

## Slide 15: M/M/1 and M/M/K as Special Cases

M/M/1 and M/M/K queues are special cases of birth-and-death processes.

For M/M/1, the state n is the number of jobs in the system. The arrival rate is usually constant lambda, and the service completion rate is usually mu whenever n is at least 1.

Pi sub n denotes the steady-state probability that the system has n jobs.

So if pi 0 is large, the system is often empty. If pi n is large for large n, the system often has many jobs and long queues.

## Slide 16: Birth and Death Processes: Balance Equations

Now we introduce the balance equations.

At steady state, the probability flow into a state equals the probability flow out of that state.

For state 0, the only way to leave state 0 is a birth from 0 to 1. The rate is lambda 0 times pi 0.

The only way to enter state 0 is a death from 1 to 0. The rate is mu 1 times pi 1.

So:

lambda 0 pi 0 equals mu 1 pi 1.

For a general state n greater than 0, the total flow out of state n is:

lambda n plus mu n, times pi n.

The flow into state n comes from state n minus 1 by a birth, and from state n plus 1 by a death.

The slide then shows that these balance equations simplify to the local balance equations:

lambda n pi n equals mu n plus 1 times pi n plus 1.

This local balance equation is what we use to solve the steady-state probabilities.

## Slide 17: Solving Steady-State Probabilities

Using local balance, we can express every pi n in terms of pi 0.

From state 0 and 1:

pi 1 equals lambda 0 over mu 1 times pi 0.

Then:

pi 2 equals lambda 1 over mu 2 times pi 1.

Substituting pi 1, we get:

pi 2 equals lambda 1 lambda 0 over mu 2 mu 1 times pi 0.

Continuing this process:

pi n equals lambda n minus 1 times lambda n minus 2, all the way down to lambda 0, divided by mu n times mu n minus 1, all the way down to mu 1, times pi 0.

Finally, we use the normalization condition:

the sum of all pi n equals 1.

This lets us solve for pi 0, and then all other probabilities follow.

## Slide 18: Deriving Steady-State Probabilities for M/M/1

For M/M/1, the birth rate is lambda in every state, and the death rate is mu whenever there is at least one job in the system.

Using local balance:

pi 1 equals lambda over mu times pi 0.

Let rho equal lambda over mu.

Then pi 1 equals rho pi 0, pi 2 equals rho squared pi 0, and in general:

pi i equals rho to the i times pi 0.

Now use normalization:

the sum from i equals 0 to infinity of pi i equals 1.

So:

pi 0 times the sum from i equals 0 to infinity of rho to the i equals 1.

If rho is less than 1, the geometric series equals 1 over 1 minus rho.

Therefore:

pi 0 equals 1 minus rho.

Substituting back:

pi i equals rho to the i times 1 minus rho.

This is the steady-state distribution of the number of jobs in an M/M/1 queue.

## Slide 19: Deriving the Expected Number of Jobs

Now we use the steady-state probabilities to compute E of N.

By definition:

E of N equals the sum over all states i of i times pi i.

For M/M/1, pi i equals rho to the i times 1 minus rho.

So:

E of N equals the sum from i equals 1 to infinity of i times rho to the i times 1 minus rho.

We can factor out rho times 1 minus rho:

E of N equals rho times 1 minus rho times the sum from i equals 1 to infinity of i rho to the i minus 1.

Using the standard geometric series derivative:

the sum from i equals 1 to infinity of i rho to the i minus 1 equals one over open parenthesis one minus rho close parenthesis squared.

Therefore:

E of N equals rho over 1 minus rho.

This matches the M/M/1 formula from earlier.

## Slide 20: Practice: Birth-and-Death Process

Now let us solve the birth-and-death practice problem.

We are given death rates:

mu n equals 2 for all n equal to 1, 2, and so on.

The birth rates are:

lambda 0 equals 3, lambda 1 equals 2, lambda 2 equals 1, and lambda n equals 0 for n greater than or equal to 3.

Because lambda 3 equals 0, once the process reaches state 3, there is no birth to state 4. Therefore, the only possible states with positive probability are 0, 1, 2, and 3.

For part (a), the CTMC diagram is:

state 0 goes to state 1 at rate 3, and state 1 goes back to state 0 at rate 2.

state 1 goes to state 2 at rate 2, and state 2 goes back to state 1 at rate 2.

state 2 goes to state 3 at rate 1, and state 3 goes back to state 2 at rate 2.

There are no states 4, 5, and so on in steady state because the birth rate from state 3 is zero.

For part (b), use local balance.

First:

lambda 0 pi 0 equals mu 1 pi 1.

So:

3 pi 0 equals 2 pi 1, which gives pi 1 equals 3 over 2 pi 0.

Next:

lambda 1 pi 1 equals mu 2 pi 2.

So:

2 pi 1 equals 2 pi 2, which gives pi 2 equals pi 1 equals 3 over 2 pi 0.

Next:

lambda 2 pi 2 equals mu 3 pi 3.

So:

1 pi 2 equals 2 pi 3, which gives pi 3 equals one half pi 2 equals 3 over 4 pi 0.

Now normalize:

pi 0 plus pi 1 plus pi 2 plus pi 3 equals 1.

Substitute:

pi 0 plus 3 over 2 pi 0 plus 3 over 2 pi 0 plus 3 over 4 pi 0 equals 1.

The coefficient is:

1 plus 1.5 plus 1.5 plus 0.75 equals 4.75, which is 19 over 4.

Therefore:

pi 0 equals 4 over 19.

Then:

pi 1 equals 6 over 19, pi 2 equals 6 over 19, and pi 3 equals 3 over 19.

For n greater than or equal to 4, pi n equals 0.

For part (c), compute the effective arrival rate:

lambda e equals the sum of lambda n pi n.

Only states 0, 1, and 2 have positive birth rates, so:

lambda e equals 3 pi 0 plus 2 pi 1 plus 1 pi 2.

Substitute the probabilities:

lambda e equals 3 times 4 over 19 plus 2 times 6 over 19 plus 6 over 19.

This equals 12 over 19 plus 12 over 19 plus 6 over 19, which equals 30 over 19.

Now compute E of N:

E of N equals 0 pi 0 plus 1 pi 1 plus 2 pi 2 plus 3 pi 3.

This equals 6 over 19 plus 12 over 19 plus 9 over 19, which equals 27 over 19.

For a single-server system, the number in queue is max of n minus 1 and 0. Therefore:

E of NQ equals 0 times pi 1 plus 1 times pi 2 plus 2 times pi 3.

This equals 6 over 19 plus 6 over 19, which equals 12 over 19.

Using Little's Law with the effective arrival rate:

E of T equals E of N divided by lambda e.

That is:

27 over 19 divided by 30 over 19, which equals 27 over 30, or 0.9.

Similarly:

E of TQ equals E of NQ divided by lambda e.

That is:

12 over 19 divided by 30 over 19, which equals 12 over 30, or 0.4.

So the final answers are:

pi 0 equals 4 over 19, pi 1 equals 6 over 19, pi 2 equals 6 over 19, pi 3 equals 3 over 19, and pi n equals 0 for n at least 4.

lambda e equals 30 over 19.

E of N equals 27 over 19.

E of NQ equals 12 over 19.

E of T equals 0.9.

E of TQ equals 0.4.

## Slide 21: Solving Birth-and-Death Process Problems

This slide summarizes the general procedure.

Step one: define the states and draw the CTMC diagram.

Look for termination rates. If a birth rate becomes zero, the system may have a finite number of reachable states.

Step two: establish the balance equations.

For birth-and-death processes, local balance is usually enough:

lambda n pi n equals mu n plus 1 pi n plus 1.

Step three: apply normalization.

The probabilities must sum to 1, so use this condition to solve for pi 0.

Step four: derive performance metrics.

E of N is the sum of n times pi n.

For time metrics, use Little's Law with the effective arrival rate lambda e.

That gives:

E of T equals E of N over lambda e, and E of TQ equals E of NQ over lambda e.

## Slide 22: Calculating E[NQ] in Single-Server Systems

This slide explains how to compute the expected number in queue.

In the practice problem, the death rate is constant and equal to 2 whenever the system is nonempty. This corresponds to a single-server system.

In a single-server system, if there are n jobs in the system and n is at least 1, then one job is in service and the remaining n minus 1 jobs are waiting in queue.

Therefore:

E of NQ equals the sum over n of n minus 1 times pi n.

For the practice problem, the largest possible state is K equals 3, so:

E of NQ equals the sum from n equals 1 to 3 of n minus 1 times pi n.

This n minus 1 logic is only for one server. If there were k servers, then the queue length in state n would be max of n minus k and 0.

## Slide 23: Thank You

That concludes today's queuing theory tutorial.

The main takeaways are:

First, always keep track of units. Arrival rates and service rates are rates; interarrival times and service times are times.

Second, Little's Law is flexible. We can apply it to the whole system, the queue only, or the server only.

Third, for M/M/1 queues, stability requires lambda less than mu, and the standard formulas depend on rho equals lambda over mu.

Fourth, birth-and-death processes let us derive steady-state probabilities using balance equations and normalization.

Thank you. If there is time, we can go back to the practice problem and discuss any step that was unclear.
