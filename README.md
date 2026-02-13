# Nuclei Templates (Custom) — CORS / CSRF / Clickjacking

Este repositório contém templates **customizados** para o **Nuclei**, focados em identificar possíveis **má configurações** e **falhas de segurança comuns**:

- **CORS mal configurado**
- **CSRF (heurístico / indícios de ausência de proteção)**
- **Clickjacking (headers ausentes ou fracos)**

## ⚠️ Aviso importante (Uso legal e autorizado)

Estes templates foram criados **exclusivamente para fins legais**, como:
- Pentest **autorizado**
- Auditoria de segurança
- Hardening e validação de configurações
- Estudos em ambientes próprios/lab

🚫 **Não use estes templates para atividades ilegais**, como varredura em sistemas sem permissão, exploração não autorizada ou qualquer ação que viole leis, contratos ou políticas de uso.

Você é responsável por garantir que tem **autorização explícita** para testar qualquer alvo.

## 🧪 Status do projeto

- Templates em **fase de testes**
- Podem gerar **falsos positivos/negativos** dependendo do contexto
- Estão sujeitos a **mudanças e melhorias** a qualquer momento

## 📦 Templates incluídos

- `cors-misconfig-pro.yaml`  
  Detecta comportamentos inseguros como wildcard, reflexão de Origin e uso de credentials com origem insegura.

- `csrf-heuristic-pro.yaml`  
  Heurístico: procura forms POST sem indicadores comuns de token CSRF (serve como alerta para análise manual).

- `clickjacking-pro.yaml`  
  Verifica ausência de `X-Frame-Options` e/ou ausência/má configuração de `Content-Security-Policy` com `frame-ancestors`.

## 🚀 Como usar

### Rodar em uma URL:
```bash
nuclei -u https://alvo.com -t cors-misconfig-pro.yaml
nuclei -u https://alvo.com -t csrf-heuristic-pro.yaml
nuclei -u https://alvo.com -t clickjacking-pro.yaml
