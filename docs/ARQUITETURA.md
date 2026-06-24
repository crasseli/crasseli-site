# Arquitetura crasseli.com.br

**Projetado por:** Christian Rasseli & Senhor Cohen  
**Data:** 24 de junho de 2026  
**Custo total:** R$40/ano

---

## Visão Geral

```
┌─────────────────────────────────────────────────┐
│                  crasseli.com.br                 │
│                 (Registro.br)                    │
│                   R$40/ano                       │
└──────────┬──────────────────────────────────────┘
           │ DNS
           ▼
┌──────────────────────────────────────────────────┐
│                 Cloudflare DNS                    │
│              (grátis, SSL automático)             │
└──────┬──────────────────────────┬────────────────┘
       │                          │
       ▼                          ▼
┌──────────────┐          ┌──────────────────┐
│   NETLIFY    │          │ CLOUDFLARE TUNNEL│
│  (vitrine)   │          │   (homelab)      │
│  24/7 no ar  │          │  quando ligado   │
│   GRÁTIS     │          │    GRÁTIS        │
└──────────────┘          └────────┬─────────┘
       │                          │
       ▼                          ▼
┌──────────────┐          ┌──────────────────┐
│ HTML/CSS/JS  │          │  M70q (homelab)  │
│ Portfolio    │          │  Serviços:       │
│ Currículo    │          │  - Dashboards    │
│ Blog         │          │  - APIs          │
│ Contato      │          │  - Monitoramento │
└──────────────┘          └──────────────────┘
```

---

## Subdomínios Planejados

| Subdomínio | Host | Função | Status |
|-----------|------|--------|--------|
| `crasseli.com.br` | Netlify | Site principal/portfolio | ⬜ Pendente |
| `homelab.crasseli.com.br` | M70q via Tunnel | Dashboards internos | ⬜ Futuro |
| `api.crasseli.com.br` | M70q via Tunnel | APIs de serviço | ⬜ Futuro |

---

## Componentes

### 1. Domínio
- **Registrador:** Registro.br
- **Domínio:** crasseli.com.br
- **Custo:** R$40/ano
- **DNS:** Delegado para Cloudflare (SSL, CDN, DDoS protection)

### 2. Netlify (Vitrine)
- **Site:** crasseli.com.br
- **Repositório:** GitHub
- **Deploy:** Git push → build automático
- **Uptime:** 99.99% (independe do M70q)
- **Custo:** Grátis (plano Starter)

### 3. Cloudflare Tunnel (Homelab)
- **Binário:** cloudflared v2026.6.0
- **Conexão:** Túnel criptografado via Cloudflare
- **Portas:** Nenhuma exposta (zero port forwarding)
- **Custo:** Grátis

---

## Pré-requisitos Verificados (24/06/2026)

| Recurso | Status |
|---------|:------:|
| cloudflared | ✅ Instalado (v2026.6.0) |
| git | ✅ Instalado (2.43.0) |
| nginx | ⚠️ Não instalado (não necessário para fase 1) |
| python3 | ✅ 3.11.15 |
| Estrutura do projeto | ✅ ~/projects/crasseli-site/ |

---

## Próximos Passos

1. [ ] Christian registra `crasseli.com.br` no Registro.br
2. [ ] Delegar DNS para Cloudflare
3. [ ] Criar repositório GitHub para o site
4. [ ] Conectar Netlify ao repositório
5. [ ] Apontar domínio customizado no Netlify
6. [ ] Configurar Cloudflare Tunnel para subdomínios

---

Documentado por: Senhor Cohen  
Data: 24 de junho de 2026
