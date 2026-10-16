# schematize-models-placar

Placar **agregado e anônimo** de quais ferramentas de IA (Codex, Cursor, Gemini e subagents Claude)
entregam bem em quais tipos de tarefa, coletado opcionalmente pela skill
[`schematize-models`](https://github.com/schematizeme/skill-models). Serve para melhorar o roteamento
da skill com evidência, não com opinião.

Cada semana ISO tem **uma issue** chamada `Placar AAAA-Www`. Cada usuário que ligou a publicação
posta **um comentário por semana** nela. Nada é enviado sem consentimento.

## O que é coletado

Só **contagens por ferramenta e tipo de tarefa**, de vocabulário fechado:

- ferramenta (`codex`, `cursor`, `gemini`, `claude-subagent/haiku|sonnet|opus`);
- tipo de tarefa (`codigo`, `refactor`, `teste`, `review`, `visual-ui`, `imagem`, `docs`, `pesquisa`, `mecanico`);
- por célula: quantas delegações, quantas `ok`, `corrigido-pelo-revisor`, `falhou`/`travou`, `indisponivel` e a duração média em segundos;
- contagem de notas de categoria fechada (`timeout`, `saida-truncada`, `ignorou-instrucao`, `sem-saida`, `erro-cli`, `auth`, `cota`, `alucinou`, `fora-de-escopo`);
- versão da skill e a semana ISO.

## O que NÃO é coletado

Código, diffs, caminhos de arquivo, nome de projeto ou de repositório, prompts, respostas dos
modelos, texto livre de qualquer tipo, horários individuais de cada delegação, identificadores de
máquina. O script recusa qualquer valor fora do vocabulário acima, e o registro local tem o mesmo
formato.

## Anonimato: o que é e o que não é

O **conteúdo** é anônimo. A **autoria não**: o comentário é postado pelo `gh` do usuário e aparece
**no nome da conta GitHub dele**, num repositório público. Por isso a publicação é **opt-in**: a
skill mostra a prévia exata do comentário e avisa disso antes da primeira vez. Dá para desligar a
qualquer momento (`/models-score`) e apagar o próprio comentário aqui no GitHub.

Para não expor padrão de uso individual, a skill só publica com **pelo menos 5 delegações** na
janela e **no máximo uma vez por semana**.

## Como a skill usa isso

O que fica aqui alimenta decisões de roteamento da skill (por exemplo, quais tipos de tarefa vale
mandar a qual ferramenta). O roteamento de cada usuário usa o **placar local dele**, não este.

## Formato do comentário

Uma tabela markdown (ferramenta, tipo, n, ok, corrigido, falhou/travou, indisponível, duração
média) mais um bloco JSON com os mesmos números, marcado por `<!-- schematize-models-placar v1 -->`.

Licença do conteúdo: domínio público (CC0).
