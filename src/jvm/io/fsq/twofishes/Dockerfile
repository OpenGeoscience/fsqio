FROM fsqio/twofishes

ENV DATA_DIR /data/twofishes
ENV TWOFISHES_LATEST_PREBUILT_INDEX twofish_data_20161029.zip
RUN rm -rf $DATA_DIR
RUN mkdir -p $DATA_DIR
RUN curl https://s3.amazonaws.com/epidemico-twofishes/$TWOFISHES_LATEST_PREBUILT_INDEX > $DATA_DIR/$TWOFISHES_LATEST_PREBUILT_INDEX \
  && unzip $DATA_DIR/$TWOFISHES_LATEST_PREBUILT_INDEX -d $DATA_DIR \
  && rm $DATA_DIR/$TWOFISHES_LATEST_PREBUILT_INDEX

EXPOSE 8080 8081 8082 8083
CMD ["./src/jvm/io/fsq/twofishes/scripts/serve.py", "-p", "8080", "--vm_map_count", "65530", "/data/twofishes/gumbo"]
