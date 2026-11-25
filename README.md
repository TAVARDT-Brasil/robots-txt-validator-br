# Validador de Robots.txt e Governança de Rastreadores

[![Validador Robots.txt](https://img.shields.io/badge/TAVARDT-Robots.txt-5b3cf5.svg)](https://tools.tavardt.com/br/validador-robots-txt/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

O **TAVARDT Validador de Robots.txt** oferece auditoria automatizada de diretivas de rastreamento, conformidade com a RFC 9309 e governança de robôs de inteligência artificial no Brasil.

***

## Arquitetura do Protocolo e Matriz de Governança

Rastreadores de busca e agentes de inteligência artificial interpretam o robots.txt para definir limites de acesso e políticas de indexação. Erros comuns como bloqueios globais indevidos ou omissão de sitemaps causam desindexação completa e perda de tráfego orgânico.

Esta ferramenta analisa a sintaxe das regras, identifica valores excessivos de crawl-delay, avalia políticas para robôs de IA e fiscaliza declarações de sitemap a partir de 100 pontos base sem dependências externas.

O motor analítico avalia as diretivas segundo as especificações da RFC 9309 e o comportamento de agentes de busca:

<table>
  <thead>
    <tr>
      <th>Vetor de Governança</th><th>Critério de Auditoria</th><th>Dedução</th><th>Impacto em Rastreamento e SEO</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Regra de Disallow Global</strong></td><td>Verifica blocos <code>User-agent: *</code> com <code>Disallow: /</code> desprovidos de regras compensatórias <code>Allow:</code>.</td><td>-50 pts</td><td>Bloqueio crítico que impede motores de busca de indexar todo o site.</td>
    </tr>
    <tr>
      <td><strong>Declaração de Sitemap XML</strong></td><td>Fiscaliza a presença de pelo menos uma diretiva <code>Sitemap:</code> apontando para arquivos de índice válidos.</td><td>-20 pts</td><td>Reduz a eficiência do bot e retarda a indexação de novas publicações.</td>
    </tr>
    <tr>
      <td><strong>Crawl-Delay Excessivo</strong></td><td>Identifica diretivas <code>Crawl-delay</code> superiores a 5 segundos aplicadas a todos os robôs.</td><td>-15 pts</td><td>Gargalo severo no orçamento de rastreamento para sites de médio e grande porte.</td>
    </tr>
    <tr>
      <td><strong>Governança de Bots de IA</strong></td><td>Mapeia políticas para 12 agentes de IA (GPTBot, ClaudeBot, PerplexityBot, etc.), indicando bloqueio ou acesso livre.</td><td>Sinal Analítico</td><td>Protege a propriedade intelectual contra raspagem de dados para treinamento de modelos.</td>
    </tr>
    <tr>
      <td><strong>Disponibilidade do Host</strong></td><td>Verifica código de resposta HTTP 200 e estabilidade de transporte durante a requisição.</td><td>Pontuação zerada (0 pts)</td><td>Host inacessível impedindo a leitura das diretivas pelos motores.</td>
    </tr>
  </tbody>
</table>

### Escala de Governança e Níveis de Status

O utilitário atribui uma pontuação consolidada classificando a saúde do arquivo robots.txt:

* <strong>80 a 100 (COMPLIANT)</strong>: Conformidade plena com a RFC 9309; sitemaps declarados, ausência de bloqueios globais e diretivas equilibradas.
* <strong>50 a 79 (WARNING)</strong>: Diretivas funcionais porém com desvios que demandam ajuste, como ausência de sitemap ou delay alto.
* <strong>0 a 49 (CRITICAL)</strong>: Bloqueio total de rastreadores, inacessibilidade do arquivo ou regras disallow desastrosas.

***

## Instalação e Execução

Construído estritamente com a biblioteca padrão do Python 3.8+, sem dependências externas.

```bash
git clone https://github.com/TAVARDT-Brasil/robots-txt-validator-br.git
cd robots-txt-validator-br
```

### Execução Padrão via CLI

```bash
python robots_validator.py https://exemplo.com.br
```

### Saída Estruturada para Pipelines em JSON

```bash
python robots_validator.py https://exemplo.com.br -j
```

***

## Conformidade e Governança Web no Brasil

A correta governança do robots.txt apoia a segurança cibernética e a integridade de dados no Brasil. Definir regras adequadas protege endpoints administrativos contra indexação indevida enquanto assegura o posicionamento orgânico de ativos públicos.

Recomenda-se integrar a auditoria de robots.txt aos pipelines contínuos de desenvolvimento para evitar bloqueios acidentais e gerenciar o acesso de rastreadores de inteligência artificial.

***

## Perguntas Frequentes Técnicas

### Como o validador identifica bloqueios globais de indexação?

O motor avalia blocos com <code>User-agent: *</code>. Caso localize a regra <code>Disallow: /</code> sem nenhuma diretiva compensatória <code>Allow:</code>, o sistema deduz 50 pontos e emite alerta de bloqueio crítico da aplicação.

### Por que a ausência da diretiva Sitemap é penalizada no robots.txt?

Declarar a localização do sitemap no robots.txt orienta diretamente os rastreadores para os feeds oficiais de conteúdo. A ausência da diretiva <code>Sitemap:</code> acarreta penalidade de 20 pontos e gera alerta de otimização.

### Qual é o impacto de um crawl-delay excessivo?

Configurar um <code>Crawl-delay</code> superior a 5 segundos restringe drasticamente o orçamento de rastreamento de portais médios e grandes, atrasando a indexação de novas páginas. Essa configuração gera dedução de 15 pontos.

### Quais robôs de inteligência artificial são monitorados pelo validador?

A auditoria mapeia doze robôs de IA proeminentes: GPTBot, ChatGPT-User, ClaudeBot, Anthropic-AI, PerplexityBot, CCBot, Cohere-AI, Google-Extended, Applebot-Extended, Omgilibot, Diffbot e ByteSpider.

### O que significam as faixas de status e pontuação de governança?

Notas entre 80 e 100 indicam status COMPLIANT sob a RFC 9309. Entre 50 e 79 pontos o status é WARNING por ausência de sitemaps ou delay elevado, e abaixo de 50 pontos o status é CRITICAL, apontando bloqueio severo de rastreamento.

***

## Resposta a Incidentes e Consultoria Técnica

Para auditorias aprofundadas de SEO técnico, governança de rastreadores e conformidade de aplicações web, consulte os especialistas da **TAVARDT**.

***

## Links Úteis

* **Portal Corporativo:** https://ag.tavardt.com/br/
* **Suíte de Diagnósticos:** https://tools.tavardt.com/br/
* **Contato Técnico:** https://ag.tavardt.com/br/contato/

***

### Licença
Distribuído sob a Licença MIT.

***

© 2026 TAVARDT. Todos os direitos reservados.
