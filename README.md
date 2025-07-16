# -Logical-Smart-Home-Agent
1. Introduction
   
This project demonstrates the implementation of a logical agent based on the Logic-of
Thought approach, which emulates human-like decision-making through propositional 
logic. The agent operates in a smart home context, interpreting natural language 
commands from the user and translating them into executable actions. This task 
involves building a rule-based reasoning system that accepts both predefined and 
dynamically generated facts and rules. 
3. System Overview 

The agent has been developed in Python and consists of two main components: 
• LogicalAgent Class: Manages a set of facts and rules, and evaluates which 
actions should be triggered based on these. 
• Natural Language Processing Module: Converts user input (in Turkish) into 
formalized facts using both predefined keyword matching and a large language 
model (Google Gemini). 

The system workflow is as follows: 
1. The user enters a natural language command. 
2. The system translates this into a logical fact. 
3. The agent adds this fact to its knowledge base. 
4. The agent evaluates which rules apply and triggers the corresponding actions.
   
3. Logical Constructs and Implementation
   
3.1 Fact and Rule Representation 
Facts are stored in a set and rules are stored in a dictionary. Each rule follows the 
format: 
<condition> -> <action> 
The agent supports logical constructs such as AND and OR in both: 
• Conditions (LHS) 
• Actions (RHS)

<img width="663" height="397" alt="image" src="https://github.com/user-attachments/assets/ee2472d2-d683-4c47-b7e1-2ccd52978493" />
This enables complex rule configurations to be represented and evaluated. 

3.2 Input Processing and LLM Integration 
The process_natural_input() function maps natural language inputs into logical facts. 
Simple mappings are handled using keyword checks, while more complex expressions 
can be processed using the Gemini API. 

4. Sample Facts and Rules
   
4.1 Facts Generated from User Input 
• "üşüyorum" → cold_weather 
• "karanlık" → dark_outside 
• "televizyon" → user_says_watch_tv 
• "geldim" → user_arrives_home 
• "sabah" → morning_time 
• "perdeyi aç" → user_wants_light 

4.2 Rules Defined 

• cold_weather -> turn_on_heater and close_windows 
• morning_time -> open_curtains and open_windows 
• user_says_watch_tv -> turn_on_tv or dim_lights 
• user_arrives_home and dark_outside -> turn_on_entrance_lamp 
• cold_weather and morning_time -> start_heater_and_coffee 
• user_arrives_home and cold_weather -> offer_hot_drink 
• user_wants_light and dark_outside -> maximize_room_lighting 
The rules reflect real-world automation behavior and use AND/OR operators 
extensively.

6. Logical Evaluation Strategy
   
The agent evaluates facts using the following logic: 
• AND condition: All sub-facts must be present in the knowledge base. 
• OR condition: At least one sub-fact must be present. 
• AND action: All actions are executed. 
• OR action: Only the first available action is executed. 
This logic mimics basic reasoning mechanisms similar to expert systems. 

8. Contributions and Novelty
   
• Advanced Rule Handling: The system supports compound logical expressions, 
enabling real-world automation rules. 
• LLM-Enhanced Fact Generation: Natural language inputs are interpreted using 
both rule-based and LLM-based approaches. 
• Modular Design: The logical agent is extendable and can be integrated into 
broader smart home systems. 

10. Conclusion
    
This project successfully implements a rule-based logical agent capable of interpreting 
natural user commands and executing smart home actions accordingly. The system 
handles both basic and complex rule evaluations using logical operators, enabling 
dynamic, context-aware automation. 
The agent design follows the Logic-of-Thought paradigm and demonstrates how 
structured reasoning can be simulated in AI systems. Integration with an LLM further 
enhances flexibility and adaptability.
