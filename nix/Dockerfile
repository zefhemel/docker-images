FROM base
MAINTAINER Zef Hemel
RUN apt-get update
RUN apt-get install -y curl tar
RUN cd /
RUN curl -L http://hydra.nixos.org/job/nix/trunk/binaryTarball.x86_64-linux/latest/download | tar xvj
RUN /usr/bin/nix-finish-install
RUN ln -s /nix/var/nix/profiles/default /root/.nix-profile
ENV HOME /root
ENV PATH /root/.nix-profile/bin:$PATH
RUN nix-channel --add http://nixos.org/channels/nixpkgs-unstable nixpkgs
RUN nix-channel --update
ENV PWD /root
CMD ["/bin/bash"]
