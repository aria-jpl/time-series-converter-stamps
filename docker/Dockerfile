FROM hysds/pge-base-conda-python368:20200818

LABEL maintainer="hysds"

COPY --chown=ops:ops ./barn/run.sh /home/ops
COPY --chown=ops:ops ./barn/get_param.py /home/ops
COPY --chown=ops:ops ./barn/create_dataset.sh /home/ops
COPY --chown=ops:ops ./barn/do_it.sh /home/ops

USER root

# timeseries from mintpy

COPY ./barn/timeseries ./timeseries

RUN chown -R ops:ops ./timeseries


# plot

RUN mkdir -p ./plot

COPY ./barn/plot ./plot

RUN chown -R ops:ops ./plot


USER ops

# Change to work directory
WORKDIR /home/ops

# Run shell
CMD ["/bin/bash", "--login"]
