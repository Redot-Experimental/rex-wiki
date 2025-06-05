---
title: Team Structure
summary: Team.
authors:
    - ChocolatechipAussie
    - decryptedchaos
date: 2025-01-10
some_url: https://example.com
---

# Purpose
This document provides a high-level overview of the development team's structure, roles, and primary functions. Its goal is to clarify each role’s purpose, expected responsibilities, and how each team member contributes to the development lifecycle.

Having a well-defined structure helps ensure:
- **Clear Role Definition**: Each team member understands their responsibilities and how they contribute to project goals.
- **Efficient Collaboration**: By outlining team roles, we create a foundation for effective collaboration and communication.
- **Aligned Objectives**: The document aligns team members with the project’s goals, setting clear boundaries and separation of duties between roles.
- **Continuous Improvement**: By defining roles and workflows, the team can regularly assess and improve its collaboration, efficiency, and outcomes.

This document complements existing workflow guides and communication protocols, providing a foundational understanding of team roles for both current and new members of the development team. As the team scales or adjusts to meet project needs, this overview will evolve to reflect new roles, updated responsibilities, and improved processes, fostering an adaptive and resilient development environment.

> This overview serves as a reference for team members, new developers, and community members to understand the operational framework of the development team.

# Team Structure
The development team is organized into several core roles to ensure focus, expertise, and efficiency in each stage of the development process. This structure provides a foundation for collaboration and growth across specialized areas, each contributing unique skills towards the project's shared goals.

Alongside these core roles, specialized sub-teams, such as **UI/UX**, **Scripting**, **Networking**, and **Core Development**, may be formed as necessary. These sub-teams enable members to concentrate on their strengths and handle specific aspects of the project with a high level of expertise.

This flexible structure allows the team to adapt as project requirements evolve, with sub-teams created or restructured as needed to respond to new challenges and areas requiring focused attention. Collaboration between these groups ensures that each part of the project benefits from specialized knowledge while maintaining alignment with the overall project vision.

By organizing into core roles and specialized teams, we support both individual growth and cohesive, efficient teamwork, helping the team to meet project milestones and deliver high-quality results.

# Roles and Responsibilities
## ReX - Manager
The ReX Manager role is assigned to select senior developers as an extension of their responsibilities. Individuals in this role possess an in-depth understanding of all Redot policies and procedures, along with a proven track record demonstrating their ability to apply and uphold these standards. ReX Managers serve as key resources in ensuring that policies are followed correctly, continuously enhancing the development process, and bridging the gap between technical and non-technical individuals.

### Responsibilities
* Collaborate with the development team to refine policies and procedures, improving the development process as needed.
* Ensure that procedures are properly executed and that all team members adhere to established policies.
* Act as a liaison between technical aspects of development and the community’s non-technical individuals, effectively communicating complex concepts.
* Guide development team members on the correct application of Redot's policies and procedures and address questions or concerns as they arise.


## ReX - QA
The ReX QA role is designated for individuals dedicated to testing engine changes and identifying bugs or unintended behaviors before they reach the community. ReX QA members play a crucial role in maintaining quality standards and ensuring a smooth user experience by catching issues early in the development process.

### Responsibilities
* Follow the established issue-reporting process to effectively communicate bugs and unintended behaviors to developers.
* Conduct hands-on testing of new features and unreleased changes to the engine to ensure functionality and stability.
* Collaborate closely with the development team to address and resolve issues discovered during testing.
* Partner with ReX Managers to continually refine and enhance testing procedures for improved efficiency and accuracy.

## ReX - Developers
Developers are the driving force of the project, responsible for implementing features and addressing issues raised by the community. They follow Redot’s policies and procedures to ensure effective communication and a streamlined development process. Developers work collaboratively, continually enhancing their individual skills and growing as a cohesive team.

### Sr. Developer
Senior Developers are among the most experienced members of the development team. They bring a deep understanding of the development process, strong leadership abilities, and a commitment to helping others succeed.

#### Responsibilities
* Lead and manage smaller teams of developers within their area of expertise.
* Review and approve changes and pull requests on GitHub, ensuring code quality and adherence to standards.
* Review and accept community proposals and ensure that maintain appropriate labeling.
* Ensure pull requests have been assigned to the appropriate milestone and that the roadmap is being updated appropriately.
* Ensure that team members are following Redot’s policies and maintaining best practices.
* Provide constructive feedback and collaborate with ReX Managers to refine and improve development procedures.
* Evaluate team members’ strengths and assign them to areas where they can have the greatest impact.
* Work closely with their teams to address complex issues, developing effective strategies for resolution.

### Core Developer
Core Developers focus on the essential components and foundational systems of the project, ensuring that the underlying architecture and main functionalities remain robust and efficient. They often tackle technically challenging tasks that require a deep understanding of the project’s core structures.

#### Responsibilities
* Implement and maintain key systems and features, ensuring high standards of performance and reliability.
* Collaborate with other developers to integrate new features into the core engine effectively.
* Document the core systems and contribute to knowledge-sharing resources for other team members.
* Work with Sr. Developers and ReX Managers to identify potential improvements to the engine's core architecture.
* Ensure GitHub issues and community proposals are tagged appropriately.

### Jr. Developer
Junior Developers are newer members of the team who are actively developing their skills and gaining experience. They contribute to project tasks under the guidance of more experienced developers and often handle entry-level responsibilities.

#### Responsibilities
* Implement features and fixes as assigned, following Redot’s development guidelines and best practices.
* Collaborate with other developers to learn and apply new techniques and processes.
* Assist in testing and debugging code, providing support for minor issues.
* Actively seek feedback from Sr. Developers and Core Developers to improve their skills and understanding of the development process.


# Collaboration Through Communication
Effective communication is essential for a development team to function smoothly. Redot utilizes its community Discord server as a central communication hub, enabling developers to exchange ideas and collaborate through text, voice, and forum channels. This centralized platform, with its variety of communication options, supports seamless coordination among team members across different time zones.

In addition to Discord, GitHub serves as the primary tool for direct communication regarding code reviews, as well as for tracking issues and pull requests within the repository. By keeping discussions organized and focused, we ensure that relevant information is easy to locate and the message history remains clear. Professional conduct and a clear separation between on-topic discussions and casual conversations are essential to maintain a productive and accessible communication environment.


# Workflow Overview
### Bug Report Workflow
1. A bug report is opened as an issue on GitHub.
2. A Core Developer or Senior Developer reviews the issue and applies relevant labels.
3. A corresponding forum post is created on Discord, with labels matching those on the GitHub issue, to centralize discussion.
4. Relevant teams are notified to review the bug report, contribute insights, and engage in the discussion on Discord.
5. Senior Developers assess the issue, assign a priority level, and add the GitHub issue to the appropriate milestone.
6. Based on priority, the task is assigned to:
    - The Senior Developer themself,
    - Core Developers,
    - Junior Developers (with a Core Developer as a mentor), or
    - Left open for community contribution.
7. Once the issue is taken on, the assigned developer(s) open a draft pull request, marking the issue as "in progress" and allowing for ongoing review of the implementation.
8. After completing and testing the fix locally, the developer(s) update the pull request, mark it as open, and request an initial review.
9. The assigned Senior Developer reviews the implementation, suggesting changes as needed and marking the pull request as "ready for testing" once the changes are satisfactory.
10. A QA team member picks up the pull request, verifies that all testing procedures pass successfully, and leaves a report.
11. Implementers make any additional changes based on QA feedback, with reviews from the Senior Developer until no further issues are reported by QA.
12. A second Senior Developer performs a final review before approving the merge.
13. The Senior Developer overseeing the pull request completes the merge and then closes both the linked GitHub issue and the associated Discord forum thread.

### Proposal Workflow
1. Proposals are reviewed and judged based on the Proposal Acceptance Guidelines
2. The accepted proposal is opened as an issue on GitHub.
3. A Core Developer or Senior Developer reviews the issue and applies relevant labels.
4. A corresponding forum post is created on Discord, with labels matching those on the GitHub issue, to centralize discussion.
5. Relevant teams are notified to review the proposal, contribute insights, and engage in the discussion on Discord.
6. Senior Developers assess the proposal and add the GitHub issue to the appropriate milestone.
7. A discussion is held to determine whether the development team will take on the feature implementation or if it will be left to community contribution.
8. If it's decided that the community will implement the feature the GitHub issue will be marked as "implementer needed". Otherwise, the Senior Developers of the relevant teams will discuss the best course of action and who should be assigned to the task.
9. Based on complexity, the task is assigned to:
    - The Senior Developer themself,
    - Core Developers, or
    - Junior Developers (with a Core Developer as a mentor)

10. Once the issue is taken on, the assigned developer(s) open a draft pull request, marking the issue as "in progress" and allowing for ongoing review of the implementation.
8. After completing and testing the feature locally, the developer(s) update the pull request, mark it as open, and request an initial review.
9. The assigned Senior Developer reviews the implementation, suggesting changes as needed and marking the pull request as "ready for testing" once the changes are satisfactory.
10. A QA team member picks up the pull request, verifies that all testing procedures pass successfully, and leaves a report.
11. Implementers make any additional changes based on QA feedback, with reviews from the Senior Developer until no further issues are reported by QA.
12. A second and third Senior Developer performs a final review before approving the merge.
13. The Senior Developer overseeing the pull request completes the merge and then closes both the linked GitHub issue and the associated Discord forum thread.

These workflows ensure thorough review, testing, and collaboration across all relevant teams, resulting in high-quality bug resolutions, feature introductions, and effective communication throughout the process.




