# docker-grafana

## setup
Use:
```bash
sudo rm -fr ~/appdata/grafana
git clone https://github.com/ALFinternet/docker-grafana.git ~/appdata/grafana
```

## install promtail via docker
```bash
docker run -d \
  --name=promtail \
  -v /home/alf/appdata/promtail:/mnt/config \
  -v /var/log:/var/log \
  --restart unless-stopped \
  grafana/promtail:latest
  --config.file=/mnt/config/promtail-config.yml
```


#### not needed because we use git clone for this
```bash
mkdir appdata/grafana
mkdir appdata/grafana/grafana
mkdir appdata/grafana/loki
mkdir appdata/grafana/promtail
sudo chown -R 1000:1000 appdata/grafana
```
