# Monte Carlo Insurance Risk Simulation Environment

This repository contains an Ansible playbook for deploying a Jupyter notebook environment specifically designed for insurance risk simulations using Monte Carlo methods.

## Overview

The Monte Carlo Risk Simulation environment provides a complete, containerized Jupyter notebook with the data science packages needed for sophisticated insurance risk modeling, including:

- NumPy, Pandas, SciPy for data manipulation and calculations
- Matplotlib and Seaborn for data visualization
- Pre-configured environment with adequate resources for complex simulations

## Deployment

The environment can be deployed using Ansible Automation Platform with the included playbook. The deployment creates:

- A dedicated Kubernetes namespace for risk simulation workloads
- A Jupyter notebook deployment with persistent storage
- Appropriate service and route configurations with TLS security

## Example Simulation

Included in this repository is an example Monte Carlo simulation for insurance risk analysis that:

- Models claim frequency using binomial distribution
- Models claim severity using log-normal distribution
- Calculates key risk metrics (VaR, CVaR)
- Performs sensitivity analysis on premium pricing
- Visualizes risk distributions and profit scenarios

## Deployment Options

### Manual Deployment

To deploy manually with the Ansible CLI:

```bash
ansible-playbook montecarlo-app.yml
```

### Ansible Automation Platform

The recommended approach is to create a job template in Ansible Automation Platform:

1. Create a Project pointing to this repository
2. Create a Job Template using the `montecarlo-app.yml` playbook
3. Ensure appropriate OpenShift/Kubernetes credentials are attached

## Resources

The default resource allocation for the environment is:
- Memory: 1Gi (request) / 2Gi (limit)
- CPU: 500m (request) / 1 CPU (limit)

These values can be adjusted in the playbook variables if needed for larger simulations.
