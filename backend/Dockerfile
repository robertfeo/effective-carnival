# Stage 1: Build the application
FROM rust:latest as builder
COPY ./api /usr/src/app
WORKDIR /usr/src/app
RUN cargo build --release

# Stage 2: Setup the runtime environment
FROM debian:buster-slim
COPY --from=builder /usr/src/app/target/release/myapp /usr/local/bin/myapp
CMD ["myapp"]