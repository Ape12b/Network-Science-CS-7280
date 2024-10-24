# Notes on Spreading Phenomenon

## Overview:
Epidemic modeling is a core concept in epidemiology used to understand and predict the spread of diseases. This framework is based on two key assumptions: **compartmentalization** and **homogeneous mixing**.

---

## 1. Compartmentalization
Epidemic models categorize individuals into compartments based on their current disease status. The most basic and widely used model is the **SIR model**, which includes three compartments:

- **Susceptible (S)**:
  - Healthy individuals who have not yet encountered the pathogen.
  - They are at risk of becoming infected when exposed.

- **Infectious (I)**:
  - Individuals who have contracted the disease and can transmit it to others.
  - These individuals are contagious during this phase.

- **Recovered (R)**:
  - Individuals who were previously infected but have since recovered.
  - They are assumed to have immunity to the disease, thus cannot be reinfected or infect others.

- **Additional Compartments** (for more complex diseases):
  - **Immune**: Some diseases might have individuals who are immune from the outset, either due to vaccination or previous exposure.
  - **Latent (Exposed)**: In some diseases, individuals are exposed but not yet infectious, representing an incubation or latent phase.

### Transitions Between States
- At the beginning of an outbreak, all individuals are typically in the **Susceptible (S)** compartment.
- Upon exposure, a susceptible individual moves to the **Infectious (I)** compartment and may transmit the disease to others.
- Eventually, the infectious individual recovers and transitions to the **Recovered (R)** state, gaining immunity.

**Example**: In an influenza outbreak, individuals progress through the SIR compartments based on contact with infectious individuals and the progression of the disease.

---

## 2. Homogeneous Mixing
- This assumption, also known as **fully mixed** or **mass-action approximation**, simplifies disease transmission by assuming that every individual has an equal chance of encountering an infectious person.
- In this model, the detailed structure of the social or contact network is not necessary. Instead, it is assumed that each person can infect any other person with equal probability.
- This hypothesis is useful in large populations and can approximate real-world conditions when detailed contact tracing is unavailable.

### Implications
- It ignores variations in social structure, such as individuals having different numbers of contacts, clustering of groups, or other network-based interactions.
- It simplifies mathematical modeling, but might not capture more localized or clustered outbreaks where contacts are unevenly distributed.

---

## Key Insights
- **Compartmentalization** helps in modeling the dynamics of disease transmission by simplifying populations into distinct states of disease progression.
- **Homogeneous Mixing** makes it easier to apply mathematical models to populations without needing to know detailed individual contact patterns, though it may not always be realistic for all disease types or population structures.

These models form the backbone of many epidemiological analyses, helping predict the course of epidemics, inform public health interventions, and evaluate the potential impact of control measures such as vaccination, quarantine, or social distancing.


## Susceptible-Infected (SI) Model

The **Susceptible-Infected (SI)** model is one of the simplest models used in epidemiology to describe the spread of infectious diseases. In this model, once individuals become infected, they remain infectious for the remainder of the simulation, as there is no recovery.

---

## Key Features

### 1. Compartmental Structure
The SI model divides the population into two main compartments:

- **Susceptible (S)**:
  - Individuals who are healthy and have not yet contracted the disease.
  - These individuals can move to the "Infected" compartment upon contact with an infected person.
  
- **Infected (I)**:
  - Individuals who have contracted the disease and can transmit it to susceptible individuals.
  - In this model, once individuals become infected, they do not recover, and there is no transition out of the "Infected" state.

The total population \(N\) is the sum of these two compartments:
$\[ N = S(t) + I(t) \]$

---

### 2. Assumptions of the SI Model

- **No Recovery**: Infected individuals remain in the infected state indefinitely. There is no recovery, immunity, or death.
- **Homogeneous Mixing**: Every individual has an equal chance of encountering an infected individual, meaning anyone can infect anyone else.
- **Constant Population Size**: The total population size \(N\) remains constant over time.

---

### 3. Mathematical Formulation

The SI model is described by a system of **ordinary differential equations (ODEs)** that govern the transitions between the compartments:

- **Change in Susceptible Population**:
  $$\[
  \frac{dS}{dt} = -\beta S I
  \]$$
  Where:
  - $\(S\)$ is the number of susceptible individuals.
  - $\(\beta\)$ is the transmission rate (the rate of infection when a susceptible individual encounters an infected one).
  - $\(I\)$ is the number of infected individuals.

- **Change in Infected Population**:
  $$\[
  \frac{dI}{dt} = \beta S I
  \]$$
  The infected population grows as susceptible individuals become infected.

---

### 4. Epidemic Dynamics

- **Exponential Growth**: At the start of an epidemic, the number of infected individuals grows **exponentially** since the infection rate depends on both the number of susceptible and infected individuals.
- **Disease Spread**: Over time, the disease spreads to most or all of the population, as there is no recovery in this model.

---

### 5. Limitations

The SI model is a simplified representation of disease dynamics and applies to specific cases where:

- **No Recovery or Immunity**: It models diseases where infected individuals do not recover or develop immunity.
- **No Death or Birth**: The model assumes a static population with no new individuals (births) or loss of individuals (deaths).

**Real-world Limitations**:
- **Lack of Recovery**: In most diseases, infected individuals either recover or die, which is not captured in the SI model.
- **No Interventions**: The model does not account for real-world interventions such as vaccination or quarantine.

---

## Key Insights

- The SI model is primarily useful in scenarios where diseases result in chronic infections, and individuals do not recover or develop immunity.
- It provides a **baseline understanding** of how diseases spread when recovery is not possible, demonstrating how the entire population could become infected over time in the absence of interventions.

---

The SI model serves as a foundational building block for more complex models like the **SIR** (Susceptible-Infectious-Recovered) or **SIS** (Susceptible-Infectious-Susceptible) models, which incorporate recovery, immunity, and other dynamics to better reflect real-world epidemiological scenarios.


## Susceptible-Infected-Susceptible (SIS) Model

The **Susceptible-Infected-Susceptible (SIS)** model is used in epidemiology to model infectious diseases where individuals do not gain immunity after recovery. In this model, once individuals recover from the infection, they become susceptible again, creating the possibility for reinfection.

---

## Key Features

### 1. Compartmental Structure
The SIS model divides the population into two main compartments:

- **Susceptible (S)**:
  - Individuals who are healthy but can become infected upon contact with an infected individual.
  - Once infected, they move into the "Infected" compartment.

- **Infected (I)**:
  - Individuals who are currently infected and can transmit the disease to others.
  - After recovering, they move back into the "Susceptible" compartment, making them vulnerable to reinfection.

The total population \(N\) is the sum of the susceptible and infected compartments:
$$\[
N = S(t) + I(t)
\]$$

---

### 2. Assumptions of the SIS Model

- **No Immunity**: Individuals who recover from the infection do not gain immunity. They return to the susceptible state and can be reinfected.
- **Homogeneous Mixing**: All individuals have an equal chance of interacting with each other, which simplifies the spread of the disease by ignoring specific contact networks.
- **Constant Population Size**: The total population size \(N\) remains constant over time, meaning no births, deaths, or migrations are included in this model.

---

### 3. Mathematical Formulation

The dynamics of the SIS model are governed by a set of ordinary differential equations (ODEs) that describe the change in the susceptible and infected populations over time.

- **Change in Susceptible Population**:
  $$\[
  \frac{dS}{dt} = -\beta S I + \gamma I
  \]$$
  Where:
  - $\(\beta\)$ is the transmission rate (how quickly the disease spreads from infected to susceptible individuals).
  - $\(\gamma\)$ is the recovery rate (how quickly infected individuals recover and return to the susceptible state).
  - $\(S\)$ is the number of susceptible individuals.
  - $\(I\)$ is the number of infected individuals.

- **Change in Infected Population**:
  $$\[
  \frac{dI}{dt} = \beta S I - \gamma I
  \]$$
  The infected population grows as susceptible individuals become infected but decreases as infected individuals recover and return to the susceptible state.

---

### 4. Epidemic Dynamics

- **Disease Persistence**: In the SIS model, diseases may not die out, as the population can continuously cycle between susceptible and infected states. This is particularly true if the transmission rate \(\beta\) is high and the recovery rate \(\gamma\) is low.

- **Endemic Equilibrium**: Depending on the values of \(\beta\) and \(\gamma\), the disease may reach an equilibrium where a certain proportion of the population remains infected over time (endemic state). This happens when the number of new infections balances the number of recoveries.

- **Basic Reproduction Number $(\(R_0\))$**: The basic reproduction number is given by $\(R_0 = \frac{\beta}{\gamma}\)$, which determines whether the infection will spread or die out. If $\(R_0 > 1\)$, the disease will spread and may persist in the population. If $\(R_0 < 1\)$, the disease will eventually die out.

---

### 5. Applications

The SIS model is useful for diseases where immunity is either not developed or is only temporary, such as:

- **Common cold**: Individuals can get reinfected after recovering from a cold.
- **Sexually transmitted infections (STIs)**: Some STIs, like gonorrhea, do not provide long-lasting immunity after recovery, making individuals susceptible to reinfection.

---

### 6. Limitations

- **No Permanent Immunity**: The model assumes no immunity develops after recovery, which limits its use to diseases where this is true.
- **Constant Population**: The model doesn't account for population changes due to births, deaths, or migration.
- **Homogeneous Mixing**: It assumes that all individuals have an equal chance of contact, which may not be realistic for all diseases or populations, particularly when considering social structures or networks.

---

## Key Insights

- The **SIS model** is ideal for diseases where individuals can be reinfected after recovering, with no long-lasting immunity.
- It predicts that some diseases may persist in a population if the reproduction number $\(R_0\)$ is greater than 1.
- This model helps to understand diseases where cycles of infection and recovery occur without permanent immunity, and it can inform public health interventions aimed at controlling diseases that are prone to reinfection.

---

The SIS model serves as a useful framework for understanding diseases where the cycle of infection and reinfection is common, providing insight into the dynamics of such diseases and helping predict their spread and persistence in populations.
