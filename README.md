# Mentes IA — protótipo Android/PWA

Projeto inicial para testar no celular. Não precisa instalar um ambiente de programação.

## O que já funciona
- Interface responsiva em preto e roxo.
- Cinco assistentes com descrições e respostas demonstrativas.
- Troca de assistente, nova conversa e envio de mensagens.
- Histórico guardado localmente no navegador.
- Manifesto PWA e cache básico para carregamento offline após a primeira visita.

## Importante
Esta versão **não usa uma IA real**. As respostas são modelos demonstrativos no JavaScript. Para conectar Gemini ou outro provedor, crie primeiro um backend/servidor seguro. Nunca publique uma chave de API dentro de `index.html` ou de outro arquivo enviado ao navegador.

## Testar rapidamente no Android
1. Extraia o ZIP.
2. Abra `index.html` num editor de código Android que tenha pré-visualização local, ou publique os arquivos seguindo as instruções abaixo.
3. Teste selecionar cada assistente, enviar uma mensagem e tocar em “Nova conversa”.

Para testar a instalação PWA de forma confiável, publique em HTTPS (por exemplo, GitHub Pages).

## Publicar grátis com GitHub Pages usando o navegador do celular
1. Entre em https://github.com/ e crie uma conta, se necessário.
2. Crie um repositório público chamado `mentes-ia`.
3. Na página do repositório, use **Add file → Upload files** e envie `index.html`, `manifest.json`, `sw.js`, `icon.svg` e `README.md` (os arquivos, não a pasta ZIP).
4. Vá a **Settings → Pages**.
5. Em “Build and deployment”, selecione **Deploy from a branch**, escolha `main` e `/ (root)` e salve.
6. Aguarde a publicação. O endereço normalmente será `https://SEU-USUARIO.github.io/mentes-ia/`.
7. Abra o endereço no Chrome do Android. Menu ⋮ → **Adicionar à tela inicial** ou **Instalar app**, se a opção aparecer.

## Atualizar o projeto
Altere os arquivos no editor do GitHub ou envie os arquivos atualizados. Se o navegador continuar mostrando a versão antiga, feche e reabra o site; o service worker pode manter arquivos em cache. Para uma atualização maior, altere `CACHE_NAME` em `sw.js` (por exemplo, `mentes-ia-v2`).

## Próxima etapa: conectar uma IA real
1. Crie e teste uma chave de API no provedor escolhido.
2. Crie um endpoint de backend/serverless que guarda a chave como segredo e recebe a mensagem e o ID do assistente.
3. O backend deve selecionar instruções fixas e seguras para cada assistente e chamar a API.
4. No front-end, substitua `demoReply()` por uma chamada `fetch()` para o endpoint.
5. Defina limites de uso e monitore custos. “Grátis” normalmente tem cotas e condições que podem mudar.
