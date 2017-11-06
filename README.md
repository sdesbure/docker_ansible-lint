# Ansible Lint Docker

ansible-lint - https://github.com/willthames/ansible-lint

Latest ansbile-lint release in pip embedded into this docker.

Used to perform ansible linting into gitlab ci runner.

## Docker image

[![](https://images.microbadger.com/badges/image/sdesbure/ansible-lint.svg)](https://microbadger.com/images/sdesbure/ansible-lint "Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/sdesbure/ansible-lint.svg)](https://microbadger.com/images/sdesbure/ansible-lint "Get your own version badge on microbadger.com")

## How to use

### Pull image

```
docker pull sdesbure/ansible-lint
```

## Run container

Per default, the docker will give you the version number of ansible-lint.

If you want to do linting you'll have to run a specific command: 

```
docker run --rm -v <path for playbook folder to lint>:/playbooks sdesbure/ansible-lint ansible-lint yourplaybook.yaml
```

## In gitlab ci runner

Here's an example of a working configuration (that have a `lint` stage):

```
ansible_linting
  stage: lint
  image: sdesbure/ansible-lint
  script:
    - ansible-lint *.y?ml
```
