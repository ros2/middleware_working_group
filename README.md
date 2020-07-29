# Middlware Working Group

This document defines the scope and governance of the Working Group (WG).

The Middleware Working Group's mission is to identify and address issues with usability and performance in the core communication features of ROS 2 which are provided by the middleware (i.e. implementation of the `rmw` API) or one of the client libraries (e.g. `rclcpp` or `rclpy`).

This working group will focus on the core ROS 2 stack, including the `rmw` API and its various implementations as well as the client libraries like `rcl`, `rclcpp`, and `rclpy`.

## Subprojects

This Working Group owns and maintains the following Subprojects.
Its meetings and membership are largely focused on the direction, design, and work on the projects.

### Subproject List

The following subprojects are owned by the Working Group:

* ros2/rmw
  * Description: ROS 2's middleware abstraction layer is defined by this API, it affects the code above, e.g. `rcl` and client libraries, as well as the middleware providers which implement it.
  * Repositories
    * https://github.com/ros2/rmw
    * https://github.com/ros2/rmw_implementation
* ros2/rosidl
  * Description: These packages provide ROS 2's user type abstraction interface, allowing the users to define new types and use them with the commuinication features provided by the client libraries.
  * Repositories
    * https://github.com/ros2/rosidl
    * https://github.com/ros2/rosidl_typesupport
    * https://github.com/ros2/rosidl_defaults
* ros2/rmw_fastrtps
  * Description: These packages provide an implementation of the `rmw` interface using Fast-RTPS (a.k.a. Fast-DDS) and is one of the tier 1 rmw implementations according to [REP-2000](https://www.ros.org/reps/rep-2000.html#foxy-fitzroy-may-2020-may-2023) as of the Foxy Fitzroy release.
  * Repositories
    * https://github.com/ros2/rmw_fastrtps
    * https://github.com/ros2/rosidl_typesupport_fastrtps
* ros2/rmw_cyclonedds
  * Description: These packages provide an implementation of the `rmw` interface using CycloneDDS and is one of the tier 1 rmw implementations according to [REP-2000](https://www.ros.org/reps/rep-2000.html#foxy-fitzroy-may-2020-may-2023) as of the Foxy Fitzroy release.
  * Repositories
    * https://github.com/ros2/rmw_cyclonedds
* ros2/rmw_connext
  * Description: These packages provide an implementation of the `rmw` interface using RTI Connext Pro and is one of the tier 1 rmw implementations according to [REP-2000](https://www.ros.org/reps/rep-2000.html#foxy-fitzroy-may-2020-may-2023) as of the Foxy Fitzroy release.
  * Repositories
    * https://github.com/ros2/rmw_connext
    * https://github.com/ros2/rosidl_typesupport_connext

#### Related Projects

These projects will be impacted directly by decisions made in this working group, but are not solely "owned" or "managed" by this working group as they will potentially overlap with other working groups.
This working group will not enforce standards (described below), but these projects will likely follow similar rules and this working group will assist with the maintenance and upkeep of these projects as it is able.

* ros2/rcl
  * Description: These packages build on the middleware abstraction and provides implementations of things commonly needed in language specific client libraries.
  * Repositories
    * https://github.com/ros2/rcl
    * https://github.com/ros2/rcl_logging
    * https://github.com/ros2/rcl_interfaces
* ros2/rclcpp
  * Description: These packages provide the main user facing C++ API, including access to the middleware features.
  * Repositories
    * https://github.com/ros2/rclcpp
    * https://github.com/ros2/rosidl
* ros2/rclpy
  * Description: These packages provide the main user facing Python API, including access to the middleware features.
  * Repositories
    * https://github.com/ros2/rclpy
    * https://github.com/ros2/rosidl_python
    * https://github.com/ros2/rosidl_runtime_py

### Standards for subprojects

Subprojects must meet the following criteria (and the WG agrees to maintain them upon adoption).

* Build passes against ROS 2 master
* The ROS 2 standard linter set is enabled and adhered to
* If packages are part of nightly builds on the ROS build farm, there are no reported warnings or test failures
* Quality builds are green (address sanitizer, thread sanitizer, clang thread safety analysis)
* Test suite passes
* Code coverage is measured, and non-decreasing level is enforced in PRs
* Issues and pull requests receive prompt responses
* Releases go out regularly when bugfixes or new features are introduced
* The backlog is maintained, avoiding longstanding stale issues

### Adding new subprojects

To request introduction of a new subproject, add a list item to the "Subprojects" section and open a Pull Request to this repository, following the default Pull Request Template to populate the text of the PR.

PR will be merged on unanimous approval from Approvers.

### Subproject changes

Modify the relevant list item in the "Subprojects" section and open a Pull Request to this repository, following the default Pull Request Template to populate the text of the PR.

PR will be merged on unanimous approval from Approvers.

### Deprecating subprojects

Projects cease to be useful, or the WG can decide it is no longer in their interest to maintain.
We do not commit to maintaining every subproject in perpetuity.

To suggest removal of a subproject, remove the relevant list item in the "Subprojects" section and open a Pull Request in this repository, following instructions in the Pull Request Template to populate the text of the PR.

PR will be merged on unanimous approval from Approvers.

If the repositories of the subproject are under the WG's GitHub organization, they will be transferred out of the organization or deleted at this time.

## Governance

### Meetings

* Regular WG Meeting: Bi-weekly on Wednesdays at 8am PST
  * https://index.ros.org/doc/ros2/Governance/#upcoming-ros-events
  * We will have meeting minutes posted after each meeting.

### Communication Channels

This working group will use discourse, and where appropriate GitHub issues, to have discussions offline.

### Backlog Management

Issues in this repository, using GitHub Project Boards as needed to organize our efforts.

### Membership, Roles and Organization Management

Working Group members may act in one or more of the following roles:

* **Member**
  * Prerequisite: Attend at least one out of the last three Working Group meetings
  * Responsible for triaging issues
* **Reviewer**
  * All reviewers are members
  * Prerequisite: Proven track record of high-quality reviews to WG Subprojects
  * Responsible for reviewing pull requests
* **Approver**
  * All approvers are reviewers
  * Prerequisite: Proven track record of high-quality contributions and reviews to WG Subprojects
  * Responsible for approving and merging pull requests
  * Responsible for vetting and accepting new projects into the Working Group
* **Lead**
  * TSC member or their delegate
  * Responsible for organizing and moderating working group meetings
  * Responsible for posting meeting materials (minutes, recordings, etc.)
  * Responsible for breaking ties

To become a member or change role, create an issue in this repository using the appropriate issue template.
Such applications are accepted upon unanimous agreement from Approvers, and are typically based on the applicant's history with the subprojects of the Working Group.
The Lead role cannot be applied for, as it is an appointee of the ROS 2 TSC.

### Modifying this governance document

Changes to this document will be made via Pull Request.
The PR will be merged on unanimous agreement from Approvers.
