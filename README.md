<div align="center">

# 💈 KauanBarber

**App oficial da barbearia: agendamento online, pacote mensal, carteira digital, vitrine de produtos e gestão completa do negócio.**

</div>

---

## 📱 Sobre o projeto

O **KauanBarber** é um aplicativo exclusivo para a barbearia, criado para tirar a agenda do papel e do WhatsApp. Ele reúne em um só lugar o agendamento dos clientes, a fidelização e o controle financeiro do dia a dia.

O app é desenvolvido em **Kotlin Multiplatform**: as regras de negócio e as telas ficam em um módulo compartilhado. A primeira versão é para **Android**, e a versão para **iOS** vem na sequência, reaproveitando o mesmo código.

## ✨ Funcionalidades

### Para o cliente
- 📅 **Agendamento em 4 passos**: serviço → barbeiro → data/hora → confirmação
- 🔁 Reagendamento e cancelamento (com reembolso até 1 h antes)
- 🎟️ **Pacote mensal "Pague 3, Leve 4"**, vinculado ao barbeiro de preferência
- 💳 **Carteira digital** com recarga por gift card
- ⭐ **Programa de pontos**, recompensas e indicação de amigos
- 🛍️ **Vitrine de produtos** com reserva e pagamento antecipado (retirada em até 24 h)
- 💬 Avaliação dos atendimentos e lembretes por notificação

### Para a equipe
- 🗓️ Agenda em tempo real, com encaixes presenciais, bloqueios e clientes recorrentes
- 📦 Controle de estoque com alerta de estoque baixo
- 💰 Comissões calculadas automaticamente

### Para o dono
- 🧾 Abertura e fechamento de caixa, com delegação e trilha de auditoria
- 📊 Relatórios de faturamento, comissões, vendas, pacotes e taxa de faltas
- ⚙️ Configuração de serviços, preços, regras de pontos e recompensas

## 🛠️ Tecnologias

| Camada | Tecnologia |
| --- | --- |
| Linguagem | Kotlin |
| Multiplataforma | Kotlin Multiplatform (KMP) |
| Interface | Compose Multiplatform · tema escuro |
| Autenticação | Firebase Authentication (e-mail/senha e Google) |
| Banco de dados | Cloud Firestore (tempo real) |
| Regras de negócio no servidor | Cloud Functions (TypeScript) |
| Notificações | Firebase Cloud Messaging |
| Pagamentos | Mercado Pago (Pix e cartão) |
| SDK Firebase multiplataforma | [GitLive firebase-kotlin-sdk](https://github.com/GitLiveApp/firebase-kotlin-sdk) |

## 📂 Estrutura do projeto

```
KauanBarber/
├── androidApp/         # App Android: MainActivity, manifest e configuração do Firebase
├── shared/             # Código compartilhado entre plataformas
│   └── src/
│       ├── commonMain/     # Regras de negócio, dados e telas (Compose)
│       ├── androidMain/    # Implementações específicas do Android
│       └── commonTest/     # Testes do código compartilhado
├── gradle/
│   └── libs.versions.toml  # Catálogo de versões das dependências
└── build.gradle.kts
```

## 🚀 Como rodar

### Pré-requisitos
- Android Studio (Otter 2025.2.1 ou mais recente) com o plugin **Kotlin Multiplatform**
- JDK 17
- Um projeto no [Firebase](https://console.firebase.google.com/) com Authentication e Firestore ativados

### Passo a passo

1. Clone o repositório:
   ```bash
   git clone https://github.com/KauannGabriel/kauanbarber.git
   ```
2. No Firebase, registre um app Android com o pacote `com.kauanbarber.app` e adicione o **SHA-1** da sua chave de debug:
   ```bash
   ./gradlew :androidApp:signingReport
   ```
3. Baixe o `google-services.json` e coloque-o em `androidApp/`.
4. Abra o projeto no Android Studio, aguarde o Gradle sincronizar e rode a configuração **androidApp** em um emulador ou celular.

## 🗺️ Roadmap

- [x] Estrutura do projeto em Kotlin Multiplatform
- [x] Integração com o Firebase
- [ ] Login, cadastro e perfis de acesso
- [ ] Agendamento e agenda dos barbeiros
- [ ] Pacote mensal, carteira digital e pagamentos
- [ ] Vitrine de produtos e estoque
- [ ] Caixa e relatórios
- [ ] Pontos, recompensas e indicação
- [ ] Publicação na Google Play
- [ ] Versão iOS

---

<div align="center">

Feito com ✂️ e ☕ para a **KauanBarber**

</div>