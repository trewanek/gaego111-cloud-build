# README

This is App Engine Go111 Sample that is Deploying and testing with Cloud Build.

## Set up gcloud command in local

```
gcloud auth login
gcloud config set project [PROJECT_ID]
```

## GO MODULES

```
mkdir {project_dir}
export GO111MODULE=on
go mod init github.com/trewanek/{project_dir}

# example
mkdir gaego111-cloud-build
cd gaego111-cloud-build
export GO111MODULE=on
go mod init github.com/trewanek/gaego111-cloud-build
```

```
# if you add new module. update go.mod && get or update all modules
go get -u

# get or update target module
go get -u github.com/hoge/foo

# delete unused module
go mod tidy
```

## Deploy to App Engine

### Local

```
gcloud app deploy
```

### Cloud Build

#### Debug

Local Debug

```
cloud-build-local --dryrun=false --config=/path/to/cloudbuild.yaml
```

How to use bash command in image

```
- name: 'gcr.io/cloud-builders/{image}'
entrypoint: 'bash'
args:
  - -c
  - |
    'bash command'
```

#### Create Trigger

[Automating builds using build triggers](https://cloud.google.com/cloud-build/docs/running-builds/automate-builds?hl=en)

## References

- [Go Modules](https://qiita.com/propella/items/e49bccc88f3cc2407745)
- [Go 1.11 の Modules (vgo) を CircleCI で使う](https://blog.tsub.me/post/go111-modules-in-circleci/)
- [github.com/golang/go/wiki/Modules#quick-start-example](https://github.com/golang/go/wiki/Modules#quick-start-example)



