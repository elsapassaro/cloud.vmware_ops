# cloud.vmware_ops Molecule E2E Testing

This repository contains Molecule test scenarios for the `cloud.vmware_ops` Ansible collection. Each scenario represents a feature in the collection, allowing you to test individual features in isolation.
Feel free to contribute, add new scenarios, or enhance existing ones to ensure comprehensive testing of the Ansible collection.

## Prerequisites

Before running Molecule scenarios, ensure that the following tools are installed on your system:

- [Ansible](https://www.ansible.com/)
- [Python 3](https://www.python.org/)
- [Molecule](https://molecule.readthedocs.io/)
- [ansible-junit](https://github.com/hspaans/ansible-junit) (for JUnit XML output)
- [pyvmomi](https://github.com/vmware/pyvmomi) (required for vSphere testing)

Additionally, create a password file for the vSphere credentials (vault password file). The password file should contain the vault password for the `vSphere creds` vault. The vault file should include the following variables:

```yaml
# vault.yml
vault_vsphere_hostname: "your_vsphere_hostname"
vault_vsphere_username: "your_vsphere_username"
vault_vsphere_password: "your_vsphere_password"

## Creating a New Molecule Scenario
To create a new Molecule scenario, follow these steps:

1. Create a new directory under tests/e2e/molecule/provision_vm/scenarios/ for your scenario.
2. Define the scenario configuration in the molecule.yml file within the new scenario directory.
3. Create the necessary playbook(s) and test files for your scenario.
4. Run the scenario using molecule test -s <new_scenario_name>.

## Running Molecule Scenarios
To run a Molecule scenario, use the following command:
molecule test -s <scenario_name>
