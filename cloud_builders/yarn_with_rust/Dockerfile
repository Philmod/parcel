ARG NODE_VERSION=8.11.0
FROM gcr.io/cloud-builders/yarn:node-${NODE_VERSION}

ENV CARGO_HOME=/usr/local/cargo \
    RUSTUP_HOME=/usr/local/rustup \
    PATH=/usr/local/cargo/bin:$PATH

RUN curl -L https://sh.rustup.rs | sh -s -- -y --default-toolchain=nightly \
  && rustup component add rust-src --toolchain nightly \
  && rustup toolchain install nightly \
  && cargo install --git https://github.com/alexcrichton/wasm-gc

ENTRYPOINT ["yarn"]
