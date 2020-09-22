# CBE 40455/60455 Process Operations

## 2020-08-13 Class Notes

### Modeling COVID-19 on a college campus

### Agenda

* Compartmental for COVID-19
    * SIR Models
    * SEIR Models
    * COVID-19 model with testing and isolation (Paltiel, 2020)

* Agent Based Model
	* Why agent based model?
	* Sketch of an implementation

* Implementing an Agent-Based Model in Simpy
	* Get started
	* Assignment: Complete the model

--
### Readings

Keeling, Matt J., and Pejman Rohani. Modeling infectious diseases in humans and animals. Princeton University Press, 2011.

--
### Susceptible-Infectious-Recovered (SIR) Model

| Compartment|Description|
|:--|:--|
|**Susceptible**|Individuals who are susceptible to infection
|**Infectious**|Infected individuals who are capable of infecting others
|**Recovered**|Individuals who have recovered, no longer infectious, and assumed to immune

Overall population balance: $N = S + I + R$


$$\begin{align*}
\frac{dS}{dt} & = -\beta S \frac{I}{N} \\
\frac{dI}{dt} & = \beta S \frac{I}{N} - \gamma I \\
\frac{dR}{dt} & = \gamma I
\end{align*}$$

