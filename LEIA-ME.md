# 🍪 Doceria da Ju Artesanais — Sistema de Pedidos

## O que está incluído

- `index.html` → App do cliente (fazer pedido + acompanhar status)
- `admin.html` → Painel da administradora (gerenciar pedidos + relatórios)

---

## Como colocar online (passo a passo, sem programação)

### Passo 1 — Criar conta no GitHub (gratuito)
1. Acesse https://github.com e clique em "Sign up"
2. Crie sua conta com email e senha
3. Clique em "New repository"
4. Nome: `doceria-da-ju`
5. Deixe como "Public" e clique "Create repository"
6. Faça upload dos arquivos `index.html` e `admin.html`

### Passo 2 — Publicar no Vercel (gratuito)
1. Acesse https://vercel.com e clique "Sign up with GitHub"
2. Clique "Add New Project"
3. Selecione o repositório `doceria-da-ju`
4. Clique "Deploy"
5. Em alguns segundos seu site estará em: `doceria-da-ju.vercel.app`

### Passo 3 — Integrar Mercado Pago
1. Acesse https://www.mercadopago.com.br/developers
2. Crie uma conta de desenvolvedor
3. Vá em "Suas integrações" → "Criar aplicação"
4. Copie sua "Public Key" e "Access Token"
5. Substitua no arquivo index.html onde está escrito:
   `SEU_PUBLIC_KEY_AQUI` e `SEU_ACCESS_TOKEN_AQUI`

### Passo 4 — Banco de dados (Supabase, gratuito)
1. Acesse https://supabase.com e crie conta
2. Clique "New project" → nome: `doceria-ju`
3. Anote a "URL" e "anon key" do projeto
4. Crie as tabelas rodando o SQL abaixo no "SQL Editor"

```sql
CREATE TABLE pedidos (
  id SERIAL PRIMARY KEY,
  cliente_nome TEXT NOT NULL,
  cliente_telefone TEXT NOT NULL,
  cliente_endereco TEXT NOT NULL,
  sabor TEXT NOT NULL,
  quantidade INT NOT NULL,
  valor_total DECIMAL(10,2),
  tipo_entrega TEXT DEFAULT 'sul',
  observacoes TEXT,
  status TEXT DEFAULT 'waiting',
  pagamento TEXT,
  pago BOOLEAN DEFAULT false,
  criado_em TIMESTAMP DEFAULT NOW()
);
```

---

## Domínio personalizado (opcional, ~R$ 40/ano)
1. Compre em https://registro.br (ex: `doceriadaju.com.br`)
2. No Vercel, vá em "Settings" → "Domains" → adicione seu domínio
3. Siga as instruções para apontar o DNS

---

## Suporte
Se travar em algum passo, qualquer desenvolvedor freelancer consegue
finalizar a configuração em 1-2 horas por ~R$ 100-200.
Você pode encontrar um em: https://www.workana.com ou https://99freelas.com.br
