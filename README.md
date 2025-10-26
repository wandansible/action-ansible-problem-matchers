# GitHub Action: Ansible Problem Matchers

GitHub Action to setup problem matchers for Ansible.

## Sample usage

```yaml
---
name: Tests

on:
  push:
    branches-ignore:
      - main
  pull_request:
    branches:
      - main

jobs:
  molecule:
    name: Molecule
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repo
        uses: actions/checkout@v5
      - name: Setup python
        uses: actions/setup-python@v6
        with:
          python-version: '3.x'
      - name: Setup ansible problem matchers
        uses: wandansible/action-ansible-problem-matchers@v1
      - name: Install dependencies
        run: pip3 install -r requirements.txt
      - name: Run molecule
        run: molecule test
```
