# Gerar APK pelo GitHub Actions

Este pacote já contém:

- `.github/workflows/gerar-apk.yml`
- `android-wrapper/`
- ícone do APK usando a imagem da coruja Owll Tech

## Passo rápido

1. Suba todo o conteúdo desta pasta para um repositório no GitHub.
2. Abra a aba **Actions**.
3. Clique em **Gerar APK Check-Diário PB**.
4. Clique em **Run workflow**.
5. Informe a URL do seu Netlify, exemplo: `https://seu-site.netlify.app`.
6. Aguarde terminar.
7. Abra a execução concluída e baixe o artifact `check-diario-pb-apk`.

O APK gerado fica dentro do artifact, normalmente com nome parecido com:

```txt
app-debug.apk
```

## Ícone

O ícone já foi gerado em:

```txt
android-wrapper/app/src/main/res/mipmap-mdpi/ic_launcher.png
android-wrapper/app/src/main/res/mipmap-hdpi/ic_launcher.png
android-wrapper/app/src/main/res/mipmap-xhdpi/ic_launcher.png
android-wrapper/app/src/main/res/mipmap-xxhdpi/ic_launcher.png
android-wrapper/app/src/main/res/mipmap-xxxhdpi/ic_launcher.png
```

E está configurado no AndroidManifest.xml:

```xml
android:icon="@mipmap/ic_launcher"
android:roundIcon="@mipmap/ic_launcher"
```
