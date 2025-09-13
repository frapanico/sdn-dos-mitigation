# Enhancing Detection and Mitigation of DoS Attacks in SDN: A Mininet and OpenFlow Switches Implementation
The project enhances **SDN security** using Mininet and the Ryu controller. It aims to improve existing countermeasures in a basic **OpenFlow** configuration, which were initially based on a static traffic threshold and an indiscriminate blocking policy that could compromise legitimate traffic. To overcome these limitations, a dynamic threshold mechanism based on a sliding window and the 3-sigma rule is introduced, which adapts to natural variations in network traffic. In addition, selective blocking based on the source MAC address is implemented to isolate only malicious traffic, and a more flexible blocking/unblocking policy is implemented that includes an observation period to prevent immediate resumption of attacks. The architecture is further enhanced through a modular thread-based design to separate monitoring, decision-making and enforcement functions, and with the ability to integrate external blocking rules defined in a JSON file, enabling more dynamic management without the need to restart the controller.

## Project Overview: Enhanced DoS Defense in SDN
The original system used a fixed traffic threshold to detect anomalies and blocked entire network ports, indiscriminately affecting all traffic. Blocking rules had a set duration, allowing attacks to immediately resume upon expiration. Furthermore, the controller's design was monolithic, making it hard to manage, and required manual code changes for new blocking policies.
The project implemented the following key enhancements:
*   **Dynamic Thresholds:** Replaced static thresholds with an adaptive, statistical model that learns normal traffic patterns and adjusts detection sensitivity in real-time.
*   **Selective Blocking:** Moved from port-wide blocking to precise mitigation by identifying and blocking only malicious MAC addresses, preserving legitimate traffic.
*   **Adaptive Blocking Policy:** Introduced an "observation period" after a block expires. If a malicious source re-engages during this period, it is immediately re-blocked, preventing recurring attacks.
*   **Modular Architecture:** Refactored the controller into distinct, lightweight threads for monitoring, decision-making, and enforcement, communicating via queues for improved maintainability.
*   **External Rule Management:** Enabled dynamic definition and application of blocking rules through an external JSON file, allowing administrators to update policies without controller restarts.
In essence, the project transformed a rigid DoS defense into an intelligent, granular, and flexible system, enhancing network resilience and administrative control.

## Documentation
The repository files contain an extract from the project documentation, which is useful for illustrating the approach used in drafting the documentation and implementing the code.

## Accessing the code
If you are a recruiter or a developer interested in viewing the source code, please open an issue in this repository with your request. I will provide access after reviewing it.
