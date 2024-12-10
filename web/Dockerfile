#Optimisation : Multi-stage build, image de base alpine plus légère

FROM golang AS builder
ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /app

#Copier le code source dans le conteneur
COPY dispatcher.go .

#Compiler le code / -o name pour le nom de l'executable
RUN go build -o dispatcher dispatcher.go

FROM alpine

WORKDIR /app
COPY --from=builder /app/dispatcher .

COPY static ./static

EXPOSE 80

CMD ["./dispatcher"]