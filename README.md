# Getting Started with Model Debugger for SimBiology

## Description
The Model Debugger for SimBiology is a MATLAB application that lets you analyze model responses, model structure, and expressions during model simulation.

## Getting started
To install the Model Debugger for SimBiology simply doubleclick the mltbx file. You can manage installed add-ons by clicking on the Add-Ons button in the MATLAB toolstrip.

To start the Model Debugger for SimBiology type "startSimBiologyDebugger(model)" where model is a SimBiology model.  
For more information type for how to apply doses and variants type "help startSimBiologyDebugger" in the MATLAB command line window.

See also the GettingStarted.mlx.

## Example
% Load model

model = sbmlimport('lotka');

% Configure model for simulation

configset = getconfigset(model);

configset.SolverOptions.AbsoluteTolerance = 1e-6;

configset.SolverOptions.RelativeTolerance = 1e-6;

% Define dose

dose = sbiodose('dose for y1', 'TargetName', 'y1', 'Amount', 50);

% Start Model Debugger for SimBiology for model and dose

startSimBiologyDebugger(model, dose);

## System Requirements
MATLAB version R2019b or later and the SimBiology ™ toolbox are required to run the Model Debugger for SimBiology.
Unit conversion is supported in MATLAB version R2020a or later.

## Features

Breakpoints to specify conditions to pause the model simulation. You can detect if species values are negative or values of model components are NaN, Inf, or complex. Triggered breakpoints are highlighted in yellow. Select an event to investigate from the dropdown menu in the control bar located at the top of the application window. You can deactivate predefined breakpoints to continue the simulation.

For debugging you can visualize the dependency graph of how values of model components are computed. You can also plot time courses of model responses and explore expressions graphically. Nodes in the expression tree represent terms that make up the expression. Colors of the nodes indicate NaN (red), infinite (orange), complex (yellow), or real values (green).
Customize your preferences for model simulation and the expression view in the Settings panel.


