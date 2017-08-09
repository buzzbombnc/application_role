application_role
================

This role creates an application user, group and allows sudo from an alternate remote user.

Tasks:
1. Create application group.
2. Create application administration group.
3. Create application user.
4. Add admin user to application admin group.
5. Allow admin user to sudo to application user.

Role Variables
--------------

The following variables are defined in vars/main.yml:

| Variable        | Required | Description                                                    |
|:----------------|:--------:|:---------------------------------------------------------------|
| app_user        | true     | Application username.                                          |
| app_group       | false    | Application group.  Defaults to '{{ app_user }}'.              |
| app_admin_group | false    | Application admin group.  Defaults to '{{ app_group }}_admin'. |
| app_admin_users | false    | Application admin user(s).  Defaults to '{{ ansible_user }}'.  |
| app_admin_sudo  | false    | Allow admins to `sudo` to '{{ app_user }}' without password.   |

* `app_admin_users` can be a string or a list.

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
