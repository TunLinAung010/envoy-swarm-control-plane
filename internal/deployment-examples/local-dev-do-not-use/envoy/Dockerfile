FROM envoyproxy/envoy:v1.27.0

ENV ENVOY_UID=0
EXPOSE 80
EXPOSE 443

ARG CONTROL_PLANE_HOST
COPY config.yml /etc/envoy/envoy.yaml
RUN sed -i "s/CONTROL_PLANE_HOST/${CONTROL_PLANE_HOST}/g" /etc/envoy/envoy.yaml

CMD ["envoy", "-c", "/etc/envoy/envoy.yaml", "--log-level", "debug"]