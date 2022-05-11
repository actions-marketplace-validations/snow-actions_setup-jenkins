[![Test](https://github.com/snow-actions/setup-jenkins/actions/workflows/test.yml/badge.svg)](https://github.com/snow-actions/setup-jenkins/actions/workflows/test.yml)

# Setup Jenkins

Set up Jenkins container (PoC).
A few features are available.

## Usage

1. Copy $JENKINS_HOME/jobs/*/config.xml from existing Jenkins to jenkins_home/ in a repository
1. Create a workflow with the jenkins_home path

```yml
steps:
  - uses: actions/checkout@v3
  - uses: snow-actions/setup-jenkins@v0.1.0
    with:
      jenkins_home: jenkins_home
```

## Inputs

See [action.yml](action.yml)

| Name | Description | Default | Required |
| - | - | - | - |
| `jenkins_home` | jenkins_home path which will mounted to /var/jenkins_home | `./jenkins_home` | no |
| `jenkins_version` | [Jenkins image](https://hub.docker.com/r/jenkins/jenkins) version | `lts-jdk11` | no |

## Supported

### Runners

- `ubuntu-20.04`
- `ubuntu-18.04`
- `self-hosted`

### Events

- Any

## Dependencies

- [Docker Compose V2](https://docs.docker.com/compose/)
- [Jenkins](https://hub.docker.com/r/jenkins/jenkins)

## Contributing

Welcome.