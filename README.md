application_role
================

This role creates an application user, group and allows sudo from an alternate remote user.

Tasks:
1. Create application group.
2. Create application administration group.
3. Create application user.
4. Add admin user to application admin group.
5. Allow admin user to sudo to application user.

Requirements
------------

* Must run as 'root' for user creation.

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

* `app_admin_users` must be a list.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

MIT License

Copyright (c) 2018 Ken Treadway

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
