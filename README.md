<p align="center">
  <img src="https://github.com/TechDufus/FluxNodeInstall/assets/46715299/214f5549-d8ff-425f-8039-ebdd210d9061" />
</p>

# Ansible project for installing RunOnFlux nodes

<p align="center">
    <a href="https://github.com/TechDufus/FluxNodeInstall/actions/workflows/ansible-lint.yml"><img align="center" src="https://github.com/TechDufus/FluxNodeInstall/actions/workflows/ansible-lint.yml/badge.svg"/></a>
    <a href="https://github.com/TechDufus/FluxNodeInstall/issues"><img align="center" src="https://img.shields.io/github/issues/techdufus/FluxNodeInstall"/></a>
    <a href="https://github.com/sponsors/TechDufus"><img align="center" src="https://img.shields.io/github/sponsors/techdufus"/></a>
    <a href="https://discord.io/techdufus"><img align="center" src="https://img.shields.io/discord/905178979844116520.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2"/></a>
</p>

This Ansible project aims to replace the current Bash script used for installing [RunOnFlux](https://runonflux.io) nodes with a more efficient and effective method using Ansible.

### Requirements

- Ansible (version >= v2.14.3)
- Python (version >= v3.10.6)
- Ubuntu (version >= v22.04)
  - You may need Ubuntu 22.04 or later to install Ansible v2.14.3 or later.


### Prerequisites

#### 1. Ansible Galaxy Modules
You will need to run the following command to install the Ansible Galaxy modules used in this project:

```bash
ansible-galaxy install -r requirements.yml
```

#### 2. `user.yml` file with filled in variables
You will need to create a user.yml file with the variables filled in. You can use the user.yml file as a template.

If you are not using an optional variable, please remove the line from the user.yml file. Do not leave a blank variable definition.

If you want to use the script to generate a user.yml file for you, you can run the following command:
```bash
./scripts/setup.sh
```
This will generate a user.yml file that you will need to move to the root of the project.

```bash
mv ./scripts/user.yml user.yml -f
```


### Usage

1. Clone this repository onto the Ansible control node.
2. Create an inventory file with the IP addresses of the nodes you want to install RunOnFlux onto.
3. Run the ansible-playbook command passing in the inventory file and the playbook file.

```bash
ansible-playbook flux.yml
```

### Playbook Contents

- **vars**: contains variables such as package names and version numbers needed to install RunOnFlux.
- **tasks**: contains the tasks needed to install and configure RunOnFlux.
- **handlers**: contains handlers for when certain tasks are executed.
- **templates**: contains configuration files necessary for RunOnFlux.

### Getting Started

See the [Getting Started](./docs/Getting_Started.md) guide for more information on how to get started with this project.

### Contributing

Please read [CONTRIBUTING.md](./.github/CONTRIBUTING.md) for details and the processes for submitting pull requests to us.

### Code of Conduct

Please read [CODE_OF_CONDUCT.md](./.github/CODE_OF_CONDUCT.md) for details on our code of conduct.
By participating in this GitHub repository, you are agreeing to abide by this code of conduct.

### Authors

- [TechDufus](https://github.com/techdufus)
- [MattConres](https://github.com/mattconres)
- [JKTUNING](https://github.com/jktuning)

### License

This project is licensed under the [MIT License](https://github.com/TechDufus/FluxNodeInstall/blob/main/LICENSE).
