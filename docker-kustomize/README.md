#Build image

docker build --no-cache=true --build-arg BUILD_DATE=$(date -u +'%Y-%m-%d') -t kustomize:(date -u +'%Y%m%d') .