FROM mcr.microsoft.com/devcontainers/typescript-node
COPY --from=docker.io/denoland/deno:bin-2.4.2 /deno /usr/local/bin/deno
# to install Stripe
RUN curl -s https://packages.stripe.dev/api/security/keypair/stripe-cli-gpg/public | gpg --dearmor | tee /usr/share/keyrings/stripe.gpg
RUN echo "deb [signed-by=/usr/share/keyrings/stripe.gpg] https://packages.stripe.dev/stripe-cli-debian-local stable main" | tee -a /etc/apt/sources.list.d/stripe.list
RUN apt-get update
RUN apt-get install -y stripe





# # to install Node 22
# RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
# RUN \. "$HOME/.nvm/nvm.sh"
# RUN nvm install 22


# RUN curl -L -o stripe.rpm https://github.com/stripe/stripe-cli/releases/download/v1.28.0/stripe_1.28.0_linux_amd64.rpm && \
#     echo "sha256:4215e35020418205e89740523abeb5172ccafc82498f8858f878950a63f26eff  stripe.rpm" | sha256sum -c - && \
#     dnf install -y stripe.rpm && \
#     rm stripe.rpm