# Tutorial
This tutorial document demonstrates the usage of SimuBridge on an example. We use the [Purchasing Example](https://github.com/AutomatedProcessImprovement/Simod/tree/master/resources/event_logs) event log in the tutorial.

 ## Start the project
When you open the tool you have two possibilities to start: create a new project or open the project from files (e.g., existing project).  
<p align="center">
   <img src="./screenshots/Screenshot_1.png" width=250>
</p>

 In this tutorial, we start from scratch: Thus, we create an empty new project by clicking the _Start New Project_ button.

 <p align="center">
   <img src="./screenshots/Screenshot_6.png" >

 It is possible either create an empty simulation scenario and fill all parameters manually or use an integrated process mining tool (currently only the Simod tool available) to automatically extract a BPMN model and the simulation parameters from the event log. We will demonstrate the second option.

 ## Process Mining & Simulation Scenario Creation

 To extract the simulation scenario and simulation parameters, we go to _Run Miner_ page by clicking  _Run Process Miner_ on the navigation sidebar or by clicking _Add Scenario from Process Mining on _the Project Overview Page_. The miner requires an event log  as an input parameter. The user can upload the event log by clicking on the _Upload new event log_ button. Additionally, the user has to choose a process mining tool from the available options. In the moment, the only integrated process mining tool is _Simod_.

 After settings are specified, we run the process miner by clicking _Start Miner_.

 <p align="center">
   <img src="./screenshots/Screenshot_2.png" >
</p>

After sucessful finising you are notified by pop-up window. 
 <p align="center">
   <img src="./screenshots/Screenshot_3.png" width=250>
</p>

and as a result multiple files in .json and .bpmn format are produced. These files represent BPMN process diagrams and simulation parameters mined from event log. You can download each of them by clicking on it. 

To convert the output to the simulation scenario, we choose simulation parameters file (.json configuration file) and BPMN XML file. After clicking _Convert to Scenario_, we specify the scenario name. 


 <p align="center">
   <img src="./screenshots/Screenshot_5.png">
</p>

## Scenario Overview

On the _Scenario Overview_ page, we can see the parameters of the scenario we created. These include general simulation parameters, resource parameters and process model-related parameters. To access this page, we need to click on _Scenario Overview_ on the navigation sidebar. If we want to change the general simulation parameters or make a copy of the scenario with some modifications, we can click on _Edit_ and do so. 

 <p align="center">
   <img src="./screenshots/Screenshot_7.png">
</p>
<br>
   <img align="right" src="./screenshots/Screenshot_9.png" height=400>


<br>
<img align="left" src="./screenshots/Screenshot_10.png" height=200>

Let us duplicate the scenario and make some changes afterward. 
After clicking _Duplicate Scenario_  Scenario1_copy is immediately created. Nevertheless, the original scenario is still shown. We can display the newly created scenario using a scenario switcher on the left sidebar. Let us simply choose Scenario1_copy. Now at 
_Scenario Overview_ page, we can see Scenario1_copy. Let us make some changes: replace the scenario name Scenario1_copy with Scenario2 and change starting time to 12:00  by clicking the _Edit_ button. To save, we click _Save Changes_.



<br>Let us now explore other simulation scenario parameters: The Resource Parameter Set and the Model Parameter Set.

<br>
<br>
<br>
<br>

## Resource Parameters

<!-- Screenshot for state after creating the data conditions -->

<br>Resource parameters provide an overview of resources involved in the business process and their timetables with their availabilities to work on process activities. To access resource parameters, we click  _Resource Parameters_ on the sidebar navigation panel. 

Each resource can be assigned to one or several role. Resources are individual employees, machines, etc that activity can work on process tasks. Roles are a grouping mechanism to collect resources with similar capabilities and responsibilities.

 <p align="center">
   <img src="./screenshots/Screenshot_12.png">
</p>

We can get detailed information about a specific role or resource by clicking on it. 

 <p align="center">
   <img src="./screenshots/Screenshot_13.png">
</p>
 <p align="center">
   <img src="./screenshots/Screenshot_14.png">
</p>

The resources that belong to a role inherit the same timetable and costs as the role. However, we can customize these parameters for each resource. To do this, we click on the resource that we want to edit, enter the new values and click _Save Changes_.

<p align="center">
   <img src="./screenshots/Screenshot_15.png">
</p>
We can assign a resource to more than one role or leave it unassigned. To unassign a resource from a role, we just need to uncheck the checkboxes of the role(s) that the resource belongs to. If a resource has no role, it will show up in the unassigned resource section. 
<p align="center">
   <img src="./screenshots/Screenshot_17.png">
</p>


We can see the timetable of each role by clicking on the _Timetable_ tab on the tabbar.
<img align="right" src="./screenshots/Screenshot_18.png" >
<br>
<br>
<br>

We can visualize the timetable by clicking on its name (usually is the same as the role name) and we can edit it by clicking on the day of the week and delete it or change the working hours (i.e., the time table items).
<img align="right" src="./screenshots/Screenshot_19.png" >   

We can add a new timetable by clicking on "plus" sign.  <img align="right" src="./screenshots/Screenshot_20.png" >
<br>
<br>
<br>
<br>

## Process Model Parameters

To display the BPMN process diagram of the business process, we click on _Modelbased Parameters_ on the navigation sidebar. We can zoom in or zoom out the model by clicking on the "plus" or "minus" at the bottom of the screen. Every element of the BPMN process diagram is clickable. After clicking, the sidebar of the selected element with parameters is displayed. It is possible to make changes. Let us add one more role to the first activity. To do this, expand the _Resources_ section, press _plus_, and select the role's name. The changes are saved automatically.

<p align="center">
   <img src="./screenshots/Screenshot_21.png" width=500>
</p>


We can represent the BPMN process diagram as XML document, or also as a table for better overview in which we can see all parameters in a table view. 
<img align="right" src="./screenshots/Screenshot_22.png" > 
For getting this view, click on _View_ on the bottom left of the screen and then click _Table_. We represent the activities, gateways, and the events in three separated sections. The _Edit mode_ can be activated by clicking on it.
<br>
<br>
<br>
<br>
<p align="center">
   <img src="./screenshots/Screenshot_24.png">
</p>


<br>
<br>


## Compare Scenarios
At the _Project Overview_ page, we can see all the scenarios that have been created. We can also duplicate and delete scenarios from this page. If we want to see how different scenarios are, we can use the _Compare Scenarios_ function.

To compare scenarios, we click on the _Compare scenarios_ button, select the scenarios we want to compare using the switches and click _Compare_.

The parameters of one scenario (current scenario, which is selected on the left sidebar). The parameters that are different in the other scenarios will be highlighted. The parameters that are the same in all scenarios will not be highlighted. We can click on a highlighted parameter to see its values in the other scenarios.


## Run Simulation

After specifying scenarios and reviewing all parameters we can run a simulation.The simulator requires a simulation scenario  as an input parameter. The user can choose it in a dropdown window. Additionally, the user has to choose a process simulation tool from the available options. Currently, the only integrated simulation tool is _Scylla_.


## Additionally 
We can download project file in json format simply by clicking _Download Project_ on the sidebar navigation menu. The file will contain all created simulation scenarios and simulation parameters.

<img align="right" src="./screenshots/Screenshot_25.png">
If you make changes to resource parameters or model parameters, the changes will only apply to the current scenario that you select in the left sidebar.