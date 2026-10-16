# Códex: como publicar e configurar

O aplicativo inteiro está num único arquivo, `index.html`. Não há servidor nem banco de dados. As notas ficam na pasta que você escolher. A chave do Gemini e o Client ID ficam guardados apenas no navegador de cada aparelho.

## 1. Publicar no GitHub Pages

1. Crie um repositório no GitHub, por exemplo `codex`. Na conta gratuita, o GitHub Pages exige repositório público. O arquivo não contém chave nem dado seu, então isso não expõe nada.
2. Envie o `index.html` para a raiz do repositório.
3. Em Settings, abra Pages. Em Source, escolha "Deploy from a branch", depois a branch `main` e a pasta `/ (root)`, e salve.
4. Em um ou dois minutos, o endereço fica disponível em `https://SEU-USUARIO.github.io/codex/`.

## 2. Ajustar o OAuth no Google Cloud Console

1. Em APIs e serviços, abra Biblioteca e confirme que a Google Drive API está ativada no projeto.
2. Em Credenciais, abra o seu ID do cliente OAuth. Ele precisa ser do tipo "Aplicativo da Web".
3. Em Origens JavaScript autorizadas, inclua `https://SEU-USUARIO.github.io`. Use só a origem, sem o nome do repositório e sem barra no final. O redirecionamento não precisa de URI.
4. Na tela de consentimento OAuth, com o app em modo de teste, cadastre o seu próprio e-mail em Usuários de teste.
5. Ao entrar pela primeira vez, o Google mostra o aviso "o Google não verificou este app". Clique em Avançado e depois em Acessar. Isso é esperado num app pessoal em modo de teste.

O aplicativo pede acesso completo ao Drive. É a única permissão que permite abrir uma pasta que já existe. Ele lê e grava apenas dentro da pasta que você escolher como cofre.

## 3. Primeiro acesso

1. Abra o endereço publicado e clique em "Configurações (Google e Gemini)".
2. Cole o Client ID do OAuth.
3. Cole a chave da API do Gemini e clique em "Carregar modelos disponíveis". Escolha o modelo.
4. Marque a opção de faturamento ativo apenas se o projeto da chave estiver no nível pago.
5. Volte e escolha onde fica o cofre:
   - Google Drive: entre na sua conta e escolha ou crie a pasta. Funciona em qualquer aparelho.
   - Pasta do computador: funciona no Chrome ou no Edge. Pode ser a mesma pasta, aberta pela unidade G: do Google Drive para computador, o que deixa o acesso mais rápido no PC.

As duas formas podem apontar para a mesma pasta do Drive, e o conteúdo é o mesmo. Essa pasta também pode ser aberta no aplicativo Obsidian.

## 4. No iPad

No Safari, abra o endereço e toque em Compartilhar e depois em "Adicionar à Tela de Início". O Códex passa a abrir em tela cheia, como um aplicativo. Use a opção Google Drive, porque o Safari não permite abrir pastas locais.

## Onde ficam as coisas

- Notas: arquivos `.md` comuns.
- Prints colados e arquivos arrastados: pasta `Anexos`. Isso pode ser alterado nas Configurações.
- Traços feitos à mão sobre um PDF: arquivo na pasta oculta `.anotacoes`, ao lado do PDF. O PDF original não é alterado. Para obter um PDF com os traços gravados, use o botão de exportar no anotador.
- Itens excluídos:
  - no Drive, vão para a lixeira do Google Drive;
  - numa pasta local, vão para a pasta `.trash` do cofre.

## Barra de formatação

Acima do editor ficam os comandos de formatação: negrito, itálico, sublinhado, tachado, fonte, tamanho, cor da fonte, cores de realce, títulos, listas, caixas de destaque e alinhamento de parágrafo.

- Negrito, itálico, tachado, títulos, listas e o realce amarelo usam Markdown puro.
- Sublinhado, cores, fonte, tamanho e alinhamento de um parágrafo específico usam pequenas etiquetas HTML. No modo edição, elas aparecem em cinza.
- O alinhamento justificado é o padrão geral. Ele pode ser alterado em Configurações, Aparência e editor, onde também se escolhe a fonte geral das notas.

## Vínculos entre parágrafos

Para ligar um trecho a outro parágrafo, da mesma nota ou de outra:

- Na mesma nota: clique no botão ¶ da barra de formatação, ou use Ctrl/⌘+Shift+K. Digite palavras do parágrafo de destino e tecle Enter. Se houver texto selecionado, ele vira o rótulo do vínculo.
- Digitando: escreva `[[#^` e palavras do parágrafo para ver as sugestões. Para outra nota, escreva `[[Nome da nota#^`. Com `[[#` aparecem títulos e parágrafos.
- Para levar o vínculo a outra nota: com o cursor no parágrafo, use Ctrl/⌘+Shift+C. O vínculo vai para a área de transferência, pronto para colar.

O Códex marca o parágrafo de destino com um código curto no fim da linha, como `^a1b2c3`. É o mesmo padrão do Obsidian. No modo leitura, o vínculo mostra o início do parágrafo de destino, e um clique leva até ele e o destaca.

## Atalhos principais

| Atalho | Ação |
|---|---|
| Ctrl/⌘+O | Abrir arquivo |
| Ctrl/⌘+P | Paleta de comandos |
| Ctrl/⌘+N | Nova nota |
| Ctrl/⌘+B, I, U | Negrito, itálico, sublinhado |
| Ctrl/⌘+Shift+K | Vincular a um parágrafo desta nota |
| Ctrl/⌘+Shift+C | Copiar vínculo do parágrafo do cursor |
| Ctrl/⌘+E | Alternar edição e leitura |
| Ctrl/⌘+G | Grafo |
| Ctrl/⌘+Shift+F | Busca |
| Ctrl/⌘+Shift+D | Nota diária |

No anotador de PDF:

| Tecla | Ferramenta ou ação |
|---|---|
| P | Caneta |
| H | Marca-texto |
| E | Borracha |
| T | Texto |
| V | Selecionar texto |
| Ctrl/⌘+Z | Desfazer |
| Ctrl/⌘+F | Buscar no PDF |
