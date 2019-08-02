### UPDATE
Added python and PIP to execute script after getting artifects. which can be sent on email or any local messenger throgh webhook.

## Available images
### javiersantos/android-ci:latest

```yml
image: javiersantos/android-ci:latest
```

Includes the latest SDK Build Tools and SDK Platform.

* Build Tools: 28.0.3
* Platform: Android 25, 26, 27 & 28

### javiersantos/android-ci:28.0.3

```yml
image: javiersantos/android-ci:28.0.3
```

* Build Tools: 28.0.3
* Platform: Android 25, 26, 27 & 28

### javiersantos/android-ci:28.0.2

```yml
image: javiersantos/android-ci:28.0.2
```

* Build Tools: 28.0.2
* Platform: Android 25, 26, 27 & 28

### javiersantos/android-ci:27.0.3

```yml
image: javiersantos/android-ci:27.0.3
```

* Build Tools: 27.0.3
* Platform: Android 25, 26 & 27

### javiersantos/android-ci:27.0.2

```yml
image: javiersantos/android-ci:27.0.2
```

* Build Tools: 27.0.2
* Platform: Android 25, 26 & 27

### javiersantos/android-ci:27.0.1

```yml
image: javiersantos/android-ci:27.0.1
```

* Build Tools: 27.0.1
* Platform: Android 25, 26 & 27

### javiersantos/android-ci:27.0.0

```yml
image: javiersantos/android-ci:27.0.0
```

* Build Tools: 27.0.0
* Platform: Android 25, 26 & 27

### javiersantos/android-ci:26.0.3

```yml
image: javiersantos/android-ci:26.0.3
```

* Build Tools: 26.0.3
* Platform: Android 25, 26 & 27

### javiersantos/android-ci:26.0.2

```yml
image: javiersantos/android-ci:26.0.2
```

* Build Tools: 26.0.2
* Platform: Android 25, 26 & 27

## Sample usages
### GitLab
*.gitlab-ci.yml*

```yml
image: javiersantos/android-ci:27.0.3

before_script:
    - export GRADLE_USER_HOME=`pwd`/.gradle
    - chmod +x ./gradlew

cache:
  key: "$CI_COMMIT_REF_NAME"
  paths:
     - .gradle/

stages:
  - build

build:
  stage: build
  script:
     - ./gradlew assembleDebug
  artifacts:
    paths:
      - app/build/outputs/apk/
```

### Bitbucket
*bitbucket-pipeline.yml*

```yml
image: javiersantos/android-ci:27.0.3

pipelines:
  default:
    - step:
        script:
          - export GRADLE_USER_HOME=`pwd`/.gradle
          - chmod +x ./gradlew
          - ./gradlew assembleDebug
```

Refernce Help from
Docker reference from android ci circle
Uber android build environment from docker hub
https://hub.docker.com/r/uber/android-build-environment/dockerfile
