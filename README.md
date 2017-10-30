ansible-django-stack
====================

Ansible Playbook designed for environments running a Django app.  It can install and configure these applications that are commonly used in production Django deployments:

- Nginx
- Gunicorn
- PostgreSQL
- Supervisor
- Virtualenv

This assumes that you have already installed nginx in your local machine. If you haven't, follow their installation guide [here](https://www.nginx.com/resources/admin-guide/installing-nginx-open-source/) 

### Instructions
1. A copy of the project's repository
2.  Edit the variables files located in the `host_vars/variables.yml`:
**Note:**
- `project_dir` should exclude the trailing backlash "/"
- Replace the IP addresses under the `[production]` or `[staging]` group name with your domain name or VPS in the `hosts` file 
3. Create a playbook. (A template named `playbook.yml` is ready for you. Just replace the `<comment>` with the proper values of the variables to be used. )
4. Replace `<password_in_the_remote_maachine_here>` with your remote machine's password and run this command in your console.
```
ansible-playbook playbook.yml --extra-vars "ansible_sudo_pass=<password_in_the_remote_maachine_here>"
```
