FROM ruby:3.1.0

ARG GROUP_ID
ARG USER_ID

RUN addgroup --gid ${GROUP_ID} user
RUN adduser --disabled-password --gecos '' --uid ${USER_ID} --gid $GROUP_ID user

ENV INSTALL_PATH /opt/monolithic
ENV BUNDLE_PATH /usr/local/bundle
RUN mkdir -p ${INSTALL_PATH}

RUN gem install rails bundler
RUN chown -R user:user ${INSTALL_PATH}
RUN chown -R user:user ${BUNDLE_PATH}
WORKDIR ${INSTALL_PATH}

USER ${USER_ID}
CMD ["/bin/sh"]
