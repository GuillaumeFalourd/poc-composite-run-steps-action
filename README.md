# poc-composite-run-steps-action

[![Action Test Workflow](https://github.com/GuillaumeFalourd/poc-composite-run-steps-action/actions/workflows/main.yml/badge.svg)](https://github.com/GuillaumeFalourd/poc-composite-run-steps-action/actions/workflows/main.yml)

POC of a composite run steps Github Action 🤖

This repository has been inspired from [this Github tutorial](https://docs.github.com/en/actions/creating-actions/creating-a-composite-run-steps-action).

## How to use this action?

Create a `.github/workflows/action.yml` file and insert the following lines:

```bash
name: Action Workflow

on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: Hello World Job
    steps:

    - uses: actions/checkout@v2

    - name: Greetings step
      id: greetings
      uses: GuillaumeFalourd/poc-composite-run-steps-action@main
      with:
        who-to-greet: 'Whoever you want'

    - name: Generating random number step
      run: echo The generated random number is ${{ steps.greetings.outputs.random-number }}
      shell: bash
```
