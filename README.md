# CHECK-DIÁRIO PB - OWLL TECH MOBILE SEGURO

Pacote atualizado para Netlify + Supabase com:

- Chaves do Supabase fora do front-end.
- Login usando cookie `HttpOnly` criado pela Netlify Function.
- Telas mobile para motorista e supervisor com navegação inferior estilo app.
- Compartilhamento de relatórios pelo WhatsApp/compartilhamento nativo do Android.
- Tela inicial minimalista com nome do sistema, card de login, assinatura OWLL TECH e mascote discreto ao fundo.
- Estrutura preparada para empacotar como APK usando o Android WebView Wrapper incluído em `android-wrapper/`.

## Netlify

Configuração esperada:

```txt
Build command: npm run build
Publish directory: public
Functions directory: netlify/functions
```

Variáveis obrigatórias no Netlify:

```env
SUPABASE_URL=https://SEU-PROJETO.supabase.co
SUPABASE_ANON_KEY=sua_anon_ou_publishable_key
SUPABASE_SERVICE_ROLE_KEY=sua_service_role_key
SUPABASE_BUCKET=checklist-pb
```

## Teste rápido

Após o deploy, abra:

```txt
https://SEU-SITE.netlify.app/api/health
```

Resposta esperada:

```json
{"ok":true,"message":"API ativa. Segredos estão no servidor."}
```

## APK

O APK não deve carregar arquivos locais se você usa Netlify Functions, porque as Functions ficam no servidor. O app Android precisa abrir a URL publicada no Netlify.

Edite este arquivo antes de compilar:

```txt
android-wrapper/app/src/main/res/values/strings.xml
```

Troque:

```txt
https://SEU-SITE.netlify.app
```

pela URL real do seu site.

Depois abra a pasta `android-wrapper` no Android Studio e gere:

```txt
Build > Build Bundle(s) / APK(s) > Build APK(s)
```

## Observação importante sobre WhatsApp

No navegador e no APK, o botão Compartilhar usa o compartilhamento nativo quando o Android permite anexar arquivo TXT. Se o aparelho/navegador não permitir arquivo, ele abre o WhatsApp com o texto do relatório.
