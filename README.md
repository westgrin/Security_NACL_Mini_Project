# # Security Groups and NACLs Mini Project

## Project Overview
This 2-hour mini-project explores Security Groups and Network Access Control Lists (NACLs) to secure an EC2 instance hosting a website in `GatoVPC1`, executed on Ubuntu (WSL) with VS Code via Ubuntu.

## Setup
- Initiated on Jul 02, 2025, 07:10 AM WAT.
- Used Ubuntu terminal (WSL) with VS Code, documented in ~/Documents/Workspace/Security_NACL_Mini_Project.

## Project Execution

### 1. Security Group Configuration
- **Initial State**: EC2 instance allowed SSH inbound, all outbound; website inaccessible (no HTTP rule).
- **New Security Group**: Created `WebSG` with HTTP (port 80) inbound, all outbound, attached to instance.
- **Tested Access**: Website loaded at `http://54.255.228.191`.
- **Scenarios**:
  - Removed outbound rule: Website still accessible (stateful).
  - Removed both rules: Website inaccessible.
  - Added HTTP outbound, no inbound: Website failed, but `curl` succeeded.

### 2. NACL Configuration
- **Created NACL**: Created `WebNACL` for `GatoVPC1`, default deny all.
- **Inbound Rules**: Added rule to allow all traffic from `0.0.0.0/0`.
- **Associated with Subnet**: Attached to `my-public-subnet-1`.
- **Outbound Rules**: Added rule to allow all traffic to `0.0.0.0/0`.
- **Tested Access**: Website accessible.
- **Scenario**: Denied all NACL traffic, website failed (stateless behavior).

### Project Reflection
- **Configuration Success**: Successfully set up Security Groups and NACLs to control traffic.
- **Differences**: Learned Security Groups are stateful (instance-level) while NACLs are stateless (subnet-level).
- **Scenarios Explored**: Understood interactions (e.g., NACL blocks override SG allows).
- **Troubleshooting**: Identified connectivity issues due to missing outbound NACL rules or SG inbound rules.
- **Best Practices**: Gained confidence in securing AWS environments with layered security.

## Tools Used
- **Ubuntu Terminal (WSL)**: For documentation and testing.
- **VS Code**: For editing `README.md`.
- **Git Bash**: For version control and GitHub push.
- **AWS Management Console**: For Security Group and NACL configuration.

## Project Deliverables
- **Documentation**: This `README.md` details the process and reflection.
- **Script Link**: [GitHub Repository](https://github.com/westgrin/Security_NACL_Mini_Project)

## Conclusion
This project enhanced network security skills for GatoGrowFast.com’s EC2 instance, providing practical insights into Security Groups and NACLs for AWS environments.