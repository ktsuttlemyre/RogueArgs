#!/bin/bash

rogueargs "$@"

docker pull "${image}"
WORKDIR=$(docker image inspect -f '{{.Config.WorkingDir}}' "${image}")

docker run \
  --interactive --tty --rm \
  --volume "${PWD}:${WORKDIR}" \
  --workdir "${WORKDIR}" \
  $image:$tag "$@"
