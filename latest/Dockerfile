FROM flectrahq/flectra:1.6

LABEL image=codejamninja/flectra:latest \
  maintainer="Jam Risser <jam@codejam.ninja>" \
  base=debian:stretch

USER root

COPY flectra_cli_server.py /usr/lib/python3/dist-packages/flectra/cli/server.py

RUN apt-get update && apt-get install -y \
  curl \
  git \
  unzip

RUN mkdir /scripts && \
  curl -L -o /scripts/odoo2flectra.py \
  https://gitlab.com/flectra-hq/developer-tools/raw/master/flectra_rename_script/odoo_flectra.py?inline=false && \
  echo '#!/bin/bash\npython3 /scripts/odoo2flectra.py "$@"' > /usr/local/bin/odoo2flectra && \
  chmod +x /usr/local/bin/odoo2flectra
