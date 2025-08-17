# Patch Frontend — 2025-08-10 21:09:43

Arquivos incluídos:
1. `src/api/client.js` — cliente Axios com `VITE_API_URL`.
2. `.env` — define `VITE_API_URL=http://localhost:3000`.
3. `src/pages/Home/index.jsx` (ou caminho equivalente) — import ajustado para usar `src/api/client.js`.

## Como aplicar no seu projeto local

1. **Feche** o servidor do Vite se estiver rodando.
2. **Copie** os arquivos deste patch para as **mesmas localizações** no seu projeto:
   - Coloque `client.js` em: `seu-projeto/src/api/client.js` (crie a pasta `api` dentro de `src` se não existir).
   - Substitua/adicione o `.env` na raiz do projeto frontend.
   - Substitua `Home/index.jsx` no caminho correspondente (ex.: `src/pages/Home/index.jsx`).

> Dica: se seu projeto usa um caminho diferente (ex.: `src/screens/Home/index.jsx`), mantenha `client.js` em `src/api/client.js` e ajuste o import na Home:
> ```js
> import api from "../../api/client"; // ajuste os ../ conforme a profundidade
> ```

3. Rode novamente:
   ```bash
   npm install
   npm run dev
   ```

4. Acesse `http://localhost:5173`. O frontend chamará a API em `http://localhost:3000`. 
   Se sua API rodar em outra porta/URL, altere no `.env`:
   ```
   VITE_API_URL=http://SEU_HOST:PORTA
   ```

Qualquer erro (CORS, 404, autenticação), compartilhe o log que eu ajusto.