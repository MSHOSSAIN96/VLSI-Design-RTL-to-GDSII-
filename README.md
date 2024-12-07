# Design to VLSI(RTL to GDS II)
Here, I  cover the basics of Chip Implementation, from designing the logic (RTL) to providing a layout ready for fabrication (GDS).

**Chapter 1 : The motivation for the Digital VLSI design (RTL to GDS) & an introduction to the chip design process.**

**Part 1a :  Motivation & an introduction to the course:**

![Screenshot 2024-11-17 124315](https://github.com/user-attachments/assets/659e2f80-b948-4940-aa4f-c86d1cd91393)

The evolution of integrated circuits, from the groundbreaking invention in 1964 to modern processors like Intel's Montecito in 2006, highlights the remarkable progress in technology. This journey—from 2,300 transistors on the Intel 4004 to over 1.7 billion transistors—demonstrates humanity's ability to push the boundaries of innovation and functionality, laying the foundation for the advanced computing systems we rely on today.

![Screenshot 2024-11-17 124344](https://github.com/user-attachments/assets/80e937c4-4d53-429e-ae3c-ca63ef972385)

The Intel Core i7-6950X Extreme Edition, also known as Broadwell-E, exemplifies the cutting-edge advancements in processor technology achieved by 2016. Here’s a breakdown of its key features and significance:

1.Fabrication Technology:

The processor was built using a 14-nanometer FinFET process.

14nm refers to the size of the transistors and other features on the chip, enabling higher density and lower power consumption.

FinFET is a 3D transistor design that improves efficiency and performance compared to earlier planar transistors.


2.Processing Power:

It features 10 cores, each capable of handling two threads simultaneously (via Hyper-Threading), resulting in 20 threads running in parallel.

This parallel processing capability makes it ideal for multi-threaded applications like video editing, 3D rendering, and complex simulations.

3.Memory Capacity:

Equipped with 25 MB of L3 cache, this large memory allows the processor to store frequently accessed data closer to the cores, improving speed and reducing latency.

4.Performance Specifications:

The chip operates at frequencies in the gigahertz range, ensuring high-speed processing for demanding tasks.
5.Physical Size:

The die measures 246 mm², a substantial size, indicative of the complexity and integration of multiple components on the same chip.

6.Transistor Count:

The processor incorporates over 3.2 billion transistors, a testament to the density and complexity of modern chip designs.

This processor's features illustrate the exponential growth of computing power enabled by innovations in microprocessor design. It pushes the boundaries of performance, energy efficiency, and integration, meeting the needs of modern applications while exemplifying the principles of Moore's Law.

One of the important inventions of that time (1964) the transistor was the ability to put several devices on one monolithic substrate and it led the way to computers as we know 
them today. 

A 14nm FinFET modern processor is a highly advanced microprocessor designed using 
cutting-edge semiconductor manufacturing technology. Here's a breakdown of its key 
features: 

1.Manufacturing Process (Node Size): The term "14nm" refers to the size of the transistors and other components on the processor, specifically the distance between the source and drain regions of a transistor. A smaller node size generally allows for greater transistor density and improved performance while reducing power consumption compared to larger nodes. 

2.FinFET Technology: FinFET stands for Fin Field-Effect Transistor, a type of transistor design that allows for better control over current flow and improved power efficiency compared to older planar transistor designs. FinFET technology has become the standard for modern processors due to its ability to mitigate issues related to power leakage and 
improve performance. 

3.Memory: The memory architecture of a modern processor can vary widely depending on its intended use and design. It typically includes various levels of cache memory (L1, L2, 
L3) integrated directly onto the processor die to reduce latency and improve data access speeds. 

4.Core Count: A modern processor fabricated using a 14nm FinFET process can feature multiple CPU cores, each capable of executing instructions independently. The core count can range from dual-core configurations suitable for low-power devices to high performance processors with eight, twelve, or even more cores.

5.Die Size: The die size refers to the physical dimensions of the silicon wafer on which the processor is fabricated. While die size can vary depending on the specific design and architecture of the processor, modern processors manufactured using a 14nm process typically have relatively compact die sizes compared to previous generations, allowing for increased transistor density and improved efficiency. 

6.Threads: Processors with support for multithreading can execute multiple threads of instructions simultaneously, improving overall system responsiveness and multitasking performance. The number of threads supported by a modern processor can vary based on factors such as core count and architecture, with high-end desktop processors often supporting simultaneous multithreading (SMT) technology to double the number of threads per core. 

7.Number of Transistors: The number of transistors integrated into a modern processor depends on its specific design and architecture. However, processors manufactured using a 14nm FinFET process can contain billions of transistors densely packed onto a single chip. These transistors are used to implement the various functional units of the processor, including arithmetic logic units (ALUs), cache memory, control logic, and other 
components essential for computation and data processing. 

In summary, a 14nm FinFET modern processor represents a state-of-the-art semiconductor device designed for high performance, energy efficiency, and scalability across a wide range of computing applications. Its advanced manufacturing process, innovative transistor design, memory architecture, core count, die size, threads, and transistor count collectively contribute to its capabilities and performance characteristics. 

The integration of transistors has grown exponentially according to Moore’s Law.  

![Screenshot 2024-11-17 124439](https://github.com/user-attachments/assets/50a49bb4-88cc-441a-8b60-8cbbe2fe04c7)

This is a kind of above graph where you can see that we have plotted two things. On the  bottom, we have the year where we have one scale on the right is productivity which is  how many transistors or theoretical transistors each staff and engineer can deal with,  and you see that has grown exponentially because this is a logarithmic graph but, on the  left, here, we have the logical transistors per chip according to Moore’s law which has grown on an exponent. The only thing is that you see that the scale of growth on the logic transistor per chip is much larger than the productivity of how much a person can deal with even with the different tools that we use to help us grow this exponentially and this has caused a gap to come along. One of the things that how we can go and close this Gap or what we can do without all these transistors that we’re putting on a chip.  

The gap between IC capacity and productivity is a serious problem for the semiconductor industry. It is making it more difficult and expensive to develop new chips, which could slow down the pace of innovation in the electronics industry.

1. Design Abstraction

Concept: Divide the design into modular, manageable layers or components.

How It Works:

a.Each engineer or team specializes in one part of the design.

b.Inputs and outputs are standardized, allowing seamless interaction between modules.

c.Engineers focus on optimizing their specific area while integrating with the larger system.

Benefits:

a.Simplifies the overall design process.

b.Enhances focus and productivity for individual teams.

c.Enables better collaboration and scalability.

2. Design Automation (EDA - Electronic Design Automation)

Concept: Use software tools to automate parts of the design process, handling large numbers of transistors and complex functionalities efficiently.

How it Works:

a.EDA tools assist in tasks such as schematic creation, logic synthesis, placement, routing, and verification.

b.Algorithms and simulations reduce the need for manual intervention in repetitive or complex tasks.

Benefits:

a.Increases speed and accuracy of design iterations.

b.Reduces human error.

c.Handles the exponential growth in transistor density effectively.

3. Design Reuse (IP - Intellectual Property)

Concept: Leverage pre-designed and validated components (Intellectual Property blocks) to save time and effort.

How It Works:
a.Teams or companies reuse blocks they previously designed or purchase IP blocks from external vendors.

Examples include standard cores (e.g., ARM processors), memory modules, or communication interfaces.

Benefits:

a.Avoids reinventing the wheel for commonly used components.

b.Saves development time and cost.

c.Ensures reliability, as pre-tested IP reduces the risk of design flaws.

By combining abstraction, automation, and reuse, engineers can tackle the immense complexity of modern chip designs efficiently, enabling the creation of increasingly sophisticated integrated circuits.

**Part 1b gives a high level overview of how a chip is built**

![Screenshot 2024-11-17 135152](https://github.com/user-attachments/assets/ca053488-4571-4754-994c-4a38472aa2e7)

Here’s a breakdown of the above design flow into key steps with explanations:

**1. Partition the Design**

What: Break the overall design into smaller, manageable sub-problems.

How: Use a hierarchical approach, where each sub-design is further partitioned into smaller designs until they are manageable by one engineer or a small team.

Why: Simplifies complexity and allows focused work on individual components.

**2. Define a Mathematical Model**

What: Create a mathematical representation of the sub-problem to understand its behavior and potential solutions.

How: Develop algorithms based on the model to solve the problem effectively.

Caution: Validate the model thoroughly to avoid inaccuracies, as a flawed model leads to flawed outcomes ("garbage in, garbage out").

**3. Develop and Implement Algorithms**

What: Translate the solution from the model into an algorithm and implement it using design tools.

How: Utilize design automation tools to create, simulate, and refine the solution.

Why: Automates repetitive tasks and ensures consistency in design execution.

**4. Define Interfaces**

What: Establish clear input and output requirements for each sub-design.

How: Ensure compatibility between sub-designs by using standard interfaces (e.g., connectors fitting specified slots).

Why: Facilitates seamless integration of the individual components into the larger design.

**5. Verify and Validate Design**

What: Check the design for correctness and functionality.

How:Use boundary condition checks to ensure reliability at the edges of expected behavior.

Assign a separate team (or third party) to verify the design, avoiding designer bias.

Why: Prevents unnoticed errors from propagating through the design process.

**6. Integrate and Manage Design Flow**

What: Assemble all sub-designs into the final system, ensuring proper connections and functionality.

How: Concatenate tools and processes into a well-defined design flow, outlining step-by-step procedures for each stage.

Why: Maintains order and consistency while allowing iterative improvements.
**
7. Iterate and Refine**

What: Test the assembled design, identify issues, and refine as necessary.

How: Review and revisit earlier stages to improve the design where issues are found.

Why: Ensures the final product meets specifications and performance expectations.

This systematic approach ensures modularity, consistency, and accuracy while enabling the efficient handling of complex designs.

![Screenshot 2024-11-17 140331](https://github.com/user-attachments/assets/09dd4ff3-6a12-4eeb-82e5-8ce4cc0cca6b)

Here’s a structured breakdown of basic design abstraction in chip design into key points:

**1. Top-Down Design Approach:**

What: The design starts at the highest level of abstraction and proceeds downward step by step to the lowest physical level.

Why: Simplifies the process by addressing higher-level goals first before focusing on implementation details.

Verification: It's crucial to verify designs at every level by working bottom-up to ensure correctness at each step.

**2. Design Abstraction Levels**

a.System Level:

Description: High-level overview of the entire system functionality.

Purpose: Defines how the system behaves as a whole, without worrying about implementation details.

b.Register Transfer Level (RTL):

Description: Describes the flow of data between registers using hardware description languages (e.g., Verilog, VHDL).

Purpose: Bridges the gap between high-level functionality and the hardware's logic gates.

Focus: Logic units and their behavior, not individual physical devices.

c.Gate Level:

Description: Represents logic gates and their interconnections.

Purpose: Details how the logic is implemented using gates (AND, OR, NOT, etc.) built from transistors.

Focus: Circuit design using predefined building blocks.

d.Transistor Level:

Description: Uses transistor models to construct gates.

Purpose: Focuses on the electrical properties and operation of transistors (e.g., MOSFETs).

e.Layout Level:

Description: Defines the geometric patterns for manufacturing the physical chip.

Purpose: Converts circuit designs into a physical form ready for fabrication.

f.Mask Level:

Description: Represents the photolithographic masks used to etch transistors and interconnections on silicon.

Purpose: Final step before fabrication, translating layouts into production-ready masks.

**3. Another View: Vertical Integration of Abstraction**

a.Bottom-Up Approach:

Starts with physics (e.g., Ohm’s Law, Maxwell’s Laws) to define basic devices like transistors.

Builds upward through devices, circuits, logic, and microarchitecture.

b.Top-Down Approach:

Starts with applications/algorithms and progressively maps them to the hardware.

Moves through operating systems, instruction set architectures (ISA), and RTL to connect software to hardware.

4. Dividing Expertise

a.Specialized Teams:

Each abstraction level has a dedicated team of experts.

Example: Circuit designers rely on models from device engineers but do not need to know the physics behind them. Similarly, RTL engineers use gates and circuits without needing knowledge of how they are fabricated.

b.Input-Output Dependencies:

Lower levels (e.g., device physics) provide inputs (e.g., transistor models) to higher levels.

Higher levels provide outputs (e.g., gates, logic functions) to drive designs upward in abstraction.

5. Key Benefits of Design Abstraction

Divide and Conquer: Simplifies large problems by breaking them into smaller, more manageable tasks.

Modularity: Each team focuses on their abstraction level, ensuring expertise and efficiency.

Scalability: Enables tackling complex designs by integrating specialized work at each level.

This layered abstraction approach ensures an organized, collaborative, and efficient pathway to complex chip design, where teams focus only on their areas of expertise while relying on inputs and providing outputs for adjacent levels.

![Screenshot 2024-11-17 141805](https://github.com/user-attachments/assets/cd0f2f36-dacb-4c1a-91c3-19c405915891)

Here’s a breakdown of the System-Level Abstraction concept into key points:

**1. Definition and Purpose**

Description:

The system-level abstraction describes the entire system's functionality at a very high level.
Typically, it's represented using programming languages like C, SystemC, or similar tools.
Purpose:

Provides an abstract and simplified model of the system to evaluate its functionality and conceptual design early in the process.

**2. Key Characteristics**

High-Level Representation:

No implementation details such as hardware configurations or timing information are included.

Compact Execution Model:

Focuses on describing "what the system does," rather than "how it does it."
Quick and efficient to create, allowing rapid prototyping.

**3. Advantages**
   
Quick Start:

Offers a fast way to conceptualize and validate initial ideas before delving into detailed design.

Design Overview:
Enables a clear understanding of the system's overall functionality and performance goals.

**4. Challenges**

No Link to Implementation:
Lack of implementation details means it cannot be directly connected to lower abstraction levels.

**5.Difficult to Maintain:**

As the project progresses, this abstraction becomes harder to use effectively because it lacks the specifics needed for detailed design and testing.

**6. Example Use Cases**

Algorithm Exploration:

Describing an algorithm's functionality without worrying about how it will be implemented in hardware.
Application Modeling:

High-level simulation of an application’s behavior to test conceptual feasibility.

This abstraction serves as the foundation for exploring a system's functionality and feasibility, but its limitations require transitioning to lower abstraction levels for implementation and validation.

![Screenshot 2024-11-17 142557](https://github.com/user-attachments/assets/880acf9b-72fa-4366-b532-8288259018de)

**Register Transfer Level (RTL)**

**Purpose and Representation:**

RTL provides a cycle-accurate model close to hardware implementation.
It uses bit-vector data types and operations to represent hardware behaviors at the bit level, enabling precise control and design of digital systems.

**Key Constructs:**

Bit Vectors:
Collections of binary values (0s and 1s) representing data, such as a 32-bit register.

Sequential Constructs:
High-level programming structures like if-then-else for modeling complex control flows.

**Behavioral Description:**

RTL is still a high-level behavioral abstraction, describing system functionality without detailing the physical implementation.

**Transition to Gate-Level:**

The RTL design must be synthesized into logic gates, transitioning from behavioral descriptions to physical hardware-level abstraction for implementation.


The next part focuses on understanding how to write RTL descriptions and synthesize them into gate-level designs.


![Screenshot 2024-11-17 143256](https://github.com/user-attachments/assets/a6f1c9e5-d237-479e-872e-805625e13641)

**Gate-Level Abstraction**

**Purpose:**

Represents the physical implementation of a design using logic gates (e.g., NAND gates, flip-flops) to create sequential systems.Translates the Register Transfer Level (RTL) description into a hardware representation that operates using Boolean logic.

**Key Features:**

Finite State Machines (FSMs):
Designs can be modeled as FSMs, implemented with interconnected gates.

Gate Characteristics:
Includes measurable properties such as:

Delays: For example, gates may have specific delays (e.g., 3 ns or 5 ns).

Power Consumption: Can estimate power at this level.

Wire Modeling: Adds insights into interconnections between gates.

Significance:

Provides timing and power insights for detailed analysis.
Forms the basis for optimizing and finalizing the physical design.

Gate-level abstraction progresses towards transistor-level design, incorporating precise modeling for fabrication.

![Screenshot 2024-11-17 143905](https://github.com/user-attachments/assets/62f0eeef-a795-4d6c-93a2-fe0e8fc30fa3)

**Transistor to Mask Level**

Transistor Level:

Uses compact models to describe the physical behavior of devices (e.g., transistors).
Enables circuit simulation to analyze and design logic gates for use in higher abstractions like RTL.

Layout Level:

Focuses on designing physical layers and polygons that connect transistors to form functional circuits.
Represents the physical design of the chip, ensuring manufacturability.

Mask Level:

Translates the layout into photographic masks used in the fabrication process.
These masks define the patterns that will be etched onto the silicon wafer to create the actual devices.

This detailed physical design and fabrication process is beyond the scope of this course but is essential for manufacturing integrated circuits.


**Part 1c goes over the concept of design automation and how it enables us to build complex ICs**


![Screenshot 2024-11-17 151857](https://github.com/user-attachments/assets/37868fbc-4e42-4f97-a9e8-86ee2d9cb1de)

**Design Automation Tools**

Design automation today involves a wide array of tools for different stages of chip design. Here are the key categories:

**1.High-Level Synthesis & Logic Synthesis Tools:**

Used for RTL and system-level design to convert high-level specifications into logic representations.

**2.Schematic Capture Tools:**

Help in designing transistor-level circuits and creating the schematic diagrams for individual components.

**3.Layout Tools:**

Focus on creating the physical layout of transistors and their interconnections on the chip.

**4.PCB Design Tools:**

Used for designing Printed Circuit Boards (PCBs), including the placement of components and routing of connections.

**5.Simulation Tools:**

Run simulations at various levels, such as:

Transistor simulations using compact models.

Logic simulations using Boolean representations of logic gates.

Hardware Emulation to emulate chip functionality before actual fabrication.

**6.Verification & Analysis Tools:**

Ensures the design functions as intended and meets specifications:

Functional Verification checks if the digital design works as expected.

Formal Verification uses mathematical analysis to ensure correctness.

Equivalence Checking compares RTL and gate-level designs.

Static Timing Analysis checks timing constraints.

Physical Verification includes checks like DRC (Design Rule Check) and LVS (Layout vs. Schematic).

Clock Domain Crossing Checks ensure synchronization between asynchronous clocks.

**7.Post-Silicon Validation:**

ATPG (Automatic Test Pattern Generation) and BIST (Built-in Self-Test) help in testing the chip after fabrication to ensure it is functioning properly.

**8.Mass Production Tools:**

Optical Proximity Correction (OPC) and similar tools are used to prepare photomasks for manufacturing.
These tools help automate and streamline the complex tasks involved in chip design and ensure the delivery of functional, reliable chips.


![Screenshot 2024-11-17 152150](https://github.com/user-attachments/assets/b3f1cad4-2c66-43da-9eab-da56e8c95ecd)

**Cadence Design Flow**

The Cadence Design Flow, supported through the Cadence Academic Network, enables a comprehensive approach to chip design. The tools and steps in this flow are integrated to support the entire process, from RTL design to final verification and optimization.

**1.RTL Design in Verilog:**

Verilog is the primary language used for designing at the Register Transfer Level (RTL). This is the standard in the industry, and it allows for a high-level description of the digital logic in a chip.

VHDL is another option, but Verilog is favored in most high-tech industries.

**2.Synthesis with Cadence Genus:**

Cadence Genus is used for logic synthesis, converting the high-level RTL code into a gate-level representation that is suitable for physical design and fabrication.

**3.Place and Route with Cadence Innovus:**

Cadence Innovus handles the physical design phase, including placement and routing of the logic gates on the chip. This step defines the physical layout and interconnections of the gates, ensuring they fit into the specified design area and adhere to timing and other constraints.

**4.Integrated Tools in Cadence Innovus:**

a.Timing Analysis (Tempest): Analyzes the timing of signals within the design to ensure all timing constraints are met.

b.Voltage and Power Estimation: This tool assesses power consumption to ensure the design does not exceed power limits.

c.Parasitic Extraction (QRC): Extracts parasitic elements (such as resistance and capacitance) that can affect the signal integrity and performance.

d.Clactory Synthesis (CC Opt): Optimizes the design for area, power, and timing.

**5.Simulation with Cadence Incisive:**

Cadence Incisive is used for simulation and verification. This tool allows for functional verification of the RTL design by running various testbenches to ensure the chip will behave as expected under real-world conditions.

Simulation is crucial for validating design before moving to physical fabrication, helping detect logical errors early in the design cycle.

This flow is a comprehensive process that integrates multiple tools for different stages of chip design, making it easier to optimize and verify the design for performance, power, and area. The Cadence Academic Network provides the tools and resources necessary for running this workflow efficiently in an academic environment, equipping students with industry-standard tools for chip design.

**Part 1d gives a quick run through of the chip design flow as a framework for the rest of the work**

![Screenshot 2024-11-17 154300](https://github.com/user-attachments/assets/dc8a2548-9633-405d-a4f3-ee7d81cfb8e3)

Don't forget package and board design, software design, test plan and etc

**Chip Design Flow**

The chip design process is divided into several key stages, each focused on a different aspect of the design and fabrication process:

1.Definition and Planning:

The first step involves defining the goals of the chip, understanding the requirements, and planning the overall design. This stage sets the foundation for all subsequent steps.

2.Front-End Design:

This phase focuses on the actual design and verification of the chip's functionality. It includes high-level architectural design, RTL (Register Transfer Level) coding, and simulation to ensure the chip's design works as intended.

3.Back-End Design:

The back-end design begins after the functional design is completed. This includes logic synthesis (converting RTL to gate-level design), followed by the physical design phase, which involves placement, routing, and ensuring the chip meets performance, power, and area requirements.

4.Sign-Off:

After completing the back-end design, a sign-off process is conducted to verify that all design rules, timing, power, and other constraints are satisfied before the design is sent to the foundry for fabrication.

5.Tape-Out:

This is the final step in the design process, where the completed chip design is sent to the semiconductor fabrication facility (the foundry) for actual manufacturing.

6.Silicon Validation:

Once the fabricated chip is received, it is tested in the lab for silicon validation. This phase ensures that the chip behaves as expected under real-world conditions.

7.Other Aspects:

Additional steps, such as package and board design, software design, and creating a test plan, are also critical to the overall process, though they may not be the focus of this course. These aspects ensure the chip integrates successfully into a product and functions in its intended environment.

This flow provides a high-level view of the chip design process, which is highly iterative and involves many specialized tools and stages to ensure the chip meets both functional and physical requirements.

![Screenshot 2024-11-17 154930](https://github.com/user-attachments/assets/72e68038-70c6-4456-815e-867c97f3e1bb)


**Definition and Planning Stage**

1.Marketing Requirements Document:

This document outlines what the chip needs to achieve, its target audience, and the key features for selling the product. It defines the broad goals based on client needs and market demands.

2.Chip Architecture Team:

The architecture team takes the marketing document and defines the chip's core design aspects:

Bus architecture, connectivity, and partitioning.

High-level system model creation.

Decisions on power, frequency, bandwidth, and hardware/software division.


Choices for cores, memories, and other chip specifications.

**3.Design Team:**

The architecture team passes on the architectural guidelines to the design team:

Break down the design into smaller blocks.

Develop specific documents for each block, discussing design details.

Create state machines, waveforms, and define interfaces for each block.

**4.Board Requirements and Floor Plan:**

Discussions about the physical layout of the chip, including its size, floor plan, and the necessary connections.

**5.Process and Fabrication (Fab) Selection:**

Selecting the process and fab type (e.g., different node technologies, price points, and features) which greatly influence the chip's performance, power consumption, and other characteristics.

**6.Project Kickoff:**

Once all decisions and documents are in place, the project moves to the implementation phase. All designs are transferred to the implementation teams for actual development.

This stage ensures that the chip's high-level specifications, architecture, and requirements are well-defined and aligned with both technical and business goals before moving forward into the design and verification phases.

![Screenshot 2024-11-17 155720](https://github.com/user-attachments/assets/0c6780c4-0c0f-47f9-bf01-fc36988b8b89)

**RTL Design and Verification**

1.RTL Design (Register Transfer Level):

The design is described using Verilog or VHDL, which are hardware description languages.

This stage involves creating the behavioral model of the chip at a high level of abstraction.

2.Integration of IPs (Intellectual Property):

IP blocks can either be:

Off-the-shelf (purchased or licensed).

Internal (developed by a different team within the company).

These blocks are integrated into the overall chip design.

3.Design Checks:

Linters and synthesizability checks are used to ensure that the RTL code is syntactically correct and can be synthesized into logic gates.

Formal verification is applied to check if the design meets the specifications based on a mathematical model, ensuring correctness at the block level.

Functional verification tests the functionality of each IP and the entire system. This is done at multiple levels:

Unit-level: Testing individual blocks.

Subsystem-level: Testing groups of related blocks.

Full-chip level: Testing the entire chip's behavior.

4.Verification Coverage:

Efforts are made to achieve maximum coverage during the verification process to ensure all design scenarios are validated.


![Screenshot 2024-11-17 160404](https://github.com/user-attachments/assets/3942a00d-ea5e-489a-8c26-5a901d8c5535)

**Hard IP Integration**

Hard IP Design:

Hard IPs are designed specifically for a single process and its flavor, meaning they are optimized for one particular fabrication process and are not easily migratable to other processes.

Integration into Design:

Hard IPs are treated as black boxes that are inserted into the chip's floor plan without modification, making it easier to integrate.
Verification:

Since Hard IPs are usually pre-verified and debugged by the IP provider, the designer can rely on these blocks being functional and well-tested, saving time and effort.

![Screenshot 2024-11-17 160933](https://github.com/user-attachments/assets/8eabecec-a62b-4b77-97a3-d70142573008)

**Prototyping and Hardware Emulation**

1.Levels of Verification:

Verification can be specification-driven, bug-driven, coverage-driven, or regression-driven.

2.FPGA Prototyping:

FPGAs allow designers to synthesize the design onto hardware, enabling hardware-speed verification. This provides better coverage than software simulations, but FPGAs do not match the exact gate-level implementation of the final chip.

3.Hardware Emulation:

Hardware emulation involves mapping the actual gate-level design to high-performance emulation platforms like Cadence Palladium. This enables testing at real gate-level speeds and provides more accurate results compared to FPGA prototyping, making it a crucial verification tool.

![Screenshot 2024-11-17 161504](https://github.com/user-attachments/assets/28b4e901-d69b-479e-9500-8363e6a390d5)


![Screenshot 2024-11-17 161751](https://github.com/user-attachments/assets/6653c303-d56c-4ac0-98e8-bfaa3c8b4842)


**Physical Implementation (Back-End Design)**

1.Chip Overview:

I/O Ring: Interfaces between the chip's internal core and the external world using large buffers to handle higher capacitance and inductance at the chip's periphery.

Landing Pads: Provide connections to the external world for wire bonding.

2.Power Distribution:

VDD and Ground Rails: Provide power across the chip, with rows of standard cells placed in between for efficient power distribution.

3.Clock Distribution:

Clock Tree Synthesis: Ensures that the clock signal is routed to all flip-flops and relevant IPs within the chip.

4.Routing and Connections:

Routing of connections between logic gates and IP blocks is critical, ensuring no shorts and adherence to design rules.

5.Verification:

Design Rule Checks (DRC), Layout Versus Schematic (LVS), Antenna Checks, Electromigration Checks: Ensure correctness and reliability of the layout.

Logic Equivalence Checking: Confirms that the final layout matches the intended design.

Post-Layout Simulations: Verify the design's behavior with actual delays and other physical parameters.

6.Goal:

Efficiently place and route the design while ensuring proper functioning and compliance with design rules.

![Screenshot 2024-11-17 162517](https://github.com/user-attachments/assets/aee9cc90-948a-45cb-bc40-53e1658a6beb)


**Physical Design (Back-End Implementation)**

1.Foundry and Process:

The Foundry provides device models and technology files that describe how transistors work and the layers used in the fabrication process.

Tech File: Describes the layers and parasitics of the manufacturing process.

Design Rules: Outline the constraints for laying out the layers (e.g., spacing, width).

2.Vendors and IP Providers:

Standard Cells: Basic building blocks for the design (logic gates, flip-flops).

Memory Compilers: Tools for generating memory blocks like SRAMs or ROMs.

I/O Buffers: Interface cells that allow communication with the external world.

Hard IPs: Pre-designed blocks like analog circuits or specialized processors that are integrated into the design.

3.Front-End Design:

Specifications (Spec): The marketing and technical requirements the chip needs to meet.

Chip Architecture: Defines the overall structure and functionality of the chip.

RTL Design: Written by designers to define the logic of the chip.

Verification: Ensures that the RTL design functions correctly and meets specifications.

4.Transition to Physical Design:

The front-end design, including the spec, architecture, RTL, and verification results, is handed off to the physical design stage, where detailed implementation begins.

5.Complexity:

The back-end flow is intricate and involves numerous steps to translate the RTL into a physical layout ready for fabrication.


![Screenshot 2024-11-17 194618](https://github.com/user-attachments/assets/c6164a1b-d82a-44db-84b9-737ea6b477fc)

Here, so we start with again RTL which is the Register Transfer Level code that we wrote Verilog (VHDL), etc. Then we start with SDC which is a constraints file and then we start with our IPs provided by the IP vendors such as the standard cells and different macros. 

We take those 3 things (RTL, SDC, and Standard cells and Macros) and we provide them to the synthesis tool named Synthesizer which provides a gate level of how everything is mapped to this technology and how it’s connected. And then we lose all our behavioral models we don’t exactly understand, we can’t read the code anymore we can just see a bunch of gates that are connected.  

At the next stage, we will have some sort of definitions for our design for test and put our gate level inside an automatic test pattern generation (ATPG) tool and we will get the ability to test this. 

Then we can take our floor plan which is how we decided our chip would look and what different parts we have in our chip maybe we take Big blocks and place them and we take different things like the power grid and special routes that we have to do previous to doing the rest of the work and we put our whole sea of gates into the placement algorithm which puts every single one of these millions of gates down into some sort of 
a place inside our floor plan and we come out of this with a place designed so we have actual coordinates for every single one of these cells that we had in our gate level netlist.  

Now we provide some clock definitions since we know in our place design exactly where each flip-flop and every clocked element is we can now provide a clock to it, and we use a clock tree synthesis tool that designs the clock tree and provides a low skew net to each of these clocks again this.  

Once we have our design with our clock tree, we can take our router which goes and connects every one of the pins of the different cells and different IPS without doing anything that it’s not supposed to according to the design rules. Then we have a fully routed or fully laid out design.  

Then we must take this and do all the different types of checks such as running static timing analysis DRC and LVS checking, Density checking, Antennas inserting decaps checking power and electromigration and running extractions, and so forth. 

Once we are satisfied with what we have we can transfer this over and we can export that as what’s known as a GDS to file which is just a format for describing the layout which we usually send to the fabrication plant for making the photo masks.   

![Screenshot 2024-11-17 195733](https://github.com/user-attachments/assets/a69f1c74-1ddb-4a6f-8b98-445ac7120b14)


**Chapter 2 overviews the Verilog Hardware Description Language and provides coding style guidelines for writing synthesizable register transfer level (RTL) code.**

**Part 2a presents the motivation for Hardware Description languages and introduces Verilog.**

![Screenshot 2024-11-17 210805](https://github.com/user-attachments/assets/161c8574-3b24-4984-9a09-a71b2ba8eb67)

In hardware description language, we are not describimg the flow of data. Here we have sensitivity of lists which are list of signals, certain constructs we have. Everytime something happend/changed in struck which is known as Events. 

![Screenshot 2024-11-17 211615](https://github.com/user-attachments/assets/c8b750d6-4fcd-4ab6-8239-9497a486d094)

Here, Gate Level means that list of gates and connectivity between them. Netlist is not readable and low level and basically what types of Nets between them. 

RTL is synthesizeable verilog (to write verilog where actually describes hardware that can be turned into Gate level netlist)

DUT means that RTL/Structural code is used here. 

Behavioral (Test bench) means higher abstract level, here we write all kinds of for loops. 

**Part 2b introduces the basics of Verilog syntax.**

![Screenshot 2024-11-17 212844](https://github.com/user-attachments/assets/a74f4f3d-e7fa-44f9-a464-7153c59c1cce)


![Screenshot 2024-11-17 213344](https://github.com/user-attachments/assets/76438b2f-517e-489b-9be0-e87970ab289e)


![Screenshot 2024-11-17 214317](https://github.com/user-attachments/assets/b3836f18-abf9-4f47-b4b0-405a9aad12a8)


![Screenshot 2024-11-17 215254](https://github.com/user-attachments/assets/130a8c9d-e7d1-407b-957d-a1439bdafd0a)


![Screenshot 2024-11-17 220006](https://github.com/user-attachments/assets/a1625906-01de-4a84-a166-6eeff01c171b)


![Screenshot 2024-11-17 220908](https://github.com/user-attachments/assets/8476a86c-d877-4c41-95d4-c375f7e3305e)


![Screenshot 2024-11-17 221119](https://github.com/user-attachments/assets/58e3a986-f380-4875-b928-163e009c0947)


**Part 2c gives some very simple "hello world" style examples of Verilog coding.**


![Screenshot 2024-11-17 221620](https://github.com/user-attachments/assets/d4ea3854-81a7-4d01-b32a-fd8568cf205b)


![Screenshot 2024-11-17 222206](https://github.com/user-attachments/assets/4b7cb3c0-00e5-4763-86d8-134956a303b8)


![Screenshot 2024-11-17 221920](https://github.com/user-attachments/assets/3ecaf08f-4f0e-4e12-92f9-76ceee411ee6)


![Screenshot 2024-11-17 222924](https://github.com/user-attachments/assets/c09ac4f4-e42f-4198-83e4-93af28617577)


![Screenshot 2024-11-17 223225](https://github.com/user-attachments/assets/cf71770a-dbe6-450c-af5c-334f604fbb8e)


![Screenshot 2024-11-17 223516](https://github.com/user-attachments/assets/fedab6a9-1c96-43c0-9615-11597aad0bf5)


**Part 2d shows how to implement a basic finite state machine in Verilog according to synthesizeable coding style.**


![Screenshot 2024-11-21 104611](https://github.com/user-attachments/assets/265ac79a-1b48-424e-b8fb-6ca0745091d1)

Here, act- (enable) represents count or just do nothing

**count** that is a bus which tells what the value of current count is & 

**ovflw** if we passed 1111/ we went below 0000

Also, here the counter width is 4 which is default value, when we instantiate this module we can override this default value. 


![Screenshot 2024-11-21 110730](https://github.com/user-attachments/assets/cf0cd0f6-e0ae-4829-8bea-185ea20629fb)

When we hit the reset button, we go back to our idle state. Then if we stay with our activate signal at zero we will just stay inside our idle stay & not doing anything. What happens afterwards if our activate signal ==1, then we have to check if we are counting up ==1 then we go count up. Then if act ==0, we will go back to idle and not change anything and then if act is going high again, we will either count up or count down. 


![Screenshot 2024-11-21 113548](https://github.com/user-attachments/assets/c1143707-5213-430c-9654-817ecaefb9a6)


![Screenshot 2024-11-21 115807](https://github.com/user-attachments/assets/f02bc2ee-593c-4345-96b0-8d75d5acd1be)


![Screenshot 2024-11-21 120328](https://github.com/user-attachments/assets/93b23add-08da-41bd-886d-ed7ceac34488)


Here, in the instantiation stage, we connects all our signals that we just declared here to our signals to our parts of the module.


**Part 2e emphasizes some of the important points for coding in Verilog in order to write synthesizable, maintainable code.**


![Screenshot 2024-11-21 123201](https://github.com/user-attachments/assets/e5b772dc-3e94-4021-be5a-b90593e6d07a)

Here,we need to write each input/output on a seperate line so that a little bit more readable & you can comment what each signal is used for as I showed here.

![Screenshot 2024-11-21 123240](https://github.com/user-attachments/assets/a68715ad-c8c6-4402-908a-41cee82e84fd)

Here, reset and clock should be always LHS. 

![Screenshot 2024-11-21 123312](https://github.com/user-attachments/assets/c5397f03-f266-4f63-8e2c-e4acb5b5642d)


Here, **localparam** , we can pass a parameter to an instance, better for enumeratimg type of constants. 


**How to write Synthesizable RTL**


![Screenshot 2024-11-21 204315](https://github.com/user-attachments/assets/77bfd0b0-a014-4773-b494-4795f8181e0e)

In this figure, we have a pair of flip-flops positive edge-triggered flip-flops that are connected to a common clock signal and a blob of logic in between. 

What happens is when the clock signal rises we take the value that’s at the end of the input to this flip-flop (next_a) and we pass it over to the output that flip-flop that’s called sampling the data and the a value is now driven into this blob of logic and we put some sort of a Boolean function on to this value a until it arrives at the output of this logic function which I call here next_b on the rise of next clock edge we sample next_b and it is driven to the output of this flip flop.


![Screenshot 2024-11-21 204542](https://github.com/user-attachments/assets/f046080e-58f9-45d8-88ef-429e287ad276)
 
 Here, never create clcok domain crossings 



![Screenshot 2024-11-21 204625](https://github.com/user-attachments/assets/8614d027-2c02-43ba-9862-c6761ca87ce6)



![Screenshot 2024-11-21 204717](https://github.com/user-attachments/assets/c5bb090e-16f8-41c3-8668-8af0a38707df)



![Screenshot 2024-11-21 204800](https://github.com/user-attachments/assets/5e382678-105b-43b5-baf8-e8ae96430d24)



![Screenshot 2024-11-21 204834](https://github.com/user-attachments/assets/5b7a037d-5e95-4935-97ce-1bdfcfc16c64)



![Screenshot 2024-11-21 204906](https://github.com/user-attachments/assets/dee86198-ef18-4065-95ac-afab7bf7cf29)



![Screenshot 2024-11-21 204946](https://github.com/user-attachments/assets/84dc5e29-6a4e-4c77-b576-ed747b411a43)



![Screenshot 2024-11-21 205034](https://github.com/user-attachments/assets/f7da8235-5f17-4b0f-9eba-d2b06a6a0520)


**Chapter 3 is the first of two part overview of logic synthesis. The first lecture focuses on Standard Cell Libraries, which are an integral part of the synthesis process.**


**Part 3a introduces the logic synthesis flow.**

![Screenshot 2024-11-22 100627](https://github.com/user-attachments/assets/0d69f2c6-7402-485c-9fbd-18884ca5e9d3)
 
 Here, in the example, describes the simple counter where all the standard cells are are instantiated after synthesis. Gate level netlists shows how they are connected. 


 ![Screenshot 2024-11-22 100951](https://github.com/user-attachments/assets/b00042bd-647c-4cfb-aaeb-d3eb44cd222d)

 Here, logic synthesis helps us to improve the productivity instaed of drawing gates and logics by hand. 


 ![Screenshot 2024-11-22 101255](https://github.com/user-attachments/assets/1369aa11-388f-451a-8227-b0e9245e9c75)

 Here, we use always@(posedge clk) blocks for flip flop. 

![Screenshot 2024-11-22 101520](https://github.com/user-attachments/assets/e80a22d8-7198-4cd6-b969-f3b06db92ce1)

By using Cadence Genus tool, we are performing logic synthesis. 
Main 3 steps are mentioned above for Basic Synthsis Flow: 1. Pre-mapping Optimization 2. Technology Mapping 3. Post-mapping Optimization 


**Part 3b briefly touches on the place of compilation within the synthesis flow.**


![Screenshot 2024-11-22 105926](https://github.com/user-attachments/assets/75535b28-e0a0-46bd-a6ec-83c6c1531b86)


**Part 3c presents library definitions and introduces the concept of a standard cell library.**


![Screenshot 2024-11-22 160913](https://github.com/user-attachments/assets/9f6918f4-728b-4ad7-bb74-6f0609c6d09a)

This certain Lib file has certain types of operating conditions in process corners. TT means typical typical means pmoses and nmoses were fabricated in their typical corner and then 1 volt would be like our main supply voltage our VDD and 25 degree Celsius that would be the temperature that the library was characterized for certain process corners for the tool to look for those Leaf cells and to map the RTL.  

![Screenshot 2024-11-22 161336](https://github.com/user-attachments/assets/4ce7b8f6-c38a-436f-863a-34297de57f93)

Here, an IP vendor delivers a library which is basically a set of files that describes all information about the different EDA tools. 

Each type of standard cell is usually provided with several drive strengths.

Each Standard cell is going to have a different width which is going to be a different multiple of minimum width of the site. Cell width is going to multiple of site width but not same for each standard cell. 

Cell height is the distance between Vdd & ground. 

Each type of standard cell is usually provided with several drive strengths. 

![Screenshot 2024-11-22 164158](https://github.com/user-attachments/assets/5e02cc56-17c3-4af5-a084-129e6f0cb97e)

Fan in = 4 (up to ) Each of the cells comes with a variety of drive strengths

Each of the cells comes with a variety of drive strengths. 

ECO cells are bonus cells we can use to fix all kinds of problems during designs. 

CMOS is not good technology for having high fans in gates, it puts serial resistance in at least one of the network either pull up or pull down, really bad driving cell. 


![Screenshot 2024-11-22 171719](https://github.com/user-attachments/assets/fb597cfb-ff12-4e1e-8ca1-efb606609231)

Sequentials are big part of standard cell library. 

![Screenshot 2024-11-22 172749](https://github.com/user-attachments/assets/bbcaf40c-51f1-4574-b22c-58b021b56e22)

Filler cells are dummy cells that just has a continuity of the well and if we just tap one of those this whole well will be tapped, used for density fillers. 


![Screenshot 2024-11-22 173053](https://github.com/user-attachments/assets/b27f6b14-4728-4551-b587-0182119d296e)


![Screenshot 2024-11-22 174540](https://github.com/user-attachments/assets/986cbf1a-0c58-49c7-9128-4bb2917ce8aa)


**Part 3d dives into cell abstracts and the library exchange format (LEF), which is the common format to describe cell abstracts.**


![Screenshot 2024-11-23 104541](https://github.com/user-attachments/assets/09fd255d-36c2-4f11-b43b-323c939c80ff)


![Screenshot 2024-11-23 104627](https://github.com/user-attachments/assets/0a524e83-faf1-4322-8619-15c5a69b7e16)


![Screenshot 2024-11-23 104707](https://github.com/user-attachments/assets/170ca0b8-78dd-4519-bbd6-446397358c1c)


**Part 3e dives into the nonlinear delay models used for static timing analysis and the Libery (.lib) format, which is the common format to provide timing models.**


![Screenshot 2024-11-23 104742](https://github.com/user-attachments/assets/73035fdc-5ee1-458b-a85d-a30f3bd62fa3)


![Screenshot 2024-11-23 104946](https://github.com/user-attachments/assets/ede392b5-3308-4a6b-a0d6-a4c473f4661e)


![Screenshot 2024-11-23 105027](https://github.com/user-attachments/assets/e45d0c1f-1f87-4a6d-b715-97b8cfd33ee6)


![Screenshot 2024-11-23 105111](https://github.com/user-attachments/assets/becc3442-1e3f-4683-8dcc-d6f9aa4a27ab)


**Part 3f overviews the remaining contents you can expect to find in a standard cell library.**


![Screenshot 2024-11-23 105303](https://github.com/user-attachments/assets/47f4759d-624a-4ec4-91b0-f52e1353e42f)


![Screenshot 2024-11-23 105341](https://github.com/user-attachments/assets/e5242374-92d5-4d84-ab47-2ff94bd534e1)



**Chapter 4 continues the discussion about logic synthesis, focusing on the algorithms and mechanics that enable logic synthesis and timing optimization.**

**Part 4a moves past the library definition that was focus of part 1 and on to the basic concepts of computational Boolean algebra that are basis for Boolean minimization during synthesis.**


![Screenshot 2024-11-23 113328](https://github.com/user-attachments/assets/ba0af73b-0867-4cef-8bbc-bbe70bece6b0)


![Screenshot 2024-11-23 120248](https://github.com/user-attachments/assets/204afbc2-6a22-4ae9-827e-eaf06fc0d75e)


![Screenshot 2024-11-23 120849](https://github.com/user-attachments/assets/d2a27b67-f16e-430f-bf8c-183a3cb42fbe)


![Screenshot 2024-11-23 121014](https://github.com/user-attachments/assets/378d5334-b22a-455e-9fdf-7b920c9e2b0b)


![Screenshot 2024-11-23 121435](https://github.com/user-attachments/assets/8ebfec22-3d7c-4a0c-973f-149cb7fafd4d)


**Part 4b continues the discussion of Boolean minimization, introducing various algorithms and data structures, such as binary decision diagrams (BDDs).**


![Screenshot 2024-11-23 123054](https://github.com/user-attachments/assets/5ae6363b-308e-4e8c-89ca-3ad140854066)


![Screenshot 2024-11-23 123511](https://github.com/user-attachments/assets/61c128de-fcb6-4394-8e87-855f3bef501b)


![Screenshot 2024-11-23 124218](https://github.com/user-attachments/assets/28207c3d-8156-499e-9563-25a73f6dd586)


**Part 4c very briefly introduces constraint definition**


![Screenshot 2024-11-23 124555](https://github.com/user-attachments/assets/c4d94ad1-c2ab-437f-bfbe-20f2a94b0951)


**Part 4d Technology Mapping with minimum tree covering at its heart.**


![Screenshot 2024-11-23 130406](https://github.com/user-attachments/assets/260a7902-ecf4-48b1-8983-cf1ca7fbe751)


![Screenshot 2024-11-23 130913](https://github.com/user-attachments/assets/3a6c7bff-9bf4-410b-96eb-6e02c6967945)


![Screenshot 2024-11-23 130958](https://github.com/user-attachments/assets/21d2e384-a8e2-4955-9e16-7dbcb9df51c3)


![Screenshot 2024-11-23 131035](https://github.com/user-attachments/assets/febb0c65-eec3-433b-9116-5f48e2232de5)


**Part 4e now that we know what happens during synthesis**


![Screenshot 2024-11-23 133643](https://github.com/user-attachments/assets/66173a12-e624-45df-98c5-377669180174)


![Screenshot 2024-11-23 134052](https://github.com/user-attachments/assets/a892abb6-8eb8-49cb-bad3-530b271834a2)


![Screenshot 2024-11-23 141643](https://github.com/user-attachments/assets/29a8fba9-e044-4712-a4a6-dd837f43a320)


![Screenshot 2024-11-23 142550](https://github.com/user-attachments/assets/19be80fd-fce2-4f2e-b645-ed97310554d1)


![Screenshot 2024-11-23 143127](https://github.com/user-attachments/assets/13b2b426-ee5d-492a-aa66-c2ad099e97c1)


![Screenshot 2024-11-23 143532](https://github.com/user-attachments/assets/4bf055a2-93c7-4e28-b9df-bb11a57c1e2f)



** Part 4f discusses techniques and approaches for optimizing the netlist to meet the design constraints. **


![Screenshot 2024-11-23 144407](https://github.com/user-attachments/assets/437deba1-f3e5-4180-85ad-788541007d6b)


![Screenshot 2024-11-23 144435](https://github.com/user-attachments/assets/d41c155d-6241-4cff-8660-f7c3e316eb79)


![Screenshot 2024-11-23 144458](https://github.com/user-attachments/assets/a4cdefa6-f246-4f27-94c7-f0afe65adb0b)


**Chapter 5 covers the basics of static timing analysis (STA), used for optimization and for constraint checking. Timing is covered from both an algorithmic and a practical level, including examples of implementations in the Cadence work flow.**

**Part 5a introduces the concept of timing analysis in sequential circuits.**


![Screenshot 2024-11-24 130304](https://github.com/user-attachments/assets/59e35014-65e1-43c7-95f5-fda19f8196dc)


![Screenshot 2024-11-24 130638](https://github.com/user-attachments/assets/7984bdee-dfc1-4c5a-be76-8c59b382a1d5)


![Screenshot 2024-11-24 130759](https://github.com/user-attachments/assets/a79c65c6-6c2c-41be-b96f-2f5618727fa9)



**Part 5b goes over the primary timing constraints (max delay and min delay) in sequential circuits.**


![Screenshot 2024-11-24 141335](https://github.com/user-attachments/assets/3e48671c-c6ac-47a3-81f4-1a8888a80d14)


![Screenshot 2024-11-24 141431](https://github.com/user-attachments/assets/53abecc4-4d80-4efc-ad28-244e6be47cf0)


![Screenshot 2024-11-24 141501](https://github.com/user-attachments/assets/ce8147ce-0086-41db-94f7-8072360aa75c)


**Part 5c introduces static timing analysis (STA) - the means for verifying timing.**


![Screenshot 2024-11-24 152738](https://github.com/user-attachments/assets/28d1cff9-28ec-47f9-a13b-e28e77cfd08e)


![Screenshot 2024-11-24 152817](https://github.com/user-attachments/assets/96f72b6e-f16c-4d13-a8e3-4fe831539719)


![Screenshot 2024-11-24 152851](https://github.com/user-attachments/assets/798ac145-6a1c-43ea-a10a-7735ed3d782b)


![Screenshot 2024-11-24 152918](https://github.com/user-attachments/assets/807b350c-9e6d-431b-bef8-2749a384825b)


![Screenshot 2024-11-24 152956](https://github.com/user-attachments/assets/0a7877be-715e-49d2-aee2-657e32f034e6)


**Part 5d provides a step by step example of how STA works.**


![Screenshot 2024-11-24 173856](https://github.com/user-attachments/assets/17148923-1eee-4df6-9da2-187c72b23a35)


![Screenshot 2024-11-24 173938](https://github.com/user-attachments/assets/43a8bc44-61fa-453f-a9ee-a9f3897f0b05)


![Screenshot 2024-11-24 174012](https://github.com/user-attachments/assets/d9baeaca-efef-47f0-8618-f63bfa5242ee)


![Screenshot 2024-11-24 174047](https://github.com/user-attachments/assets/d513d730-4750-4934-ba0f-952eeb3a096d)




Part 5e introduces the Synopsys Design Constraint (SDC) format and its most important commands.


![Screenshot 2024-11-24 175526](https://github.com/user-attachments/assets/43005232-c6f1-46a5-9459-1a4c4ac1dd81)


![Screenshot 2024-11-24 175615](https://github.com/user-attachments/assets/58de12ff-7d86-402b-919c-6509be23ce66)


**Part 5f continues the tutorial about SDC.**

![Screenshot 2024-11-24 184123](https://github.com/user-attachments/assets/8a072ab2-bed7-418a-a9d6-90f16b44d1af)


![Screenshot 2024-11-24 184143](https://github.com/user-attachments/assets/63925aa8-3096-4fd4-8b6d-7d1d1bc5db82)


![Screenshot 2024-11-24 184159](https://github.com/user-attachments/assets/2f5f06bd-f9a1-408e-acfd-dd379b46ee91)


![Screenshot 2024-11-24 184214](https://github.com/user-attachments/assets/9a2419ce-5590-43e5-9108-4a759b17b17c)


![Screenshot 2024-11-24 184229](https://github.com/user-attachments/assets/12128097-1fae-404e-a49e-4481b8b30b7f)


**Part 5g demonstrates what a timing report looks like and how to read it.**

![Screenshot 2024-11-24 200924](https://github.com/user-attachments/assets/fef2be4f-8939-4a59-a496-3c01be877220)


![Screenshot 2024-11-24 200945](https://github.com/user-attachments/assets/1444ece4-9416-4193-b885-f46f43b120b1)


![Screenshot 2024-11-24 201003](https://github.com/user-attachments/assets/b8bc3c2b-d03e-41fe-8692-f0165ca6ca17)


![Screenshot 2024-11-24 201040](https://github.com/user-attachments/assets/0cde8ecf-b90d-453f-b2be-32fbe9508d2a)


![Screenshot 2024-11-24 201057](https://github.com/user-attachments/assets/f9445227-307b-4737-a26c-4cf39243aa68)


![Screenshot 2024-11-24 201111](https://github.com/user-attachments/assets/b1ca484e-46bf-47ac-b2fb-ac30ad446bc0)


![Screenshot 2024-11-24 201125](https://github.com/user-attachments/assets/e5e7682c-bf9a-4b08-9a15-b7a64b5bd829)


![Screenshot 2024-11-24 201139](https://github.com/user-attachments/assets/0d374fd6-2d9e-48b8-b780-b2041c5ae4cf)


**Part 5h introduces the concept of multi-mode multi-corner (MMMC or MCMM) and how to define it within Cadence tools.**


![Screenshot 2024-11-24 203904](https://github.com/user-attachments/assets/71d106bb-3d21-4038-9a92-ec53553f1d47)


![Screenshot 2024-11-24 204002](https://github.com/user-attachments/assets/138d08fa-f10c-4fbf-b01c-1e227bc5c2e8)


![Screenshot 2024-11-24 204019](https://github.com/user-attachments/assets/aad0645a-f129-490f-b561-682f25fb5783)


![Screenshot 2024-11-24 204034](https://github.com/user-attachments/assets/bc1d66c0-598f-4981-83a6-b32fb776d60d)


![Screenshot 2024-11-24 204046](https://github.com/user-attachments/assets/2233e905-4d91-4193-b39e-629489c1cec1)


![Screenshot 2024-11-24 204058](https://github.com/user-attachments/assets/559faad4-8ed7-445d-9b59-a80f736f00aa)


**Chapter 6 covers the traversal from the logical domain of RTL and Synthesis to the Physical Implementation stages of Floorplanning, Placement and Routing. This chapter focuses on Floorplanning, including Power Planning and a bit about Multi-Voltage and Hierarchical design.**

**Part 6a goes over the move from the logical to the physical domain at a high-level, including an overview of the place and route flow.**


![Screenshot 2024-11-25 094122](https://github.com/user-attachments/assets/24a89da6-0faa-45ea-9bed-62c7af3ebac7)


![Screenshot 2024-11-25 094200](https://github.com/user-attachments/assets/2d1a52f4-8d25-440c-9729-68463efef029)


![Screenshot 2024-11-25 094221](https://github.com/user-attachments/assets/ef43c917-8e3b-4928-9101-d85827514e89)



![Screenshot 2024-11-25 094241](https://github.com/user-attachments/assets/7869cd39-55e3-40db-83f3-5e93abfbe31b)



**Part 6b provides a brief introduction to the concept of multiple voltage domain design, power gates, CPF/UPF, and low-power design in general.**


![Screenshot 2024-11-25 095519](https://github.com/user-attachments/assets/56666297-10a5-4a3c-8941-56cd55727552)


![Screenshot 2024-11-25 095540](https://github.com/user-attachments/assets/7fcfb937-fd81-4a86-b774-a162b91275a3)


![Screenshot 2024-11-25 095627](https://github.com/user-attachments/assets/69d91ba7-64af-48e1-aa56-133fef659b6e)


![Screenshot 2024-11-25 095712](https://github.com/user-attachments/assets/d2dc2fd6-8736-428e-ae27-054bc89018c8)



**Part 6c explains the process of floorplanning, one of the most important parts of the backend design, including methodologies, tips, and good practice when building a floorplan.**


![Screenshot 2024-11-25 205635](https://github.com/user-attachments/assets/3203ab71-e172-4da2-9a27-79efb88864b2)



![Screenshot 2024-11-25 205649](https://github.com/user-attachments/assets/b03b9819-692c-400b-b295-6bccf48cb00f)




![Screenshot 2024-11-25 205730](https://github.com/user-attachments/assets/fec00b61-529f-4bfd-ad15-edd0b469ffd0)


![Screenshot 2024-11-25 205708](https://github.com/user-attachments/assets/40b09ee9-9f5a-432a-9aa8-a946f32c395b)


![Screenshot 2024-11-25 205749](https://github.com/user-attachments/assets/8cb65276-2b56-44b3-9d81-388ee69faf69)



![Screenshot 2024-11-25 205809](https://github.com/user-attachments/assets/570231c0-d538-4dca-b294-debf08f92125)


![Screenshot 2024-11-25 205825](https://github.com/user-attachments/assets/7b74c8f3-28df-47b2-a5fd-fb09df4aa843)


![Screenshot 2024-11-25 205845](https://github.com/user-attachments/assets/f8fb7529-5ec9-40e3-bb7c-2cf6dfc48e83)


![Screenshot 2024-11-25 205900](https://github.com/user-attachments/assets/ddc52172-c8e0-4b59-bc47-d7aedb69d48a)


![Screenshot 2024-11-25 205916](https://github.com/user-attachments/assets/c756a6de-999c-4a13-9aa8-40e363cae8f4)



![Screenshot 2024-11-25 205934](https://github.com/user-attachments/assets/40ea584a-82b1-447d-bded-5ff49be352d2)



![Screenshot 2024-11-25 205956](https://github.com/user-attachments/assets/26d5da78-a73d-4150-919a-c824c01362fe)


![Screenshot 2024-11-25 210015](https://github.com/user-attachments/assets/fa658e6b-b841-4f10-b2ae-1ad25b02cd38)


**Part 6d provides a brief overview of hierarchical physical design, which is commonly used for designs with a very large number of instances. This overview includes the interface logic models (ILM). **


![Screenshot 2024-11-25 211726](https://github.com/user-attachments/assets/f3a28ccf-ee44-4072-81ac-8f357d87a92f)


![Screenshot 2024-11-25 211811](https://github.com/user-attachments/assets/bf09bdc7-96c3-439e-8a47-ca3c83013d49)


![Screenshot 2024-11-25 211844](https://github.com/user-attachments/assets/d2253757-741f-4c2b-9c1d-272f4b99f8ee)


![Screenshot 2024-11-25 211925](https://github.com/user-attachments/assets/c509f448-2282-4ec0-b699-f3bc605c6d5b)

**
Part 6e overviews power planning, explaining important design considerations, such as IR Drop and Electromigration, with examples from famous ICs, such as the DEC Alpha chips.**


![Screenshot 2024-11-30 153338](https://github.com/user-attachments/assets/8e037a7f-8800-4937-8c0e-e86bea8dc751)


![Screenshot 2024-11-30 153354](https://github.com/user-attachments/assets/047ae039-90a2-4178-a11e-10170d81b756)


![Screenshot 2024-11-30 153500](https://github.com/user-attachments/assets/7333123a-9d25-4bf2-bb94-c4f8d2a9674d)


![Screenshot 2024-11-30 153558](https://github.com/user-attachments/assets/38232c47-e42c-4158-a11a-2f3c38fa627b)


![Screenshot 2024-11-30 153636](https://github.com/user-attachments/assets/ae9f3abb-0e9f-47d3-842c-cbe72b241e9a)


![Screenshot 2024-11-30 153711](https://github.com/user-attachments/assets/72f3ada4-e00e-4c9d-b1b3-0d7ba981c0b9)


![Screenshot 2024-11-30 153745](https://github.com/user-attachments/assets/729da092-7530-4aac-94f7-6637f88fe4ba)


![Screenshot 2024-11-30 153821](https://github.com/user-attachments/assets/16db9b89-1cb7-43bb-a3da-bf6c1a8951f2)


![Screenshot 2024-11-30 153856](https://github.com/user-attachments/assets/fd1c9468-6624-421c-8074-784d7651a6b4)


![Screenshot 2024-11-30 153924](https://github.com/user-attachments/assets/4be1809c-50f7-4044-91f0-c91310be5486)


![Screenshot 2024-11-30 154011](https://github.com/user-attachments/assets/7fdde9cf-9489-4a56-87ca-1be42e612da5)


![Screenshot 2024-11-30 154048](https://github.com/user-attachments/assets/21dea327-f8fd-43bd-a04f-cf14d96cfbcf) 



**Chapter 7 covers the basics of standard cell placement, including algorithmic basis (random and analytical placement) and practical aspects of placement.**


**Part 7a introduces the placement process and also goes over the meaning of (equivalent) gate count.**


































































































