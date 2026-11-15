# DragonZord — Teste 2

**Showroom de vídeo, voz e imagem + matriz de compliance comercial.**

O Teste 2 é a segunda instância prática do ecossistema DragonZord. Ele reúne os **24 projetos de código
aberto focados em geração de vídeo, voz e imagem** mapeados no vídeo de referência de André Lug, com um
semáforo de licenciamento para orientar o que pode ser empacotado e vendido pelo Grupo Reis.

> **Regra de isolamento:** todo processamento pesado (Python, GPU, embeddings, motores locais) vai para
> notebooks do Kaggle. A infraestrutura de produção da AWS permanece 100% blindada e intocada.

---

## 1. Como rodar

```bash
npm start
# abra http://localhost:3000
```

Requisitos: Node.js 18+. Não é necessário `npm install`.

O painel abre com login. A sessão fica em `localStorage` na chave `dragonzord_auth`; para encerrar, use
**Configurações → Sair / Encerrar sessão**.

---

## 2. Estrutura

```
dragonzord-teste-2/
├── index.html                  # grid, relatórios, compliance, estaleiro, Kaggle
├── assets/
│   ├── styles.css              # tema "Zord"
│   └── app.js                  # render, filtros, modal, relatórios, compliance, estaleiro
├── projects.json               # 24 projetos + categorias + regras de compliance
├── server.js                   # back-end leve
├── package.json                # sem dependências
├── docs/
│   ├── ARCHITECTURE.md
│   ├── CATALOG.md
│   ├── COMPLIANCE.md
│   ├── INSTANCE-GUIDE.md
│   └── KAGGLE.md
├── estaleiro/
│   └── README.md               # doca de montagem
├── reports/
│   └── README.md
└── .github/workflows/deploy-pages.yml
```

---

## 3. Os 24 projetos

| # | Projeto | Categoria | Licença | Semáforo | Repositório |
| --- | --- | --- | --- | --- | --- |
| 24 | Krita AI Diffusion | Imagem | GPL-3.0 | Verde | https://github.com/Acly/krita-ai-diffusion |
| 23 | LTX-Video | Vídeo | Lightricks (verificar) | Amarelo | https://github.com/Lightricks/LTX-Video |
| 22 | HunyuanVideo | Vídeo | Tencent (verificar) | Amarelo | https://github.com/Tencent-Hunyuan/HunyuanVideo |
| 21 | CogVideo | Vídeo | Pesquisa (verificar) | Amarelo | https://github.com/zai-org/CogVideo |
| 20 | SadTalker | Vídeo | MIT | Verde | https://github.com/OpenTalker/SadTalker |
| 19 | F5-TTS | Áudio | MIT | Verde | https://github.com/SWivid/F5-TTS |
| 18 | Wan 2.1 | Vídeo | Wan (verificar) | Amarelo | https://github.com/Wan-Video/Wan2.1 |
| 17 | LivePortrait | Vídeo | Pesquisa (restrito) | Amarelo | https://github.com/KlingAIResearch/LivePortrait |
| 16 | AudioCraft | Áudio | CC-BY-NC / MIT | Amarelo | https://github.com/facebookresearch/audiocraft |
| 15 | rembg | Imagem | MIT | Verde | https://github.com/danielgatis/rembg |
| 14 | FLUX | Imagem | Non-Commercial | Amarelo | https://github.com/black-forest-labs/flux |
| 13 | faster-whisper | Mídia | MIT | Verde | https://github.com/SYSTRAN/faster-whisper |
| 12 | Ultimate Vocal Remover | Áudio | MIT | Verde | https://github.com/Anjok07/ultimatevocalremovergui |
| 11 | Chatterbox | Áudio | MIT / verificar | Amarelo | https://github.com/resemble-ai/chatterbox |
| 10 | InvokeAI | Imagem | CreativeML Open RAIL-M | Amarelo | https://github.com/invoke-ai/InvokeAI |
| 9 | Open-Sora | Vídeo | Apache 2.0 / pesos | Amarelo | https://github.com/hpcaitech/Open-Sora |
| 8 | Fish Speech | Áudio | Verificar termos | Amarelo | https://github.com/fishaudio/fish-speech |
| 7 | Diffusers | Mídia | Apache 2.0 | Verde | https://github.com/huggingface/diffusers |
| 6 | Real-ESRGAN | Imagem | BSD 3-Clause | Verde | https://github.com/xinntao/Real-ESRGAN |
| 5 | RVC | Áudio | MIT / voz de terceiros | Amarelo | https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI |
| 4 | Bark | Áudio | MIT / Suno | Amarelo | https://github.com/suno-ai/bark |
| 3 | Coqui TTS | Áudio | MPL 2.0 | Amarelo | https://github.com/coqui-ai/TTS |
| 2 | Segment Anything | Imagem | Apache 2.0 / pesos | Amarelo | https://github.com/facebookresearch/segment-anything |
| 1 | MoneyPrinterTurbo | Vídeo | MIT | Verde | https://github.com/harry0703/MoneyPrinterTurbo |

---

## 4. Matriz de compliance

A aba **Compliance** mostra o semáforo completo, os projetos de cada cor e a matriz por projeto.

| Semáforo | Regra | Ação |
| --- | --- | --- |
| **Verde** | Licenças permissivas abertas (MIT, Apache 2.0, BSD) | Comercialização livre, white-label e empacotamento completo. |
| **Amarelo** | Créditos obrigatórios, restrições a pesos, copyleft moderado (MPL 2.0) | Comercializar com atribuição, revisão de uso e verificação de escala. |
| **Vermelho** | Pesquisa, uso pessoal ou patentes fechadas | Apenas homologação interna no Kaggle; proibida revenda direta. |

> **Atenção RVC:** o projeto é amarelo, mas o uso de voz de terceiros sem consentimento é um gatilho
> vermelho. Use apenas vozes próprias ou com autorização explícita.

Detalhes em [`docs/COMPLIANCE.md`](docs/COMPLIANCE.md).

---

## 5. Estaleiro

A aba **Estaleiro** permite selecionar módulos avulsos, montar um produto e exportar o manifesto JSON.
Os rascunhos ficam no `localStorage` deste navegador. A pasta `estaleiro/` contém a documentação da doca.

---

## 6. Relatórios e Kaggle

- **Relatórios de Teste:** veredito, nota de usabilidade e observações, com exportação JSON/CSV.
- **Kaggle Sandbox:** atalhos por projeto, checklist de isolamento e regra de nunca usar credenciais AWS.

---

## 7. Deploy

O workflow `.github/workflows/deploy-pages.yml` publica a raiz do repositório na branch `main`.
Ative **Settings → Pages → Source: GitHub Actions**.

---

## 8. Licença

MIT. As licenças dos projetos catalogados são de responsabilidade de cada repositório; consulte a matriz
de compliance antes de qualquer uso comercial.