---
title: Sobre revisão de dependências
intro: 'A revisão de dependências permite que você capture dependências vulneráveis antes de introduzi-las no seu ambiente e fornece informações sobre licença, dependências e idade das dependências.'
product: '{% data reusables.gated-features.dependency-review %}'
shortTitle: Revisão de dependência
versions:
  fpt: '*'
  ghes: '>= 3.2'
  ghae: issue-4864
  ghec: '*'
type: overview
topics:
  - Advanced Security
  - Dependency review
  - Vulnerabilities
  - Dependencies
  - Pull requests
redirect_from:
  - /code-security/supply-chain-security/about-dependency-review
---

{% data reusables.dependency-review.beta %}

## Sobre revisão de dependências

{% data reusables.dependency-review.feature-overview %}

Se um pull request for direcionado ao branch padrão do seu repositório e contiver alterações em manifestos de pacote ou arquivos de bloqueio, você poderá exibir um comentário de dependência para ver o que foi alterado. A revisão de dependências inclui detalhes de alterações nas dependências indiretas nos arquivos de bloqueio, e informa a você se alguma das dependências adicionadas ou atualizadas contém vulnerabilidades conhecidas.

{% ifversion fpt %}
A revisão de dependências está disponível em todos os repositórios públicos de todos os produtos e não pode ser desabilitada. A revisão de dependências está disponível em repositórios privados pertencentes a organizações que usam o GitHub Enterprise Cloud e têm uma licença para {% data variables.product.prodname_GH_advanced_security %}. Para obter mais informações, consulte a [documentação de {% data variables.product.prodname_ghe_cloud %}](/enterprise-cloud@latest/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review).

{% elsif ghec %}
Revisão de dependências está incluída em {% data variables.product.product_name %} para repositórios públicos. Para usar a revisão de dependências em repositórios privados pertencentes a organizações, você deve ter uma licença para {% data variables.product.prodname_GH_advanced_security %} e ter o gráfico de dependências habilitado. Para obter mais informações, consulte "[Explorar as dependências de um repositório](/code-security/supply-chain-security/understanding-your-software-supply-chain/exploring-the-dependencies-of-a-repository#enabling-and-disabling-the-dependency-graph-for-a-private-repository)".

{% elsif ghes or ghae %}
A revisão de dependências está disponível quando o gráfico de dependências está habilitado para {% data variables.product.product_location %} e {% data variables.product.prodname_advanced_security %} está habilitado para a organização ou repositório.
{% endif %}

Às vezes, você pode apenas querer atualizar a versão de uma dependência em um manifesto e gerar um pull request. No entanto, se a versão atualizada desta dependência direta também atualizou as dependências, seu pull request pode ter mais alterações do que o esperado. A revisão de dependência para cada manifesto e arquivo de bloqueio fornece uma maneira fácil de ver o que foi alterado e se alguma das novas versões de dependências contém vulnerabilidades conhecidas.

Ao verificar as revisões de dependências em um pull request e alterar todas as dependências sinalizadas como vulneráveis, você pode evitar que vulnerabilidades sejam adicionadas ao seu projeto. Para obter mais informações sobre como funciona a revisão de dependências, consulte "[Revisar as alterações de dependência em um pull request](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-dependency-changes-in-a-pull-request)".

{% data variables.product.prodname_dependabot_alerts %} encontrará vulnerabilidades que já estão nas suas dependências, mas é muito melhor evitar a introdução de possíveis problemas do que corrigir problemas em uma data posterior. Para obter mais informações sobre {% data variables.product.prodname_dependabot_alerts %}, consulte "[Sobre alertas para dependências vulneráveis](/github/managing-security-vulnerabilities/about-alerts-for-vulnerable-dependencies#dependabot-alerts-for-vulnerable-dependencies)".

A revisão de dependências é compatível com as mesmas linguagens e os mesmos ecossistemas de gestão de pacotes do gráfico de dependência. Para obter mais informações, consulte "[Sobre o gráfico de dependência](/github/visualizing-repository-data-with-graphs/about-the-dependency-graph#supported-package-ecosystems)".

{% ifversion ghec or ghes or ghae %}
## Habilitar revisão de dependências

O recurso de revisão de dependências é disponibilizado quando você habilitar o gráfico de dependências. {% ifversion ghec %}Para obter mais informações, consulte "[Habilitando o gráfico de dependências](/code-security/supply-chain-security/understanding-your-software-supply-chain/about-the-dependency-graph#enabling-the-dependency-graph).{% endif %}{% ifversion ghes or ghae %}Para obter mais informações, consulte "[Habilitando o gráfico de dependências para a sua empresa](/admin/code-security/managing-supply-chain-security-for-your-enterprise/enabling-the-dependency-graph-for-your-enterprise)".{% endif %}
{% endif %}
