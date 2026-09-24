# BilinguIA

BilinguIA é um projeto de tradução bidirecional entre voz e LIBRAS, integrando visão computacional, processamento de áudio e inteligência artificial para permitir comunicação entre pessoas que utilizam fala e pessoas que utilizam LIBRAS.

A proposta principal do projeto é transformar a comunicação em um fluxo multimodal capaz de:
- captar fala e convertê-la em texto;
- converter texto em representações de LIBRAS;
- interpretar gestos de mão e sinais;
- identificar expressões faciais;
- reconhecer movimentos relevantes em tempo real por meio da câmera;
- facilitar a inclusão e a acessibilidade.

## Visão geral

Este projeto unifica diferentes tecnologias para criar uma solução de tradução assistida por IA, com foco em:

- Reconhecimento de voz
- Processamento de imagem e vídeo
- Rastreamento de mãos
- Análise facial e expressões
- Mapeamento de palavras e sinais para LIBRAS
- Tradução e interpretação em tempo real

A ideia é criar uma plataforma local e modular, com arquitetura simples, escalável e adequada para desenvolvimento por uma pessoa, mantendo foco em funcionalidade real e evolução incremental.

## Objetivo principal

Desenvolver uma solução capaz de:

1. identificar fala humana em tempo real;
2. transformar a fala em texto;
3. mapear texto para LIBRAS;
4. identificar gestos e sinais de mão pela câmera;
5. reconhecer expressões faciais e contextos de comunicação;
6. possibilitar a conversão de LIBRAS para texto/voz em evolução futura.

## Funcionalidades previstas

### 1. Tradução de voz para LIBRAS
- Captura de áudio do microfone
- Reconhecimento automático de fala
- Conversão da fala em texto
- Mapeamento do texto para sinais de LIBRAS
- Exibição visual e/ou animação de gestos

### 2. Tradução de LIBRAS para texto/voz
- Captura de vídeo pela webcam
- Rastreamento de mãos e dedos
- Reconhecimento de gestos e sinais
- Interpretação de expressões faciais e postura
- Conversão para texto
- Possível reprodução em voz sintetizada

### 3. Reconhecimento de expressões e sinais
- Identificação de gestos com as mãos
- Leitura de expressões faciais
- Classificação de sinais e intenções
- Construção de contexto para tradução

### 4. Interface interativa
- Exibição do fluxo de câmera em tempo real
- Visualização do texto reconhecido
- Preview de sinais e traduções
- Controle de modos de operação e configurações

## Arquitetura do projeto

A arquitetura foi organizada para separar claramente responsabilidades e facilitar manutenção por uma única pessoa.

### Camadas principais
- Camera / Visão computacional
- Rastreamento de mãos
- Análise facial
- Processamento de áudio
- Tradução e mapeamento
- Inteligência artificial
- Interface do usuário
- Persistência e dados

## Estrutura recomendada do projeto

```text
AiDrew/
├── README.md
├── requirements.txt
├── .env.example
├── .gitignore
├── pyproject.toml
├── setup.cfg
│
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── app.py
│   └── ui/
│       ├── __init__.py
│       ├── main_window.py
│       ├── camera_view.py
│       ├── translator_view.py
│       └── settings_view.py
│
├── core/
│   ├── __init__.py
│   ├── config.py
│   ├── logger.py
│   ├── constants.py
│   └── exceptions.py
│
├── modules/
│   ├── __init__.py
│   ├── camera/
│   │   ├── __init__.py
│   │   ├── camera_manager.py
│   │   └── frame_processor.py
│   │
│   ├── hand_tracking/
│   │   ├── __init__.py
│   │   ├── mediapipe_handler.py
│   │   ├── landmarks.py
│   │   └── gesture_detector.py
│   │
│   ├── face_analysis/
│   │   ├── __init__.py
│   │   ├── face_detector.py
│   │   ├── expression_recognition.py
│   │   └── pose_analysis.py
│   │
│   ├── audio/
│   │   ├── __init__.py
│   │   ├── microphone.py
│   │   ├── speech_to_text.py
│   │   └── audio_processor.py
│   │
│   ├── translation/
│   │   ├── __init__.py
│   │   ├── text_processor.py
│   │   ├── libras_mapper.py
│   │   ├── sentence_builder.py
│   │   └── translator.py
│   │
│   ├── libras/
│   │   ├── __init__.py
│   │   ├── gesture_library.py
│   │   ├── sign_sequence.py
│   │   └── visualizer.py
│   │
│   └── ai/
│       ├── __init__.py
│       ├── model_loader.py
│       ├── inference.py
│       └── classifier.py
│
├── services/
│   ├── __init__.py
│   ├── vision_service.py
│   ├── audio_service.py
│   ├── translation_service.py
│   └── session_service.py
│
├── data/
│   ├── README.md
│   ├── vocabularies/
│   │   ├── libras_dictionary.json
│   │   ├── common_phrases.json
│   │   └── expressions.json
│   ├── models/
│   │   └── checkpoints/
│   └── sample/
│       ├── sample_audio.wav
│       └── sample_video.mp4
│
├── tests/
│   ├── __init__.py
│   ├── test_camera.py
│   ├── test_hand_tracking.py
│   ├── test_audio.py
│   ├── test_translation.py
│   └── test_libras.py
│
├── docs/
│   ├── architecture.md
│   ├── setup.md
│   └── libras_dictionary.md
│
├── scripts/
│   ├── prepare_data.py
│   ├── train_model.py
│   └── benchmark.py
│
└── utils/
    ├── __init__.py
    ├── image_utils.py
    ├── video_utils.py
    ├── audio_utils.py
    └── validators.py
```
