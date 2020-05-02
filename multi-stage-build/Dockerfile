FROM rocker/rstudio:3.6.3 AS builder

ARG GITHUB_PAT
RUN install2.r remotes && installGithub.r username/pkgname

FROM rocker/rstudio:3.6.3
COPY --from=builder /usr/local/lib/R/site-library /usr/local/lib/R/site-library
