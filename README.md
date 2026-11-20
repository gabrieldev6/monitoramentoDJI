# DJI Mobile SDK para Android V5 — Última versão: V5.20.1

(README.md)

## O que é o DJI Mobile SDK V5?

O DJI Mobile SDK V5 oferece uma série de APIs para controlar as interfaces de software e hardware de uma aeronave. Disponibilizamos exemplos de código aberto para produção e tutoriais para ajudar desenvolvedores a criar soluções mais competitivas para drones em dispositivos móveis. Isso melhora a experiência e a eficiência no desenvolvimento de aplicativos utilizando o MSDK.

**Produtos compatíveis:**

[DJI Matrice 5T]() · [DJI Mavic 3TA]() · [Matrice 400]() · [Matrice 4D Enterprise Series]() · [DJI Mini 4 Pro](https://www.dji.com/cn/mini-4-pro?from=store-product-page) · [Matrice 4 Enterprise Series](https://enterprise.dji.com/cn/matrice-4-series) · [Série H30](https://enterprise.dji.com/cn/zenmuse-h30-series) · [DJI Mini 3 Pro](https://www.dji.com/cn/mini-3-pro?site=brandsite&from=landing_page) · [DJI Mini 3](https://www.dji.com/cn/mini-3?site=brandsite&from=landing_page) · [Série Mavic 3 Enterprise](https://enterprise.dji.com/cn/mavic-3-enterprise) · [Série M30](https://www.dji.com/matrice-30?site=brandsite&from=nav) · [M300 RTK](https://www.dji.com/matrice-300?site=brandsite&from=nav) · [Matrice 350 RTK](https://enterprise.dji.com/cn/matrice-350-rtk) · [DJI Mavic 3TA]()

## Exemplos de código

| Exemplo | Descrição |
|---|---|
| [open-pilot-plugin-sample](SampleCode-V5/open-pilot-plugin-sample/README_EN.md) | Demonstração da interface de plugins do Pilot: interface personalizada, mapa / AR, desenho sobre transmissão de vídeo, pontos de rota, arquivos e fluxo de dados. |
| [open-pilot-flighttask-sample](SampleCode-V5/open-pilot-flighttask-sample/README_EN.md) | Gerenciamento de tarefas de voo: envio de tarefas pela Web, recebimento de tarefas pelo controle remoto, execução de rotas por pontos (waypoints) KMZ e envio de recursos. |
| [open-pilot-gasdetection-sample](SampleCode-V5/open-pilot-gasdetection-sample/README_EN.md) | Detecção de gases: envio de tarefas, acesso a cargas úteis PSDK, monitoramento e alarmes em tempo real, identificação e acompanhamento de embarcações. |
| [open-pilot-patrol-sample](SampleCode-V5/open-pilot-patrol-sample/README_EN.md) | Patrulhamento inteligente: patrulhamento por pontos de rota, reconhecimento e captura de alvos, marcações em mapa / AR e envio de recursos. |
| [android-sdk-v5-uxsdk](SampleCode-V5/android-sdk-v5-uxsdk) | Exemplo de interface visual (UX SDK). Atualmente, oferece suporte apenas a aeronaves. |
| [android-sdk-v5-sample](SampleCode-V5/android-sdk-v5-sample) | Aplicativo de exemplo básico do MSDK, que utiliza o UX SDK como dependência. |

## Open Pilot Wizard (OPW)

O OPW é um conjunto de ferramentas de inteligência artificial desenvolvido para auxiliar na criação de plugins do DJI Pilot, utilizando OpenCode, Claude Code ou Codex.

Descreva seus requisitos em linguagem natural para obter ajuda na criação de projetos de plugins, implementação de funcionalidades, resolução de problemas e migração de aplicativos MSDK existentes.

Baixe o [instalador do OPW 1.0.0](OpenPilotWizard/open-pilot-wizard-installer-1.0.0.zip) utilizando a opção de download do arquivo original (*raw file*) na página do arquivo.

Forneça o caminho local do arquivo ZIP à sua ferramenta de IA e solicite que ela siga as instruções do arquivo `INSTALL_AGENT.md`, localizado dentro do pacote.

Se você já clonou este repositório, poderá utilizar diretamente o arquivo disponível na pasta `OpenPilotWizard`.

Para obter instruções de instalação e utilização, consulte o [README do OPW](OpenPilotWizard/README.md).

## Integração

Para obter mais detalhes sobre como integrar o DJI Android SDK ao seu projeto no Android Studio, consulte o tutorial:

- [Avisos e orientações para executar o MSDK](https://developer.dji.com/doc/mobile-sdk-tutorial/en/quick-start/user-project-caution.html)

## Explicação dos arquivos AAR

> **Aviso:** `sdkVersion = 5.20.1`

| Pacote SDK | Explicação | Como utilizar |
|---|---|---|
| `dji-sdk-v5-aircraft` | Pacote principal para aeronaves, que fornece suporte ao MSDK para controlar a aeronave. | `implementation 'com.dji:dji-sdk-v5-aircraft:{sdkVersion}'` |
| `dji-sdk-v5-aircraft-provided` | Pacote de compilação para aeronaves, que disponibiliza as interfaces relacionadas ao pacote principal de aeronaves. | `compileOnly 'com.dji:dji-sdk-v5-aircraft-provided:{sdkVersion}'` |
| `dji-sdk-v5-networkImp` | Pacote de biblioteca de rede, que fornece recursos de conexão de rede ao MSDK. Sem essa dependência, todas as funcionalidades de rede do MSDK deixarão de funcionar, mas as interfaces de controle de hardware continuarão funcionando normalmente. | `runtimeOnly 'com.dji:dji-sdk-v5-networkImp:{sdkVersion}'` |

- Se o projeto precisar oferecer suporte apenas aos produtos da categoria aeronaves, utilize:

```groovy
implementation 'com.dji:dji-sdk-v5-aircraft:{sdkVersion}'
compileOnly 'com.dji:dji-sdk-v5-aircraft-provided:{sdkVersion}'
```

- Se o MSDK precisar utilizar recursos de rede (necessários por padrão), adicione também:

```groovy
runtimeOnly 'com.dji:dji-sdk-v5-networkImp:{sdkVersion}'
```

## Licença de software

O DJI Android SDK é vinculado dinamicamente a bibliotecas não modificadas do [FFmpeg](http://ffmpeg.org), licenciadas sob os termos da [LGPL v2.1](https://www.gnu.org/licenses/lgpl-2.1.html.en).

O código-fonte dessas bibliotecas FFmpeg, as instruções de compilação e a licença LGPL v2.1 estão disponíveis no [GitHub](https://github.com/dji-sdk/FFmpeg).

O DJI Sample Code V5, disponível neste repositório, é distribuído sob a licença MIT.

## Suporte

Você pode obter suporte da DJI por meio dos seguintes canais:

- Publique suas dúvidas nos fóruns oficiais de desenvolvedores da DJI: [SUPORTE AO DESENVOLVEDOR](https://djisdksupport.zendesk.com/hc/en-us/community/topics)