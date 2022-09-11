Java update
=========

Обновляет пакеты, прописывает симлинк $JAVA_HOME, перезапускает службы

Role Variables
--------------

defaults/main.yml

Указать нужные пакеты

Example Playbook
----------------
```yaml
- name: Update to {{ java_version }}
  hosts: "{{ var_host | default('java') }}"
  become: yes
  gather_facts: yes
  roles:
    - java_update
```
Запуск, если в inventory группа хостов называется не `java`:
```bash
ansible-playbook java-update.yml -i hosts --extra-vars "var_host=inc"
```

License
-------

MIT

Author Information
------------------

https://nudimannui4e.github.io/