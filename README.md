# Bom Dia, Todo Dia

App Android nativo (Kotlin) com um desafio de 30 dias de mensagens de bom dia e boa noite, a partir de 19/10/2026. Funciona offline, sem cadastro, sem anúncios e sem coleta de dados.

## O que o app faz
- 30 mensagens de bom dia e 30 de boa noite, guardadas no próprio app.
- Calendário dos 30 dias, progresso em número e porcentagem, marcar e desmarcar dias.
- Copiar e compartilhar cada mensagem (você escolhe o destinatário; nada é enviado automaticamente).
- Tema claro, escuro ou automático.
- Lembretes diários locais (padrão 08:00 e 20:30), reagendados após reiniciar o celular ou atualizar o app.

## Escolhas técnicas
- JDK 17, Gradle 8.7, Android Gradle Plugin 8.5.2, Kotlin 1.9.24, compileSdk 34.
- minSdk 26 (Android 8.0 ou superior).
- Dados em SharedPreferences. Nenhuma biblioteca além de AndroidX e Material.
- Alarmes inexatos (`setAndAllowWhileIdle`): não exigem permissão especial, mas podem atrasar alguns minutos.
- Não há Gradle Wrapper no projeto. O workflow instala o Gradle 8.7 oficial na nuvem.

## Limitações reais
- O Android e alguns fabricantes limitam alarmes em segundo plano; a economia de bateria também interfere.
- Em Android 13 ou superior é preciso permitir notificações.
- Nenhum app garante entregar 100% das notificações.

## Compilação na nuvem (GitHub Actions)
O arquivo `.github/workflows/build.yml` roda os testes, compila o APK de **depuração** e publica o arquivo como artefato **BomDiaTodoDia-APK** na aba Actions. O APK de depuração é instalável e assinado com uma chave de teste; um APK de lançamento exige uma chave privada sua e não é necessário para uso pessoal.

Cotas: repositórios públicos têm uso gratuito dos runners padrão; repositórios privados têm uma cota mensal de minutos no plano gratuito. Confira os valores atuais na página de preços do GitHub.

## Estado deste projeto
Os arquivos foram escritos mas ainda **não foram compilados nem testados**. O primeiro resultado real será o da execução no GitHub Actions. Veja `TESTES.md`.
