# Thumber Studio Portátil — aplicativo instalável

Este pacote reúne Biblioteca, Ajustador, Capa e Post. O editor e a biblioteca funcionam offline depois que o app é aberto uma vez pelo endereço HTTPS e o cache termina de instalar. A busca na AniList e imagens carregadas por URL continuam precisando de internet.

## Publicar no GitHub Pages

1. Crie um repositório para a ferramenta no GitHub. Envie **o conteúdo desta pasta** para a raiz do repositório: `index.html`, `manifest.json`, `sw.js`, `icons/` e `.nojekyll`.
2. Em **Settings → Pages → Build and deployment**, escolha **Deploy from a branch**, a branch principal (`main`) e a pasta **/(root)**. Salve.
3. Aguarde o link HTTPS informado pelo GitHub Pages. Abra esse endereço no Chrome do Android ou no navegador do computador.
4. No Android, use **Instalar app** quando aparecer no topo da ferramenta. Se esse botão não aparecer, procure **Instalar app** ou **Adicionar à tela inicial** no menu do navegador.
5. Abra o aplicativo instalado uma vez com internet. Depois, teste o modo avião: capa, post, ajustador, biblioteca e projetos locais devem funcionar. A AniList não responderá sem conexão.

Não basta abrir `index.html` como arquivo local para instalar o PWA: a instalação exige HTTPS (ou localhost no desenvolvimento).

## Migrar o acervo

Na Biblioteca separada, exporte o backup `.tmbb`. Na versão instalada, abra a aba **Biblioteca** e importe esse arquivo. O armazenamento do novo endereço é separado do armazenamento usado pelo HTML local ou por outro navegador.

Os projetos e miniaturas ficam no armazenamento deste navegador/dispositivo (IndexedDB). O GitHub Pages hospeda apenas os arquivos do aplicativo e **não recebe o acervo**. Exporte `.tmbb` regularmente e guarde outra cópia. Para usar em outro aparelho, importe o backup lá.

## Atualizar

Substitua os arquivos do repositório pelo novo pacote. Mantenha o mesmo endereço do GitHub Pages para preservar o armazenamento associado à origem. O arquivo `sw.js` muda o nome do cache a cada build. Após uma atualização, feche e reabra o aplicativo com internet para carregar a versão nova.

## Verificação rápida

- Abas Biblioteca, Ajustar, Capa e Post abrem.
- Ajustador envia pôster e fundo para o Studio.
- Studio gera a capa, cria o Post e salva na Biblioteca.
- O mesmo ID é encontrado pela busca e o projeto reabre no editor.
- Backup `.tmbb` exporta e importa.
- O aplicativo instalado reabre em modo avião após a primeira abertura online.
