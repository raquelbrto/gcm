# gcm
 
A. Estabilidade das configurações de software
A estabilidade de diferentes configurações de um software está relacionada ao seu grau de maturidade, completude e confiabilidade. De acordo com os slides:

“Uma configuração de software representa o conjunto de subprodutos do trabalho em um dado momento no tempo”​
.

Tipos de configuração (quanto à estabilidade)​
:
Configuração Intermediária

Criada a cada commit, merge, rebase, etc.

Pode ser instável, usada para desenvolvimento contínuo.

Build

Conjunto de artefatos que já possui certa estabilidade.

Gerado automaticamente (ex: integração contínua).

Ainda incompleto, mas com propósito de testes.

Baseline

Ponto estável formalmente estabelecido, referência para próximos passos.

Só pode ser modificada mediante controle formal de mudanças.

Release

Entrega final de uma versão estável para o cliente/produção.

Já testada e validada.

Convenções de nomenclatura:
Git tags: v1.0.0, v2.2.1-rc, stable-2.1.0

Sufixos:

-alpha, -beta, -rc: indicam estágio de amadurecimento.

Ex: release-2.3-beta = versão em testes antes de virar release.

Essas classificações permitem rastreabilidade, controle de mudanças e reprodutibilidade.

B. Controle de versão centralizado vs distribuído
Centralizado (ex: Subversion - SVN):
Arquitetura: Um único repositório central.

Vantagens:

Simplicidade operacional.

Controle centralizado.

Desvantagens:

Dependência da rede.

Trabalho offline é limitado ou impossível.

Risco de gargalos e falhas únicas.

Distribuído (ex: Git):
Arquitetura: Cada desenvolvedor tem um clone completo do repositório.

Vantagens:

Trabalho offline.

Operações locais rápidas (commit, branch, diff).

Mais flexível para múltiplas realidades (ex: várias versões coexistentes).

Desvantagens:

Pode ter curva de aprendizado maior.

Requer práticas bem definidas para colaboração.

Citação dos slides:
"Git → controle de versão local (em sua máquina); GitHub → compartilhamento e colaboração em nuvem"​
.

✅ Questão 2
Cenário: Projeto SIGA e uso de estratégias de branching
1. Aplicação do Git Flow
O Git Flow é ideal para cenários com liberação formal e manutenção de múltiplas versões.

(1) Branches:
main: Produção (v2.1)

develop: Desenvolvimento principal

release/2.2: Estabilização da versão 2.2

hotfix/2.1.1: Correção urgente para produção

feature/*: Novas funcionalidades (v2.3)

(2) Propósitos:
main: Apenas código já entregue ao cliente.

develop: Integração das novas features.

release/2.2: Correções de bugs da equipe de testes (F1).

hotfix/2.1.1: Correção crítica feita por membro destacado.

feature/nova-funcionalidade: Funcionalidades da v2.3 (F2).

(3) Equipes:
F1: Atua em release/2.2.

F2: Atua em feature/* + develop.

Membro específico: Atua na hotfix/2.1.1.

(4) Merges:
feature/* → develop

release/2.2 → main e develop

hotfix → main e develop

(5) Extras:
Pull requests revisados antes de merge.

Tags de versão: v2.2.0, v2.1.1.

Branches protegidas.

CI/CD automático nos merges.

Branches descartadas após merge.

2. Aplicação do GitHub Flow
Mais simples e ideal para desenvolvimento contínuo, com deploys frequentes.

(1) Branches:
main: Produção

fix-critic-prod: Bug crítico

feature/melhorias-2.3: Novas funcionalidades

fix/teste-erro: Correções da v2.2

(2) Propósitos:
main: Código sempre pronto para produção.

Branches curtas para features, fixes e hotfixes.

(3) Equipes:
F1: Corrige erros em branches de fix (fix/teste-erro).

F2: Atua em branches de features (feature/*).

Membro designado: fix-critic-prod.

(4) Merges:
Todos feitos via Pull Request para main.

CI verifica se está tudo ok antes do merge.

Revisão de código obrigatória.

(5) Extras:
Tags marcando versões estáveis.

Branch protegida com exigência de revisão.

Pull Requests documentados com histórico e comentários.

GitHub Actions para testes e builds automáticos.