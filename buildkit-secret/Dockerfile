# syntax = docker/dockerfile:1.0-experimental
FROM rocker/tidyverse:3.6.3

RUN --mount=type=secret,id=dotenv,dst=/run/secrets/.env \
  set -a && . /run/secrets/.env && set +a \
  && install2.r remotes \
  && installGithub.r username/pkgname
