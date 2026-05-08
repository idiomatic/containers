FROM rust:1.95-alpine AS builder

WORKDIR /build
COPY . .

RUN cargo build --release

FROM docker.io/library/alpine:latest

COPY --from=builder /build/target/release/freemkv /usr/bin/freemkv

ENTRYPOINT ["/usr/bin/freemkv"]

