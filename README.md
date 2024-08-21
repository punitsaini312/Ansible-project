Here's a sample `README.md` file for your Ansible project:

```markdown
 Ansible Role: Project

This Ansible role automates the deployment and configuration of an Apache (`httpd`) web server. The role handles everything from package installation to service configuration, including the deployment of a custom HTML file and modifying the default port configuration.

 Features

- **Installs Apache (`httpd`)**: Ensures the web server is installed on the target machine.
- **Deploys a Custom Web Page**: Copies a Jinja2 template file (`index.html.j2`) to the web server's root directory.
- **Configures Custom Port**: Changes the Apache listening port from the default (80) to a custom port (8080).
- **Manages Service**: Restarts the Apache service to apply the new configuration and ensures it is enabled to start on boot.

 Role Variables

This role does not require any specific variables. It is configured to work with default settings.

Usage

1. **Create a Role Directory**: The role is structured in the standard Ansible format.
   ```
   project/
   ├── tasks
   │   └── main.yml
   ├── templates
   │   └── index.html.j2
   └── README.md
   ```

2. Tasks (tasks/main.yml)**: This is the main task file where the following actions are defined:
   - Install the `httpd` package.
   - Copy the `index.html.j2` template to `/var/www/html/index.html`.
   - Modify the Apache configuration to listen on port 8080.
   - Restart and enable the `httpd` service.

3. Template (templates/index.html.j2)**: The custom HTML file template to be served by the Apache web server.

### Example Playbook

Below is an example of how to use this role in a playbook:

```yaml
---
- hosts: webservers
  become: yes
  roles:
    - project

How to Run

1. Ensure that your Ansible environment is set up and that the target machine(s) are accessible via SSH.
2. Run the playbook:
   ```bash
   ansible-playbook -i inventory playbook.yml
   
 Prerequisites

- Ansible 2.9+ installed on the control machine.
- Target machines running a supported version of Linux (e.g., CentOS, RHEL, Fedora).

 Author
Punit Saini
