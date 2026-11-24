# Validador de Robots.txt e Diretivas de Rastreamento

[![Validador Robots.txt](https://img.shields.io/badge/TAVARDT-Robots.txt-5b3cf5.svg)](https://tools.tavardt.com/br/validador-robots-txt/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)

Auditoria de arquivos robots.txt, deteccao de bloqueios indevidos de indexacao, analise de regras para bots de busca e IA, e checagem de declaracao de sitemap.

Desenvolvido e mantido pela divisao de engenharia de busca e infraestrutura de rastreamento da **TAVARDT Brasil**.

***

## Capacidades de Auditoria de Robots.txt

* **Deteccao de Bloqueios Criticos**: Identificacao imediata de regras acidentais de `Disallow: /` que causam desindexacao completa no Google e Bing.
* **Governanca de Rastreadores de IA e Busca**: Gestao diferenciada de permissoes para buscadores convencionais e agentes de IA (GPTBot, ClaudeBot, PerplexityBot).
* **Validacao de Declaracao de Sitemap**: Checagem de sintaxe e acessibilidade das diretivas `Sitemap:` declaradas no arquivo.
* **Analise de Diretivas Especiais**: Validacao de `Crawl-delay`, `Allow` e mapeamento de rotas administrativas expostas.
* **Indice de Eficiencia de Rastreamento**: Metrica quantitativa de 0 a 100 com alertas de configuracao priorizados.

***

## Instalacao e Execucao

Requer Python 3.8 ou superior sem dependencias externas adicionais.

```bash
git clone https://github.com/TAVARDT-Brasil/robots-txt-validator-br.git
cd robots-txt-validator-br
python robots_validator.py https://exemplo.com.br
```

Para gerar a saida em formato estruturado JSON:

```bash
python robots_validator.py https://exemplo.com.br -json
```

***

## Diagnostico Completo na Web

Para auditorias profundas e teste visual de regras de exclusao de robos:

* **Validador de Robots.txt Oficial**
* **[Portal Corporativo TAVARDT Brasil](https://ag.tavardt.com/br/)**

***

## Consultoria em Governanca de Rastreamento e SEO

Para arquitetura avancada de rastreabilidade e conformidade com Protocolo de Exclusao de Robos e Diretrizes de Rastreamento, consulte a equipe da **TAVARDT Brasil**.

***

© 2026 TAVARDT. Todos os direitos reservados.
