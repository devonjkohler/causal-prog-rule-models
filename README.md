
# Explorations of causal probabilistic programming approaches for rule-based models of biological signaling pathways

#### Devon Kohler, Jeremy Zucker, Vartika Tewari, Karen Sachs, Robert Ness, Olga Vitek

This repository contains the implementation of three different causal probabilistic programming languages, Omega, Kappa, and Probability Trees, when applied rule based biological models. This work was recently presented at ProbProg 2021. The corresponding abstract and poster presentation can be found in this repository.

## Introduction

Signaling pathways are the molecular circuits that underlie cellular processes, such as proliferation and cell-cell communication. They can be thought of as causal stochastic generative processes and have historically been characterized by forward simulation, using algorithms such as Gillespie. Recently, signaling pathways have been represented using rule-based models, where agents and their interactions are viewed as events that cause the system to change to a new state.  We argue that probabilistic programming languages (PPL) offer a robust framework for deriving counterfactual traces in rule-based models of signaling pathways. Specifically, we explore for this task with Omega, a causal probabilistic programming language, probability trees, which can represent a causal generative or stochastic process, and Kappa, a language for rule-based modeling. We highlight advantages, limitations, and practical implementation challenges of each language for this application.

## PPL Overview

### Omega

Omega is designed for general counterfactual inference. It relies on a twin world workflow to learn exogenous variables from conditioned data, allowing us to ask counterfactual questions. This  workflow  involves  using  program  transformation  torepresent a joint distribution over the observed model and the intervened model, where both models share the same exogenous variables. For inference, Omega implements a variety of sampling algorithms, including Replica chain MCMC. Additionally, it utilizes a higher order  implementation of Judea Pearl’s do operator, implemented as replace in the code.

### Kappa

Kappa is explicitly designed for rule-based modeling of signaling pathways. It is based on a formalism known as process algebra, and thus has a clear semantics for representing parallel processes. Kappa is based on OCaml, a general purpose programming language that emphases expressiveness and safety. It has an efficient implementation and is equipped with parametric polymorphism and type inference, which makes it fast. Recently, Kappa was extended with causal semantics to allow counterfactual resimulation, which marries the con-currency community’s notion of causality as enablement with Pearl’s notion of causality as counterfactualprevention, and allows us to evaluate counterfactual statements.

### Probability Trees

A probability tree is a simple model for representing the causal generative process of a random experiment or stochastic process.  Each node in the tree corresponds to a potential state of the process, and the arrows indicate both the probabilistic transitions, and the temporal ordering of those transitions. Recently, developed algorithms that endowed probability trees with causal semantics, enabling them to answer probabilistic and deterministic questions at all 3 levels of Pearl’s causal hierarchy.

## References
1. Daniel T. Gillespie. “Exact stochastic simulation of coupled chemical reactions”. In:The Journalof Physical Chemistry81 (1977), p. 2340.
2. Glenn Shafer.The Art of Causal Conjecture. 1996.[MSD04]T.  C.  Meng,  S.  Somani,  and  P.  Dhar.  “Modeling  and  simulation  of  biological  systems  with stochasticity”. In:In Silico Biology4 (2004), p. 293.
3. J. Pearl.Causality: Models, Reasoning and Inference. Cambridge University Press, 2009.
4. J. Pearl. “The algorithmization of counterfactuals”. In:Annals  of  Mathematics  and  ArtificialIntelligence61 (2011), p. 293.
5. J. Laurent, J. Yang, and W. Fontana. “Counterfactual resimulation for causal analysis of rule-based models”. In:Proceedings of the 27th International Joint Conference on Artificial Intelli-gence. 2018, p. 1882.
6. Z. Tavares et al.A language for counterfactual generative models. Tech. rep. MIT, 2019.
7. Z. Tavares et al. “Soft constraints for inference with declarative knowledge”. In:arXiv:1901.05437(2019).
8. Z. Tavares et al. “The random conditional distribution for uncertain distributional properties”.In:arXiv(2019).
9. T. Genewein et al. “Algorithms for causal reasoning in probability trees”. In:arXiv:2010.12237(2020).
10. E. Bareinboim et al. “On Pearl’ hierarchy and the foundations of causal inference”. In:Probabilistic and Causal Inference: The Works of Judea Pearl. 2021
