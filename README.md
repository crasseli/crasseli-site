# crasseli-site

Site estático do portfolio de Christian Rasseli.

**Domínio:** [crasseli.com.br](https://crasseli.com.br)  
**Hospedagem:** Netlify (vitrine 24/7)  
**Homelab:** Lenovo ThinkCentre M70q (processamento/dashboards)

## Arquitetura

```
crasseli.com.br (Registro.br)
  └─ DNS → Cloudflare
       └─ @ → Netlify (este site)
       └─ homelab → Cloudflare Tunnel → M70q
```

## Deploy

Push na branch `main` dispara deploy automático no Netlify.

## Stack

- HTML/CSS puro (sem framework)
- Netlify CDN
- HTTPS via Let's Encrypt (Netlify automático)
