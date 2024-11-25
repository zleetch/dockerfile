ARG app_name

#build stage
FROM rust:1 as build-env
WORKDIR /app
COPY . /app
RUN cargo build --release

FROM gcr.io/distroless/cc-debian12:latest
COPY --from=build-env /app/target/release/$app_name /
CMD ["./$app_name"]
