# Minha página no GitHub Pages

Você tem 3 coisas: `index.html` (a página), `config.json` (todo o conteúdo) e este guia.

**Testar agora:** dê duplo clique no `index.html`. Ele abre sozinho com dados de exemplo.

---

## 1. Criar o repositório público
1. Entre em https://github.com e faça login.
2. Clique em **+** (canto superior direito) → **New repository**.
3. Dê um nome (ex.: `minha-pagina`), marque **Public** e clique em **Create repository**.

## 2. Subir os arquivos
1. No repositório, clique em **Add file → Upload files**.
2. Arraste `index.html` e `config.json`.
3. Clique em **Commit changes**.
4. Para as pastas: **Add file → Create new file**, digite `arquivos/LEIAME.txt` (a barra cria a pasta), escreva qualquer coisa e confirme. Faça o mesmo com `midia/LEIAME.txt` se for usar vídeo mp4.

## 3. Ativar o GitHub Pages
1. Vá em **Settings → Pages**.
2. Em **Build and deployment**, escolha **Deploy from a branch**.
3. Branch: **main**, pasta **/ (root)** → **Save**.
4. Espere 1 a 2 minutos. O endereço aparece na mesma tela: `https://SEUUSUARIO.github.io/minha-pagina/`

## 4. Trocar o vídeo
Abra `config.json` no GitHub, clique no **lápis** e edite a linha `"video"`:
- YouTube: `"video": "https://www.youtube.com/watch?v=XXXXXXXXXXX"`
- Arquivo seu: envie o mp4 para a pasta `midia/` e use `"video": "midia/video.mp4"`

Depois clique em **Commit changes**. Dica: mp4 pequeno (até ~25 MB) carrega mais rápido.

O vídeo começa mudo (regra dos navegadores). O visitante liga o som pelo botão **Ativar som**.

## 5. Adicionar ou remover legendas
Em `config.json`, procure `"legendas"`:
- **Adicionar:** copie uma linha `{ "texto": "...", "inicio": 1, "fim": 5 }`, cole embaixo e coloque vírgula entre as linhas (a última não leva vírgula). Tempos em segundos.
- **Remover:** apague a linha inteira.
- **Sem tempos:** apague `inicio` e `fim` de todas e elas trocam sozinhas a cada 4 segundos (mude em `legendas_intervalo_segundos`).

## 6. Adicionar ou substituir arquivos para download
1. No repositório, abra a pasta `arquivos/`.
2. **Add file → Upload files** e envie. Para substituir, envie outro com o **mesmo nome**.
3. Para apagar: clique no arquivo → **⋯ → Delete file**.

A lista no botão **Arquivos** atualiza sozinha (pode levar 1 a 2 minutos por causa do cache do GitHub).

---

## 7. Música de fundo
1. Envie o mp3 para a pasta `midia/` do repositório.
2. No `config.json`, ajuste `"musica": "midia/NOME-DO-SEU-ARQUIVO.mp3"` (nome e extensão exatamente iguais).
3. A música toca baixinho assim que a página abre. Se o navegador bloquear o som automático (comum), ela começa no primeiro toque/clique do visitante. A bolinha de som (canto inferior esquerdo) liga e desliga.
4. Volume: `"musica_volume"` de 0 a 1 (padrão 0.18, bem discreto).
5. Para tirar a música: `"musica": ""`.

---

## Dicas
- **Esconder o link Gerenciar:** `"mostrar_gerenciar": false`.
- **Só quem tem permissão edita:** visitantes veem apenas a página; o botão Gerenciar só abre a edição para quem está logado com acesso ao repositório.
- **Erro no JSON?** Quase sempre é vírgula faltando ou sobrando. O GitHub avisa antes de salvar.
- **YouTube no arquivo local:** pode não tocar com duplo clique (o YouTube bloqueia). No GitHub Pages funciona normalmente.
- **Domínio próprio:** preencha `repositorio` no `config.json` (usuario, repo, branch).
