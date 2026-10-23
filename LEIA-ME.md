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

## Edição unificada

Edição e leitura são uma coisa só. O texto aparece formatado enquanto você escreve: negrito como negrito, links como links, títulos grandes, caixas de destaque, tabelas, imagens e PDFs incorporados. Os códigos Markdown só aparecem no trecho exato em que está o cursor, para permitir editá-lo.

No topo da nota há dois botões:

| Botão | Função |
|---|---|
| `< >` | Mostra todos os códigos (modo código-fonte). |
| Livro | Abre o modo somente leitura. |

Clicar num link abre a nota de destino. Para editar o link, leve o cursor até ele com as setas do teclado.

## Tela dividida

Dá para trabalhar com dois arquivos ao mesmo tempo, em qualquer combinação: duas notas, dois PDFs, ou uma nota e um PDF. Cada lado tem as próprias abas.

- Para abrir: use o ícone de colunas na faixa de ícones à esquerda ou no fim da barra de abas, a opção "Abrir ao lado" no menu de um arquivo na árvore, ou Alt+clique num arquivo ou link. No teclado, Ctrl/⌘+Alt+\\.
- Para mover uma aba de um lado para o outro: clique com o botão direito na aba (no iPad, mantenha o dedo pressionado) e escolha "Mover para o outro painel".
- A divisória do meio pode ser arrastada para ajustar a largura. O botão no fim da barra de abas alterna entre lado a lado e um em cima do outro, que funciona melhor com o iPad na vertical.
- O painel em uso tem a aba destacada com uma linha colorida. A estrutura, os backlinks e o Gemini acompanham esse painel.
- Os PDFs se ajustam sozinhos à largura do painel, até você mudar o zoom manualmente.

## Códigos e leis

Quando a nota tem artigos ("Art. 1º", "Art. 2º"…), o Códex a trata como lei. Funciona bem com o texto copiado do Planalto.

- A árvore da estrutura abre pelo botão de lista no topo da nota, pela aba Estrutura da barra esquerda ou por Ctrl/⌘+Shift+O. Ela mostra Parte › Livro › Título › Subtítulo › Capítulo › Seção › Subseção › Artigo. Clique para ir ao ponto. O campo de filtro aceita, por exemplo, "art 5" ou "capítulo II".
- Linhas de Título, Capítulo e semelhantes aparecem centralizadas. Os números dos dispositivos (Art., §, incisos, alíneas) aparecem em negrito.
- Comentários por dispositivo: ponha o cursor no artigo, parágrafo, inciso ou alínea e clique no botão de comentário da barra de formatação, ou use Ctrl/⌘+Shift+M.
  - O comentário é salvo como uma nota comum em `Comentários/<nome da lei>/Art. 5º, § 1º.md`. Pode ser longo e ter links, tags e formatação.
  - Dispositivos comentados ficam sublinhados em pontilhado, com um pequeno ícone ao lado. Passar o mouse sobre o número ("Art. 5º", "§ 1º", "I", "a)") mostra o comentário. No iPad, toque no ícone.
  - Na janela do comentário dá para editar ou abrir o comentário como nota inteira.
  - Se a lei for renomeada, a pasta de comentários acompanha.

## Barra de formatação

Acima do editor ficam os comandos de formatação: negrito, itálico, sublinhado, tachado, fonte, tamanho, cor da fonte, cores de realce, títulos, listas, caixas de destaque e alinhamento de parágrafo.

- Negrito, itálico, tachado, títulos, listas e o realce amarelo usam Markdown puro.
- Sublinhado, cores, fonte, tamanho e alinhamento de um parágrafo específico usam pequenas etiquetas HTML, que só ficam visíveis no trecho em que está o cursor.
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
| Ctrl/⌘+E | Alternar edição e somente leitura |
| Ctrl/⌘+Shift+E | Mostrar ou ocultar os códigos |
| Ctrl/⌘+Shift+M | Comentar o dispositivo do cursor |
| Ctrl/⌘+F | Buscar e substituir dentro da nota |
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

## Canetas, marca-texto e borracha no PDF

- Tipos de caneta: com a ferramenta Caneta, o botão com o nome da caneta abre a lista. As opções são esferográfica, tinteiro (traço caligráfico), lápis, marcador (espessura sempre igual) e pincel (muito sensível à pressão). A pressão funciona com a Apple Pencil, a S Pen e as canetas de PC.
- Cores: a barra mostra as seis cores usadas por último. O círculo colorido abre a paleta, com 30 cores para a caneta e 18 para o marca-texto, e a opção "Outra cor…".
- Tamanho do ponto: além dos quatro tamanhos rápidos, o botão "pt ▾" abre um controle deslizante com prévia do traço e 16 tamanhos prontos.
- Destaque reto: com o marca-texto, o botão "Reto/Livre" alterna o modo. No modo reto, o destaque fica na horizontal, na altura exata da linha do texto, e não passa do fim da linha. Se não houver texto sob a caneta (PDF escaneado), vira uma faixa reta na espessura escolhida.
- Borracha:
  - O botão lateral da S Pen apaga enquanto estiver pressionado, com qualquer ferramenta.
  - A ponta-borracha de canetas de PC (Surface e similares) também apaga.
  - Na barra da borracha há quatro tamanhos.
  - Com "Só caneta" ligado, dois toques rápidos com o dedo na página alternam entre a caneta e a borracha.
  - O duplo toque da Apple Pencil não chega aos sites: o iPadOS o reserva para os próprios apps. Por isso, no iPad, use o toque duplo com o dedo.

## Arquivo de revisão dos destaques

No topo do PDF, o botão "Revisão" gera a nota "Revisão — <nome do PDF>", na mesma pasta do PDF, e a abre ao lado.

- A nota traz o texto de cada destaque, na ordem em que foi feito, com a cor do marca-texto e um link para a página do PDF. Entram os destaques feitos com o marca-texto (reto ou livre), os feitos pela seleção de texto e o texto dos post-its.
- A cada novo clique, a parte automática é refeita com todos os destaques, inclusive os novos. Ela fica entre duas marcas invisíveis na leitura. O que você escrever fora delas, acima ou abaixo, é preservado.
- Destaques feitos antes desta versão não têm registro de horário. Eles entram primeiro, na ordem das páginas.
- Em PDF escaneado, sem texto reconhecível, o destaque aparece como "destaque sem texto reconhecível".

## Post-its no PDF

- Escolha a ferramenta Post-it (ícone de bilhete, ou a tecla N) e toque na página onde quer colar a nota.
- O post-it abre como um cartão para escrever. No cabeçalho dele dá para:
  - arrastar o post-it para outro lugar;
  - trocar a cor (6 opções);
  - recolher o cartão, deixando só um ícone colado na página;
  - excluir o post-it.
- O texto é salvo automaticamente, entra no arquivo de revisão e sai no PDF exportado.

## Vincular trechos do PDF a notas, tags e favoritos

Selecione um trecho com a ferramenta de seleção, pelo mouse ou pela caneta. O menu que aparece tem três botões:

- Nota: cita o trecho na nota escolhida, com um link de volta para a página do PDF. O vínculo aparece nos backlinks e no grafo. Shift+Enter cria uma nota nova.
- Tag: marca o trecho com uma tag, nova ou já existente. A tag entra no arquivo de revisão e aparece no painel de tags e na busca.
- Favorito: o trecho vai para os favoritos. Clicar nele abre o PDF direto na página.

Os trechos vinculados ficam sublinhados em azul tracejado. Tocar neles abre um menu para abrir a nota, ver a tag, adicionar outros vínculos ou removê-los.

## Copiar o link de um artigo e vincular trechos de PDF

- Copiar o link de um artigo, parágrafo, inciso ou parágrafo comum de uma nota (por exemplo, o art. 20 da Constituição):
  - ponha o cursor na linha e toque no botão de copiar da barra de formatação, ao lado do ¶ (ou Ctrl/⌘+Shift+C);
  - ou clique com o botão direito sobre a linha e escolha "Copiar link deste dispositivo";
  - ou use "Copiar link" na janela de comentário do dispositivo.
- O link sai no formato `[[Constituição…#^código|Constituição…, Art. 20]]`. Cole em qualquer nota.
- No PDF, selecione o trecho que cita o artigo e toque em "Vincular ao copiado". O trecho fica sublinhado em azul, e tocar nele abre a nota já no art. 20.
- Pelo botão "Nota" do PDF, você escolhe a nota e, em seguida, o artigo ou parágrafo. Digite, por exemplo, "art 20": o art. 20 aparece primeiro, à frente do 200 e do 201. A opção "Nota inteira" continua citando o trecho no fim da nota.
- No sentido inverso: "Copiar link" no menu de seleção do PDF (ou "Copiar link deste trecho", ao tocar num trecho vinculado) copia um link que abre o PDF na página certa, rola até o trecho e o faz piscar. Cole esse link na nota, ao lado do artigo.
- O reconhecimento de artigos agora também funciona nas leis em formato de lista (`* **Art. 20.**`), como a Constituição e as leis inseridas no cofre. Com isso, a árvore da estrutura, os comentários por dispositivo e os rótulos dos links passam a funcionar nelas.

## Voltar ao ponto onde parou

- O Códex lembra a posição de cada nota e de cada PDF.
- Ao reabrir o arquivo, mesmo depois de fechar o app, você volta ao mesmo trecho.
- Se você abrir o arquivo por um link que aponta para um ponto específico, prevalece o ponto do link.

## Redação no destino e vínculo automático na origem

- Ao copiar um artigo (botão de copiar da barra de formatação ou menu do botão direito), o link sai com a redação: `![[Lei#^código|Lei, Art. 20]]`. Onde for colado, aparece o texto completo do dispositivo: caput, parágrafos, incisos e alíneas. Os incisos inteiramente revogados (tachados) ficam de fora. Não é preciso abrir a lei. No Obsidian, o mesmo link também mostra o texto.
- Se quiser só a referência, sem o texto, use "Copiar só o link" no menu do botão direito.
- No PDF, tocar num trecho vinculado abre um cartão com a redação do artigo. O botão "Abrir na lei" continua lá, se você precisar.
- Na origem, cada artigo que recebe vínculos ganha automaticamente um marcador com o número de vínculos, no modo de edição e no de leitura. Tocar no marcador mostra de onde vem cada vínculo (notas e trechos de PDF), com a frase em volta, e permite abrir a origem.
- O marcador é calculado na hora. O texto da lei não é alterado, e o marcador some sozinho quando o vínculo é apagado.
