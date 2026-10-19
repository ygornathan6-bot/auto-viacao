# Sistema de Gestão de Frota e Operações – Auto Viação Jabour

Site estático (HTML + CSS + JavaScript puro). Não precisa de build nem de servidor.

## Estrutura
```
index.html              páginas/abas e estrutura
css/style.css           visual (vermelho/azul, responsivo, modo escuro)
js/app.js               toda a lógica (frota, veículos de apoio, linhas, monitoramento, garagens, manutenções, passageiros, subsídio, importação/exportação)
assets/                 logo, favicon e ícones do app
manifest.webmanifest    permite "Adicionar à tela inicial" no celular
vercel.json             configuração do Vercel
```

## Rodar localmente
Abra `index.html` no navegador, ou rode `npx serve .`

## Publicar no GitHub
```
git init
git add .
git commit -m "Sistema de frota Jabour"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/jabour-frota.git
git push -u origin main
```

## Publicar no Vercel
1. Em vercel.com, clique em **Add New → Project** e importe o repositório.
2. Framework Preset: **Other**. Deixe Build Command e Output Directory em branco.
3. Clique em **Deploy**. O link funciona em computador e celular.

## Conectar planilhas do Google Sheets
1. No Google Sheets: **Compartilhar → Qualquer pessoa com o link → Leitor** (ou **Arquivo → Compartilhar → Publicar na web → CSV**).
2. No sistema, aba **Importar**: cole o link da planilha na base desejada (e o nome da aba, se não for a primeira) e clique em **Buscar da planilha**.
3. A primeira linha pode ser o cabeçalho. As colunas esperadas aparecem em cada base.
4. Para baixar uma base com o visual do sistema: **Planilha formatada (.xlsx)**. Suba no Google Drive para abrir como Google Sheets.
Obs.: a leitura dos .xlsx e a geração das planilhas formatadas carregam bibliotecas do cdnjs (precisa de internet).

## Dados
- Os dados ficam no **localStorage** do navegador de cada aparelho (não são compartilhados entre aparelhos).
- Para levar os dados a outro aparelho: aba **Importar → Exportar backup (JSON)** e, no outro aparelho, **Importar backup**.
- Todas as tabelas podem ser exportadas em CSV (abre no Excel).
- Para compartilhar os dados em tempo real entre vários usuários seria necessário um back end com banco de dados (ex.: funções serverless do Vercel + banco), ainda não incluído.
