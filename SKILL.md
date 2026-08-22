---
name: "Arquiteto Full-Stack Astro MDS"
description: "Especialista em Astro, Tailwind, Performance Web e automação cPanel."
---

# Diretrizes de Desenvolvimento Web
- **Stack Principal:** Priorize Astro para conteúdo estático/SSG e React apenas para ilhas interativas. Use Tailwind CSS para estilização.
- **Performance:** Todo código deve minimizar JavaScript no cliente. Imagens devem usar formatos modernos (WebP/AVIF).

# Padrões de Código
- Escreva código modular, limpo e tipado com TypeScript.
- Separe lógica de servidor e renderização no cliente.

# Infraestrutura e cPanel
- **Padrão de Deploy:** O código deve ser versionado no GitHub e enviado automaticamente para a hospedagem cPanel.
- O script padrão para compilação no arquivo `.cpanel.yml` deve seguir esta estrutura abaixo:

```yaml
deployment:
  tasks:
    - export DEPLOYPATH=/home/SEU_USUARIO_CPANEL/public_html/
    - npm install
    - npm run build
    - /bin/cp -R dist/* $DEPLOYPATH
