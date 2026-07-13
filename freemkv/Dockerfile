FROM rust:1.95-alpine AS builder

WORKDIR /build
COPY . .

RUN cd freemkv && cargo build --release

FROM docker.io/library/alpine:latest

COPY --from=builder /build/freemkv/target/release/freemkv /usr/bin/freemkv

ENTRYPOINT ["/usr/bin/freemkv"]

