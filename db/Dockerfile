#Optimisation : Multi-stage build, image de base alpine plus légère

FROM postgres:alpine

ENV POSTGRES_HOST_AUTH_METHOD=trust

COPY words.sql /docker-entrypoint-initdb.d/

EXPOSE 5432