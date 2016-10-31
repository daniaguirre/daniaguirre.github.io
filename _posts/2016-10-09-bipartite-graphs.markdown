---
layout: post
title:  "Transitive Graphs"
subtitle: "a brief introduction"
date: 2016-10-09 23:34:01
images_url: /assets/images/
categories: [graph-theory]
---

## Automorphism

An automorphism of a graph $$G=(V,E)$$ is a bijective map $$\pi:V \to V$$ that preserves adjacency, i.e. 
if $$(v_1,v_2)\in E$$ then $$(\pi(v_1),\pi(v_2))\in E$$. 

$$
\begin{align*} 
	\begin{array}{ccc}
		\sigma:&V	&\to	&V \\
      		&1	&\to	&4 \\
      		&2	&\to	&1 \\
			&3	&\to	&2 \\
			&4	&\to	&3 \\
    \end{array}
\end{align*}
$$

![automorphism]({{page.images_url}}graph_test.png)

**Example 1.** *An automorphism of the square graph defined by the permutation $$\sigma=(1,2,3,4)$$.*

An automorphism of a graph $$G=(V,E)$$ can be seen as a permutation over the set of vertices $$V$$. 
Then, the automorphism of the **Example 1** is denoted by the permuation $$\sigma=(1,2,3,4)$$ (in [cycle notation][cycle_notation]{:target="_blank"}). 
Notice that $$\sigma^2=(1,3)(2,4)$$, $$\sigma^3=(1,4,3,2)$$ and $$\sigma^4=(1)(2)(3)(4)$$ are also automorphisms of the square graph.

**Example 2.** *The automorphisms of the square graph defined by the permutations $$\sigma^2$$, $$\sigma^3$$ and $$\sigma^4$$.*

Here, we have two interesting questions:

1. Do all graphs have any automorphism?
2. What is the maximum number of automorphisms of a graph?

The answer of the first question is *yes*, all graphs have at least the `trivial automorphism`, denoted by $$\varepsilon$$, 
that maps each vertex with itself. As we can see in the **Example 2**, $$\varepsilon=\sigma^4$$. 
Turning now to the second question, since an automorphism is defined by a permutation over $$|V|$$, 
then a graph has at most $$|V|!$$ automorphisms, it is the number of permutation of the set $$V$$. 
Then the set of automorphisms of a graph $$G=(V,E)$$, denoted by $$Aut(G)$$, is a subset of the set of permutations of $$V$$.
In fact, for the complete graph $$K_n$$, $$Aut(K_n)$$ is set of permuation of $n$ elements.
By the other hand, for the square graph $$Aut(G)=\{\varepsilon, \sigma, \sigma^2, \sigma^3, \rho, \tau\}$$, where $$\rho=(2,4)$$ and $$\tau=(1,3)$$.

**Example 3.** *The automorphisms of the $$K_3$$.*

## Vertex-transitive Graphs

A graph $$G=(V,E)$$ is vertex-transitive if there is an automorphims between any two of its vertices, i.e. 
for all $$u,v \in V$$, there exists $$\pi \in Aut(G)$$ such that $$\pi(u)=v$$. Notice that the graph of **Example 1** is vertex-transitive.
Now, look at the graph of **Example 4**, is it vertex-transitive?. 

**Example 4.** *The 3-path graph with the automorphism $$\sigma = (1,3)$$ and $$Aut(G)=\{\varepsilon, \sigma\}$$*

Roughly speaking, all nodes in a vertex-transive graph have the same *"graph perpective"*. 
From **Example 4** vertices $$1$$ and $$3$$ have the same *"graph perpective"*, actually $$\sigma$$ defines an automorphism between these vertices.
However, the vertex $$2$$ has a different *"graph perpective"*, then it is not possible
define automorphism over $$G$$ that maps the vertex $$2$$ with the vertex $$1$$ or $$3$$.
Therefore, the graph of **Example 4** is not vertex-transitive. 

In general, all vertex-transitive graph are [regular][regular_graph]{:target="_blank"} but not all regular graphs are vertex-transitive.

## Edge-transitive Graphs

A graph $$G=(V,E)$$ is edge-transitive if there is an automorphism between any two adjacent vertices, i.e. 
for all $$(u,v) \in E$$, there exists $$\pi \in Aut(G)$$ such that $$(\pi(u),\pi(v))\in E$$. 
From **Example 4**, $$E=\{(1,2),(2,3)\}$$ and  $$(\sigma(1),\sigma(2))=(3,2), (\sigma(3),\sigma(2))=(1,2)\in E$$,
therefore the 3-path graph is edge-transitive. Following a similiar approach it can be showed that
the square graph (see **Example 1**) is also edge-transitive.  

**Example 5.** *A graph with the automorphisms $$\sigma = (1,2,3,4,5)(6,7,8,9,10)$$, $$\rho=(1,6)(2,7)(3,8)(4,9)(5,10)$$, 
$$\tau=(2,5)(3,4)(7,10)(8,9)$$ and $$Aut(G)=\{\varepsilon, \sigma^i, \sigma^i\rho, \rho, \tau\}$$* for $$1\leq i \leq 5$$.

Let see if the graph $$G=(V,E)$$ of **Example 5** is edge-transitive. Let $$E_1$$, $$E_2$$ and $$E_3$$ be subsets of $$E$$, such that 
$$E=E_1\cup E_2 \cup E_3$$ where $$E_1=\{(1,2),(2,3),(3,4),(4,5),(5,1)\}$$, $$E_2=\{(6,7),(7,8),(8,9),(9,10)\}$$ and
$$E_3=\{(1,6),(2,7),(3,8),(4,9),(5,10)\}$$. We have that:

- $$\sigma^i\rho$$ defines an automorphism from edges in $$E_1$$ to edges in $$E_2$$, 
e.g. $$(1,2)\in E_1$$ and $$(\sigma(\rho(1)),\sigma( \rho (2)))=(\sigma(6),\sigma(7))=(7,8)\in E_2$$.
- $$\sigma^i$$ defines an automorphism between edges in $$E_1$$ and $$E_2$$, 
e.g. $$(3,4)\in E_1$$ and $$(\sigma(3),\sigma(4))=(4,5)\in E_1$$. Similarly, $$(7,8)\in E_2$$ and $$(\sigma^2(7),\sigma^2(8))=(9,10)\in E_2$$.
- $$\tau$$ defines an automorphism between edges in $$E_3$$. 
e.g. $$(2,7)\in E_3$$, $$(\tau(2),\tau(7))=(5,10)\in E_3$$. 

However, since edges in $$E_3$$ are part of two cycles of length 4 and edges in 
$$E_1 \cup E_2$$ are part of a cycle of length 4 and a cycle 5, then it is not possible define an automorphism between them.
Therefore, the graph of **Example 5** is not edge-transitive, however it is vertex-transitive.
Intuitively, it means that edges in sets $$E_1 \cup E_2$$ and $$E_3$$ have a different *"graph perpectives"*.  

## Arc-transtive graphs

As we can see there are graphs that have edge-transitive but not vertex-transitive (see **Example 2**) and
there are graph that are vertex-transive but not edge-transitive (see **Example 3**)

## Some remarks

Lectors familiarized with [algebraic groups][algebraic_groups]{:target="_blank"} can note that 
$$Aut(G)$$ has a group structure with respect to the composition of functions, where $$\varepsilon$$ is the identity element.
In fact, $$Aut(G)$$ is a subgroup of the [symmetric group][symmetric_group]{:target="_blank"} 
which consists of the set of all permutations of a set.

The smallest knew graph that is vertex and edge-transitive but not arc-transitive is the **Holt graph** discovered by Derek Holt in the seventies.
By the way, if you want keep in touch with Derek Holt, it is only necessary to ask for an interesting question about automatic group theory
in [mathoverflow][mathoverflow_dholt]{:target="_blank"}.

[algebraic_groups]: https://en.wikipedia.org/wiki/Group_(mathematics)
[symmetric_group]: https://en.wikipedia.org/wiki/Symmetric_group
[cycle_notation]: https://en.wikipedia.org/wiki/Permutation#Cycle_notation
[regular_graph]: https://en.wikipedia.org/wiki/Regular_graph
[mathoverflow_dholt]: http://mathoverflow.net/users/35840/derek-holt