# ECLIPSE — continuidade entre trabalho e casa

Este repositório pode ter um **GitHub Codespace** configurado com os arquivos em `.devcontainer/`.
A imagem oferece **Godot 4.7.2 (linha de comando/headless), Python 3 e Git**, em Linux.

## Primeira inicialização

1. Adicione `.devcontainer/` e este documento ao repositório e faça commit + push.
2. Visite o repositório no GitHub e selecione **Code > Codespaces > Create codespace on main**.
3. Espere a construção do contêiner. Confira no terminal:

```bash
godot --headless --version
python3 --version
git status
```

## Continuar o trabalho

- **No trabalho:** abra o Codespace pelo navegador. Edite, teste via CLI, faça commit e push.
- **Em casa:** reabra o mesmo Codespace para continuar na nuvem; ou use um clone local
  com o Godot gráfico e faça `git pull` para receber mudanças antes de trabalhar.
- **Para publicar mudanças feitas em casa:** faça commit e push da mesma branch.
- **Antes de mudar de máquina:** salve e sincronize alterações. Não trabalhe ao mesmo
  tempo nos mesmos arquivos em duas cópias sem sincronizar.

## Limitações importantes

- O ambiente é **Linux headless**; não oferece automaticamente uma janela do editor
  Godot, GPU, emulador Android ou teste visual de jogabilidade.
- **Android SDK e Export Templates não vêm instalados neste contêiner.** Build APK
  requer configuração separada. A chave de assinatura nunca deve ser versionada.
- O Codespace não vira automaticamente um workspace local do aplicativo Codex para Windows.
- Consulte limites e cobrança do Codespaces nas configurações do GitHub.
- Pare o Codespace quando não estiver usando para economizar sua cota.

## Após o `project.godot` ser criado

```bash
godot --headless --editor --path . --quit
```

Esse comando ajuda a identificar falhas de importação e scripts, mas não substitui
abrir e jogar o projeto no Godot local.
