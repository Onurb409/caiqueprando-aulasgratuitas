# Landing Page de Captura - Caíque Prando

Landing page estática para captura de leads das **5 aulas gratuitas de Caíque Prando**.

O projeto é composto por um arquivo HTML com CSS e JavaScript embutidos, além da imagem principal usada na página.

## Estrutura

```text
.
+-- index.html
+-- caique-foto.jpg
+-- README.md
+-- .gitignore
```

## Como executar localmente

Como a landing page é estática, basta abrir o arquivo `index.html` no navegador.

Também é possível servir a pasta com qualquer servidor estático local, por exemplo:

```bash
npx serve .
```

## Publicação

Esta página pode ser publicada em serviços como Vercel, Netlify, GitHub Pages ou qualquer hospedagem de arquivos estáticos.

Antes de publicar, revise:

- O link de destino após o envio do formulário.
- O endpoint usado para salvar os leads.
- As permissões do Google Apps Script ou serviço equivalente.
- Se nenhum arquivo sensível foi adicionado ao repositório.

## Formulário e segurança

O formulário envia os dados para um webhook externo. Em uma landing page estática, qualquer URL presente no JavaScript do navegador é pública por natureza.

Por isso, **não coloque no `index.html` nem faça versionamento no Git**:

- ID da planilha do Google Sheets.
- Chaves de API.
- Credenciais de conta de serviço.
- Arquivos `.json` de autenticação.
- Arquivos `.env`.
- Código interno do Google Apps Script contendo permissões ou lógica sensível.
- Cópias/exportações da planilha com respostas.

O webhook publicado deve apenas receber os campos necessários (`nome`, `email` e `telefone`) e gravar na planilha configurada no ambiente seguro do Apps Script ou backend usado.

Recomendações:

- Mantenha a planilha privada.
- Compartilhe a planilha apenas com contas autorizadas.
- Não publique o link de edição da planilha.
- Não salve credenciais no frontend.
- Use validação e limitação de permissões no Apps Script/backend.
- Considere adicionar proteção contra spam se o volume de acessos crescer.

## Arquivos sensíveis

O `.gitignore` deste projeto bloqueia arquivos comuns de credenciais, ambientes locais, planilhas exportadas e artefatos de build.

Se algum arquivo sensível já tiver sido commitado anteriormente, apenas adicioná-lo ao `.gitignore` não remove o histórico do Git. Nesse caso, gere novas credenciais e remova o segredo do histórico antes de publicar o repositório.

## Manutenção

Ao alterar a landing page:

1. Teste o formulário localmente.
2. Confirme se o lead chegou corretamente na planilha.
3. Verifique se o redirecionamento abre a página correta.
4. Rode `git status` antes do commit para conferir se nenhum arquivo privado entrou por engano.
