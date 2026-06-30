# GERAR APK ANDROID - CHECK-DIÁRIO PB

Este projeto Android é um wrapper WebView para abrir seu sistema publicado no Netlify.

## Por que abrir a URL do Netlify?

Porque as chaves do Supabase estão protegidas dentro da Netlify Function. Se o APK carregasse arquivos locais, ele não teria acesso ao backend `/api` corretamente.

## Passo 1 - Editar URL do site

Abra:

```txt
app/src/main/res/values/strings.xml
```

Troque:

```xml
<string name="app_url">https://SEU-SITE.netlify.app</string>
```

pela URL real do seu projeto.

## Passo 2 - Abrir no Android Studio

1. Abra o Android Studio.
2. Clique em Open.
3. Selecione a pasta `android-wrapper`.
4. Aguarde sincronizar.

## Passo 3 - Gerar APK

No Android Studio:

```txt
Build > Build Bundle(s) / APK(s) > Build APK(s)
```

O APK costuma aparecer em:

```txt
android-wrapper/app/build/outputs/apk/debug/app-debug.apk
```

## Permissões usadas

- Internet: para acessar o sistema no Netlify.
- Câmera/arquivos: o input de fotos do checklist continua funcionando pelo WebView.

## Observação

Neste ambiente do ChatGPT não existe Android SDK/Gradle instalado, então o APK compilado não pôde ser gerado aqui. A estrutura Android foi deixada pronta para abrir e compilar no Android Studio.
