---
title: "Lição 12 - Publique o site com o GitHub Pages"
description: "Use o aplicativo GitHub Copilot para configurar um workflow do Pages, revisar o pull request e verificar se o Space Quiz está no ar."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Dê ao Space Quiz um endereço público publicando-o com o GitHub Pages. O Copilot pode preparar o workflow e orientar a publicação, mas você é responsável por revisar as mudanças e confirmar que o site está no ar.

Nesta lição, você vai:

- pedir ao Copilot que configure a publicação no GitHub Pages.
- revisar o workflow e o pull request antes de fazer o merge.
- acompanhar a publicação e verificar o site publicado.

## Cenário

O Space Quiz já está em um repositório do GitHub, mas ainda precisa de uma forma simples para as pessoas experimentarem. Publicar o site de arquivo único com o GitHub Pages o disponibiliza em uma URL pública, sem adicionar um servidor ou dependência de runtime.

## Peça ao Copilot para preparar a publicação

> [!WARNING]
> Criar um pull request pode fazer commit e push de código. Revise as configurações de aprovação e o repositório de destino antes de enviar este prompt. Com **Approve all**, não espere uma solicitação separada de confirmação.

Na sessão do aplicativo Copilot para `space-quiz`, envie este prompt:

```plaintext
Prepare a publicação deste repositório no GitHub Pages. Crie um workflow do GitHub Actions que compile o site, se necessário, e o publique no GitHub Pages depois que as mudanças chegarem à branch padrão. Adicione um README que descreva o aplicativo e como executá-lo localmente, caso ainda não exista. Crie um pull request com essas mudanças e informe o link e quaisquer configurações ou permissões necessárias do Pages. Não faça merge, não habilite o merge automático, não altere as configurações do Pages e não publique o site. Pare e aguarde minha revisão.
```

## Revise o workflow e o pull request

1. Confirme que o README só foi adicionado se o repositório ainda não tinha um.
2. Revise as mudanças do pull request, incluindo as etapas de compilação e publicação do workflow, os gatilhos e as permissões.
3. Confirme que o workflow publica a partir da branch padrão, e não de um pull request ainda não mesclado.
4. Peça as correções necessárias e revise o diff atualizado. Aguarde a aprovação das verificações obrigatórias do pull request antes de autorizar o merge.

## Autorize o merge e a publicação

> [!WARNING]
> O prompt a seguir autoriza o agente a fazer merge do pull request revisado, alterar as configurações do Pages no repositório e publicar o site. Envie-o somente depois de concluir a revisão e confirmar o repositório e o pull request. Dependendo das configurações de aprovação, essas ações podem ocorrer sem uma confirmação adicional.

Substitua `<PR_NUMBER>` pelo número do pull request que você revisou e envie este prompt separado:

```plaintext
Revisei o pull request <PR_NUMBER> neste repositório e autorizo o merge e a publicação. Habilite o GitHub Pages usando o GitHub Actions, faça merge somente desse pull request depois que as verificações obrigatórias forem aprovadas e acompanhe a publicação até que ela seja concluída com sucesso. Informe a URL final do site publicado. Se você não tiver permissão para habilitar o Pages ou fazer merge, diga exatamente o que preciso aprovar ou fazer; não informe que a tarefa foi concluída até que o site esteja no ar.
```

![Diagrama em três etapas: pull request do space-quiz mesclado; execução bem-sucedida de Deploy website no GitHub Actions com as etapas Build website, Upload artifact e Deploy to Pages; e Space Quiz no ar em yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Verifique a publicação

1. Acompanhe a execução de publicação do GitHub Actions até que ela seja concluída com sucesso.
2. Abra a URL informada e confirme que o Space Quiz carrega.

Se o agente não puder habilitar o Pages ou fazer merge do pull request, siga as instruções específicas fornecidas. Não considere a tarefa concluída até que a publicação tenha sucesso e o site esteja no ar.

## Resumo e próximas etapas

O Space Quiz está disponível como um site publicado, e você verificou a publicação em vez de confiar apenas no relato do agente. Continue para a [lição 13: Revisão e próximos passos][next-lesson].

[next-lesson]: ../13-review/
