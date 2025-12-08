# Viikkotehtävä 6 – LEMP-stack Kubernetesissa (Minikube)

## Tehtävänanto

Hyödynnä aiemmin luotua LEMP-stack arkkitehtuuria. Rakenna useamman kontin sovellus **Kubernetes-orkestroinnilla (Minikube)** ja varmista, että host-palvelimen **Nginx reverse proxy** ohjaa sovelluksen näkyviin polkuun:

- `http://<palvelimen-ip>/kube`

Tässä tehtävässä harjoitellaan useamman kontin sovelluksen rakentamista Kubernetesin avulla.

Tarkemmat ohjeet:
- https://www.villemajavan.com/linuxkubernetes#lemp-stack

Muista:
- Palvelut pysyvät käynnissä myös rebootin jälkeen
- Tarvittavat portit ovat auki
- Kubernetes YAML -tiedostot ovat repossa näkyvissä

Pisteytys:
- Konttisovellus toimii ohjeistuksen mukaan ja Kubernetes on käytetty (+6p)
- Uusi(a) toiminnallisuuksia sivulle käyttäen konttitietokantaan tallennusta (+2p)

---

## Arkkitehtuuri

Sovellus pyörii Minikube-klusterissa ja koostuu kolmesta osasta:

- **Frontend**: Nginx (palvelee staattisen HTML-sivun)
- **Backend**: Python/Flask (REST API)
- **Database**: MySQL (tallentaa käyttäjät)

Host-koneen **Nginx** toimii reverse proxyna ja ohjaa `/kube/`-polun Minikuben palveluun (NodePort).

---