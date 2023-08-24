# Preparando o ambiente
- Download do VS Code 
  https://code.visualstudio.com/download
- Download do github desktop
  https://desktop.github.com/
- Download do git linha de comando 
  https://git-scm.com/downloads
- Baixar e instalar do link o Node: 16.20.1
  https://nodejs.org/download/release/v16.20.1/
- Instalar Ionic CLI: `npm install -g @ionic/cli@7.1.1`
- Verificar versão ionic: `ionic -v`

# Criando o projeto
- Criar o novo projeto em ionic 7
  `ionic start primeiro-app`
- Acessar a pasta do projeto 
  `cd primeiro-app`
- Abrir o projeto no VsCode
  `code .`
- Subindo o projeto no servidor local - Acessar a raiz do projeto
  `ionic serve`

# Subindo o projeto no github
- Abrir o github desktop
- File -> Add local repository -> seleciona a pasta onde foi criado o projeto
- Repository -> repository settings -> para fazer o publish do projeto no github

# Instalando o projeto no aparelho Android
- Referencia
https://ionicframework.com/docs/angular/your-first-app/deploying-mobile
- ionic build na raiz do projeto  
  `ionic build`
- Adicionar plataforma ios (este passo só é necessário 1x para adicionar a pasta da plataforma no projeto) 
  `ionic cap add ios`
- Adicionar plataforma android (este passo só é necessário 1x para adicionar a pasta da plataforma no projeto)   
  `ionic cap add android`
- Toda vez que você realiza uma compilação (por exemplo, 'ionic build') que atualiza seu diretório da web (padrão: www), você precisará copiar essas alterações para seus projetos nativos:
  `ionic cap copy`
- Após fazer atualizações na parte nativa do código (como adicionar um novo plugin), use o comando de sincronização:
  `ionic cap sync`
- Baixar e instalar o AndroidStudio
  https://developer.android.com/studio
- Abrir o android studio 
- File -> Open -> Selecionar a parta do projeto -> D:\primeiro-app
- Instalar o AndroidSdk
- Tools -> SDK Manager  
  - Aba Sdk Platforms marcar a opção abaixo
    - Android API 34
  - Aba Sdk Tools marcar a opção abaixo
    - Android SDK Build-Tools 34
    - Android Sdk Command-line Tools
    - Android Emulator
    - Android Emulator hypervisiordriver
    - Android Sdk Platform-Tools
    - Intel x86 Emulator Accelerator
- Alterar o package.json e criar um script
``` lang-js
"scripts": {
    "gera-versao": "ionic build && ionic cap copy && ionic cap sync && ionic cap open android"
  }
```